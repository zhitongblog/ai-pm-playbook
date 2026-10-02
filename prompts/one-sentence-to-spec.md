# One sentence to a spec

[English](one-sentence-to-spec.md) · [简体中文](one-sentence-to-spec.zh.md) · [All prompts](README.md)

**When to use:** you have an idea in one sentence and want the AI to turn it into a spec it can build from, without inventing the parts you haven't decided.

If you just say "write a spec", the AI fills every gap with a guess and the result reads as complete. This prompt makes it mark what it would have guessed and ask you instead.

```
Here is my idea in one sentence: [your sentence].

Turn it into a short dev brief with these seven sections:
1. Whose problem are we solving, and what problem?
2. How do they cope today, and why isn't that good enough?
3. What does success look like? Write it as something that can be checked
   (a number or a countable fact), not an adjective.
4. The smallest usable version: list the core actions, one per line.
5. Key states: what loading, empty, error and success each look like.
6. Constraints: platform, style, and what we are explicitly NOT doing.
7. Which irreversible actions (publish, pay, delete, overwrite) must wait for me.

Rules:
- Do not invent answers. Where my sentence doesn't tell you, write
  "OPEN QUESTION:" and the question, instead of filling it in.
- After the brief, list the open questions, most important first, at most five.
- Don't write any code yet.
```

After you answer the open questions, ask it to update the brief, then use [ask before coding](ask-before-coding.md) to start building. For a release or a refactor, ask it to fill the [spec template](../templates/spec-template.md) instead.
