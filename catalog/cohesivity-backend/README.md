# Cohesivity Backend — Agentlas Plugin

Infra and on-the-fly backend for agentic tasks and projects by cohesivity.ai. Offers Postgres, hosting, storage, AI gateway, email inbox, and more through one API/MCP. No account or API key needed to get started.

## Quickstart

```bash
npx --yes @cohesivity/init@0.8.3
```

Creates an ephemeral tenant, writes credentials to `.cohesivity`, and installs the skill. Everything works immediately — no account, no signup. Tenants expire after 72 hours unless claimed.

## Pathways

### HTTP (default)

Bootstrap with `npx @cohesivity/init@0.8.3`, then use the management key from `.cohesivity` as a Bearer token for all API calls:

- `POST /api/resources/<name>` — provision a service
- `GET /api/resources` — list provisioned resources
- `GET /api/status` — tenant lifecycle, limits, notifications
- Deployment, env vars, and other operations per the live docs

### MCP

Cohesivity also offers local and remote MCP servers:

- **Local:** stdio server installed by `npx @cohesivity/init`, provides `create_tenant`, `claim_tenant`, `tenant_status`, `provision_resource`, `give_feedback`
- **Remote:** `https://cohesivity.ai/mcp/manage` — streamable HTTP with OAuth. Guest access auto-creates a 72h identity, no signup needed.

Both paths are documented in the skill.

## Skill

The full workflow — bootstrap precedence, provisioning, deploys, consent gates, lifecycle, billing — lives in the Cohesivity skill. This plugin pins `cohesivity-org/cohesivity-skill@13e0057` (skill version `39cad13754e6`). Latest is always at `https://cohesivity.ai/skill.md`; bumps come through a plugin update.

## Install

Listed on the Agentlas Hub. When a task needs a backend, `agentlas_resolve_plugins` returns this plugin with its install command; the user confirms the install.

## Requires

- Network access (HTTPS to `cohesivity.ai` and `*.cohesivity.app`)
- Node.js (for the one-time `npx` bootstrap)

## Links

- Cohesivity: https://cohesivity.ai
- Offerings: https://cohesivity.ai/llms.txt
- Skill (pinned): https://github.com/cohesivity-org/cohesivity-skill/blob/13e0057660bec1f133f59fa14ba4beb1c61a0839/cohesivity.skill.md
- Skill (latest): https://cohesivity.ai/skill.md
- Privacy: https://cohesivity.ai/privacy
- Terms: https://cohesivity.ai/terms
