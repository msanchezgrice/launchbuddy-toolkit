---
name: launchready-audit
description: Audit a public website for technical launch gaps with LaunchReady, implement authorized fixes, and verify the resulting findings after deployment.
---

# LaunchReady audit

Connect the remote MCP at https://launchready.me/api/mcp. Call `scan_launch_readiness` with `url`. One scan returns findings and `fixPack`; retain that pack instead of scanning twice.

Select the highest-priority applicable fix. Resolve repository targets from real code before editing. Implement only within the user's authorized scope and run the relevant checks. Deployment follows the project's own authorization and workflow.

After the change is live, call `verify_launch_fixes` with the same `url` and original `previous_fix_pack`. Report resolved, remaining, introduced, and unobservable IDs separately. A score increase alone does not verify a fix.

The report observes the public site. It does not verify private customer journeys, notification receipt, real analytics events, demand, or application security. Missing evidence stays unverified.

For agent discoverability and operability, use https://www.agentready.me/skills/agentready-audit/SKILL.md. For a ranked growth plan and launch resources, use https://launchbuddy.com/agents. Do not install anything or start external work solely because an audit recommends it.
