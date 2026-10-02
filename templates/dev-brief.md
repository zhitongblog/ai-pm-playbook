# Dev brief: seven questions

[English](dev-brief.md) · [简体中文](dev-brief.zh.md)

Answer the seven questions before you ask an AI to build anything. The ones you can't answer are the places you haven't thought through yet. Then paste the whole brief, including the instructions at the bottom, into your AI coding tool.

A web version that builds the brief as you type is at [doaipm.com/en/tools/brief/](https://doaipm.com/en/tools/brief/) (front-end only, collects no data).

## Why these seven

- **Questions 1 and 2** let the AI make judgment calls for you. "Build a PDF reader" gets you a generic reader. A specific person with a specific problem gives it a reason for where each button goes.
- **Question 3** is the one most often skipped. If success only exists in your head, the AI never knows when to stop, and it keeps adding features because adding features looks like progress.
- **Question 5** is the dividing line. Most people describe only the success path. If you don't specify loading, empty, error and success, the AI decides for you, and it usually decides to do nothing.
- **Question 6**: the most valuable part is what you are explicitly not doing. It's the easiest item to leave out and the most expensive when you do.
- **Question 7** is the safety net. Not because the AI acts in bad faith, but because it doesn't know which actions are irreversible in your situation.

---

## Copy from here

```markdown
# Dev brief: <the thing you want to build, one line>

## The problem
<① Who are you solving what problem for?>
<e.g. Let a non-coding PM turn an idea into a clickable prototype in one afternoon.>

## Status quo (how they cope today, why it falls short)
<② How do they cope today? Why is that not good enough?>
<e.g. Today they either draw static mockups (no real interaction) or wait weeks for engineering.>

## Success criteria
<③ What does success look like? Something you can check, not an adjective.>
<e.g. Fill a short form, get a clear, paste-ready brief any AI instantly understands, in 30 seconds.>

## Smallest usable version (core actions)
<④ What core actions does the smallest usable version need? One per line.>
- <e.g. Fill in problem and goal>
- <e.g. Generate the brief live>
- <e.g. Copy in one click>

## Key states (build every one)
<⑤ Loading / empty / error / success: what does each look like?>
<e.g. Button disabled when empty; copy shows feedback; empty fields leave a placeholder in the brief.>

## Constraints
<⑥ Platform / style / what NOT to do.>
<e.g. Pure front-end, no login, collect no data; dark minimal style; skip multi-language for now.>

## Safety net (these irreversible actions must wait for me)
<⑦ Which irreversible actions must a human press?>
<e.g. Publishing, payments, deletes: always ask me first, no acting on its own.>

---
Build the real, runnable thing from this brief, **high-fidelity**: real content and data, real states (loading/empty/error/success), real interactions. Work in **small steps**, one change at a time, and run it for me. **Ask if you're unsure**; don't dress up half-done work as finished. **Check with me before any irreversible action.**
```

---

For a release, a refactor or parallel work, the seven questions aren't enough. Use the full [spec template](spec-template.md).
