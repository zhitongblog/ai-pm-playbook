# Phase 2 · Define

[English](02-define.md) · [简体中文](02-define.zh.md) · [Back to the method](README.md)

**Goal:** turn a fuzzy idea into a requirement anyone could build from.

The most expensive thing in AI-assisted building is not compute. It's what you haven't thought through. The agent won't stop and ask when you're vague. It picks a reasonable-looking interpretation and keeps going, and by the time you notice the direction is wrong, it has been going that way for three hours.

## What to do

**1. Say it in one sentence.**

```
I want to help [who] solve [what problem].
When it's built, users can use it to [the single most important action].
The sign that it worked is [one visible outcome].
We are explicitly NOT doing [non-goals].
Known risks / assumptions: [...].
```

**2. Make the agent repeat it back and ask before building.** Add: "Before you start, repeat back what I want in your own words, then ask me 3–5 of the most critical questions. Once I've answered, start building." This step produces no document; it produces shared understanding. The full prompt is in [`prompts/ask-before-coding.md`](../prompts/ask-before-coding.md).

**3. For anything bigger than a small tool, answer the seven questions** in the [dev brief](../templates/dev-brief.md): who and what problem, how they cope today, what success looks like, the smallest usable version, the four states, the constraints (including what you are not doing), and which irreversible actions a human must press.

**4. For a release, a refactor or parallel work, use the full [spec template](../templates/spec-template.md):** one-sentence goal plus acceptance criteria, current-state diagnosis, shared contract, workstreams, orchestration, self-test strategy, milestones, risks, and out-of-scope.

## What "done" looks like

The test: if you handed this to someone who doesn't know you, would they build something very different from what's in your head? If yes, keep writing. Three quick self-checks:

1. **Any adjectives in the acceptance criteria?** "Better", "faster", "more consistent" get rewritten as numbers or countable facts.
2. **Is "what we're not doing" written down?** If there isn't one item, the scope is still open.
3. **Are the irreversible actions named?** Going live, paying, deleting, overwriting files.

## Common pitfall

**Jumping straight to "write me a PRD".** The agent fills the gaps by guessing. Always make it ask you questions first.

## In the cases

On SoloPDF's first day, four of seventeen commits went back and forth on one question: what the product website's address was. Each time the agent did exactly what it was told. The instructions kept changing because the decision was never written down. One line in a spec would have saved the day. See the [SoloPDF case](../cases/official/solopdf.md).

Previous: [Phase 1 · Discover](01-discover.md) · Next: [Phase 3 · Design](03-design.md)
