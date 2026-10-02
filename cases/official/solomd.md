# SoloMD: launch is where it really starts

[English](solomd.md) · [简体中文](solomd.zh.md) · [All cases](README.md)

> Website: [solomd.app](https://solomd.app) · Repo: [github.com/zhitongblog/solomd](https://github.com/zhitongblog/solomd) (public)
> Numbers below are as stated in the doaipm playbook, as of August 2026.

## What it is

A local-first desktop Markdown editor with a bundled MCP server, so AI coding agents can work with your notes directly. The first two cases stop at launch. SoloMD is the one that shows what happens after: **about 669 commits, 84 releases, 134 issues, 38 PRs and 551 stars**, from a repo created on 2026-04-08 and still being updated.

## Timeline

| Month | Releases |
|---|---|
| 2026-04 | 40 |
| 2026-05 | 13 |
| 2026-06 | 22 |
| 2026-07 | 9 |

v0.x started on 04-17, v1.x on 04-25, v2.x one day later on 04-26, v3.x on 04-29, and v4.x from May on. Forty releases and four major versions in the first month were not planned; they were real users finding problems and each fix shipping as soon as it was done. By July it was nine a month because the product had settled.

## What users found

A slice of closed issues shows three shapes of problem the author's own testing could not reach:

- **Environments he doesn't use:** an AppImage that wouldn't start, a Mac arm build where dragging the title bar didn't move the window, a WSL path format that wasn't handled, and on iOS, opening any file failed with `OS Error 2`.
- **Things that only hurt after hours of use:** the cursor jumping to the bottom after switching tabs, which tab to show after closing one, line breaks that differed between editing and export.
- **"I thought the setting applied":** font and size settings that didn't reach the preview.

The iOS `OS Error 2` is the same kind of bug an Apple reviewer hit in [SoloPDF](solopdf.md): the same trap, found once by a user and once by App Review. The gaps in your own testing have a recognizable shape, and the next product can guard against them in advance.

## Key decisions

**Accept outside code, selectively.** Of the 38 PRs, 21 came from other people. One contributor, beihai23, sent 15. Others added things not on the roadmap: a MiniMax provider, Gitea support. Only a minority of the outside PRs listed in the playbook were merged; the test was whether a PR fit the architecture and avoided dependencies that couldn't be maintained, not how enthusiastic it was.

**Refactor when nobody else will ask for it.** By June, the v4.6 plan diagnosed 56 components each with their own scoped styles, the same dropdown menu copied 5 times and modal styles copied more than 5 times. Every change the AI made had been locally right: asked for a dropdown, it wrote one. Nobody told it there were already five. The root cause in the plan: no middle layer of design tokens and a shared component library. An AI won't propose that refactor, because from its side every step was correct. That plan became this repo's [spec template](../../templates/spec-template.md).

## What went wrong

Mostly what's described above: environment bugs, long-session annoyances, settings that weren't wired through, and three months of locally correct changes that added up to a lot of duplication. None of it was visible before real people used the product for real work. The author writes the playbook itself in SoloMD for that reason.

---

More on the release curve, the issue list and the v4.6 refactor is in the [playbook](https://doaipm.com/en/presale/). The real v4.6 plan is public at [`docs/v4.6-plan.md`](https://github.com/zhitongblog/solomd/blob/main/docs/v4.6-plan.md).
