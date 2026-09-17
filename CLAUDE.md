# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A personal collection of Agent Skills: each top-level directory is one skill, with `SKILL.md` as its entry point. Skills are built and verified before they land here, so this file names no individual skill and documents none — it records only what holds for every skill, and stays valid as the set changes.

There is no build, test, lint, or CI toolchain. Verifying a change means invoking the skill in a Claude Code session.

## Skill Anatomy

A skill is installed by copying its directory, so it must be self-contained: nothing inside it may reference files elsewhere in this repo, including other skills.

`name` is the invocation name. `description` is what the harness matches against to decide whether a skill triggers — a trigger surface, not documentation.

## READMEs

`README.md` (English, primary) and `README.zh.md` (Chinese) are translations of each other: same sections, same entries, same order, both alphabetical. Both are updated in the same change as adding, removing, or renaming a skill — the one rule here that every skill change touches.

Each opens with a language-switch link right after the `# Skills` heading: `README.md` opens `English | [中文](README.zh.md)`, and `README.zh.md` opens `[English](README.md) | 中文`. Skill names, identifiers, file names, and the `Source` / `来源` column stay English; prose is translated.
