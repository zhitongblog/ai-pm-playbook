# <Product/version name> — <one-line characterization, e.g. "UI rebuild + knowledge graph completion"> Project Plan

> Status: <Direction locked, implementation not started / In progress / Shipped>
> Decisions (signed off by <who> on <date>):
> - **<Decision 1>**: <What was decided. Write down what you're NOT doing too, e.g. "Don't copy their cool gray-blue, keep our warm brand colors">
> - **<Decision 2>**: <e.g. pacing: all parallel / sequential. If it's a high-risk path, state "user is aware and accepts">

---

## 0. One-sentence goal

Ship **<version number>**: <One sentence on what this version must achieve. Not two.>

**Acceptance criteria (Definition of Done):**
1. <A condition that's either true or false. Don't write "better experience," you can't verify that>
2. <Every item must be something a person can check>
3. <Data/storage-layer constraints go here>
4. <"No regressions" items like multi-language, themes, compatibility go here>
5. <Compatibility with external systems>

---

## 1. Current-state diagnosis — why it doesn't work now

<Which scan/survey this comes from. Name the source, don't go on impressions>

| Dimension | Current state | Problem |
|---|---|---|
| <Dimension> | <Quantified current state, numbers you can count> | <Why this number is a problem> |

**Root cause**: <One sentence on the gap at the very bottom. Not "the code is messy," but "the XX layer is missing.">

✅ Good stuff that already exists and can be reused: <List it and explicitly keep it. Stops the AI from casually rewriting the parts that work.>

---

## 2. Shared contract (the foundation of this version)

> This is the only trunk in parallel development: every implementing agent pulls **from this written contract** instead of inventing its own.
> Even if everything runs in parallel, this spec has to be written first, or you will definitely redo work.

### 2.1 <Token / interface / data structure layer>

<Write out the concrete values. Don't write "use consistent spacing," write `--sp-1:4px --sp-2:8px …`.
AI won't make aesthetic decisions for you. It'll just have each part do its own thing.>

### 2.2 <Component / module list>

<List each one: name, responsibility, which file it lives in.>

---

## 3. Feature workstreams

| # | Feature | Files involved (new/changed) | Depends on |
|---|---|---|---|
| F1 | <Feature name> | `new/file/path` (new) / `existing file` (changed) | <Which part of the shared contract it depends on> |

### Key technical notes
<The pitfalls the AI will definitely fall into if you don't write them down. Write them here up front.>

---

## 4. Task assignment and parallel orchestration

**Dependency graph:**
```
        [Foundation] <shared contract>
                ↓ everyone pulls from the written contract §2
   F1   F2   F3   F4   F5
        └── unified merge + integration self-test ──┘
```

**Orchestration strategy:**
1. **Phase 0 (foundation, trunk)**: <What gets done first and why it must be sequential. Spell out the sequential points you physically can't get around.>
2. **Phase 1 (parallel)**: <How many in parallel, how they're isolated (worktree), how much the files overlap.>
3. **Merge phase**: <Merge order (light → heavy, fewer dependencies → more), which files the conflicts concentrate in, what you use to reduce conflicts (e.g. "append-only registration").>

---

## 5. Self-test strategy (mandatory for every feature)

Before a feature **can be declared done**, it must pass:
1. **Data round-trip**: create a fixture → drive the feature → read back and assert, confirm only what should change changed.
2. **UI path**: drive the real UI + verify with screenshots, not just unit tests.
3. **Unit tests**: <run whichever layers are involved>
4. **Git safety**: compare before and after, confirm one edit = a clean, minimal diff.
5. **CLI + MCP smoke test**: new capabilities are exposed in both the CLI and MCP at the same time.
6. **Multi-language**: new strings go into the primary language file, other languages get placeholders filled in.

> **Red line: no feature is declared done until its self-test passes.**
> Some things can't be tested by automation (e.g. third-party components that synthetic keyboard events can't drive).
> In that case fall back to store-level assertions + screenshot verification, **write down the fallback plan**, and never skip it.

---

## 6. Milestones

| Milestone | Content | Exit condition |
|---|---|---|
| M0 <Foundation> | <What gets done> | <What counts as passing. Must be true or false.> |
| M1 <…> | | |
| M<n> Release | <Atomicity requirements for packaging/store release: which artifacts must all be ready at once> | |

---

## 7. Risks and rollback

- **<Risk name>**: <How to reduce it / how to roll back if it goes wrong>
- **Scope creep**: <Spell out which "might as well do it while we're here" items are pushed to the next version>

---

## 8. Out of scope for this version (explicit)

<List what you want to do but won't do in this version. This section isn't a formality.
If you don't write it down, the AI will follow your tone and build all of it, and this version will never ship.>
