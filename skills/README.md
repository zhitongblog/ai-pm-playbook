# The doaipm Agent Skill

[English](README.md) · [简体中文](README.zh.md)

The method in this repo is written for people. The **doaipm Agent Skill** is the same method written for your AI coding agent, so it works this way by default: questions before code, high-fidelity over wireframes, and the human keeping the irreversible buttons.

Source and full instructions: **[github.com/zhitongblog/doaipm-skill](https://github.com/zhitongblog/doaipm-skill)** (MIT).

## What it changes

Give your agent a deliberately vague task, such as "Build me a tip calculator web app."

- **Without the skill**, a typical result is a single static HTML file, called done.
- **With the skill**, the agent first asks 3–5 sharp questions (split the bill? round up? which currency? tax before or after?), then builds a runnable high-fidelity prototype with real interactions and real states (empty, typing, error, result), checks it by actually opening it in a browser, and doesn't press an irreversible button (publish, deploy, pay) without you.

## Install

| Tool | How |
|------|-----|
| **Claude Code** | Clone the repo into `~/.claude/skills/doaipm/` (it must contain `SKILL.md`). It is discovered automatically. |
| **Codex CLI** | Clone into `~/.codex/skills/doaipm/`, or append `doaipm.method.md` to `~/.codex/AGENTS.md`. |
| **Gemini CLI** | Append `doaipm.method.md` to `~/.gemini/GEMINI.md`. |
| **Cursor** | Copy `doaipm.mdc` into `~/.cursor/rules/` (global) or `.cursor/rules/` (per project). |
| **Any other agent** | Put `doaipm.method.md` into the project's `AGENTS.md` / `CLAUDE.md`. |

One line for Claude Code:

```bash
git clone https://github.com/zhitongblog/doaipm-skill ~/.claude/skills/doaipm
```

## How it relates to this repo

| Here | In the skill |
|---|---|
| [`method/`](../method/README.md): the method explained for people | `SKILL.md`: the same method as instructions for an agent |
| [`prompts/`](../prompts/README.md): prompts you paste in by hand | Behaviour the agent follows without being asked |
| [`templates/`](../templates/README.md): briefs, specs, checklists | What the agent asks you for, or fills in from your answers |

The skill makes the defaults right. The prompts and templates here are for when you want to steer a specific step. Found a case where the skill behaves wrongly? Open an issue in the [skill repo](https://github.com/zhitongblog/doaipm-skill/issues).
