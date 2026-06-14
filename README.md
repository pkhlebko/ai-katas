# Kata 2: Internationalization

> **Starting point branch.** For the reference solution, checkout `feat/i18n`.

## Task

Add multi-language support to the Northstar Travel app using **react-i18next**.

The app currently has all UI text hardcoded in English across components and pages. Your job is to:

1. Install and configure `i18next` and `react-i18next`
2. Extract all user-facing strings into locale files (English, Lithuanian, Mandarin Chinese)
3. Replace hardcoded text with `useTranslation()` calls and `t()` keys
4. Add a language switcher component
5. Persist the selected language to `localStorage`
6. Ensure the app works correctly in all three languages

## Starting State

This branch contains a working React 19 + TypeScript app with:

- Three pages: Home (planner), Guides, Help
- Hardcoded English text in all components
- No i18n library installed
- No test infrastructure configured

## Hints

- Start by installing: `npm install i18next react-i18next`
- Create `src/i18n/` with an `index.ts` initializer and per-language locale files
- Use `useTranslation()` in components and `useLocalizedContent()` for structured data (destinations, FAQs, etc.)
- Destination data currently lives in `src/data/destinations.ts` — consider moving localized content into your locale files
- Test language switching by clicking the language toggle and verifying content changes

## Setup

```bash
npm install
npm run dev
```

## Verification

```bash
npm run lint
npm run build
```

Confirm:

- All three languages render correctly when selected
- Language choice persists across page reloads (`localStorage`)
- `<html lang>` attribute updates on language switch
- No English text remains hardcoded in component JSX (all strings come from translation keys)

## Deliverable

A working branch where the app renders in English, Lithuanian (`lt`), and Chinese (`zh`) with a visible language switcher.