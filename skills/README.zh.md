# doaipm Agent Skill

[English](README.md) · [简体中文](README.zh.md)

这个仓库里的方法是写给人看的。**doaipm Agent Skill** 是写给 AI 编程工具的同一套方法，装上之后它默认就这么干活：先问再写代码，直接做高保真而不是线框图，不可逆的按钮留给人按。

源码和完整说明：**[github.com/zhitongblog/doaipm-skill](https://github.com/zhitongblog/doaipm-skill)**（MIT）。

## 装上之后有什么不同

故意给它一个含糊的任务，比如「给我做一个小费计算器网页」。

- **没装的时候**，常见的结果是一个静态 HTML 文件，然后说做完了
- **装了之后**，它先问你 3–5 个关键问题（要不要分摊？要不要取整？什么币种？税前还是税后？），再做出一个能跑的高保真原型：真实交互、真实状态（空、输入中、出错、出结果），真的在浏览器里打开验证过；不经过你，不会去按发布、部署、付款这类不可逆的按钮

## 安装

| 工具 | 怎么装 |
|------|-----|
| **Claude Code** | 把仓库 clone 到 `~/.claude/skills/doaipm/`（目录里要有 `SKILL.md`），会被自动识别 |
| **Codex CLI** | clone 到 `~/.codex/skills/doaipm/`，或者把 `doaipm.method.md` 追加到 `~/.codex/AGENTS.md` |
| **Gemini CLI** | 把 `doaipm.method.md` 追加到 `~/.gemini/GEMINI.md` |
| **Cursor** | 把 `doaipm.mdc` 拷到 `~/.cursor/rules/`（全局）或 `.cursor/rules/`（单个项目） |
| **其他 agent** | 把 `doaipm.method.md` 放进项目的 `AGENTS.md` / `CLAUDE.md` |

Claude Code 一行装好：

```bash
git clone https://github.com/zhitongblog/doaipm-skill ~/.claude/skills/doaipm
```

## 跟这个仓库的关系

| 这里 | Skill 里 |
|---|---|
| [`method/`](../method/README.zh.md)：讲给人听的方法 | `SKILL.md`：同一套方法，写成给 agent 的指令 |
| [`prompts/`](../prompts/README.zh.md)：要你手动粘贴的提示词 | agent 不用你提醒就会照做的行为 |
| [`templates/`](../templates/README.zh.md)：简报、规格、清单 | agent 会向你要的东西，或者根据你的回答替你填的东西 |

Skill 负责把默认行为摆正，这里的提示词和模板用在你想具体掌控某一步的时候。发现 skill 哪里做得不对，到 [skill 仓库](https://github.com/zhitongblog/doaipm-skill/issues)提 issue。
