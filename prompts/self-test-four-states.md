# Self-test with real content and four states

[English](self-test-four-states.md) · [简体中文](self-test-four-states.zh.md) · [All prompts](README.md)

**When to use:** the AI says a feature is done. Before you believe it.

"Done building" is not "built right". The checks below run the real thing, not just the unit tests, and the AI shows you each result instead of reporting that it passed.

```
Before we call this done, go through this checklist on the running app.
For each item: run it, show me the evidence (screenshot, output or the
exact steps you took), and fix anything that fails on the spot.

1. Real content: any Lorem ipsum, "sample text" or placeholder left?
   Replace with realistic content and real data structures.
2. Four states: show me loading, empty, error and success for the main
   screen. Empty and error are the ones usually missing.
3. Real interactions: every button clicks, every form submits, every link
   goes somewhere. Nothing that only looks like it works.
4. Critical path: walk the single most important user flow end to end.
5. Narrow screen: check it at phone width.
6. Awkward input: wrong, empty, very long, and odd characters. Does it break?
7. Diff: show me `git diff --stat` and point out any change unrelated
   to this feature. Revert those.

Don't tell me an item passed unless you ran it. If something can't be
tested automatically, say which lower-level check you used instead.
Not done until every item passes.
```

**If it's an AI feature, add:**

```
8. Write 12 realistic, awkward inputs for this AI feature (including ones
   designed to make it fail or make things up). Run all of them in a row.
   Show me each input and output, and mark where it was inconsistent,
   wrong, or failed badly.
```

Then do the part no prompt can do: hand it to someone else and watch quietly where they get stuck.
