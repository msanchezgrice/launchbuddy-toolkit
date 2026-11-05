# LaunchBuddy agent toolkit

Help a builder turn a working product into one useful launch action.

Public documentation and ten portable skills for LaunchBuddy, LaunchReady and AgentReady. The service runs at [launchbuddy.com](https://launchbuddy.com); this repository contains no application backend, provider credentials, customer projects or billing implementation.

## Start with an outcome

Give your coding agent this request:

> Set up LaunchBuddy using INSTALL_FOR_AGENTS.md in https://github.com/msanchezgrice/launchbuddy-toolkit. Audit my public product URL, show three evidence-backed next actions, help me do one, and verify the change. Ask before any paid or external action.

Or [run the free web audit](https://launchbuddy.com/audit-my-launch).

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

Public diagnosis, resources and DIY recipes are free. A free connected identity saves the original LaunchBuddy assessment and project progress. Hosted asset work has separate eligibility, entitlement and approval checks. Read [accounts and costs](docs/accounts-and-costs.md); do not infer payment permission from installation.

The web and hosted skill release is live. The CLI source update to 0.3.3 is awaiting npm publication; the current packet is available independently. No marketplace listing or native-client certification is implied by this repository. The current supported endpoint and web export path work independently of catalogue acceptance. Native OAuth expansion, setup diagnostics and broader plugin bundles are roadmap work.

[Privacy and boundaries](docs/privacy.md) · [Resources and audit methods](docs/resources.md) · [Support](https://launchbuddy.com/contact)
