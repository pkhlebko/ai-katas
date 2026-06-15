# CLAUDE.md — Kata 1: Legacy Modernization

This file provides guidance for the **Legacy Modernization kata**. The work happens in the **kelp404/angular-form-builder** repository, not in Northstar Travel.

## Commands (inside the cloned source repo)

```bash
npm install          # Install Node dependencies
grunt dev            # Start legacy Grunt dev server
bower install        # Install Bower front-end dependencies (if grunt dev fails)
```

## Architecture (Legacy Source)

**kelp404/angular-form-builder** — an AngularJS 1.x form builder circa 2015.

### Key files

- `Gruntfile.js` — build pipeline (Grunt tasks: concat, uglify, sass, watch)
- `bower.json` — front-end package manifest (AngularJS, jQuery, etc.)
- `package.json` — Node dev-tool dependencies (grunt-cli, grunt plugins)
- `src/js/` — Angular controllers, directives, services
- `src/scss/` — SASS stylesheets
- `index.html` / `demo/` — entry points and demo forms

### Build chain

Grunt → Bower → RequireJS. Node.js is only for the build tooling, not the runtime.

## Modernization Goals

1. Make the original AngularJS app run locally (fix legacy dependency issues)
2. Explore and document the existing form-builder behavior
3. Rewrite using a modern stack (React, Vue, or Angular 17+)
4. Add new controls and UX:
   - switch / toggle control
   - date picker control
   - dark theme
   - theme switcher

## AI Hints

- **Read `Gruntfile.js` first** before changing anything — understand the build pipeline before modifying it.
- **Check Node and npm versions** — this project predates Node 18+; some Grunt plugins may have compatibility issues.
- **Bower may need global install**: `npm install -g bower` then `bower install`.
- **Use the working app as a baseline** — make the original run first, then use its behavior as acceptance criteria for the rewrite.
- **Plan before coding** — ask AI to produce a migration plan (component mapping, data model, routing) before generating new code.
- **Preserve the core workflow** — drag-and-drop form building is the critical path; verify it works at each stage.
