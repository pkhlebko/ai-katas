# Kata 4b: Skills (Cursor)

> **Starting point branch.** For the reference solution, checkout `cursor-skills`.

## Task

Create reusable **agent skills** for Cursor that codify project conventions.

An agent skill is a markdown file under `.cursor/skills/` that teaches an AI assistant how to perform a specific task consistently in this codebase. Your job is to:

1. Create a **conventional commits** skill that enforces the project's commitlint rules
2. Create a **unit test writer** skill that produces tests matching this project's patterns (Vitest, React Testing Library, i18n wrapping)
3. Ensure the skills are well-documented with examples and project-specific constraints

## Starting State

This branch has:

- Full app with i18n and 95% test coverage
- Commitlint + Husky enforcing conventional commit format
- No agent skills defined yet

## Hints

- A Cursor skill file must have YAML frontmatter with `name` and `description`
- Include concrete examples from this project (e.g., commit scopes like `i18n`, `form`, `budgetUtils`)
- The unit-test skill should reference the project's actual test patterns (co-located files, i18n wrapping, `renderWithI18n` helper)
- Test your skill by invoking it in Cursor and verifying the output matches conventions

## Setup

```bash
npm install
npm run dev
```

## Verification

In Cursor, verify the skills appear in the skills panel and produce correct output when invoked:

- Conventional commits skill — verify messages follow commitlint rules
- Unit test writer skill — verify generated tests match project patterns

## Deliverable

Both skill files (`.cursor/skills/conventional-commits/SKILL.md` and `.cursor/skills/unit-test-writer/SKILL.md`) populated with working, well-documented skill definitions.