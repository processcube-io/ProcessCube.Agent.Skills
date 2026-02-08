# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Claude plugin marketplace** for ProcessCube release management. It provides Claude with structured instructions (as markdown files) to automate semantic versioning, changelog generation, and GitFlow-based releases for ProcessCube components. The project is entirely documentation-driven — there is no build system, no runtime code, and no tests.

**Owner:** ProcessCube UG
**Language:** All documentation and commands are written in German.

## Repository Structure

```
.claude-plugin/marketplace.json    # Root marketplace registry (lists available plugins)
processcube-release/               # Release manager plugin
  .claude-plugin/plugin.json       # Plugin metadata + command registration
  commands/
    release-stable.md              # Stable release from 'main' branch
    release-insiders.md            # Insiders release from 'insiders' branch
    release-development.md         # Dev release from 'develop' branch
  README.md                        # Plugin documentation (German)
skills/
  changelog/skill.md               # Changelog generation skill
  release-process/SKILL.md         # Release process workflow skill
```

## Architecture

### Plugin System
- `marketplace.json` registers plugins by name and source path
- Each plugin has a `plugin.json` defining metadata and an array of command file paths
- Commands are markdown files containing step-by-step instructions that Claude executes

### Skills vs Commands
- **Commands** (in `processcube-release/commands/`): Plugin-bound, triggered via slash commands like `/release-stable`. Each command is specific to a branch and release type.
- **Skills** (in `skills/`): Reusable, standalone workflows. The `release-process` skill uses a **single-branch workflow** (only `main`), while the plugin commands follow a **multi-branch GitFlow** model (`main`, `insiders`, `develop`).

**Important inconsistency to be aware of:** The `release-process` skill and the plugin commands use different branching strategies. The skill uses a single-branch approach (all releases from `main`), while commands enforce specific branches per release type.

### Versioning Schemes

| Release Type | Format | Branch (Commands) | Branch (Skill) |
|---|---|---|---|
| Stable | `MAJOR.MINOR.PATCH` | `main` | `main` |
| Insiders | `X.Y.Z-insiders.TIMESTAMP` (commands) / `X.Y.Z-insiders.N` (skill) | `insiders` | `main` |
| Development | `X.Y.Z-dev.BRANCH.TIMESTAMP` (commands) / `X.Y.Z-develop.N` (skill) | `develop` | `main` |

Note: The insiders/development suffix format differs between commands (timestamp-based) and the skill (sequential numbering).

## Making Changes

When editing command or skill markdown files:
- Preserve the instruction structure (numbered steps, validation checks, changelog templates)
- Branch validation is marked as **KRITISCH** (critical) — always keep strict branch checks
- Changelog entries must be written from the **user's perspective** (Nutzersicht), not technical
- All release workflows follow the pattern: validate branch → determine version → generate changelog → update files → git tag → push → summary

When adding a new plugin:
1. Create a directory with `.claude-plugin/plugin.json`
2. Register it in the root `.claude-plugin/marketplace.json`
3. Command files go in a `commands/` subdirectory

When adding a new skill:
1. Create a directory under `skills/`
2. Add a `skill.md` or `SKILL.md` with frontmatter (name, description, allowed-tools)
