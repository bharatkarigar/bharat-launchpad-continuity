# START HERE — Bharat Launchpad continuity protocol
Last reconciled: 2026-11-16 (Asia/Kolkata)

**Objective:** A new ChatGPT conversation should be able to resume Founder-led Pre-P3 work without asking settled questions, hallucinating implementation status, or confusing old findings with current approval.

## Mandatory context-loading sequence
1. Read this file and [OPERATING_RULES.md](OPERATING_RULES.md) in full.
2. Read [CURRENT_STATE.md](CURRENT_STATE.md) **first for up-to-date execution state**, then [the detailed 8–16 Nov catch-up](evidence/2026_11_16_FULL_DELTA.md) and [cross-chat completeness audit](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md). Do NOT mistake the historical Wave 0A header or original planning-only status for current development gate. Current SEC-8c R2 is **ACCEPTED** after independent Wave 5 ACCEPT and Wave 6 REJECT. Next task is local SEC-2 forward integration and fresh independent Codex.
3. Read [REVIEW_CANDIDATE_LEDGER.md](REVIEW_CANDIDATE_LEDGER.md), [Wave 0–2 detailed context](evidence/PRE_P3_WAVES_0_TO_2_DETAILED_CONTEXT_2026_11_16.md), [Wave 3–5 detailed context](evidence/PRE_P3_WAVES_3_TO_5_DETAILED_CONTEXT_2026_11_16.md) and [P2/Pre-P3 operating model](evidence/P2_TO_PREP3_RUNTIME_SAFETY_AND_AGENT_WORKFLOW_2026_11_16.md) for history and governance.\n4. Read the complete canonical [V10.4 Founder Decision Registry](canonical/FOUNDER_DECISIONS_V10_4.md), [V10.4 Scope](canonical/PRE_P3_SCOPE_V10_4.md), and [V10.4 Master Plan](canonical/PRE_P3_MASTER_PLAN_V10_4.md). The registry is long; selectively read exact relevant sections when a question concerns one feature, but do not claim all 210 decisions have been reverified without reading them.
4. Read [REVIEW_HISTORY.md](REVIEW_HISTORY.md) and [EVIDENCE_INDEX.md](EVIDENCE_INDEX.md), then [the Mac evidence map](evidence/LOCAL_REVIEW_ARTIFACTS_2026_11_16.md). Retrieve exact local source evidence through upload/connected source if a dispute needs it. GitHub documentation cannot see the Mac directly.
5. For new information, distinguish: Founder-approved rule, actual GitHub/repo evidence, Claude report, Codex report, and unproven production behavior.
6. Produce a **continuity check**: Project goal, frozen W5/W6/security SHAs, ACCEPTED vs REJECTED vs pending Codex, Staff security finding, unproven live-provider items, next permitted action, and stale historical files. Then proceed with the current user request; do not repeatedly demand generic reconfirmation.
7. If the user shares a new SHA or Codex verdict, **reconcile CURRENT_STATE, REVIEW_HISTORY and EVIDENCE_INDEX through the GitHub connector** before/after answering whenever appropriate. Append dated delta records without deleting prior rejected history. Update files with clear source attribution; NEVER silently infer a PASS.
8. Do not touch production app repos, local agent branches, DB, activation flags, email/WhatsApp, deploys or customer data by maintaining this documentation repo.

## Authority / precedence
- Explicit new Founder decision > current canonical Founder registry (when not contradicted) > scoped plan > implementation/report evidence.
- Verified current repo/runtime reality > old static audit, but this does NOT silently alter Founder product rules.
- Latest documented and independently reviewed candidate > older candidate; **code candidates and review report commits are different SHAs**.
- Repo docs are not necessarily the latest local Claude state. If a local unpushed change is reported by the user, label it REPORTED until independently checked.
- Superseded drafts are historical. Don't revive rejected approaches without fresh evidence.

## Project purpose
Bharat Launchpad is a unified, multi-tenant ecommerce operating system, not just aggregated dashboards. End-to-end merchant work should function inside one product: onboarding → products/sales channels → order truth → vendor → shipping → WhatsApp customer journey → delivery/cancellation → Growth and Ask AI → Admin/security. Preserve mature features; fix disconnected paths rather than blindly rebuilding.

## Context-transfer reality
This repository makes context **durable, inspectable, versioned and recoverable**; it does not include every verbatim chat line or guarantee identical private reasoning in a new conversation. Original archives/transcripts must be retained separately; the evidence index identifies what is and isn't stored here.
