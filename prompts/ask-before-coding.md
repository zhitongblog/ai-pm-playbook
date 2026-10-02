# Ask before coding

[English](ask-before-coding.md) · [简体中文](ask-before-coding.zh.md) · [All prompts](README.md)

**When to use:** right before the AI starts building anything, every time.

The AI won't stop to ask when you're vague. It picks a plausible reading and keeps going. Making it repeat back and ask first produces no document; it produces shared understanding. If it repeats you correctly and asks the right questions, it understood.

```
[Paste your one-sentence spec or dev brief here.]

Before you start:
1. Repeat back what I want in your own words, in five lines or fewer.
2. Ask me the 3–5 most critical questions: the ones where a wrong guess
   would waste the most work. Number them.
3. Wait for my answers. Don't write code until I've answered.

When you do start: build it high-fidelity (real content; all four states:
loading / empty / error / success; real interactions), in small steps,
and run it for me after each step.
```

If you don't know what the questions should be, add one line to borrow a structure:

```
Use [jobs to be done / an opportunity solution tree / working backwards from
the launch announcement] to structure your questions.
```

If the repeat-back is wrong, correct it before answering the questions. That correction is the cheapest fix you'll make on the whole project.
