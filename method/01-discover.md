# Phase 1 · Discover

[English](01-discover.md) · [简体中文](01-discover.zh.md) · [Back to the method](README.md)

**Goal:** understand what users want, what competitors are doing, and where the market is heading.

## What to do

Ask the agent for research the same way you'd brief an analyst: a specific subject, a specific focus, a specific output format.

```
Analyze [competitor URL]. Focus on [pricing / AI features / onboarding].
Put the result in a comparison table against [our product or idea],
and end with three gaps nobody is filling well.
```

If you use a skills framework, this is where a competitor-analysis skill goes (the site's setup guide uses `/competitor-watch`). Without one, plain language works.

When you don't know what to ask, borrow a structure and let the agent walk you through it. Pick one:

- **Jobs to be done:** "In what situation would someone want to use this? What are they trying to get done? How are they cobbling it together today?"
- **Opportunity solution tree:** "What outcome are we after? What pain-point opportunities do users have? What solutions could address each one?"
- **Working backwards:** "Imagine this has shipped and works. Write the paragraph a user would say when recommending it. Then work back to what we actually need to build."

You don't need all three. Use the one that feels natural.

## What "done" looks like

- You can state the user's biggest pain in three sentences.
- You know how competitors solve it today and where your difference is.
- You can answer the first two questions of the [dev brief](../templates/dev-brief.md): whose problem, and how they cope today.

## Common pitfall

**Asking too broadly.** "Research the PDF reader market" gets you a generic essay. Give a subject, a focus and an output format, and you get something you can act on.

## In the cases

FreeID Photo's second commit was not code. It was "verify spec dimensions against official sources; expand to 16 specs / 10 countries". With ID photos, one millimetre off and the photo is useless. The agent can look things up and organize them; deciding that a fact has to be checked against an official source is the PM's call. See the [FreeID Photo case](../cases/official/freeid-photo.md).

Next: [Phase 2 · Define](02-define.md)
