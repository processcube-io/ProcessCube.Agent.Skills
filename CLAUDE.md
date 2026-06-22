# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **Agent Skills marketplace** for ProcessCube development workflows. It provides coding agents (Claude Code, Codex, OpenClaw) with structured instructions (as SKILL.md files) to automate semantic versioning, changelog generation, documentation, and releases for ProcessCube components. The project is entirely documentation-driven — there is no build system, no runtime code, and no tests.

**Owner:** ProcessCube UG
**Language:** All documentation and skills are written in German.

## Repository Structure

```
skills/
  changelog/
    SKILL.md               # Changelog generation skill
  release-process/
    SKILL.md               # Release process workflow skill
  repo-doku/
    SKILL.md               # Repo documentation skill (README/DEVELOPMENT)
    references/            # Bundled reference files (doku-ziel.md, konventionen.md)
CLAUDE.md                  # Project guidance for Claude Code
README.md                  # Installation and usage guide (German)
```

## Skills Format (Agent Skills Open Standard)

Each skill lives in its own directory under `skills/` and contains a `SKILL.md` file with YAML frontmatter:

```yaml
---
name: <directory-name>           # Must match the directory name
description: <description>       # Used for skill discovery and invocation
allowed-tools: Bash, Read, ...   # Tools the skill may use
disable-model-invocation: true   # Optional: only trigger manually via slash command
---
```

The rest of the file contains markdown instructions that the agent executes.

### Versioning (Single-Branch)

All releases are created from the `main` branch:

| Release Type | Format | Example |
|---|---|---|
| Stable | `MAJOR.MINOR.PATCH` | `1.0.0` |
| Insiders | `X.Y.Z-insiders.N` | `1.1.0-insiders.1` |
| Development | `X.Y.Z-develop.N` | `1.1.0-develop.1` |

## Making Changes

When editing skill markdown files:
- Preserve the instruction structure (numbered steps, validation checks, changelog templates)
- Changelog entries must be written from the **user's perspective** (Nutzersicht), not technical
- Release workflows follow the pattern: validate branch → determine version → generate changelog → update files → git tag → push → summary

When adding a new skill:
1. Create a directory under `skills/`
2. Add a `SKILL.md` with YAML frontmatter (`name`, `description`, `allowed-tools`)
3. Ensure `name` matches the directory name
