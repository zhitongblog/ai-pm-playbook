# Unterm: two people and AI, on someone else's foundation

[English](unterm.md) · [简体中文](unterm.zh.md) · [All cases](README.md)

> Website: [unterm.app](https://unterm.app) · Repo: [github.com/zhitongblog/unterm](https://github.com/zhitongblog/unterm) (public)
> Numbers below are as stated in the doaipm playbook, as of August 2026.

## Two facts first

**Two people built Unterm.** The other three cases are solo projects. Unterm has two committers: zhitong, and xuyao, who made the project's first three commits, including the one that initialized it. In the local repo's 1,122 commits, 1,054 are zhitong's (under three identities on several machines) and 68 are xuyao's.

**It is built on WezTerm's engine.** The renderer, fonts, TUI, SSH and multiplexing come from [WezTerm](https://github.com/wezterm/wezterm); Unterm is a product layer on top. The second line of its LICENSE credits WezTerm's author, and the README says so plainly.

## What it is

A cross-platform terminal built on one bet: the terminal itself should be drivable from outside by any AI agent. Claude Code, Codex, Gemini CLI, Cursor, Aider or your own scripts reach the same JSON-RPC interface over MCP to open shells, run commands, read pane state, take screenshots, change settings and record sessions. The playbook counts **99 methods in 21 namespaces**.

## Timeline

Repo created 2026-04-15, still being updated. **About 521 commits on main and 73 releases.**

## Key decisions

**Split by territory, not by task.** In July, xuyao's most-changed files were the window, tab bars, rendering, mouse events and icons: the product's face. zhitong's were architecture docs, the engine core and the dependency map: its bones. The only shared file was the MCP handler, the interface both sides had to touch (6 changes vs 112). Two people each with an AI editing the same files clash worse than two people writing by hand, because an AI's edits naturally touch more of the surrounding code.

**Stagger the timing.** In July the two almost never touched the repo on the same day: xuyao on 7/4 to 7/24, zhitong on 7/26 to 7/29. It wasn't scheduled, but it kept concurrent conflicts close to zero, at the source rather than at merge time.

**Mark AI work in branch names.** Branches like `agent/fix-windows-input-instance-stability` tell the other person that an AI is pushing that chunk, the change may be wide, and those files are best left alone for now.

## What changed with a second person

zhitong's two most-changed files in the project are documents, not code: `docs/engine-dependency-map.md` (240 changes) and the core technical architecture doc (226). Code comes third (205). With another person and two AIs in the same repo, the architecture in one head has to become a file, or it doesn't exist: the other person's AI only reads what's in the repo, and next week's session won't remember this week's decisions. For solo projects the method keeps rules global and project files minimal; Unterm is the exception, and the reason is the second person.

## Why the two facts are stated up front

The git history was re-initialized, so nobody would find the author split without being told, and few people read the second line of a LICENSE. Leaving them out would have been false metadata, the same kind of problem that got FreeID Photo rejected under guideline 2.3.7. Things nobody would notice if you didn't write them down are the most expensive on the day someone does.

---

The full author breakdown, file lists and collaboration notes are in the [playbook](https://doaipm.com/en/presale/).
