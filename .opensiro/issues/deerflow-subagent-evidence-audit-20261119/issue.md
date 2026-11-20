# DeerFlow — evidence-gated subagent completion as an optional S3* constructor

**PLAN_ONLY · GO (proposal-stage) · NEEDS_EVIDENCE (research) · DRAFT — NOT PUBLISHED**

**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

**One-sentence proposal:** Give a developer a scoped, optional independent subagent-result reviewer that can inspect evidence beyond a worker's self-report, request bounded correction and verify the later result before downstream acceptance.

**Canonical decision receipt:** [roadmap.md](roadmap.md) (frozen Index and original source, all dispositions, P0/P1/P2 and verdict).
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md) (Track A/B, smallest source-native ports, counterfactuals and tests).
**Working fork:** `opensiro-contributions/deer-flow` · case `.opensiro/issues/deerflow-subagent-evidence-audit-20261119/` on independent `opensiro/meta` branch. This is a *new additional case* outside the 23-row #58 cohort, not a claim that a listed target had never been run.

## 1. Why OpenSiro and accepted historical VSM assessment

OpenSiro studies whether reusable Viable System Model ownership/feedback descriptions can reduce agent-harness engineering and integration effort. This is a research hypothesis, not a measured benefit, quality rating, or request that DeerFlow adopt VSM.

**ACCEPTED HISTORICAL INDEX (2026-09-15; no current regrade): `S1=A · S2=— · S3=— · S3*=— · S4=— · S5=—`.** [Frozen Index](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/de/deerflow.md), assessment blob `3a57781223e3378bc53f4822bd9a3ae7673a691c`; original reviewed ref `6f81daefff2035d76d41e45d021626f022885372`; Profile 0.2.1 / Skills procedure 0.3.1. Current original: [main@b4b489d7f2fb22fc88305a26e1c6e6077b497216](https://github.com/bytedance/deer-flow/commit/b4b489d7f2fb22fc88305a26e1c6e6077b497216) (2026-11-19).

**Whole-repository screen:** current gateway, lead/subagent runtime, direct and durable batches, task reports, result acceptance, authz, scheduler, skills/extension host, memory, config, frontend review, contracts, tests and CI at the pinned original; external plugins, code of maintainers and parent S5 grants excluded from the assessed operating boundary.

| Function / plain-language role | Historical Index state | Current source-backed actor/return | Independent rerun priority |
| --- | --- | --- | --- |
| **S1 · Operations** | A | [Lead/worker runtime](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/agents/lead_agent/agent.py) performs autonomous model/tool work | Preserve; not a new C |
| **S2 · Coordination** | — | [Batch prerequisites](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/subagents/batch_dependencies.py) and FIFO capacity constrain run overlap; not automatically agent-owned S2 | DEFER separate S2 evidence |
| **S3 · Current management** | — | Lead controls subtasks, operators configure quotas/Goals; a whole-system autonomous owner not evidenced here | DEFER distinct ownership question |
| **S3* · Independent audit** | — | [Receipt verification](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/agents/middlewares/receipt_verification.py) and [acceptance checks](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/subagents/acceptance_checks.py) are strong *advisory* evidence but do not force independent corrective return | **P0: new opt-in C construction** |
| **S4 · Future adaptation** | — | [Skill-mutation host](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/docs/skill-evolution-host.md) and RFC #7066 allow future work, without an evidenced separate outside/then owner in this scenario | DEFER, do not infer an S4 defect |
| **S5 · Policy/identity** | — | Gateway authz, human approval, extension grants and task objectives remain operator/parent rights | NO_TARGET; preserve legitimate parent authority |

Here A is agent-owned closure, C a first-party developer-composed ownership path, P an allowed parent-governed mode, and — bounded absent evidence under the accepted historical criteria. They are **not maturity scores**. New source capabilities are observed separately and do not change Index facts.

## 2. Concrete operator scenario and selected C

A worker reports a completed output, but a factual statement is not covered by a tool receipt or deterministically checkable criterion. A downstream batch continuation may consume the result because the [batch finalizer](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/subagents/batch_service.py) marks it successful based on the execution status and stores acceptance warnings as advisory; if the checker throws, it also treats the result as unchecked rather than requiring a retry. This is a **source-backed hypothetical failure**, not an executed production incident.

**Cheapest native baseline:** the lead/human reads the acceptance verdict and primary artifacts, verifies uncertain claims, then retries or adjusts the task. For decidable file or test evidence, the existing [checklist](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/subagents/acceptance_checks.py) is already preferable; no new reviewer should run by default.

**P0:** an extension/developer binds a reviewer *different from the reporting worker* with legitimate read-only primary-evidence access at the task completion seam. That reviewer chooses `accept`, `request_changes`, or `reject` with a typed evidence basis; the runtime holds an unaccepted result from dependent continuation, reschedules bounded work when authorized, then records a later observed outcome. Parent policy, source identity, quotas and human veto remain authoritative.

## 3. Track A versus parallel Track B

**Track A, shipped:** tool receipts [merged #4659](https://github.com/bytedance/deer-flow/pull/4659), report contract [#5090](https://github.com/bytedance/deer-flow/pull/5090), checklist [#5109](https://github.com/bytedance/deer-flow/pull/5109), durable checklist [#5289](https://github.com/bytedance/deer-flow/pull/5289), saved result inspection [#6416](https://github.com/bytedance/deer-flow/pull/6416), and ordered continuation [#7839](https://github.com/bytedance/deer-flow/pull/7839). Original [RFC #4651](https://github.com/bytedance/deer-flow/issues/4651) CLOSED but its shipped partial layers and current code do not demonstrate a binding independent S3* decision. External agent evaluation [PR #4070](https://github.com/bytedance/deer-flow/pull/4070) remains OPEN and is not a live subagent gate.

**Track B, smallest complete proposal:** attach an independent evidence-aware reviewer only for criteria marked `UNVERIFIED` or contradicted by external read, connect a typed judgment to existing batch task result/continuation, and enforce bounded rework with a durable evidence-to-result link. [VerificationConfig](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/config/verification_config.py) already declares a default-off `judge_enabled` setting but no runtime use was found in the frozen source. Merely enabling a model to score the same self-report is **insufficient** to reach C.

| C link | Current native path | Proposed extra owner or integration |
| --- | --- | --- |
| Independent sensing and decision | Runtime stamps receipts, checks deterministic leaves, reports unresolved ones | Separate reviewer with **different** authorized artifact/source access and typed verdict |
| Enforced correction with subsequent observation | [Batch service](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/subagents/batch_service.py) persists completed status and advisory check, [ledger](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/backend/packages/harness/deerflow/agents/middlewares/delegation_ledger.py) tells lead to inspect | Opt-in hold/limited rework, then evidence-backed released or rejected outcome, without duplicate side effects |

**Distinctness:** not another receipt logger, generic approval gate, human S5 decision, or duplicate evaluation platform. If existing paths already let independent evidence veto release and confirm correction, or if the new reviewer sees only the same worker text, this proposal fails.

## 4. Priority and future gates

**P0:** source-native S3* C construction, proposal only. **P1:** prove evidence independence; callback/AgentRuns identity and resource scope; batch lease and continuation safety, cancellation/timeout, count/attempt caps and durable receipts; respect maintainer preference. **P2:** no other VSM function mandated.

**Proposed C-sufficiency verdict:** PROPOSED_C_SUFFICIENT as architecture *conditional on* actual independent evidence and enforced correction; **not validated or shipped**.

**Future positive test:** a worker's uncited/false claim would otherwise be considered completed, the independent reviewer uses a different source to request changes, the batch blocks downstream release, a revised attempt produces a grounded artifact, and the later acceptance becomes inspectable.

**Future negative tests:** no reviewer credentials, wrong tenant/workspace, unreadable evidence, stale lease, timeout, duplicate resubmission or a model-only self-report judgment must not create a false acceptance or cross authority. **Validation state:** NOT_RUN; cost NOT_MEASURED.

**Falsifier:** equal useful results already achieved by existing native inspect/retry; loss of independent evidence; missing safe correction/feedback path. A single model judgment without later operational consequence is not S3* C.

## 5. Separation and publication

External original issue/PR/comment and public fork GitHub Issue are **DRAFT — NOT PUBLISHED**. Current DeerFlow [MIT license](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/LICENSE) and [CONTRIBUTING](https://github.com/bytedance/deer-flow/blob/b4b489d7f2fb22fc88305a26e1c6e6077b497216/CONTRIBUTING.md) were reviewed; native PR tests and AI-assistance disclosure would be required for external code work. No code or tests performed, no Index regrade, no measured costs. A case under `opensiro/meta` is internal fork research only. Exact owner/publication requirements still apply even after a valid structural receipt. This result is outside the original 23-item Upstream #58 cohort and does not alter its denominator.

## 2026-11-20 · native-specific Human Issue refinement (v0.18.1; same case)

**Concrete user capability:** For **one durable DeerFlow subagent batch item** whose task reports `completed` but whose claimed result cannot be established by deterministic acceptance checks, a developer may opt in to a separate evidence-reading reviewer. Before the next dependent batch action treats this item as accepted, that reviewer may **accept, request bounded correction or reject** on read-only primary evidence and later inspect the *actual* corrected result. No such reviewer is enabled by default.

**Use native DeerFlow interfaces first:** the existing [batch finalizer](https://github.com/bytedance/deer-flow/blob/e3edd05114c17d09082221a1ce1555bfbffeec16/backend/packages/harness/deerflow/subagents/batch_service.py) saves `acceptance_verdict`, result artifact, item status and attempt; [batch persistence](https://github.com/bytedance/deer-flow/blob/e3edd05114c17d09082221a1ce1555bfbffeec16/backend/packages/harness/deerflow/persistence/subagent_batches/sql.py) already owns leases, dependencies and continuations; [completed-run evidence](https://github.com/bytedance/deer-flow/blob/e3edd05114c17d09082221a1ce1555bfbffeec16/backend/packages/harness/deerflow/extensions/completed_run_evidence.py) supports separately scoped read-only evidence but not arbitrary batch-item inspection/release. A proposed review mode must prove the exact owner/thread/item/attempt/evidence link and add the smallest hold-and-return hook, not another general audit service, duplicate receipt logger, background evaluator or autonomous permission grant.

**Human decision still open:** Is an optional binding acceptance hold worth integrating for this narrow situation, or is existing manual/lead inspection plus deterministic checks sufficient? This is not a claim that shipped behavior is defective or that maintainers want this change. Original [RFC #4651](https://github.com/bytedance/deer-flow/issues/4651) and [open eval PR #4070](https://github.com/bytedance/deer-flow/pull/4070) are related but not demonstrated equivalents of the proposed full loop.

**Assessment/proposal boundary:** historical `S1=A; S2/S3/S3*/S4/S5=—` remains unchanged. Proposed `S3*=— → S3*=C` **GO / NEEDS_EVIDENCE, PLAN_ONLY**, not implemented and not independently tested. No public fork/original Issue/PR/comment was authorized or published. [AI constructor details](constructor-sufficiency.md), [canonical dated receipt](roadmap.md), [same-case README](README.md).
