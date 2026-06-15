# Validators — Per-Kata Check Lists

Detailed check lists for each kata. The `/validate` skill reads this file
to know exactly what to check for each kata.

---

## Kata 1: Legacy Modernization

### Automated Checks

| # | Check | Command / Method |
|---|-------|------------------|
| 1 | Deliverable note exists | Check for `DELIVERABLE.md`, `KATA-NOTES.md`, or any notes file in the working directory |
| 2 | External repo referenced | Grep notes file for `angular-form-builder` or `kelp404` |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|--------------|
| 1 | Original app ran successfully | Ask participant to describe the baseline behavior they established before rewriting |
| 2 | Modern stack used | Check the rewritten project for React, Vue, or Angular 17+ — not AngularJS 1.x |
| 3 | All 4 new controls present | Verify: switch/toggle control, date picker, dark theme, theme switcher |
| 4 | Core workflow preserved | Confirm drag-and-drop form building still works in the modernized version |

### Failure Advice

- **No deliverable note**: Ask the participant to create a `DELIVERABLE.md` describing the modernized app and linking to the repo or demo.
- **Still using AngularJS**: The kata requires a full rewrite. AngularJS patches or upgrades do not satisfy the modernization goal.
- **Missing controls**: Each of the four additions (switch/toggle, date picker, dark theme, theme switcher) must be independently verifiable.

---

## Kata 2: Internationalization

### Automated Checks

| # | Check | Command / Method |
|---|-------|------------------|
| 1 | Build passes | `npm run build` exits 0 |
| 2 | Lint passes | `npm run lint` exits 0 |
| 3 | i18n config exists | `src/i18n/index.ts` exists |
| 4 | Locale files exist | `src/i18n/locales/en.ts`, `lt.ts`, `zh.ts` all exist |
| 5 | Language switcher exists | Grep `LanguageSwitcher` or language-related component in `src/components/` or `src/pages/` |
| 6 | localStorage persistence | Check `src/i18n/index.ts` for `localStorage` or `lookup` from `i18next-browser-languagedetector` |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | All 3 locales complete | Compare key counts across `en.ts`, `lt.ts`, `zh.ts`. Flag any locale missing > 5% of keys. |
| 2 | `useLocalizedContent()` hook used | Grep for `useLocalizedContent` in components. Should appear in at least `HomePage.tsx`. |
| 3 | `<html lang>` updates | Check `src/i18n/index.ts` or language switcher for `document.documentElement.lang` update. |
| 4 | No hardcoded English in JSX | Grep components for common English patterns: `>Home<`, `>About<`, `>Contact<`, `"Welcome"`, `"Search"` etc. inside `.tsx` files. Any match is a ❌. |
| 5 | Translation keys structured | Check that locale JSONs use nested keys (e.g., `hero.title`) not flat keys. |

### Failure Advice

- **Missing locale keys**: Run a diff between `en.ts` keys and the other locale keys. List specific missing keys.
- **Hardcoded English**: Show the file, line, and the string found. Suggest the translation key to use instead.
- **No language switcher**: Suggest adding a `LanguageSwitcher` component that calls `i18n.changeLanguage()`.

---

## Kata 3: Unit Test Coverage

### Automated Checks

| # | Check | Command / Method |
|---|-------|------------------|
| 1 | Coverage passes at 95% | `npm run test:coverage` exits 0 |
| 2 | Lines ≥ 95% | Parse coverage output for lines threshold |
| 3 | Functions ≥ 95% | Parse coverage output for functions threshold |
| 4 | Branches ≥ 95% | Parse coverage output for branches threshold |
| 5 | Statements ≥ 95% | Parse coverage output for statements threshold |
| 6 | Test files exist for key modules | Check for test files in `src/lib/`, `src/services/`, `src/pages/`, `src/components/` |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | AAA pattern | Read 2–3 test files. Check that tests follow Arrange-Act-Assert. Each test should have clear setup, action, and assertion phases. |
| 2 | i18n handled correctly | Read component test files. Check for `I18nextProvider` wrapper or `renderWithI18n` helper. `useTranslation` should NOT be mocked directly — real i18next should be used. |
| 3 | React Router wrapped | Read test files for pages. Check for `MemoryRouter` or `renderWithRouter` helper when testing components that use `useNavigate` or `Link`. |
| 4 | Good test naming | Test descriptions should describe behavior, not implementation. `should show error when budget is empty` ✅, `should call setState` ❌. |
| 5 | No anti-patterns | Check for: testing implementation details (enzyme-style), `snapshot` tests without semantic assertions, `any` type casts in tests. |

### Failure Advice

- **Below 95% coverage**: Show which files have lowest coverage. Suggest which files need more tests.
- **i18n mock issues**: Explain that mocking `useTranslation` makes tests fragile. Show how to use `I18nextProvider` wrapper.
- **Missing Router wrapper**: Show how to add `MemoryRouter` around components using navigation.

---

## Kata 4a: Skills (Claude Code)

### Automated Checks

| # | Check | Command / Method |
|---|-------|---------------|
| 1 | `.claude/skills/` directory exists | Check `.claude/skills/` exists (plural, not singular `skill/`) |
| 2 | At least 2 skill directories | List directories in `.claude/skills/`. Should find `conventional-commits/` and `unit-test-writer/` (or similar). |
| 3 | SKILL.md files have valid frontmatter | Each SKILL.md should have `---` delimiters with `name` and `description` fields. |
| 4 | Frontmatter parses | No syntax errors in YAML frontmatter. |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | Conventional commits skill is project-specific | Read `conventional-commits/SKILL.md`. Should reference project scopes (i18n, hero, form, etc.) from commitlint config. |
| 2 | Unit test skill references correct stack | Read `unit-test-writer/SKILL.md`. Should mention Vitest, React Testing Library, jest-dom, user-event. |
| 3 | Examples file provided | Check for `unit-test-writer/examples.md` or similar. Should contain project-specific test examples. |
| 4 | Skills include `allowed-tools` | SKILL.md frontmatter should list which tools the skill needs. |
| 5 | Skills are invocable | The skill should have an `Invocation` section with `/skill-name` command. |

### Failure Advice

- **Singular `skill/` directory**: Note that Claude Code expects `.claude/skills/` (plural). Rename the directory.
- **Generic boilerplate**: Skills should reference this project's specific stack, scopes, and conventions — not copy-paste from documentation.
- **Missing examples**: The test writer skill should include project-specific examples showing `renderWithI18n`, `renderWithRouter`, etc.

---

## Kata 4b: Skills (Cursor)

### Automated Checks

| # | Check | Command / Method |
|---|-------|---------------|
| 1 | `.cursor/skills/` directory exists | Check `.cursor/skills/` exists |
| 2 | At least 2 skill directories | List directories in `.cursor/skills/` |
| 3 | SKILL.md files have valid frontmatter | Each SKILL.md should have `---` delimiters with `name` and `description` fields. |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | Skills adapted for Cursor | Read SKILL.md files. Cursor skills should NOT have `allowed-tools` or `compatibility` frontmatter fields — those are Claude-specific. |
| 2 | Content is project-specific | Same as Kata 4a — should reference this project's stack, scopes, conventions. |
| 3 | Examples file provided | Check for `unit-test-writer/examples.md`. |

### Failure Advice

- **Claude-specific fields in Cursor skills**: Remove `allowed-tools`, `compatibility`, `metadata` from Cursor SKILL.md frontmatter. Cursor doesn't use these.
- **Same as Kata 4a**: Most qualitative advice applies to both.

---

## Kata 5: OpenSpec Development

### Automated Checks

| # | Check | Command / Method |
|---|-------|---------------|
| 1 | Spec directory exists | Check for `.openspec/` or `specs/` or similar directory |
| 2 | Spec files exist | At least one `.md` or `.yaml`/`.yml` spec file |
| 3 | Spec references source files | Grep spec files for `src/` paths or component names |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | Spec covers key features | Read spec files. Should cover: destinations, booking form, language switching, guides. |
| 2 | Spec follows OpenSpec conventions | Check for proper OpenSpec structure (metadata, description, behavior, edge cases). |
| 3 | Spec is not boilerplate | Content should be specific to Northstar Travel, not generic templates. |

### Failure Advice

- **No spec files**: Create an OpenSpec directory and start with the most critical user flow (destination selection + booking).
- **Generic content**: Specs should reference specific component names, state variables, and data shapes from this project.

---

## Kata 6: MCP

### Automated Checks

| # | Check | Command / Method |
|---|-------|---------------|
| 1 | `.mcp.json` exists | Check `.mcp.json` in project root |
| 2 | Valid MCP config structure | Parse `.mcp.json` — should have `mcpServers` key with server objects containing `command` and `args` |
| 3 | At least one server configured | `.mcp.json` should have ≥1 server entry |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | Server configs are valid | Check that `command` is a real command, `args` reference real files/scripts. |
| 2 | KATA-INSTRUCTIONS.md has notes | File should have setup notes beyond the template. |
| 3 | MCP server is connectable | Try running the MCP command to verify it starts (non-destructive — just check if the process launches). |

### Failure Advice

- **Placeholder tokens**: If `.mcp.json` has placeholder tokens (like `YOUR_TOKEN_HERE`), the MCP server won't connect. Replace with real credentials.
- **Wrong command path**: Verify the MCP command exists at the specified path.

---

## Kata 7: Codemie

### Automated Checks

| # | Check | Command / Method |
|---|-------|---------------|
| 1 | `CODEMIE-PLAN.md` exists | Check for `CODEMIE-PLAN.md` in project root |
| 2 | `CODEMIE-PLAN.md` is not empty/template | File should have substantial content (> 500 chars), not just a heading |

### Qualitative Checks

| # | Criterion | How to Check |
|---|-----------|---------------|
| 1 | Plan references Jira ticket | Grep for `EPMGDLT-1565` in CODEMIE-PLAN.md |
| 2 | Plan includes implementation steps | Should have numbered steps or sections describing what to implement. |
| 3 | Release notes documented | Should have a release notes section or reference to published notes. |

### Failure Advice

- **Empty plan**: Fill in the discovery steps — what you found on Codemie, how Jira integration works, what the BI Assistant does.
- **Missing Jira reference**: Add the specific ticket description and how it translates to implementation steps.

---

## Not a Kata Branch

If the branch is `main` or doesn't match any kata pattern, print:

```
This branch is not a kata branch.

Available kata branches:
  git checkout kata-1-start         — Kata 1: Legacy Modernization (external repo)
  git checkout kata-2-start         — Kata 2: Internationalization
  git checkout kata-3-start         — Kata 3: Unit Test Coverage
  git checkout kata-4-claude-start  — Kata 4a: Skills (Claude)
  git checkout kata-4-cursor-start  — Kata 4b: Skills (Cursor)
  git checkout openspec-development — Kata 5: OpenSpec Development
  git checkout ai-kata-mcp          — Kata 6: MCP
  git checkout discovery-codemie    — Kata 7: Codemie

Reference solution branches:
  git checkout feat/i18n            — Kata 2: Reference (i18n completed)
  git checkout unit-test-coverage   — Kata 3: Reference (95% coverage)
  git checkout claude-skills        — Kata 4a: Reference (Claude skills)
  git checkout cursor-skills        — Kata 4b: Reference (Cursor skills)
```