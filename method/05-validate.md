# Phase 5 · Validate

[English](05-validate.md) · [简体中文](05-validate.zh.md) · [Back to the method](README.md)

**Goal:** let real people use it, and decide with evidence instead of gut feeling.

"Done building" is not the same as "built right". Running tests checks whether the code logic is right. Validating checks whether it works when a person uses it. Agents are very good at the first, and passing the first doesn't mean passing the second.

## What to do

**1. Run the high-fidelity checklist on the real thing.** Send it to the agent: "Go through this checklist item by item, run each check and show me, and fix anything that fails on the spot." You sign off on the result.

| Check | Ask yourself |
|---|---|
| Real content | Real content and data structures? Any Lorem ipsum, "sample text", placeholders? |
| Four states | Loading, empty, error, success: all four built? Empty and error are the easiest to miss |
| Real interactions | Buttons click, forms submit, links navigate? Or do they just look like they do? |
| Critical path | Does the single most important user flow work end to end? |
| Cross-device | Checked on phone and desktop? At least one pass at a narrow width |
| Edge-case input | Wrong input, empty input, very long input, odd characters: does it break? |

The prompt is in [`prompts/self-test-four-states.md`](../prompts/self-test-four-states.md).

**2. If it's an AI feature, run an eval loop.** One successful try doesn't count. Have the agent write a dozen real, awkward test inputs and run them in a row; check for consistency, made-up answers, and how it fails.

**3. Give it to someone else and stay quiet.** Watch where they get stuck. Don't explain.

**4. Before you trust a "done", ask three questions:**

1. **Who decided it succeeded?** A success the code reported about itself doesn't count. Read it back from the outside world.
2. **Could this step change something it shouldn't?** If it finds its target by text, position or index and a write follows, take over.
3. **Can the agent see the result?** Packaged builds, real devices, store review, third-party services and real user data are outside what it can see. A person checks those once.

What you can safely hand off: logic changes, refactors, tests, docs, translations, style unification. Mistakes there show up immediately and aren't irreversible.

Before you release anything, run the [launch self-check](../templates/launch-checklist.md).

## What "done" looks like

- The main flow runs without obvious bugs.
- Real users have tried it.
- You can answer, with evidence, whether it's worth continuing.

## Common pitfall

**Clicking through it yourself for two minutes and calling it done.** The problems that matter show up after two hours of real use, or on an environment you don't own.

## In the cases

After SoloMD launched, users reported problems the author's own machines could never hit: an AppImage that wouldn't start, a Mac arm build where the window couldn't be dragged, a WSL path format that wasn't handled, a cursor that jumped to the bottom after switching tabs. On iOS, opening any file failed with `OS Error 2`, the same kind of bug an Apple reviewer found in SoloPDF. See the [SoloMD case](../cases/official/solomd.md).

Previous: [Phase 4 · Develop](04-develop.md) · Back to [the method](README.md)
