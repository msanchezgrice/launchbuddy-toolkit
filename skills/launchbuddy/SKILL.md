---
name: launchbuddy
description: Assess launch readiness from a public URL, identify evidence-backed launch gaps, create a ranked growth plan, preview the highest-leverage recommended asset, and route explicitly approved entitled execution through LaunchBuddy. Use when someone asks what is blocking a launch, what to do next, how to improve launch readiness, or asks for launch assets such as landing pages, ads, social cards, GTM copy, blog content, or demo creative.
---

# LaunchBuddy

Answer one vertical question: **What is blocking this launch, what should happen next, and can LaunchBuddy make it?**

Use the LaunchBuddy MCP tools for durable assessment, project, plan, access, and asset state. Inspect the local repository only when it adds useful implementation context; scans, identity, billing, generation, approvals, and persistence remain hosted in LaunchBuddy.

Resolve private state before acting:

- Use `list_projects` after connection and whenever the exact `projectId` is unknown. Match the assessed URL; if multiple projects could match, ask rather than guessing.
- Use `get_access` with the exact `projectId` before presenting checkout or answering subscription, trial, entitlement, or publishing questions.
- Use `get_assessment` when a `scanId` is already available. Use `assess_launch` for a new URL and `reassess_launch` for a connected project's refresh so the result stays on the same project.
- Treat `report.topGaps[0].finding` as the strongest evidence unless the response explicitly identifies stronger evidence.

## Audit my launch and resources

For a combined public-site audit, call `audit_my_launch` with the URL and the user's selected checks. Preserve its native fix packs, show separate scores and unavailable checks, and use the matching resources for one scoped next action. After the change is live, call `verify_launch_audit` with the original audit. Use `search_launch_resources` and `get_launch_resource` for additional guides, skills, and Swarm channels. Channel entries are leads, not submission or publication proof.

The current skills packet is available at https://launchbuddy.com/skills and includes signup proof, first-user feedback, distribution, creative, and support recipes. Do not install the unrelated npm package named `agentready`.

## Route the request

1. If no assessment exists, call `assess_launch` with the public launch URL.
2. Report the score, primary gap, strongest evidence, and report URL. Then render every returned `starterTodo` (up to three) as a checkbox with its title, evidence/finding, action, `doneWhen`, and `recommendedAsset`. Do not compress the checklist into one prose recommendation.
3. Plans and assets require an exact `projectId`.
   - If the assessment returned one, continue with it and call `create_growth_plan`.
   - If the assessment was anonymous, preserve its returned `claimToken`. Say: “Save this checklist and track progress for free: run `npx getlaunchbuddy connect`. Connecting does not start checkout or a trial.” After connection, call `claim_assessment` with that token to save the original assessment without scanning again or starting a trial.
   - Never call a project tool with a guessed or missing `projectId`.
4. Present every todo returned by `create_growth_plan` as a checkbox; include `id`, status, owner, evidence/finding, action, `doneWhen`, and the LaunchBuddy-buildable asset. Never collapse the first full connected checklist into a summary sentence. Use `get_launch_todos` to resume it later. Call `update_launch_todo` only when the user asks to change a task's owner, note, or status. Completed tasks remain pending verification until a fresh reassessment removes the gap.
5. After `create_growth_plan` or `get_launch_todos`, render the returned `nextActions` as an explicit close:
   - **Start #1** — call the returned `update_launch_todo` tool/arguments only if the user chooses it.
   - **Make #1** — call the returned `preview_recommended_asset` tool/arguments only if the user chooses it. This is still a $0, no-provider-spend preview.
   - **Not now** — make no mutation. Confirm that the checklist stays saved.
6. For an asset request, call `preview_recommended_asset` and show the exact title, brief, evidence, expected impact, and `trialOffer`. If eligible, state price `$0`, that the trial starts after create approval, and that provider spend starts only after separate workspace approval.
7. Obtain approval after showing that preview. A request made before the preview, including “make the top asset,” does not approve an asset the user has not yet seen.
8. Before presenting checkout, call `get_access(projectId)`. If the user says they already pay, do not recommend checkout until the connected identity and exact project report `paid_active`. If state disagrees, show the connected account/project state, resolve the mismatch, and fail closed.
9. After asset approval, call `create_recommended_asset`. The call is non-charging and creates or resumes a review intent; it does not render or publish. For `payment_required`, show the exact returned offer, obtain separate checkout approval, and only then open the returned URL. For `approval_required`, present the exact returned workspace URL. Explain that it opens the proposed card directly, opening the review costs `$0`, and provider work starts only after the user approves that exact card.
10. After a checkout or workspace handoff, poll `get_action_intent` to report entitlement, approval, render, and verification state. A signed Stripe webhook is authoritative; polling reconciles newly active access into the same intent. Do not infer completion from the browser redirect.
11. Asset creation approval and publication approval are separate. This MCP version exposes no publish tool. Do not deploy code, push Git, call provider APIs, or use browser automation to publish. Route the user to the workspace and explicitly state that nothing has been published unless `get_action_intent` reports verified publication.
12. After changes ship, call `reassess_launch` with the exact `projectId`. Present the result diff-first: score delta, `changes.verifiedWins`, `changes.added`, then `changes.remaining`. A previously open gap that disappears is automatically completed and verified with `completionSource: reassessment`. Do not repeat the full checklist on every reassessment unless the user asks. Close with the returned **Start #1 / Make #1 / Not now** actions.

## Checklist presentation

Use this shape for each task:

```text
[ ] 1. Add an actionable conversion CTA — High impact
    ID: todo_conversion_path
    Evidence: No signup, trial, or lead-capture action was detected.
    Do: Add one primary and one secondary CTA above the fold.
    Done when: The fix is live and a fresh reassessment no longer flags this gap.
    LaunchBuddy can make: Hero + CTA copy pack
```

Use `[~]` for `in_progress` and `[x]` for `completed`. State whether a completed task is pending reassessment, still detected, or verified.

For reassessment, use a compact change-first shape:

```text
Score: 72/100 (+14)
Verified wins: Conversion CTA
New gaps: none
Still blocking launch: Credible social proof

Choose: Start #1 · Make #1 · Not now
```

## Safety and commercial boundary

- Anonymous assessment and public reports are free.
- Connected identity unlocks project continuity, the complete durable checklist, owner/note/status updates, preview, and reassessment.
- Identity is not a subscription. Connecting, claiming, planning, and previewing never start a trial.
- The first explicitly approved `create_recommended_asset` may grant an eligible never-paid account a one-time agent trial. It is bound to that exact recommended asset, one approval, one render attempt, and a durable provider budget. It does not unlock full-kit generation, ongoing growth, or publishing.
- The existing broad web product trial remains separate from this one-asset agent trial; neither is a Stripe entitlement.
- Existing paid users retain their entitlement after connection and must not be sent through a second checkout.
- Lapsed users remain connected and can read prior work and reassess; only paid writes are gated.
- Never auto-charge, start provider spend, publish, or make an external mutation from an assessment or preview.
- A `payment_required` response is a resumable intent, not permission to purchase.
- Asset approval permits the non-charging intent call; checkout still requires separate approval after the exact offer is shown.
- A `payment_required` result is not proof that an existing user must repurchase. Verify access for the exact connected project first.
- Capability flags describe entitlement; they do not prove that a corresponding MCP operation is exposed. Publishing is workspace-only in this version.

See [references/access-model.md](references/access-model.md) when the user asks how identity, trials, subscriptions, or the agent-to-web handoff work.

## Common requests

- “Assess `https://example.com` before I launch.” → `assess_launch`
- “Save the assessment I ran before connecting.” → `claim_assessment`
- “What should I do next?” → `create_growth_plan`
- “Show my launch checklist.” → `get_launch_todos`
- “Mark `todo_conversion_path` complete.” → `update_launch_todo`, then recommend a fresh reassessment after the fix is live
- “Make the top recommended asset.” → `preview_recommended_asset`, obtain approval, then `create_recommended_asset`
- “Did the work improve my launch?” → `reassess_launch` and report its before/after comparison
