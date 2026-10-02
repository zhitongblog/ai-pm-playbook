# Phase 4 · Develop

[English](04-develop.md) · [简体中文](04-develop.zh.md) · [Back to the method](README.md)

**Goal:** turn the design into a prototype people can click, use and test. The rule here is small steps, fast cycles.

## What to do

**Break the work into steps you can see running.** Ask the agent to do the breaking:

```
Break this into small steps where I can run it in a browser and see
the result after each one. List them. We'll go one at a time.
```

Then, for each step:

1. **Say one step.** Only what's happening now.
2. **Have it shown to you.** "When it's done, start the server so I can see it in the browser." (Or install it on the phone.)
3. **Give feedback on the spot.** Right: next step. Wrong: "this part is wrong, it should be..."

The test for step size: when this step is done, can you run it right away and tell whether it's right? If not, the step is too big.

Three rules for splitting tasks:

1. **One verifiable result at a time**, not one "module" at a time.
2. **A change that crosses a platform boundary gets its own step.** Camera, file metadata and export are three layers; a fix that touches all three deserves to be alone.
3. **When the agent says "while I was at it, I also changed X", make it roll that back.** Bundling saves its time and costs you debugging time.

## When you're stuck

There are two kinds of stuck.

**It can't get it done.** It keeps changing things, never gets it right, and gives a different reason each time. The order is: stop; have it reproduce the problem with a minimal example; ask for the cause with evidence, not "it might be because"; only then change code. Skipping the reproduction usually fixes something else. The prompt is in [`prompts/stuck-reproduce-first.md`](../prompts/stuck-reproduce-first.md).

**The tool or environment is acting up.** You can type into a field but clicks do nothing; a page has loaded but a script reads it as empty. Do the same action by hand. If it works by hand and fails when automated, it's the tool layer, and rewriting the prompt won't help.

**Long sessions drift.** When a conversation gets long, have the agent summarize the decisions so far into a short document and continue in a fresh session.

## What "done" looks like

- It actually runs, in a browser or on a device.
- The main flow can be clicked through without errors.
- The data is fake but realistic enough to demo.

## Common pitfall

**Throwing twenty requirements at it at once.** One at a time. And don't obsess over prototype code quality; it's a spec that runs, not the production build.

## In the cases

FreeID Photo went from zero into the App Store in 21 commits, 14 of them numbered builds, each one a change that could be checked on a real phone. Builds 3 to 7 were five consecutive fixes to capture and orientation. Two features were cut right after they were built, which only happened because each step was checked on its own. See the [FreeID Photo case](../cases/official/freeid-photo.md).

Previous: [Phase 3 · Design](03-design.md) · Next: [Phase 5 · Validate](05-validate.md)
