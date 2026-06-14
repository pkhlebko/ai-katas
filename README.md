# Kata 3: Unit Test Coverage

> **Reference solution branch.** For the starting point, checkout `kata-3-start`.

This branch contains the completed unit test coverage implementation for the Northstar Travel app, with 95%+ coverage across lines, functions, branches, and statements.

## What was implemented

- Test files for all utility functions, services, i18n content hooks, pages, and components
- Coverage gate enforced at 95% (lines, functions, branches, statements) in `vite.config.ts`
- Tests use Vitest + React Testing Library + jest-dom
- Agent skill at `.claude/skill/unit-test/SKILL.md`

## Quick Start

```bash
npm install
npm run dev
```

## Verification

```bash
npm run test:coverage
```

All four thresholds pass at 95%:
- Lines ≥ 95%
- Functions ≥ 95%
- Branches ≥ 95%
- Statements ≥ 95%