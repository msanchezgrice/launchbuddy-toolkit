# Client verification — November 5, 2026

The published getlaunchbuddy 0.3.3 installer output was tested in clean project configurations using the actual Claude Code, Codex CLI and Cursor CLI. Each client read the LaunchBuddy skill and successfully called the hosted `search_launch_resources` tool for first-user feedback. The client sessions returned public LaunchBuddy resource URLs. Cursor's skill read and successful search were checked in separate sessions.

These were anonymous public-resource checks through a local bridge that added explicit QA markers. They do not certify editor GUI sessions, native marketplace approval, private account access, checkout or paid execution.

The normal interactive client should ask before a tool needs approval. A headless client configured to never ask can reject an otherwise healthy connection. Scope any approved automation to the exact public tool needed; keep private writes and other tools under their normal approval rules.

For isolated Cursor CLI QA, the project-level `.cursor/cli.json` permitted only `Mcp(launchbuddy:search_launch_resources)`. For isolated Codex QA, the process enabled only `search_launch_resources` and set that tool's approval mode to `approve`. User-wide approval settings and unrelated server settings were preserved. Initial permission failures and temporary provider connection stalls were resolved before successful readback.

References: [Cursor CLI permissions](https://cursor.com/docs/cli/reference/permissions), [Codex configuration](https://developers.openai.com/codex/config-reference/).

## Registry maintenance

`server.json` advertises the LaunchBuddy hosted endpoint. Maintainers can run the manual **Publish LaunchBuddy MCP** workflow using GitHub OIDC, following the [Official Registry workflow](https://modelcontextprotocol.io/registry/github-actions). The publisher release and checksum are pinned. The job requests a temporary GitHub identity and read access to this repository; it requires no stored publication secret.

Registry acceptance, catalogue approval and successful use remain separate claims. Check the public record after the job completes.
