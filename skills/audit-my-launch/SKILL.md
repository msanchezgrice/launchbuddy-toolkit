---
name: audit-my-launch
description: Audit a public launch URL with LaunchBuddy, LaunchReady, and AgentReady, match gaps to resources, and choose the next useful action.
---

# Audit my launch

Use the LaunchBuddy MCP at https://launchbuddy.com/api/mcp. Call `audit_my_launch` with the public `url`; optionally select `checks` from `launch`, `technical`, and `agents`. Use the requested scope rather than expanding every audit by default.

Retain the returned JSON and native fix packs. Present the status of every requested check, separate scores, evidence, next actions, and matching resources. An unavailable result is unknown. Do not average scores or infer demand from a scan.

Select one applicable task with the user or follow their already-stated priority. Resolve candidate paths against the authorized repository, implement the scoped change, and run its checks. After an authorized deployment, call `verify_launch_audit` with the same URL and `previous_audit`. Report resolved, remaining, introduced, and unobservable findings separately.

Use `search_launch_resources` to find a missing guide, skill, or launch channel and `get_launch_resource` to read an exact resource ID. Reuse an existing assessment rather than immediately scanning again.

Public scans do not prove real analytics events, inbox delivery, private task success, customer willingness to pay, or application security. Finish with the next useful conversation, first-value test, or distribution action. Connection, code changes, and external actions follow existing user authorization; the audit itself grants none.

References: https://launchbuddy.com/agents and https://launchbuddy.com/resources.

## Save without rescanning

If the combined result includes `continuation`, keep its expiring claim token private in this agent session. After the person connects, call `claim_assessment` with that token to save the original launch assessment. Do not put the token in a public report, shared export, URL, or log. Connecting does not start a trial or checkout.
