# Bharat Launchpad — Canonical Continuity Hub

**Purpose:** Preserve Founder-approved decisions, rationale, audited evidence, executable scope, and the exact latest engineering/review gate across ChatGPT conversations. This repository is **documentation only**: it is not the SaaS application repository.

## Start here

1. **[START_HERE.md](START_HERE.md)** — mandatory context-rehydration protocol.
2. **[CURRENT_STATE.md](CURRENT_STATE.md)** — latest checkpoint, candidate SHA, review status, and what is forbidden.
3. **[OPERATING_RULES.md](OPERATING_RULES.md)** — evidence hierarchy, Founder governance, release safety.
4. **[canonical/FOUNDER_DECISIONS_V10_4.md](canonical/FOUNDER_DECISIONS_V10_4.md)** — exact V10.4 Founder decisions.
5. **[canonical/PRE_P3_SCOPE_V10_4.md](canonical/PRE_P3_SCOPE_V10_4.md)** and **[canonical/PRE_P3_MASTER_PLAN_V10_4.md](canonical/PRE_P3_MASTER_PLAN_V10_4.md)** — approved planning baseline, with the current runtime gate in CURRENT_STATE.
6. **[REVIEW_HISTORY.md](REVIEW_HISTORY.md)** and **[EVIDENCE_INDEX.md](EVIDENCE_INDEX.md)** — historical rejections, exact source reports, limitations.
7. **[Exact SHA/review candidate ledger](REVIEW_CANDIDATE_LEDGER.md)** — authoritative indexed reported verdicts and next gates.
8. **[Nov 8–16 FULL DELTA](evidence/2026_11_16_FULL_DELTA.md)**, **[Cross-chat completeness audit](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md)** and **[Mac report index](evidence/LOCAL_REVIEW_ARTIFACTS_2026_11_16.md)** — exact SHAs, review chronicle, Founder decisions, safety and source-access gaps.
9. **[Wave 0–2 detailed context](evidence/PRE_P3_WAVES_0_TO_2_DETAILED_CONTEXT_2026_11_16.md)** and **[Wave 3–5 detailed context](evidence/PRE_P3_WAVES_3_TO_5_DETAILED_CONTEXT_2026_11_16.md)** — reviewed and reported contracts, QA and history.
10. **[P2→Pre-P3 bridge](evidence/P2_CONTINUITY_BRIDGE_TO_PREP3_V10_4_2026_11_16.md)**, **[operating model](evidence/P2_TO_PREP3_RUNTIME_SAFETY_AND_AGENT_WORKFLOW_2026_11_16.md)** and **[original-source hash manifest](evidence/SOURCE_FILE_COVERAGE_AND_HASH_MANIFEST_2026_11_16.md)** — protected decisions, production restrictions, source/coverage gaps.
11. **[NEW_CHAT_BOOTSTRAP.md](NEW_CHAT_BOOTSTRAP.md)** — current message for new ChatGPT conversation.

## Critical operating assumptions

- **Do not infer launch readiness from plans, screenshots, mocked tests, or earlier PASS claims.**
- **Current as of Nov 16:** Wave 5 independent Codex R3 **ACCEPTED** `ce811b2a`; Wave 6 independent Codex R1 **REJECTED** `db1bed9f`; SEC-8c R2 **ACCEPTED** at `036da7b2` after first Codex rejection (B1/B2 CLOSED); SEC-2 `748d292d` internal approved but Codex not yet run — **next merge accepted SEC-8c forward**, reverify and freeze new SEC-2 SHA for review. See `CURRENT_STATE.md` and [Nov 8–16 full delta](evidence/2026_11_16_FULL_DELTA.md). Wave 0A text elsewhere is historical.
- No app changes, source-branch changes, provider/WhatsApp calls, migrations, pushes, merges, or production actions are authorized by maintaining this continuity repository.
- Recorded evidence has levels: FOUNDER LOCKED, REPO/TOOL VERIFIED, USER/CLAUDE REPORTED, CODEX REPORTED, NOT PROVEN. A report is not a live source-of-truth for subsequent commits.
- Keep personal payment identifiers, access tokens, actual customer PII, and secrets out of this repository even if it is public.

## Updating

At any **meaningful checkpoint** (Founder decision, new candidate SHA, Codex verdict, scoped test evidence, scope/release change), update CURRENT_STATE first, reconcile REVIEW_HISTORY and EVIDENCE_INDEX, and commit with a descriptive message. Older canonical versions stay archived; never silently overwrite Founder rules.

This is a **manually maintained continuity system**. ChatGPT can commit via the connected GitHub integration during an active conversation; it cannot silently monitor local Claude/Codex activity or guarantee identical context in every future chat. The new chat must explicitly read this repo before acting.
