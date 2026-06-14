# Kata 2: Internationalization

> **Reference solution branch.** For the starting point, checkout `kata-2-start`.

This branch contains the completed internationalization implementation for the Northstar Travel app.

## What was implemented

- `i18next` and `react-i18next` configured with language detection and `localStorage` persistence
- Three locale files: English (`en`), Lithuanian (`lt`), Mandarin Chinese (`zh`)
- `useLocalizedContent()` hook for typed access to structured content (destinations, FAQs, guides)
- Language switcher component persisting choice across sessions
- All hardcoded English text replaced with translation keys

## Quick Start

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