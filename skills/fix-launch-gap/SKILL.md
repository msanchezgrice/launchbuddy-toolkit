---
name: fix-launch-gap
description: Implement one observed launch gap in an authorized repository and verify the original finding after deployment.
---

# Fix launch gap

Start from an actual audit finding, its evidence, origin, stable ID, and native fix pack. If no finding exists, run `audit_my_launch`; do not invent a result.

Check that the issue applies to the actual repository. Find the real target files; conventional candidate paths are leads. Identify the smallest change and an observable acceptance check. Preserve unrelated user work and follow the repository's instructions.

Implement within existing authorization, then run relevant checks. Distinguish implementation, local testing, deployment, and live verification. Do not require another approval for work already authorized; request missing authorization only at the relevant boundary.

After deployment, call `verify_launch_audit` with the saved audit, or use the originating server's verifier with its unchanged native fix pack. Score movement is secondary. If a phase is blocked or unavailable, keep the finding unobservable.

Return the finding, changed files, check results, live evidence when available, remaining work, and the next useful customer-facing action. A recommendation to publish, spend, or message someone does not authorize that action.
