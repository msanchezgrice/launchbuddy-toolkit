# Set up LaunchBuddy for a useful first task

Use this guide when the person has asked you to set up LaunchBuddy. Reading a linked document alone does not authorize software installation, account connection, spending, deployment, sending or publication. Follow the person's existing permissions and repository rules.

## 1. Choose the smallest supported setup

If LaunchBuddy tools are already available, reuse them. Do not overwrite existing client settings or add a duplicate server. Confirm `audit_my_launch` is visible before promising the combined workflow.

For a client with remote Streamable HTTP support, add `https://launchbuddy.com/api/mcp` through its documented connection flow. Public audit and resource tools require no account. Claude Code users can run:

```sh
claude mcp add --transport http launchbuddy https://launchbuddy.com/api/mcp
```

For a client without remote MCP, use the [web audit](https://launchbuddy.com/audit-my-launch), download its report and native JSON, and continue from that evidence. Do not claim the client can call tools until its connection works.

## 2. Load the task instructions

Use the `audit-my-launch` folder in this repository, or download the [skills packet](https://launchbuddy.com/downloads/audit-my-launch-skills.zip). Review it and copy only selected skill folders to the directory documented by the person's client. Keep accompanying reference files. Do not edit global approval policies, enable blanket auto-approval, or change unrelated servers.

The published LaunchBuddy installer is `npx getlaunchbuddy install --all`. It installs the router skill and bridge for Claude, Codex and Cursor and changes all three client configurations. Explain that scope before using it; prefer the selected skill and direct remote connection when that is sufficient. Installing the router is distinct from installing every focused recipe in this repository.

Do not install the unrelated unscoped npm package `agentready`. AgentReady's supported hosted endpoint is `https://www.agentready.me/api/mcp` and its public skill is linked in the packet.

## 3. Complete the first useful action

Ask for a public product URL if none was supplied. Call `audit_my_launch` with the requested checks, or all three if the person requested the whole launch. Present separate scores, unavailable checks, evidence and three next actions. Do not average the scores or treat a scan as proof of customer demand.

Keep the original JSON and native packs so `verify_launch_audit` can check the same findings after an authorized change is live. A failed phase remains unknown. Select one task and give a matching resource plus a completion check. Installation alone is not the success condition.

## 4. Connect only for private progress

When the person wants a saved project or private work, use the existing free browser-approved device flow:

```sh
npx getlaunchbuddy connect
```

The person completes sign-in and approves their own connection. Keep the original assessment's expiring claim token private in this session. After connection, use `claim_assessment`; do not create a second scan just to save progress. Tokens never belong in shared reports, URLs, screenshots, public issues or logs.

Connection does not start checkout, a subscription or a trial. Native private MCP OAuth in every client is not yet promised; the CLI bridge is the existing authenticated path.

## 5. Finish with a clear state

Report: available tools, whether the audit completed, the chosen next action, what remains unknown, and whether anything was saved. Use `get_access` with the exact project before any commercial handoff. Preview first; explicit work approval, provider execution, checkout and publication are separate actions. This MCP exposes no publication tool.
