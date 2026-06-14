# Kata 6: MCP (Model Context Protocol)

> **Starting point branch.** No separate reference solution branch for this kata.

## Task

Configure MCP servers and implement a Jira feature using AI-assisted tooling.

You will:

1. Set up MCP server configurations for Jira and Confluence access
2. Read a Jira ticket describing a "Favorites" feature
3. Implement the feature described in the ticket
4. Verify the feature using the testing checklist
5. Publish release notes to Confluence

## Starting State

This branch has:

- The completed Northstar Travel app with i18n, tests, and skills
- `.mcp.json` with MCP server configurations (Jira, Confluence, Chrome DevTools)
- `KATA-INSTRUCTIONS.md` with detailed setup steps

## Setup

Follow the instructions in `KATA-INSTRUCTIONS.md` to:

1. Configure your `.mcp.json` with real Jira/Confluence tokens
2. Install required tools (Astral/uvx for mcp-atlassian)
3. Launch your AI agent (Claude Code / Cursor / Copilot)

## Hints

- The Jira ticket (`EPMGDLT-1565`) describes a "Save destination as favorite" feature
- Use the Chrome DevTools MCP to inspect the running app during development
- The feature should persist favorites in `localStorage`
- Language switching should not break the favorites state

## Testing Checklist

- [ ] Open the app
- [ ] Save a destination — button changes from **Save** to **Saved**
- [ ] Saved count appears/increments
- [ ] Reload the page — destination is still saved (`localStorage`)
- [ ] Switch language (English → Lithuanian or Chinese) — saved state persists, labels update
- [ ] Remove the favorite — count updates, `localStorage` changes
- [ ] Use chrome-devtools to inspect behavior

## Deliverable

Release notes published to Confluence at the specified location (see `KATA-INSTRUCTIONS.md`).