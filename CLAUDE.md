# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A personal collection of Agent Skills. Each top-level directory is exactly one skill, and `SKILL.md` is its entry point.

There is no build, test, lint, or CI toolchain — the artifacts are markdown, and verification means invoking the skill in a Claude Code session (`/eli5 <topic>`, `/technical-example`).

## Skill Anatomy

A skill is self-contained: its `SKILL.md` plus any files it references, all paths relative to the skill directory. Skills are installed by copying the directory, so nothing inside may depend on files elsewhere in this repo.

The YAML frontmatter is functional, not documentation:

- `name` — the invocation name.
- `description` — what the harness matches against to decide whether the skill triggers. It states *when to use* the skill (trigger phrases, user phrasings), not just what it does. `technical-example`'s description is deliberately long and packs Chinese trigger words (`例子`, `原理`, `机制`, …) alongside English ones — that length is the mechanism, not bloat.

## README.md

README.md is the index and must be updated in the same change as adding, removing, or renaming a skill. It has three sections:

- **Skills in This Repo** — this repo's own skills, as bullets with a link to `SKILL.md` and the invocation form.
- **Skills From Elsewhere** — single external skills.
- **Skill Collections** — whole repositories of skills.

Every list and table is kept in alphabetical order.

## The Two Existing Skills

`eli5/` is the minimal shape: a four-line `SKILL.md` whose body is a one-sentence instruction plus the `$ARGUMENTS` placeholder.

`technical-example/` is the full-workflow shape and carries conventions worth preserving:

- Communicates with the user and writes READMEs in Chinese; code, identifiers, and file names stay English.
- Plans before writing code and stops for explicit confirmation — the plan is a cheap place to catch a misunderstanding of what the user wanted to learn.
- Generates into `{tech}-app-example/` or `{tech}-principle-example/` in the *current working directory*, never modifying files outside that directory, and only after checking the runtime and package manager exist.
- Must actually run the generated code before reporting completion.
