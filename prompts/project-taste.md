# Set the project's taste once

[English](project-taste.md) · [简体中文](project-taste.zh.md) · [All prompts](README.md)

**When to use:** at the start of a project, or the second time you catch yourself correcting the same preference.

Some preferences you don't want to repeat every session: tech choices, style, constraints, red lines. Say them once and have the AI save them where it reads them at the start of every session.

```
For this project, always follow these rules:
· Tech taste: [e.g. use Astro, avoid heavy frameworks, static when possible]
· Style: [e.g. dark, restrained, lots of whitespace, plain language in copy]
· Constraints: [e.g. no paid or third-party tracking; mobile-first]
· Red lines: [e.g. don't touch production data; ask me before delete / publish / pay]
· Done means: [e.g. you ran it and showed me; the self-test passed]

Save this as a standing agreement for the project, in the file you read at
the start of every session. Tell me which file you used. Don't change
anything else.
```

Rules that hold for every project you do (what counts as done, what must be asked first) are easier to keep once in your agent's global instructions than copied into each project; keep the project file for what only this project needs. When a second person and their AI join, write the architecture down as well. Their AI only knows what's in the repo.
