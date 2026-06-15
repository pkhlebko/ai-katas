---
name: validate
description: >-
  Validate kata completion. Detects which kata branch you're on, runs automated
  checks, assesses code quality, and gives structured per-item feedback.
allowed-tools: Read Glob Grep Bash Edit Write
---

## Invocation

```
/validate
/validate [kata-number]
```

Without arguments, auto-detects the kata from the current git branch.
With a number (1–7, or 4a/4b), validates that specific kata.

## Kata Detection

Read the current branch name with `git branch --show-current` and match:

| Branch pattern | Kata |
|---|---|
| `kata-1-start` | 1: Legacy Modernization |
| `kata-2-start` or `feat/i18n` | 2: Internationalization |
| `kata-3-start` or `unit-test-coverage` | 3: Unit Test Coverage |
| `kata-4-claude-start` or `claude-skills` | 4a: Skills (Claude) |
| `kata-4-cursor-start` or `cursor-skills` | 4b: Skills (Cursor) |
| `openspec-development` | 5: OpenSpec Development |
| `ai-kata-mcp` | 6: MCP |
| `discovery-codemie` | 7: Codemie |
| `main` or other | Not a kata branch — list available branches |

If the branch doesn't match any kata, suggest which branches to checkout:

```
This branch (main) is not a kata branch.
Available kata branches:
  kata-1-start    — Kata 1: Legacy Modernization
  kata-2-start    — Kata 2: Internationalization
  kata-3-start    — Kata 3: Unit Test Coverage
  kata-4-claude-start — Kata 4a: Skills (Claude)
  kata-4-cursor-start — Kata 4b: Skills (Cursor)
  openspec-development — Kata 5: OpenSpec Development
  ai-kata-mcp     — Kata 6: MCP
  discovery-codemie — Kata 7: Codemie
```

## Validation Flow

1. **Detect kata** from branch name
2. **Print kata title** and brief description
3. **Run automated checks** (bash commands, file existence)
4. **Run qualitative checks** (read files, analyze code quality)
5. **Generate report** with ✅/⚠️/❌ per criterion
6. **Summarize** with overall status and actionable advice

For detailed per-kata check lists, read `.claude/skills/validate/validators.md`.

## Report Format

Output a markdown report:

```markdown
# Kata N: [Title] — Validation Report

## Branch: `branch-name`

### Automated Checks

| Criterion | Status | Details |
|-----------|--------|---------|
| Build passes | ✅ | `npm run build` succeeded |
| Lint passes | ✅ | No errors |
| ... | ... | ... |

### Qualitative Assessment

| Criterion | Status | Details |
|-----------|--------|---------|
| Translation completeness | ⚠️ | `lt.json` has 12 missing keys: ... |
| ... | ... | ... |

### Summary

**Overall: ⚠️ Partial**

- ✅ 5/7 automated checks pass
- ⚠️ 1/4 qualitative checks needs work
- ❌ 1/4 qualitative checks failed

**Action items:**
1. Add missing Lithuanian translations for `hero.*` keys
2. Fix `<html lang>` attribute update in `SiteHeader.tsx`
```

## Status Definitions

| Status | Meaning |
|--------|---------|
| ✅ | Pass — criterion fully met |
| ⚠️ | Partial — criterion partially met, needs improvement |
| ❌ | Fail — criterion not met |

## Important Notes

- Be thorough but constructive — explain *why* something fails and *how* to fix it
- For qualitative checks, cite specific files and line numbers
- For skill katas (4a/4b), actually invoke the skills to verify they work
- For test kata (3), read sample test files to assess quality patterns
- For i18n kata (2), check all three locale files for completeness
- Always run `npm run build` and `npm run lint` first — if these fail, other checks are unreliable