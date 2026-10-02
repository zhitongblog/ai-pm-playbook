# Stuck? Reproduce first, fix later

[English](stuck-reproduce-first.md) · [简体中文](stuck-reproduce-first.zh.md) · [All prompts](README.md)

**When to use:** the AI keeps changing things, never gets it right, and gives a different reason each time.

Every failed attempt stays in the context and the mess piles up. Skipping straight to "fix it" usually fixes something else: it looks solved, then comes back two days later in another form.

```
Stop. Don't change any more code for now.

1. Give me a minimal example that reproduces this problem reliably,
   and the exact steps to trigger it. Run it and show me it fails.
2. Then tell me the cause, with evidence: the log line, the value,
   the file and line. "It might be because..." is not an answer.
   If you're not sure, tell me what you'd check next to find out.
3. Wait for me to agree on the cause before changing anything.
4. When you fix it, run the same reproduction again and show me it passes.
```

**If the conversation has gone on too long,** start clean:

```
Summarize what we've established about this problem into a short note:
what we tried, what was ruled out, and what the evidence shows.
I'll start a fresh session with that note.
```

**Before blaming the AI, do the same action by hand.** If it works by hand and fails when automated (for example, you can type into a field but clicks do nothing), the problem is in the tool or the environment, and no prompt will fix it.
