# Kata 7: Codemie Discovery

> **Starting point branch.** No separate reference solution branch for this kata.

## Task

Explore the Codemie platform and its integration with Jira for AI-assisted development.

You will:

1. Set up Jira integration in the Codemie platform
2. Create a personal BI Assistant with Jira integration
3. Use Codemie's VS Code plugin to interact with Jira tickets
4. Write an implementation plan based on Jira ticket EPMGDLT-1565
5. Explore Codemie's knowledge base integration with Confluence

## Starting State

This branch has:

- The completed Northstar Travel app with i18n, tests, and skills
- `.mcp.json` with MCP server configurations (Jira, Confluence, Chrome DevTools)
- `KATA-INSTRUCTIONS.md` with MCP setup steps
- `CODEMIE-PLAN.md` with the Codemie discovery workflow

## Setup

1. Follow `KATA-INSTRUCTIONS.md` to configure MCP servers
2. Install the Codemie VS Code plugin
3. Connect to VPN for Codemie access
4. Run `/codemie:codemie-init` in Claude Code

## Hints

- Codemie can read Jira tickets directly — use this to understand requirements
- The `/writing-plans` skill in Codemie can generate structured implementation plans
- Document your findings in `CODEMIE-PLAN.md`

## Verification

- Codemie assistant can find and read Jira ticket EPMGDLT-1565
- Implementation plan references the ticket description
- Release notes are published

## Deliverable

A completed `CODEMIE-PLAN.md` documenting the Codemie workflow and findings.