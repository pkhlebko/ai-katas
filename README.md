# Kata 4a: Skills (Claude Code)

> **Reference solution branch.** For the starting point, checkout `kata-4-claude-start`.

This branch contains completed agent skills for Claude Code:

- **`.claude/skills/conventional-commits/`** — skill enforcing project commitlint rules (scopes, types, format)
- **`.claude/skills/unit-test-writer/`** — skill generating Vitest + React Testing Library tests matching project patterns

## What was implemented

Two Claude Code agent skills:

1. **Conventional Commits** (`.claude/skills/conventional-commits/SKILL.md`)
   - Enforces `type(scope): description` format
   - Project-specific scopes: i18n, hero, form, filters, destinations, guides, help, services, lib, ci, deps
   - Workflow: read staged diff → craft message → commit

2. **Unit Test Writer** (`.claude/skills/unit-test-writer/SKILL.md`)
   - Generates Vitest + React Testing Library tests
   - AAA pattern enforced, real i18n provider (no mocks)
   - Includes `examples.md` with project-specific test patterns

## Quick Start

```bash
npm install
npm run dev
```

## Verification

In Claude Code, invoke the skills:

- `/conventional-commits` to write a commit message
- `/unit-test-writer` to generate a test file