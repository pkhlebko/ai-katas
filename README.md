# Kata 4b: Skills (Cursor)

> **Reference solution branch.** For the starting point, checkout `kata-4-cursor-start`.

This branch contains completed agent skills for Cursor:

- **`.cursor/skills/conventional-commits/`** — skill enforcing project commitlint rules
- **`.cursor/skills/unit-test-writer/`** — skill generating Vitest + React Testing Library tests matching project patterns

## What was implemented

Two Cursor agent skills:

1. **Conventional Commits** (`.cursor/skills/conventional-commits/SKILL.md`)
   - Enforces `type(scope): description` format
   - Project-specific scopes: i18n, hero, form, filters, destinations, guides, help, services, lib, ci, deps
   - Simplified workflow for Cursor's agent interface

2. **Unit Test Writer** (`.cursor/skills/unit-test-writer/SKILL.md`)
   - Generates Vitest + React Testing Library tests
   - AAA pattern enforced, real i18n provider (no mocks)
   - Includes `examples.md` with project-specific test patterns

## Quick Start

```bash
npm install
npm run dev
```

## Verification

In Cursor, verify the skills appear in the skills panel and produce correct output when invoked.