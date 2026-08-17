# MCP App Submission Checklist

Use this before submitting the Partnership Leaders Research plugin to a public app or plugin directory.

## Build Items

- [x] Public-safe plugin wrapper directory exists.
- [x] Plugin manifest exists with an immutable kebab-case plugin name.
- [x] `.mcp.json` points at the Railway MCP endpoint and contains no secrets.
- [x] One to three PL skills are included under `skills/`.
- [x] README explains install, pilot, auth status, datasets, and tools.
- [x] MCP tools are read-only and annotated as read-only in the server.
- [x] Confirm `.mcp.json` points at the live production Railway MCP URL.
- [x] Confirm `GET /health` on the same host returns the expected dataset counts.
- [ ] Run the relevant platform validation command.
- [ ] Pilot with the relevant client development flow.
- [ ] Split or mirror the wrapper into a public GitHub repo.
- [ ] Decide final license string before public marketplace submission.
- [ ] Add final public repository URL to plugin docs, if desired.

## OAuth And Auth Items

- [ ] Register the reviewing client's callback URL in the auth layer.
- [ ] Confirm the auth layer supports OAuth 2.0 authorization code with PKCE S256.
- [ ] Confirm refresh tokens are issued and refresh works from the reviewing AI client.
- [ ] Confirm the server returns `401` or `403` for unauthenticated MCP calls.
- [ ] Confirm `/.well-known/oauth-protected-resource` returns the correct resource metadata.
- [ ] Confirm public connector users authenticate with OAuth, not shared `QUERY_API_KEY`.
- [ ] Validate every request server-side from the user token, not from plugin input.

## Tenant, Tier, And Data Security Items

- [ ] Create or verify partner user to tenant mapping.
- [ ] Enforce entitlement, tier, and allowed datasets on every MCP tool call.
- [ ] Enforce Postgres RLS keyed to authenticated tenant.
- [ ] Confirm no tool accepts `tenant_id` or tier as user-controlled input.
- [ ] Confirm downgraded, expired, or deleted users fail closed.
- [ ] Confirm service-role keys stay only in Railway environment variables.
- [ ] Confirm no tokens, secrets, partner rows, or Supabase keys appear in logs.
- [ ] If public self-serve is enabled, run and verify `database/auto_approve_mcp_signups.sql`.

## Reviewer Assets

- [ ] Public documentation URL.
- [ ] Privacy policy URL.
- [ ] Reviewer test account with known tenant and tier.
- [ ] Reviewer setup instructions.
- [ ] Test prompts that exercise each MCP tool.
- [ ] Support/contact route for marketplace review.
- [ ] Confirmation email includes the connector link and stale-auth note.

## Submission

- [ ] Run the relevant platform validation command.
- [ ] Submit through the reviewing platform's app or plugin submission flow.
- [ ] Pilot from the GitHub link while review and nightly catalog sync are pending.
