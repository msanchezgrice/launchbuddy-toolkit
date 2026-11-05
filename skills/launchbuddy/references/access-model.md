# Access and handoff model

LaunchBuddy has four independent states:

1. **Installed** — the router skill and MCP bridge are available in the agent client.
2. **Identified** — a browser-approved device token connects the client to a Clerk account.
3. **Entitled** — a project capability policy decides which reads and writes are available.
4. **Paid** — Stripe webhook state grants paid creation, ongoing growth, and publishing capabilities.

Connecting never creates a checkout, subscription, provider job, or publish action.

| State | Available |
|---|---|
| Anonymous | Assess a public URL; read/share the report; receive up to three complete starter tasks |
| Connected free | Claim/save/list projects; complete durable checklist with owner/notes/status; asset brief + trial preflight; fresh reassessment |
| Agent asset trial | One exact recommended asset; one approval/render attempt within a durable cents budget; no full-kit kickoff, ongoing growth, or publish |
| Product trial | The existing broad web trial: time-limited create/refine and publish eligibility through explicit review; not a paid Stripe entitlement |
| Paid active | Create/refine through explicit review; ongoing managed work; publishing tools when enabled |
| Paid lapsed | Read prior work and reassess; paid writes return a restart handoff |

An anonymous `assess_launch` returns a high-entropy, expiring `claimToken` plus up to three useful starter tasks. After the free browser connection, `claim_assessment` consumes the token once and links the original scan to the Clerk account. Do not rescan merely to create a project. Connection is for checklist continuity, progress tracking, and later verification—not access to the first useful advice.

`preview_recommended_asset` resolves trial eligibility without provider spend. For an eligible account that has never paid and has not used an agent trial for the same account or registrable domain, the first approved `create_recommended_asset` starts the narrow one-asset trial and returns the exact proposal review URL. Opening the review costs $0, lands on that proposal card, and records the agent-to-workspace handoff; the first possible provider spend is a separate workspace approval. Otherwise, the paid handoff returns a stable intent id, exact offer, and web URL. Show that offer and obtain separate checkout approval before opening the browser handoff. The signed Stripe webhook changes capabilities, and `get_action_intent` reconciles the same intent into a reviewable proposal; no reinstall, reconnect, or second asset approval is required.

Connected plan and checklist responses end with structured **Start #1**, **Make #1**, and **Not now** choices. Reassessment responses lead with score delta, verified wins, added gaps, and remaining gaps. A previously open task whose gap disappears is closed automatically as a scan-verified win; the full checklist remains available but does not need to be repeated after every refresh.
