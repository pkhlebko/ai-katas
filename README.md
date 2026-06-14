# Kata 3: Unit Test Coverage

> **Starting point branch.** For the reference solution, checkout `unit-test-coverage`.

## Task

Write unit tests to bring the Northstar Travel app to **95% coverage** across lines, functions, branches, and statements.

The app has a small but growing codebase with:

- Pure utility functions in `src/lib/`
- Service-layer logic in `src/services/`
- React components in `src/components/` and `src/pages/`
- i18n hooks in `src/i18n/`

Currently only `src/lib/budgetUtils.ts` has tests. You need to cover the rest.

## Starting State

This branch has:

- Full i18n implementation (English, Lithuanian, Chinese)
- Vitest + React Testing Library configured
- One test file: `src/lib/budgetUtils.test.ts`
- Coverage threshold set to 80% lines/functions/statements, 75% branches

## Hints

- Run `npm run test:coverage` to see which files need tests
- Focus on pure functions first (`src/lib/`, `src/services/`) — they are easiest to test
- For React components, use `@testing-library/react` and `@testing-library/user-event`
- All components use `useTranslation` — wrap them with `I18nextProvider` in tests, do not mock `useTranslation`
- Co-locate test files with their source: `ComponentName.test.tsx` next to `ComponentName.tsx`

## Setup

```bash
npm install
npm run test:coverage
```

## Verification

```bash
npm run test:coverage
```

All four thresholds must pass at 95%:

- Lines ≥ 95%
- Functions ≥ 95%
- Branches ≥ 95%
- Statements ≥ 95%

## Deliverable

A branch or PR where `npm run test:coverage` passes with all thresholds at 95%.