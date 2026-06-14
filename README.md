# AI Kata 2.0 — Northstar Travel

A collection of AI training exercises (katas) built on the **Northstar Travel** React 19 + TypeScript SPA.

This branch (`main`) contains the completed reference state: i18n infrastructure, 95% test coverage, agent skills, and all service-layer logic. It serves as the "answer key" — each kata branch starts from an earlier state so participants can do the work themselves.

## Katas

| # | Kata | Start Branch | Reference Branch | Focus |
|---|------|-------------|-------------------|-------|
| 2 | Internationalization | `kata-2-start` | `feat/i18n` | Add multi-language support using react-i18next |
| 3 | Unit Test Coverage | `kata-3-start` | `unit-test-coverage` | Reach 95% test coverage with Vitest |
| 4a | Skills (Claude) | `kata-4-claude-start` | `claude-skills` | Create reusable agent skills for Claude Code |
| 4b | Skills (Cursor) | `kata-4-cursor-start` | `cursor-skills` | Create reusable agent skills for Cursor |
| 5 | OpenSpec Development | `openspec-development` | — | Drive development from structured specifications |
| 6 | MCP | `ai-kata-mcp` | — | Configure MCP servers and implement a Jira feature |
| 7 | Codemie | `discovery-codemie` | — | Explore Codemie platform and Jira integration |

> Kata 1 (Legacy Modernization) uses a separate repository.

Switch to a branch to see its kata assignment:

```bash
git checkout kata-2-start           # Kata 2: start
git checkout feat/i18n              # Kata 2: reference solution
git checkout kata-3-start           # Kata 3: start
git checkout unit-test-coverage     # Kata 3: reference solution
git checkout kata-4-claude-start    # Kata 4a: start (Claude)
git checkout claude-skills          # Kata 4a: reference (Claude)
git checkout kata-4-cursor-start    # Kata 4b: start (Cursor)
git checkout cursor-skills          # Kata 4b: reference (Cursor)
git checkout openspec-development   # Kata 5: start
git checkout ai-kata-mcp            # Kata 6: start
git checkout discovery-codemie      # Kata 7: start
```

## Quick Start (this branch)

```bash
npm install
npm run dev
```

## Verification

```bash
npm run lint
npm run build
npm run test:coverage
```