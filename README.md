# LaunchBuddy agent toolkit

Help a builder turn a working product into one useful launch action.

Public documentation and ten portable skills for LaunchBuddy. Find practical resources, use free builder tools, or inspect a public launch gap. The service runs at [launchbuddy.com](https://launchbuddy.com); this repository contains no application backend, provider credentials, customer projects or billing implementation.

## Start with an outcome

Give your coding agent this request:

> Use INSTALL_FOR_AGENTS.md in https://github.com/msanchezgrice/launchbuddy-toolkit. I am building [product] and need help with [problem]. Find a useful LaunchBuddy resource or tool, help me take one next step, and explain what remains uncertain.

Explore [13 free builder tools](https://launchbuddy.com/tools), [guides and worksheets](https://launchbuddy.com/resources), or [run a public launch audit](https://launchbuddy.com/audit-my-launch) when a diagnostic would help.

## Choose your access path

- **Portable skills:** copy a selected directory from `skills/` into your agent's supported skills location. Start with `audit-my-launch`; other recipes are optional. A skill provides instructions; it does not itself connect an MCP server.
- **Remote MCP:** use `https://launchbuddy.com/api/mcp` in a client that supports Streamable HTTP. [Client instructions](https://launchbuddy.com/agents).
- **CLI / private continuity:** the verified npm package is `getlaunchbuddy`. Its browser-approved device connection is free. [Setup guide](INSTALL_FOR_AGENTS.md).
- **Downloads:** [skills page](https://launchbuddy.com/skills), [versioned packet manifest](https://launchbuddy.com/skills/packet.json), [ZIP](https://launchbuddy.com/downloads/audit-my-launch-skills.zip).

## Skills

| Skill | Outcome |
| --- | --- |
| audit-my-launch | Separate audit results, evidence and three next actions |
| fix-launch-gap | Scoped implementation and finding-specific recheck |
| launch-signup-check | Signup persistence, analytics event and founder notification proof |
| first-user-feedback | Interviews and real customer learning |
| launch-distribution | An audience-fit channel shortlist and reviewed launch material |
| launch-demo | An approved demo brief and production plan |
| launch-support | Approved-source replies and escalation checks |
| launchbuddy | Saved checklist, access state and approved asset handoff |
| launchready-audit | Technical audit and native Fix Pack v1 |
| agentready-audit | Agent-access audit and native Fix Pack v2 |

## Free and paid

Public diagnosis, resources and DIY recipes are free. Connect only when a specific task needs private project progress. Optional hosted work has separate eligibility, entitlement and approval checks. Read [accounts and costs](docs/accounts-and-costs.md); do not infer payment permission from installation.

The web and hosted skill packet is version 1.0.1. The CLI is published as [getlaunchbuddy 0.3.3](https://www.npmjs.com/package/getlaunchbuddy/v/0.3.3), including the ten skill modules. The installer adds the LaunchBuddy router and MCP bridge for Claude, Codex and Cursor; focused skills are available separately through the packet or this repository. The registry download was verified against the tested package, with isolated installation/reinstallation checks and anonymous live MCP discovery for each client configuration. This does not certify native agent sessions or marketplace approval. Native OAuth expansion, setup diagnostics and broader plugin bundles are roadmap work.

[Privacy and boundaries](docs/privacy.md) · [Resources and audit methods](docs/resources.md) · [Support](https://launchbuddy.com/contact)

## Verified client resource discovery

Claude Code, Codex CLI and Cursor CLI completed anonymous public-resource searches on November 5, 2026. See [scope and permission notes](docs/client-verification.md). Native marketplace approval and private/paid workflows require separate checks.
