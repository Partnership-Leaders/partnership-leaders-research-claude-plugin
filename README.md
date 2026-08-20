# Partnership Leaders Research MCP App

This MCP app points supported AI clients at the Partnership Leaders hosted MCP research server and adds PL-specific skills for source-grounded partner ecosystem research.

The plugin repository is safe to make public because it contains only:

- plugin manifest
- `.mcp.json` with the public Railway MCP endpoint
- skills and documentation

It must not contain server source code, Supabase data, service-role keys, API keys, OAuth client secrets, or partner records.

## Included

- MCP server: `https://partnership-leaders-research.up.railway.app/mcp`
- Skills:
  - `pl-research-answering`
  - `pl-partner-ecosystem-scan`
  - `pl-source-grounded-brief`

## Local Testing

Validate the wrapper with the relevant client CLI before submitting to a directory or marketplace. For platform-specific validation commands, use the internal submission checklist or the reviewing platform's docs.

Approve the plugin-provided MCP server if prompted, then authenticate if the server requests sign-in.

## Pilot Install From GitHub

After this directory is split or mirrored into a public GitHub wrapper repo, pilot users can install from that repo when their client supports direct MCP app installation.

Example:

```text
Install from the public wrapper repo URL supplied by Partnership Leaders.
```

If the production Railway URL changes, update `.mcp.json` before validation, pilot, or submission.

## Authentication Status

The production flow is per-user OAuth:

```text
AI client user -> Supabase Auth consent -> Railway MCP server -> entitlement gate -> Supabase Postgres RLS
```

Current repo status:

- The public plugin wrapper is scaffolded.
- The MCP endpoint exists.
- The MCP tools are read-only and annotated as read-only.
- Supabase OAuth sign-in works with supported MCP clients.
- Self-serve email verification can auto-create public-preview MCP entitlements through `database/auto_approve_mcp_signups.sql`.

Before public submission, confirm `SUBMISSION_CHECKLIST.md`, `REVIEWER_INSTRUCTIONS.md`, and `PRIVACY.md` have final public URLs and support contacts.

## Self-Serve Connector

Users can add the live MCP server when their AI client supports custom MCP apps or connectors:

```text
https://partnership-leaders-research.up.railway.app/mcp
```

Expected user flow:

1. Add the MCP server URL in the AI client.
2. Click Add, then Connect.
3. Create an account or sign in.
4. Verify email if prompted.
5. Return to the connector and click Connect again if the original authorization page expired.
6. Approve access.
7. Ask the AI client to use Partnership Leaders Research.

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
