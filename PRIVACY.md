# Privacy Policy For Partnership Leaders Research Plugin

Last updated: September 24, 2026

## What The Plugin Does

The Partnership Leaders Research plugin lets a user query Partnership Leaders research through a hosted MCP server. The connected AI client sends the user's research request to the Partnership Leaders server, and the server returns research results from the Partnership Leaders database.

The plugin is read-only. It does not modify customer systems or write back to the connected AI client.

## Data Processed

The plugin may process:

- The user's query text.
- MCP tool arguments generated from the user's request.
- Authentication tokens issued through the approved sign-in flow.
- Research records returned from the Partnership Leaders server.
- Limited operational metadata such as request time, MCP client platform, tool name, endpoint, status code, and error state.

## Query Analytics

Partnership Leaders may store limited query analytics to understand usage, improve research coverage, debug errors, and prioritize future research topics. Query analytics are limited to the user question, the MCP tool called, the client platform when available, timestamps, and request status metadata.

Query analytics are retained for up to 24 months, unless a longer period is required for security, abuse prevention, legal, or compliance purposes. Partnership Leaders may also retain aggregated or de-identified analytics after that period.

## Evaluation Tooling

The hosted server includes internal evaluation routes used by Partnership Leaders for quality assurance and testing. These evaluation routes are not exposed as public MCP tools.

When the optional `evaluate_research_answer` workflow is used internally and an evaluation model is configured, Partnership Leaders may send the evaluation prompt, candidate answer, rubric, and supporting evidence to OpenAI for LLM-judge scoring. This OpenAI LLM-judge is optional and is used for internal answer-quality evaluation, not for normal end-user research queries.

## Data Not Stored In The Plugin Repository

The public plugin repository does not contain:

- Supabase data.
- Partner records.
- Service-role keys.
- API keys.
- OAuth client secrets.
- Private server source code.

The MIT license in this repository applies to the plugin wrapper files and related documentation only. It does not grant rights to Partnership Leaders trademarks, logos, private research content, databases, or other proprietary materials.

## Access Control

Access control is enforced by the hosted Partnership Leaders server and Supabase. The plugin does not decide tenant or tier access. The server validates the authenticated user and returns only permitted rows.

Authentication records are retained while the user's account remains active and for a reasonable period afterward for security, audit, account recovery, and abuse-prevention purposes.

## Third Parties

The plugin uses:

- The user's selected AI client, such as Claude or ChatGPT/OpenAI, as an independent platform chosen by the user or the user's organization.
- Railway for hosting the MCP/API server.
- Supabase for authentication and database services.
- OpenAI, only when the optional internal LLM-judge evaluation workflow is configured and used.

## User Choices

Users can disconnect or revoke plugin authentication through their AI client's MCP/plugin authentication controls. Users may also request account removal or access help by contacting Partnership Leaders.

## Contact

For privacy, support, or account questions, contact Partnership Leaders at marketing@partnershipleaders.com.
