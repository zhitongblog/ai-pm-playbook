# FreeID Photo: three days, 15 builds, into the App Store

[English](freeid-photo.md) · [简体中文](freeid-photo.zh.md) · [All cases](README.md)

> App Store: [id6779873542](https://apps.apple.com/app/id6779873542) · Repo: [github.com/zhitongblog/freeid-photo](https://github.com/zhitongblog/freeid-photo) (public)
> Numbers below are as stated in the doaipm playbook, as of August 2026.

## What it is

An iOS app for taking passport and ID photos and cropping them to official specs, built with Swift and Apple's Vision framework. It is the smallest of the four cases: **21 commits, 14 of them numbered builds**, and a native iOS app in the store. If you want to know the minimum it takes to go from zero to the App Store, this is the one to read.

## Timeline

- **2026-06-13:** repo created. The first commit: "FreeID Photo: core, Vision engine, export, CLI, MCP, iOS app".
- **2026-06-13 to 06-15:** builds 2 to 15, all in three days.
- **2026-06-15:** reusable App Store release automation (`scripts/asc`).
- **2026-06-30:** rejection resolved, live in the store.

## Key decisions

**CLI and MCP from the first commit.** Not added after the app was done. Because they were there, later requests such as "replace the background with white without cropping" and "export at any size in millimetres" went into the `freeidctl` command line without touching the app UI, and scripts and AI agents can call them directly.

**Verify the specs against official sources.** The second commit was not code: "Verify spec dimensions against official sources; expand to 16 specs / 10 countries". One millimetre off and an ID photo is useless. The AI can look things up; deciding that a fact must be checked against the official source was a human call.

**Two subtractions, both early.** Build 3 dropped expression detection: it was unreliable and kept users from taking a photo at all, and an unreliable check is worse than none. Build 11 limited the background colour picker, added in build 8, to compliant cases, because ID photos have rules about background colour. Both cuts came right after the feature was built, which is only possible when each build is checked on its own.

## What went wrong

- **Orientation, twice.** Build 6 fixed portrait shots exporting sideways by honouring EXIF orientation everywhere; build 7 had to fix it again with a rotation coordinator. The bug spans capture, metadata and export, and the first fix wasn't enough. Small steps made that visible.
- **Passport crop cut off the top of the head, with no margin.** Fixed over builds 14 and 15. Only comparing the finished photo with the real requirement shows this; the AI only knows the crop parameters ran.
- **App Store rejection on 2026-06-30, two guidelines at once.** Guideline 2.3.7: "free" appeared in the subtitle, keywords, promotional text and description, and the first screenshot's headline was "Truly free". Guideline 2.1: the app uses face detection, so the privacy page got a "Face data" section (processed on device, not stored, shared or retained) and the answers went into the review notes. It was a metadata-only fix; the same build 15 was resubmitted.

## What carried over

The release scripts were "built during the v1.0 submission and reusable for every future update". SoloPDF's `scripts/asc/` was moved over from here. The half month between the last build and approval is paid once, if it ends up as a command you can rerun.

---

The full build-by-build table and the rejection details are in the [playbook](https://doaipm.com/en/presale/). Related: [launch self-check](../../templates/launch-checklist.md), [App Store review prompt](../../prompts/app-store-review.md).
