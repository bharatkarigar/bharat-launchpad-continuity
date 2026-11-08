# Bharat Launchpad — Canonical Continuity Hub

**Purpose:** Preserve Founder-approved decisions, rationale, audited evidence, executable scope, and the exact latest engineering/review gate across ChatGPT conversations. This repository is **documentation only**: it is not the SaaS application repository.

## Start here

1. **[START_HERE.md](START_HERE.md)** — mandatory context-rehydration protocol.
2. **[CURRENT_STATE.md](CURRENT_STATE.md)** — latest checkpoint, candidate SHA, review status, and what is forbidden.
3. **[OPERATING_RULES.md](OPERATING_RULES.md)** — evidence hierarchy, Founder governance, release safety.
4. **[canonical/FOUNDER_DECISIONS_V10_4.md](canonical/FOUNDER_DECISIONS_V10_4.md)** — exact V10.4 Founder decisions.
5. **[canonical/PRE_P3_SCOPE_V10_4.md](canonical/PRE_P3_SCOPE_V10_4.md)** and **[canonical/PRE_P3_MASTER_PLAN_V10_4.md](canonical/PRE_P3_MASTER_PLAN_V10_4.md)** — approved planning baseline, with the current runtime gate in CURRENT_STATE.
6. **[REVIEW_HISTORY.md](REVIEW_HISTORY.md)** and **[EVIDENCE_INDEX.md](EVIDENCE_INDEX.md)** — historical rejections, exact source reports, limitations.
7. **[NEW_CHAT_BOOTSTRAP.md](NEW_CHAT_BOOTSTRAP.md)** — short message for a new ChatGPT conversation.

## Critical operating assumptions

- **Do not infer launch readiness from plans, screenshots, mocked tests, or earlier PASS claims.**
- The active Wave 0A safety candidate is `ab74f11459e1efdab62464fd4d7614b1132203eb` and **Codex review #3 is pending** as of the latest supplied update; Wave 0A is **OPEN**. Do not start Wave 0B.
- No app changes, source-branch changes, provider/WhatsApp calls, migrations, pushes, merges, or production actions are authorized by maintaining this continuity repository.
- Recorded evidence has levels: FOUNDER LOCKED, REPO/TOOL VERIFIED, USER/CLAUDE REPORTED, CODEX REPORTED, NOT PROVEN. A report is not a live source-of-truth for subsequent commits.
- Keep personal payment identifiers, access tokens, actual customer PII, and secrets out of this repository even if it is public.

## Updating

At any **meaningful checkpoint** (Founder decision, new candidate SHA, Codex verdict, scoped test evidence, scope/release change), update CURRENT_STATE first, reconcile REVIEW_HISTORY and EVIDENCE_INDEX, and commit with a descriptive message. Older canonical versions stay archived; never silently overwrite Founder rules.

This is a **manually maintained continuity system**. ChatGPT can commit via the connected GitHub integration during an active conversation; it cannot silently monitor local Claude/Codex activity or guarantee identical context in every future chat. The new chat must explicitly read this repo before acting.
