# Privacy Policy Draft For Partnership Leaders Research Plugin

This draft is a starting point for counsel and business-owner review before public submission.

## What The Plugin Does

The Partnership Leaders Research plugin lets an authenticated user query Partnership Leaders research through a hosted MCP server. The connected AI client sends the user's research request to the Partnership Leaders server, and the server returns only records the authenticated user is entitled to access.

## Data Processed

The plugin may process:

- The user's query text.
- MCP tool arguments generated from the user's request.
- Authentication tokens issued through the approved sign-in flow.
- Research records returned from the Partnership Leaders server.
- Operational metadata such as request time, endpoint, status code, and error state.

## Data Not Stored In The Plugin Repository

The public plugin repository does not contain:

- Supabase data.
- Partner records.
- Service-role keys.
- API keys.
- OAuth client secrets.
- Private server source code.

## Access Control

Access control is enforced by the hosted Partnership Leaders server and Supabase. The plugin does not decide tenant or tier access. The server validates the authenticated user and returns only permitted rows.

## Retention

Retention for server logs, research records, and authentication records is controlled by the Partnership Leaders Railway and Supabase environments. Final retention periods should be filled in before public marketplace submission.

## Third Parties

The plugin uses:

- The user's connected AI client.
- Railway for hosting the MCP/API server.
- Supabase for authentication and database services.

## User Choices

Users can disconnect or revoke plugin authentication through their AI client's MCP/plugin authentication controls. Partnership Leaders should also provide a support route for account removal or access questions before submission.

## Contact

Add the final Partnership Leaders privacy or support contact before submission.
