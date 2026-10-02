# Phase 3 · Design

[English](03-design.md) · [简体中文](03-design.zh.md) · [Back to the method](README.md)

**Goal:** before building, see roughly what it will look like, and pick a direction.

## What to do

**Ask for several rough options side by side, then choose from what you see.**

```
Make 3 style options for the [login page / dashboard / main screen]:
A minimal, B corporate, C playful.
Put them on one page so I can compare them side by side.
Use real copy from our product, not placeholder text.
```

(With a skills framework, this is where a multi-option design skill goes; the site's setup guide uses `/design-shotgun`.)

**Lock in the project's taste once, so you don't repeat it every session.** Tech choices, style, constraints and red lines go into a standing agreement that the agent saves in the project and follows from then on:

```
For this project, always follow these rules:
· Tech taste: [e.g. use Astro, avoid heavy frameworks, static when possible]
· Style: [e.g. dark, restrained, lots of whitespace, plain language]
· Constraints: [e.g. no paid or third-party tracking; mobile-first]
· Red lines: [e.g. don't touch production data; ask me before delete/publish/pay]
```

The full prompt is in [`prompts/project-taste.md`](../prompts/project-taste.md). Once taste is fixed, every high-fidelity output comes out consistent, and you stop correcting the same thing twice.

**When you reference someone else's design, write down what you are not copying.** "Learn from their restrained style" without "but keep our warm brand colour" usually means the agent copies the palette too.

## What "done" looks like

- One direction is chosen.
- The key screens have a clear shape in your head.
- Taste and red lines are written down where the agent will read them.

## Common pitfall

**Wanting it perfect from the start**, and getting stuck in revision loops. Ask for three rough options first and pick from what you see. Polish happens in Develop, one small step at a time.

## In the cases

SoloMD's v4.6 plan recorded the design decision with its non-goal: learn the restrained feel of a reference app, neutral grey with a warm orange accent `#ff9f40` and 8px radius, and explicitly "don't copy its cool grey-blue". The spec then turned taste into concrete values (spacing, radius and z-index scales) so that seven parallel agents wouldn't invent seven spacing systems. See the [SoloMD case](../cases/official/solomd.md) and the [spec template](../templates/spec-template.md), section 2.

Previous: [Phase 2 · Define](02-define.md) · Next: [Phase 4 · Develop](04-develop.md)
