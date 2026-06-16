# AI Kata 2.0 — Northstar Travel

A collection of AI training exercises (katas) built on the **Northstar Travel** React 19 + TypeScript SPA.

This branch (`main`) contains the completed reference state: i18n infrastructure, 95% test coverage, agent skills, and all service-layer logic. It serves as the "answer key" — each kata branch starts from an earlier state so participants can do the work themselves.

## Katas

| # | Kata | Start Branch | Reference Branch | Focus |
|---|------|-------------|-------------------|-------|
| 1 | Legacy Modernization | `kata-1-start` | — | Modernize a legacy AngularJS form builder |
| 2 | Internationalization | `kata-2-start` | `kata-2-reference` | Add multi-language support using react-i18next |
| 3 | Unit Test Coverage | `kata-3-start` | `kata-3-reference` | Reach 95% test coverage with Vitest |
| 4a | Skills (Claude) | `kata-4-claude-start` | `kata-4-claude-reference` | Create reusable agent skills for Claude Code |
| 4b | Skills (Cursor) | `kata-4-cursor-start` | `kata-4-cursor-reference` | Create reusable agent skills for Cursor |
| 5 | OpenSpec Development | `kata-5-start` | — | Drive development from structured specifications |
| 6 | MCP | `kata-6-start` | — | Configure MCP servers and implement a Jira feature |
| 7 | Codemie | `kata-7-start` | — | Explore Codemie platform and Jira integration |

> Kata 1 uses the external repo [kelp404/angular-form-builder](https://github.com/kelp404/angular-form-builder) — see `kata-1-start` for instructions.

Switch to a branch to see its kata assignment:

```bash
git checkout kata-1-start           # Kata 1: start (external repo)
git checkout kata-2-start           # Kata 2: start
git checkout kata-2-reference       # Kata 2: reference solution
git checkout kata-3-start           # Kata 3: start
git checkout kata-3-reference       # Kata 3: reference solution
git checkout kata-4-claude-start    # Kata 4a: start (Claude)
git checkout kata-4-claude-reference # Kata 4a: reference (Claude)
git checkout kata-4-cursor-start    # Kata 4b: start (Cursor)
git checkout kata-4-cursor-reference # Kata 4b: reference (Cursor)
git checkout kata-5-start           # Kata 5: start
git checkout kata-6-start           # Kata 6: start
git checkout kata-7-start           # Kata 7: start
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