# Break it into small steps

[English](small-steps.md) · [简体中文](small-steps.zh.md) · [All prompts](README.md)

**When to use:** the spec is agreed and the AI is about to build. Also when it has been working for a while and you've lost track of what changed.

The test for a good step: when it's done, can you run it right away and tell whether it's right? If not, the step is too big.

```
Break this into small steps where I can run it and see the result
after each one (in the browser, or installed on my phone).

Rules for the list:
- Each step produces one result I can check, not one "module".
- A change that crosses a platform boundary (for example camera capture,
  file metadata and export) is its own step.
- Number the steps and say, for each one, what I should see when it's done.

Then do step 1 only. When it's done, start it so I can see it, and stop.
Don't do anything outside the current step. If you notice something else
that should change, add it to the list for later instead of changing it.
```

For each following step: "Step N looks right. Go ahead with step N+1, same rules." When it says "while I was at it, I also changed X", ask it to roll X back and add it to the list.
