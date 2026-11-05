# Choose a resource for the actual gap

The complete searchable library is at https://launchbuddy.com/resources. Public metadata is available at https://launchbuddy.com/api/launch-resources. Use `search_launch_resources` and `get_launch_resource` from the MCP for the same reference index.

LaunchBuddy covers growth, feedback, page clarity, creative and customer support. LaunchReady covers technical launch checks and remediation recipes. AgentReady covers agent discovery, access, operability and machine-readable contracts. Swarm supplies launch-channel discovery and availability metadata.

Keep the originating resource's canonical URL, method, native finding ID and pack version. Recommend a few relevant resources per gap, explaining the action and the evidence needed to finish. A catalogue channel is a discovery lead, not proof that an agent can submit, that a product is eligible, or that a listing is live.

For a technical audit alone, use LaunchReady's `scan_launch_readiness` and preserve Fix Pack v1 for `verify_launch_fixes`. For an agent audit alone, `scan_url` already includes Fix Pack v2; immediately calling `get_fix_pack` would scan again. Preserve that pack for `verify_fixes`.

The public AgentReady companion is https://github.com/msanchezgrice/agentready-tools. Its hosted MCP is https://www.agentready.me/api/mcp; do not substitute the unrelated npm package named `agentready`.
