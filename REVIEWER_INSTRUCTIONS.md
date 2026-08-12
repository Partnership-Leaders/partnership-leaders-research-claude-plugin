# Reviewer Instructions

Use these instructions for Anthropic review or an external pilot reviewer.

## Connector

Connector name:

```text
Partnership Leaders Research
```

Connector URL:

```text
https://si-research-dashboard-production-25d8.up.railway.app/mcp
```

Direct Claude connector link:

```text
https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Partnership%20Leaders%20Research&connectorUrl=https%3A%2F%2Fsi-research-dashboard-production-25d8.up.railway.app%2Fmcp
```

## Test Account

Provide the reviewer with a real email/password account that has verified email and an active `pl_user_entitlements` row.

```text
Reviewer email: <fill in before submission>
Temporary password: <share securely, not in GitHub>
Tier: public
Datasets: insight_si, ec75, aip
```

Do not commit real reviewer passwords or secrets.

## Setup Steps

1. Open the direct Claude connector link.
2. Click Add.
3. Click Connect.
4. Sign in with the reviewer account.
5. Approve the requested access.
6. Ask Claude to use Partnership Leaders Research.

If the auth page says `authorization not found`, reopen the direct Claude connector link and click Connect again. The prior Claude authorization request expired.

## Test Prompts

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

```text
Use Partnership Leaders Research to answer:
What should a Head of Ecosystems watch from recent AI partnership moves?
Do not provide a news list. Give the executive judgment and explain what action to take.
```

## Expected Behavior

- Claude should call read-only MCP tools.
- The server should require authenticated access.
- The answer should be grounded in returned research evidence.
- The answer should be written for a senior partnership leader, not as a generic news summary.
- The answer should avoid exposing internal dataset/process labels unless specifically asked for testing or admin context.

