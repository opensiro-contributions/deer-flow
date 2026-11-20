# DeerFlow — new additional S3* evidence-audit roadmap case (2026-11-19)

- **Original:** [bytedance/deer-flow main@b4b489d7f2fb22fc88305a26e1c6e6077b497216](https://github.com/bytedance/deer-flow/commit/b4b489d7f2fb22fc88305a26e1c6e6077b497216) (pinned).
- **Accepted Index:** [DeerFlow](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/de/deerflow.md), `included`, historical S1=A / S2=— / S3=— / S3*=— / S4=— / S5=—, reviewed 2026-09-15; no current regrade.
- **Matching fork:** `opensiro-contributions/deer-flow`; no `opensiro/meta` before the explicitly requested research bootstrap. The owner-directed new case is **outside** the initial 23 targets in Upstream #58.
- **Proposal-stage:** `GO` to optional `S3*=— -> S3*=C` subagent independent evidence reviewer, **not implemented**.
- **Research:** `NEEDS_EVIDENCE`; native tests `NOT_RUN`; costs `NOT_MEASURED`.
- **Public fork GitHub Issue:** NOT PUBLISHED; **Original Issue/PR/comment:** NOT PUBLISHED; product/default branch unchanged.
- **Native overlap:** [RFC #4651](https://github.com/bytedance/deer-flow/issues/4651) and already-merged deterministic receipt/checklist PRs, plus [unmerged eval platform PR #4070](https://github.com/bytedance/deer-flow/pull/4070). No duplicate original proposal.

## Read this case

[Human decision](issue.md) · [AI constructor and falsifiers](constructor-sufficiency.md) · [Canonical source-pinned receipt](roadmap.md).

This first-time case should be interpreted as a *separately selected additional harness* after #58's initially selected targets had acquired their own v0.18 reports. It does not change the original cohort's total or claim implementation, test success, public maintainer consent, or measured savings. Initial metadata commit and exact readback are required before treating this case as PERSISTED.

## 2026-11-20 · Upstream v0.18.1 native-specific follow-up

**Same case, refined in place:** `GO / NEEDS_EVIDENCE`, `PLAN_ONLY / HYPOTHETICAL`. The original 2026-11-19 decision, source pins and alternative cases above remain historical provenance. This is **not** a new independent original-level assessment, acceptance of a current Index grade, implementation, native test pass or maintainer product decision.

**New original observation:** [bytedance/deer-flow@e3edd05114c17d09082221a1ce1555bfbffeec16](https://github.com/bytedance/deer-flow/commit/e3edd05114c17d09082221a1ce1555bfbffeec16) (2026-11-20), later than the original case pin. **Narrowed P0:** only one opted-in *durable subagent batch item* whose execution completed but whose acceptance is evidentially unresolved. Reuse DeerFlow's native `check_batch_acceptance`, `acceptance_verdict`, item/result-artifact owner-scoped readback, SQL lease/dependency/continuation machinery and host-bound read-only run evidence; add only a distinct developer-composed audit choice with an enforced, versioned accept/hold/rework return. No generic verification service, second storage layer, unattended writes or new VSM metrics.

**What remains missing at source:** no established native link from an independently authorized reviewer of *that exact batch item/attempt* to a binding acceptance/continuation gate and subsequent correction observation. The existing extension run-evidence reader is read-only and run-scoped; it must not be asserted to grant batch-item inspection or finalization rights. Refer to the dated addenda in [Human issue](issue.md), [AI constructor](constructor-sufficiency.md) and [canonical receipt](roadmap.md).

**Validation:** case structural check PENDING independent runtime execution; native behavioral tests NOT_RUN, benefit/cost NOT_MEASURED, original/fork-public interaction NOT_PUBLISHED. [Coordination reservation](https://github.com/opensiro/upstream/issues/58#issuecomment-7045251917). No new per-run Upstream PR by current reporting protocol.
