# Kata 5: OpenSpec Development

> **Starting point branch.** No separate reference solution branch for this kata.

## Task

Drive development from a structured specification (OpenSpec) before writing implementation code.

An OpenSpec document defines requirements, acceptance criteria, and constraints in a machine-readable format. Your job is to:

1. Create an OpenSpec specification for a new feature or modification
2. Review the spec for completeness and clarity
3. Translate spec requirements into implementation tasks
4. Implement each requirement traceably, linking code changes back to spec sections
5. Verify each acceptance criterion is met

## Starting State

This branch has the completed Northstar Travel app with i18n, tests, and skills. No OpenSpec file exists yet — you will create one as part of the exercise.

## Hints

- An OpenSpec file typically lives at the project root as `open-spec.yaml` or `SPEC.md`
- Structure your specification with: overview, requirements, acceptance criteria, constraints
- Use the spec's acceptance criteria as your test cases
- Keep implementation commits traceable back to spec sections (e.g., `feat(filters): implement pace filter per spec §3.2`)
- Ask AI to draft the specification before touching code

## Setup

```bash
npm install
npm run dev
```

## Verification

- Each spec requirement has a corresponding test
- All acceptance criteria pass
- Implementation matches spec constraints (no over-engineering)
- Commits reference spec sections

## Deliverable

A branch where all OpenSpec requirements are implemented and verified, with an OpenSpec file at the project root.