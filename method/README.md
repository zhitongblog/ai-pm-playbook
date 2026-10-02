# The doaipm method

[English](README.md) · [简体中文](README.zh.md)

A product manager in the AI era takes an idea to a running product by describing it clearly and letting an AI coding agent build it. The method below is how that works in practice. The longer versions live on [doaipm.com/en/method/](https://doaipm.com/en/method/).

## Four ideas

### 1. Trust the AI. Don't go tool-hunting.

The old PM habit is to meet every problem with a new tool: Figma for wireframes, Axure for flows, a plugin for charts, another one for animation. Half the energy goes into picking, learning and stitching tools together, and the actual problem stays untouched.

The new rule: when you hit any problem, the first question is not "what tool do I use?" but "how do I describe this to the AI?" Research, documents, prototypes and tests can all come out of one conversation.

The site's version of the method is opinionated about the setup: use Claude, use Claude Code (the agent that runs code, not the web chat), and pay for a tier with enough headroom (it recommends Claude Max at $100 or above) so daily high-fidelity work isn't interrupted by rate limits. The method itself works with any agentic coding tool; the [Agent Skill](../skills/README.md) supports Codex CLI, Gemini CLI and Cursor as well.

### 2. Not knowing how to code is an advantage

You are not held back by "how hard is this to implement". You focus on saying what you want, and saying things clearly is what product managers are trained to do.

Treat the agent as a very capable intern who needs you to be clear. Three phrases cover most of the work:

- "Help me build..." (assign the task)
- "This isn't right, it should be..." (give feedback)
- "Before you start, ask me a few questions" (let it help you think)

In your own project folder you can't break anything that matters. The worst case is that it does something wrong and you say "that's not right, try again".

### 3. High-fidelity first

Building a high-fidelity prototype used to take one to two weeks of PRD, scheduling and engineering, so PMs settled for sketches. With an agent, it runs the same day. When something goes from a luxury to an everyday tool, the way you work should change.

There are three levels of fidelity:

| Level | Form | Problem |
|---|---|---|
| L1 | Description (written or spoken) | Maximum ambiguity. Everyone imagines something different |
| L2 | Low-fidelity (wireframes, sketches) | You see the boxes, not the real experience |
| L3 | High-fidelity (runnable prototype) | Clickable, interactive, usable by real people |

Go straight to L3. "High-fidelity" means five concrete things:

1. Skip wireframes. Describe it and have the agent generate a runnable prototype.
2. Real copy and real data structures. Fake data is fine; Lorem ipsum and "Title placeholder" are not.
3. Real states: loading, empty, error, success. Not only the happy path.
4. Real interactions: it clicks, it accepts input, it gives feedback.
5. Test it on a real device or browser, not in your head.

Prototype code is not production code, and it doesn't need to be. It is the most precise spec you can hand to engineering.

### 4. Five phases

**Discover → Define → Design → Develop → Validate.** Each phase has a goal, a way to talk to the agent, and a definition of done.

| Phase | Goal | Done when |
|---|---|---|
| [1. Discover](01-discover.md) | Understand what users want and what competitors do | You can state the user's biggest pain in three sentences |
| [2. Define](02-define.md) | Turn a fuzzy idea into something anyone can build from | Success criteria and edge cases are written down; someone who wasn't in the room understands it |
| [3. Design](03-design.md) | See roughly what it looks like and pick a direction | One direction is chosen |
| [4. Develop](04-develop.md) | A prototype that runs, one small step at a time | The main flow runs in a browser or on a device without errors |
| [5. Validate](05-validate.md) | Let real people use it; decide with evidence | Real users have tried it and you can say, with evidence, whether to continue |

Develop is where most of the time goes. Validate is where most people cut corners.

## The safety net

Five rules form the floor. They exist so that you can be bold above it.

1. **No real sensitive data.** Use fake or anonymized data for prototypes.
2. **No secrets in code.** Use test-only credentials.
3. **A human presses irreversible buttons.** Publishing, deleting, paying: the agent asks, you press.
4. **Don't touch production.** Prototypes run locally or in a test environment.
5. **When in doubt, ask.** Compliance, payments, privacy and stack choices go to someone accountable before the agent acts.

The net gets tighter the closer you get to real users. Prototypes can be bold; production has to be careful.

## One thing the method keeps repeating

**Success has to be read back from the outside world. You can't declare it yourself.**

An AI agent rarely says "I failed". Much more often it says "I'm done". A build that works in development and breaks once packaged, a post that the script reports as published but never appeared, a setting that silently falls back to a default: none of these throw errors. The check is always the same: look at the real result, on the real device or the real platform, before calling it done. The [launch self-check](../templates/launch-checklist.md) turns this into a list.

## Where to go next

- Start a project with the [dev brief](../templates/dev-brief.md) and the [ask-before-coding prompt](../prompts/ask-before-coding.md).
- For a release, a refactor or parallel work, use the full [spec template](../templates/spec-template.md).
- See the method applied to four shipped products in [`cases/official/`](../cases/official/README.md).
