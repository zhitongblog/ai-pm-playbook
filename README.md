# AI PM Playbook

[English](README.md) · [简体中文](README.zh.md)

[![Content: CC BY 4.0](https://img.shields.io/badge/content-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![Code: MIT](https://img.shields.io/badge/code-MIT-blue.svg)](LICENSE-CODE)

**The open home of the doaipm method: product managers who ship real products with AI. Speak it, and AI builds it.**

doaipm stands for "DO AI PM". The idea is simple: the skill that matters is no longer writing code, it is saying clearly what you want, judging whether the AI got it right, and taking over when it didn't. This repo collects the method, the templates, the prompts and the case summaries behind that idea, and it is where people who build things this way compare notes.

## Who this is for

- Product managers who want to take an idea all the way to something people can click, install or download, without waiting on an engineering queue.
- Founders, designers and operators who don't write code but already use an AI coding agent (Claude Code, Codex CLI, Gemini CLI, Cursor and similar).
- Engineers who want a shared vocabulary for working with a PM who now builds prototypes on their own.

The bar for taking part is that you are making something, even if it's only a prototype.

## What's inside

| Folder | What you get |
|---|---|
| [`method/`](method/README.md) | The method in one page: four ideas, the safety net, and one short file per phase (Discover, Define, Design, Develop, Validate) |
| [`templates/`](templates/README.md) | Spec template, seven-question dev brief, launch self-check (including the App Store rejection checklist) |
| [`prompts/`](prompts/README.md) | Copy-paste prompts: one sentence to a spec, make the AI ask first, small steps, self-test, App Store review, launch post |
| [`cases/official/`](cases/official/README.md) | Summaries of four shipped products: SoloPDF, FreeID Photo, SoloMD, Unterm |
| [`cases/community/`](cases/community/README.md) | Cases submitted by people who built something with AI, plus the template to write your own |
| [`skills/`](skills/README.md) | The doaipm Agent Skill: install the method into your AI coding tool |

Every content file has an English version (`X.md`) and a Chinese version (`X.zh.md`) with the same structure.

## How to use it in 3 steps

1. **Read [`method/README.md`](method/README.md).** It takes about ten minutes and tells you what to do in each phase and what "done" looks like.
2. **Fill in the [dev brief](templates/dev-brief.md)** for the thing you want to build (or use the free web version at [doaipm.com/en/tools/brief/](https://doaipm.com/en/tools/brief/)), paste it into your AI coding tool, and add the [ask-before-coding prompt](prompts/ask-before-coding.md).
3. **Build in small steps, then run the [launch self-check](templates/launch-checklist.md)** before you call it done or submit it anywhere.

If you want the agent itself to follow the method by default, install the [doaipm Agent Skill](skills/README.md).

## Contributing

The most useful thing you can give back is a real case: what you built, which AI tools you used, how long it took, where you got stuck.

- **Submit a case**: [open a case issue](https://github.com/zhitongblog/ai-pm-playbook/issues/new?template=case.yml). A maintainer will turn it into a file under `cases/community/` with your name on it.
- **Submit a prompt**: [open a prompt issue](https://github.com/zhitongblog/ai-pm-playbook/issues/new?template=prompt.yml). Prompts you actually used on a real project are worth more than clever ones.
- **Ask a question**: [open a question issue](https://github.com/zhitongblog/ai-pm-playbook/issues/new?template=question.yml) or post in Discussions.
- **Fix or improve the text**: pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

Everyone who contributes is listed in [CONTRIBUTORS.md](CONTRIBUTORS.md).

## Community

- **[GitHub Discussions](https://github.com/zhitongblog/ai-pm-playbook/discussions)** is the main venue in English. Categories: Show & Tell (post what you built), Q&A, Ideas, and Rankings (nominations and score debates for the [Top 100 PM rankings](https://github.com/zhitongblog/top-pm-rankings)).
- **WeChat group "AI 产品经理 · 说出来就做出来"** for Chinese-speaking members: weekly "what I shipped this week" threads, Q&A, and the monthly case. Joining instructions are in the [Chinese README](README.zh.md#社区).

Good cases from the WeChat group are written up here (with the author's consent and credit), and new content in this repo is announced in the group.

Every month we pick one submitted case as the case of the month and write it up in full.

## Ambassadors

Ambassadors are members who help the community grow. There is no commission. What they get instead is listed below.

**Who can become one** (any one of these):

- You submitted a case that was accepted into this repo.
- You organized a talk or session, online or offline, about the doaipm method or about how you build things with AI.
- You brought 10 or more people into the community group (counted through your personal link).

**What you get:**

| Benefit | Details |
|---|---|
| We write one about you | Your product or case, written up as an article on our Toutiao or WeChat Official Account. This is the most concrete exposure we can offer an individual |
| Your name on the wall | Listed in [`CONTRIBUTORS.md`](CONTRIBUTORS.md) and on the ambassador wall of the site's community page, with your personal link |
| Playbook and updates free | The early-bird playbook in both Chinese and English, and every future update, free |
| Early access to new products | Beta access to new apps (TestFlight and similar) |
| Ambassador group | A separate small group for talking directly with the maintainer |
| Personal referral link | A link with `?utm_source=amb-<name>`; site stats show how many people you brought, published monthly |

**What you do** (it's light):

- At least once a month: submit a case or a prompt, or share community content with your own circle.
- After three months with no activity, you go back to being a regular member. Your name stays in the contributors list.

To apply, post in [Discussions](https://github.com/zhitongblog/ai-pm-playbook/discussions) (Ideas category) with what you've done so far.

## Related

- **[doaipm.com](https://doaipm.com)**: the method, the free tools, and the blog.
- **The early-bird playbook** ([English](https://doaipm.com/en/presale/) · [中文](https://doaipm.com/zh/presale/)): the paid, full step-by-step version. This repo gives away the method, templates, prompts and case summaries. The playbook keeps the complete chapter-by-chapter walkthrough of the four products, commit by commit, plus Q&A.
- **[zhitongblog/doaipm-skill](https://github.com/zhitongblog/doaipm-skill)**: the method as a portable Agent Skill.
- **[zhitongblog/top-pm-rankings](https://github.com/zhitongblog/top-pm-rankings)**: the 100 product managers who changed the world, scored by AI. Nominations and score debates happen there and in the Rankings category of Discussions.

## License

- Text content (method, templates, prompts, cases): [CC BY 4.0](LICENSE). You can copy, adapt and share it, including commercially, as long as you give credit.
- Code and scripts: [MIT](LICENSE-CODE).
