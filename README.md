# Kata 1: Legacy Modernization

> **Starting point branch.** This kata uses an external legacy repository — not the Northstar Travel app.

## Task

Start from an old AngularJS-based form builder and use AI assistance to understand, repair, and then fully modernize the application. The original project is intentionally dated and may not run successfully on the first attempt.

1. Download or clone the repository: [kelp404/angular-form-builder](https://github.com/kelp404/angular-form-builder)
2. Run `npm install`
3. Run `grunt dev`
4. Observe the failure and use AI assistance to make the existing solution work locally
5. Explore the current application behavior and architecture
6. Rewrite the whole solution using a modern stack
7. Add new controls and UX improvements:
   - switch / toggle control
   - date picker control
   - dark theme
   - theme switcher

## Starting State

External repo: [kelp404/angular-form-builder](https://github.com/kelp404/angular-form-builder)

The source project is an **AngularJS** form builder circa 2015:

- `src/js/` — Angular controllers, directives, and services
- `src/scss/` — SASS stylesheets
- `Gruntfile.js` — Grunt build configuration
- `bower.json` — Bower dependencies (legacy package manager)

The build chain uses **Grunt + Bower + RequireJS**.

## Hints

- Ask AI to explain the legacy build chain before changing it
- First make the original solution run; then use that behavior as the acceptance baseline
- Preserve the core form-builder workflow while modernizing the implementation
- When rewriting, ask AI to produce a migration plan before generating code

## Setup

```bash
git clone https://github.com/kelp404/angular-form-builder
cd angular-form-builder
npm install
grunt dev
```

## Useful Links

- Source repository: [kelp404/angular-form-builder](https://github.com/kelp404/angular-form-builder)
- Grunt documentation: https://gruntjs.com

## Verification

Once the original app runs:

- The form builder loads in the browser
- Drag-and-drop form building works
- Forms can be previewed

Once modernized:

- All original form-building behavior is preserved
- New controls are present: switch/toggle, date picker
- Dark theme is available with a theme switcher

## Deliverable

A modern form builder application that reproduces the important legacy behavior and adds the requested controls and theme switching.
