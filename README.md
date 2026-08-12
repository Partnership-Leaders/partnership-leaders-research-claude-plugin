# Partnership Leaders Research Claude Plugin

This Claude plugin points Claude at the Partnership Leaders hosted MCP research server and adds PL-specific skills for source-grounded partner ecosystem research.

The plugin repository is safe to make public because it contains only:

- `.claude-plugin/plugin.json`
- `.mcp.json` with the public Railway MCP endpoint
- Claude skills and documentation

It must not contain server source code, Supabase data, service-role keys, API keys, OAuth client secrets, or partner records.

## Included

- MCP server: `https://si-research-dashboard-production-25d8.up.railway.app/mcp`
- Skills:
  - `pl-research-answering`
  - `pl-partner-ecosystem-scan`
  - `pl-source-grounded-brief`

## Local Testing

From the root of the `si-research-dashboard` repo:

```bash
claude plugin validate ./claude-plugin
claude --plugin-dir ./claude-plugin
```

Inside Claude Code:

```text
/plugin
/mcp
```

Approve the plugin-provided MCP server if prompted, then authenticate if the server requests sign-in.

## Pilot Install From GitHub

After this directory is split or mirrored into a public GitHub plugin repo, pilot users can install from that repo while marketplace review is in flight.

Example:

```bash
claude plugin install github:YOUR_ORG/YOUR_PLUGIN_REPO
```

Replace `YOUR_ORG/YOUR_PLUGIN_REPO` with the public wrapper repo.

If the production Railway URL changes, update `.mcp.json` before validation, pilot, or submission.

## Authentication Status

The production flow is per-user OAuth:

```text
Claude user -> Supabase Auth consent -> Railway MCP server -> entitlement gate -> Supabase Postgres RLS
```

Current repo status:

- The public plugin wrapper is scaffolded.
- The MCP endpoint exists.
- The MCP tools are read-only and annotated as read-only.
- Supabase OAuth sign-in works with the Claude custom connector.
- Self-serve email verification can auto-create public-preview MCP entitlements through `database/auto_approve_mcp_signups.sql`.

Before Anthropic submission, confirm `SUBMISSION_CHECKLIST.md`, `REVIEWER_INSTRUCTIONS.md`, and `PRIVACY.md` have final public URLs and support contacts.

## Self-Serve Claude Connector

Users can add the live connector directly:

```text
https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Partnership%20Leaders%20Research&connectorUrl=https%3A%2F%2Fsi-research-dashboard-production-25d8.up.railway.app%2Fmcp
```

Expected user flow:

1. Open the connector link in Claude.
2. Click Add, then Connect.
3. Create an account or sign in.
4. Verify email if prompted.
5. Return to the connector link and click Connect again if the original authorization page expired.
6. Approve access.
7. Ask Claude to use Partnership Leaders Research.

## Datasets

- `insight_si`: systems integrator and consulting ecosystem signals.
- `ec75`: ecosystem-company and partner-tech signals.
- `aip`: AI-in-partnerships signals, including AI partner programs, partner-facing AI, AI marketplaces, frontier AI partnerships, and partner AI upskilling.

## Tooling

The hosted MCP server exposes:

- `search_findings`
- `answer_research_question`
- `get_finding`
- `list_companies`
- `list_tags`
- `list_events`
- `evaluate_research_answer`
- `answer_and_evaluate_research_question`

## Example Prompts

```text
Use Partnership Leaders Research to answer:
How are AI partner programs becoming harder or more selective for partners?
Lead with the judgment, name the companies driving the pattern, include dates and figures only when supported, and close with one action a Head of Partnerships should take.
```

```text
Use Partnership Leaders Research to answer:
Which ecosystem companies are changing partner incentives or marketplace routes in ways a VP of Partnerships should act on?
Name the companies, avoid unsupported superlatives, and close with a specific next step.
```
