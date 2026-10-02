# Review App Store metadata against common rejection reasons

[English](app-store-review.md) · [简体中文](app-store-review.zh.md) · [All prompts](README.md)

**When to use:** before submitting an iOS or Mac app to App Review, or after a rejection, before resubmitting.

The checks come from three real rejections (guidelines 2.3.7, 2.1, 2.1(a)) and two packaging validation failures. Most of them are not in your code. Some of them the AI cannot see at all, so the prompt ends with what you have to check by hand.

```
Review this app for App Store submission. Look at the metadata files,
the screenshots' text, the entitlements, the privacy page, and the build
and packaging scripts. Report each item as PASS, FAIL (with the exact
file and text), or CAN'T CHECK (and say why).

1. Price words: any "free", "no cost" or other price claim in the name,
   subtitle, keywords, promotional text, description, in every language,
   and in the text drawn on the screenshots? (Guideline 2.3.7)
2. Sensitive data: does the app use camera, face detection, health,
   location or similar? Does the privacy page say plainly how that data
   is processed, stored, shared and retained? Draft the review-notes
   answers. (Guideline 2.1)
3. Sandbox entitlements (Mac): compare the entitlements with what the app
   actually does at launch, e.g. a WebView needs
   com.apple.security.network.client under App Sandbox. (Guideline 2.1(a))
4. File handling: anywhere a file picker or "open with" returns a URL,
   is it converted to a normal path before use? (Guideline 2.1(a))
5. Mac App Store bundle: any bare nested executables (CLI helpers)?
   (Validation 90049 / 90885)
6. Does the packaging script clear extended attributes (xattr -cr)?
   (Validation 91109)
7. Is hardened runtime off for the Mac App Store build? (It conflicts
   with the sandbox.)
8. Draft review notes: what the app does, a sample file the reviewer can
   use, the support page, and the root cause of any earlier rejection.

Don't change anything yet. Give me the report first.
```

**Then check by hand; the AI can't see these:**

- Install the **signed release build** in a clean environment and launch it once.
- Walk the plainest path, as a reviewer would: open the app, pick a file, use it.
- Look at every screenshot yourself.

Full checklist: [launch self-check](../templates/launch-checklist.md#4-app-store-submission).
