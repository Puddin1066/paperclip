# Contractor Graph: Paperclip autonomous operating mandate

## Objective
Use **this Paperclip instance as the sole orchestration/control plane**, with **one Codex-adapter worker** initially, to finish assembling and operate [Contractor Graph](https://github.com/Puddin1066/contractor-graph) as a paying HVAC-distributor intelligence business.

The complete loop is: authoritative contractor data → validated territory intelligence → prospective distributors → verified contact and authorized outreach → sample/trial → paid subscription and delivery → retention and iterative improvement.

## Existing implementation to reuse
- Paperclip's native server, persistent database, goals/issues, Codex adapter, sessions, heartbeats, budgets and approvals. See `AGENTS.md`, `doc/GOAL.md`, `doc/DEVELOPING.md`.
- Contractor Graph's `AGENTS.md`, `COMMERCIAL_READINESS.yaml`, `COMMERCIAL_EXECUTION.md`, source, tests and existing domain services.
- Existing Paperclip PR #1 and Contractor Graph PR #120 specified integration boundaries **but did not establish live execution**.
- Contractor Graph's internal agent specifications, OMO, assembly agent and GitHub Codex workflows are **not evidence of operational agents**. Treat them as code to audit, not prerequisites to activate.

## Bootstrap sequence
1. Detect any existing Paperclip company/agent/session/runtime before provisioning anything. Preserve existing state.
2. Establish a persistent authenticated Paperclip server and durable database; verify API/UI and restart persistence. GitHub Actions by itself is not a persistent control plane.
3. Register a Contractor Graph company/project, the objective above, and one Codex worker with an isolated checkout of `Puddin1066/contractor-graph`. Verify the actual adapter credentials and permitted git operations with a bounded task.
4. Paperclip assigns a repository audit task: inspect source, tests, runtime evidence, workflows, data freshness, sample generation, and customer delivery. Separate working, unverified, and broken features. Select the highest-value gap.
5. Codex implements the gap on a branch, tests it, submits a PR, and reports evidence to Paperclip. Native heartbeat/session continuation assigns the next task without user prompting.
6. Continue through a real evidence-backed territory intelligence delivery, qualified acquisition, trial, paid delivery, retention, and commercial metrics.

## Controls
- Initially one active worker/task, bounded token/compute spend, no runaway retries. Remove overlapping AI development schedules only after Paperclip is proven live.
- Never send production email, change billing, make customer commitments, deploy or mutate production data outside existing approved deterministic services and authorization.
- Do not write directly to `main`, bypass suppression, expose secrets, fabricate business results, or silently change scoring.
- A missing host, credential, quota or account permission is an explicit blocker to surface, not an invitation to build another orchestration framework.

## Acceptance tests
- Reachable persistent Paperclip server with durable company, goal and worker.
- One **real** Paperclip-assigned Codex execution with task history and logs.
- A substantive Contractor Graph code change with passing tests and PR.
- Paperclip autonomously schedules and completes a second task without a manual prompt.
- A demonstrable contractor-intelligence deliverable and eventually verified paying customer outcomes.

**Important:** This document is the persisted operating contract, **not proof of a deployed runtime or connected worker**.
