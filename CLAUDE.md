# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev          # Start Vite dev server
npm run build        # TypeScript check + production build
npm run lint         # ESLint
```

## Architecture

**Northstar Travel** — a React 19 + TypeScript travel planning SPA.

### Key layers

**Pages** (`src/pages/`) — Three routes via React Router 7:

- `/` — `HomePage`: stateful page managing destination selection, booking form fields, validation, and summary display
- `/guides` — `GuidesPage`
- `/help` — `HelpPage`

**Components** (`src/components/`) — UI components with hardcoded English text:

- `BookingForm.tsx`, `BookingSummary.tsx`, `DestinationCard.tsx`
- `FaqList.tsx`, `Hero.tsx`, `HeroVisual.tsx`
- `SiteHeader.tsx`, `TripFilters.tsx`

**Data** (`src/data/`) — Static data files:

- `destinations.ts`: destination array and `Destination`/`TravelPace` types
- `faqs.ts`: FAQ entries

All UI text is currently hardcoded in English. This is the starting state for the Internationalization kata.