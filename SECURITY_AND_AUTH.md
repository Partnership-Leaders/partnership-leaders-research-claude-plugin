# Security And Auth Notes

This plugin wrapper is public-safe. The backend uses per-user OAuth through Supabase Auth, then the Railway MCP server checks the verified user against server-side entitlements before returning research data.

## Current Server State

The Railway MCP server supports Claude connector OAuth. Internal API-key routes may still exist for controlled backend/testing use, but public connector users should authenticate through the Supabase OAuth flow.

For public Claude connector users, the intended path is:

```text
Claude -> OAuth authorization flow -> Supabase Auth -> Railway MCP server -> entitlement lookup -> Supabase RLS
```

## Production Behavior

- Unauthenticated MCP requests return `401` or `403`.
- OAuth sign-in is per user.
- The callback URL `https://claude.ai/api/mcp/auth_callback` is registered.
- Authorization code flow uses PKCE S256.
- Refresh tokens are supported.
- The Railway server verifies each access token on every request.
- Entitlement, tier, and allowed datasets are derived from server-side lookup.
- Tool input never includes trusted tenant or tier values.
- Supabase RLS restricts rows to entitled users.
- Self-serve users can receive the public entitlement after email verification when `database/auto_approve_mcp_signups.sql` is installed.

## Fallback If Supabase Auth Stops Meeting Client Requirements

Add a thin Railway auth shim that:

1. Presents Claude-compatible authorization metadata.
2. Handles authorization-code + PKCE.
3. Delegates user login to Supabase Auth.
4. Issues/refreshes tokens Claude can store.
5. Maps tokens to Supabase user, tenant, and tier.
6. Injects only server-verified context into database queries.

Do not put OAuth client secrets, service-role keys, or refresh tokens in the plugin repo.
