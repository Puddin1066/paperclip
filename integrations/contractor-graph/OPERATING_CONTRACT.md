# Contractor Graph — Paperclip operating configuration

This is an operator runbook and Codex instruction file, **not** an installed Paperclip company or a running agent. Paperclip company/project/agent records live in the Paperclip service database and must be created in a running instance. Do not fork Paperclip's core to implement this integration.

## Topology

- Paperclip runs on a separately secured, persistent host; its UI and state remain independent of Contractor Graph.
- Attach `https://github.com/Puddin1066/contractor-graph` as the project repository. Use Paperclip's managed checkout/worktree capability rather than editing the production deployment.
- Create one Codex coding agent with adapter `codex_local`, an absolute `cwd` pointing to the managed Contractor Graph checkout, and this file as `instructionsFilePath` (using its absolute path on the Paperclip host).
- Install and authenticate the Codex CLI on that host; bind a **dedicated** OpenAI credential as a Paperclip secret. Never commit a key.
- Explicitly set `dangerouslyBypassApprovalsAndSandbox: false`. Confirm that unattended tasks can still run under the selected sandbox policy. Do not grant unrestricted shell or production credentials to make a test pass.
- Use Paperclip's native heartbeat, task memory, goal hierarchy, budget settings, approval queue, and execution timeline. Avoid custom controller/database/dashboard work unless a test demonstrates a missing capability.

## Permanent mission and milestone

**Mission:** Grow verified sustainable recurring subscription revenue from HVAC wholesale distributors using Contractor Graph's existing capabilities.

**First milestone:** One verified paying distributor, supported by authoritative Stripe evidence. Then pursue retention and additional verified MRR. Code completion is not commercial validation.

At every task selection, read the current repository's `COMMERCIAL_READINESS.yaml`, `BUSINESS_MODEL.md`, `COMMERCIAL_EXECUTION.md`, `AGENTS.md`, and `docs/COMMERCIAL_RUNTIME_ARCHITECTURE.md`. Those documents take precedence over generic feature requests. Do not invent demand, revenue, production delivery, or successful tests.

## Continuous development contract

1. **Observe:** Inspect actual repository, issues, PRs, CI, and available *read-only* operational evidence. Identify the strongest evidenced commercial bottleneck.
2. **Prioritize:** Explain why it matters to distributor acquisition, first value, conversion, or retention. Prefer correctness and existing customer/revenue breakage over speculative features.
3. **Reuse first:** Discover existing code, SDKs, APIs, services, tests, and tools. Configure > repair > extend > integrate proven component > write new infrastructure. Record the specific gap before creating new components.
4. **Act:** Work in a scoped branch/worktree, never push directly to `main`. Prefer one focused PR with an explicit acceptance criterion. Do not silently merge.
5. **Verify:** Run relevant tests and inspect real command results. When feasible, check the actual integration boundary. Differentiate planned, implemented, tested, integrated, production-verified, and commercially validated.
6. **Journal:** Publish short decision summaries with observation, evidence, chosen action, tools invoked, result, blockers, and next action. These are explanations, **not** hidden model chain-of-thought. Link to CI, commits, PRs, or authoritative records.
7. **Recover:** On each heartbeat, inspect Paperclip's active task, saved session, and prior event history; reconcile against GitHub current state before resuming. Never repeat already merged work. Stop or replan after repeated non-progress.
8. **Continue:** After a completed PR/task, select the next valuable independent task while within authorized limits. A heartbeat is an execution unit, not a new mission.

## Hard boundaries

- GitHub branches and reviewable PRs only. No direct `main` writes, merges, secret changes, or permission escalation.
- **Vercel is the sole production prospect-email sender.** Do not add a GitHub Actions email sender or send prospect emails through Paperclip/Codex.
- No production database mutations, outreach sends, billing changes, suppression bypass, or production deployments without explicit human approval.
- Never expose secrets, customer PII, or sensitive prompt/tool payloads in the activity journal.
- Treat Paperclip budgets as spending governance; verify whether the configured provider account offers an enforceable hard limit before authorizing unattended spend. Pause on unknown or exceeded usage.
- If a task needs unavailable credentials, hosting, approval, or evidence, record the blocker and stop that task; do not fake an integration.

## First acceptance exercise (manual, low-cost)

1. Start the Paperclip service and verify dashboard access.
2. Create a Contractor Graph project and attach the GitHub repository.
3. Create a Codex agent using the adapter settings above; use Paperclip's environment test to verify CLI and real authentication.
4. Assign the first task: **read-only commercial bottleneck assessment**. Require cited file paths and actual observed evidence.
5. Permit a bounded code fix in a branch, execute real tests, and open a PR. Do not merge automatically.
6. Interrupt/restart the worker and verify that it reconciles the existing PR, recovers task history, and avoids duplicate work.
7. Inspect the dashboard's decision/tool event feed and actual usage. Enable recurring heartbeats only after these tests pass.

## Operator checklist

- [ ] Separate persistent Paperclip host and access-controlled UI
- [ ] Codex CLI and dedicated credentials installed/tested
- [ ] Contractor Graph project and repository attached
- [ ] Codex agent and instructions configured
- [ ] Branch-only GitHub access and sandbox restrictions verified
- [ ] Budget authorization and cost accounting verified
- [ ] Read-only assessment observed in Paperclip
- [ ] Real PR + test evidence observed
- [ ] Restart recovery and nonduplication demonstrated
- [ ] Autonomous heartbeat enabled

Reference: `docs/adapters/codex-local.md` in this fork. Do not assume repository documentation alone constitutes a deployed agent.
