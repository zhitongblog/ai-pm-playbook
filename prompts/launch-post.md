# Write a launch post

[English](launch-post.md) · [简体中文](launch-post.zh.md) · [All prompts](README.md)

**When to use:** the product is live and you want to tell people about it, on a forum, a blog, Show HN, Product Hunt, or a WeChat article.

Left alone, the AI writes launch posts full of adjectives, invented user reactions and "revolutionary". This prompt keeps it to what you can back up: one sentence on what it is and isn't, real numbers from the repo, and an honest account of who built it and on what.

```
Write a launch post for [product name], for [where it will be posted and
who reads there]. Use only the facts below and what you can read in this
repo. Don't invent users, quotes, numbers or results.

Facts:
- What it is, in one sentence: [e.g. "a free, ad-free PDF reader where
  your highlights become Markdown notes"]
- Who it's for and the problem it solves: [...]
- What it deliberately does NOT do: [...]
- Who built it, and what it's built on: [e.g. "two people, on top of
  the WezTerm engine"; name upstream projects and collaborators]
- How it was built: [e.g. "built with Claude Code; I described it,
  the AI wrote the code"]
- Real numbers I can point to: [commits, days, releases, platforms]
- One problem we hit and how we fixed it: [...]
- Links: [website, repo, store page]

Rules:
- First line: what it is and who it's for. No warm-up.
- Plain language. No "revolutionary", "game-changing", "seamless".
- Every number must come from the facts above or the repo; tell me
  where each one came from.
- Say clearly what it doesn't do and what's still rough.
- End with the links and one specific thing you want feedback on.
- Keep it under [N] words. Give me two title options.
```

After posting, open the post from a logged-out browser or another account and confirm other people can actually see it. A post that only you can see looks exactly like a published one from inside your own account.
