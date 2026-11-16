# Bharat Launchpad — P2 production boundary, Pre-P3 discipline and agent orchestration continuity
**As-of:** 2026-11-16. Founder preferences and previously reported project behavior. Treat P2 production facts as dated historical reports, not a fresh production inspection. This is a **public safe summary** without account credentials or customer PII.

## Architecture / product purpose
- Bharat Launchpad is an integrated multi-tenant boutique/ecommerce SaaS, supported by Bharat Karigar's own commerce operating experience; user has distinct brand sites and the dashboard. Preserve company isolation, merchant permissions and ecommerce truth.
- P2 had a production deployment at a merchant dashboard domain on **Nov 4, 2026**; report says candidate main/production SHA matched, 23/23 production migrations for that release applied, 0 owner parity violations over 10 linked companies. This is **P2 only**, NOT proof of Pre-P3 deployment.
- P2 later review work remaining included Company Profile, plans/entitlements, trusted commerce data, hosted/custom domains, dark self-serve onboarding, Wix/Shopify, analytics, payments and wallet. Keep P2 regression/report close-out and Pre-P3 programme distinct; do not mistakenly redeploy or turn on disabled capabilities.
- P2 production policies originally dark: public self-serve onboarding OFF; provider live-sync/webhook apply OFF unless explicitly authorized; SMTP/email-dependent flows OFF; no feature flags/trust anchors/signing/production DB changes merely to test. **Exception:** Growth Hub 'Provider execution — Enabled' is Founder-expected and should NOT be marked blocker or disabled. Enabled configuration is **not** carte blanche to issue provider writes.
- Existing P2 multi-tenant company/role/entitlement boundaries, commerce/order truth vs Meta claimed purchases, and COD/prepaid finance distinction must be preserved. Migrating Pre-P3 changes to live P2 service is a distinct final Founder release decision.

## Current reviewed engineering workflow (frozen process)
- Founder: sets product outcomes, makes major product/security/release decisions, authorizes production and manual independent Codex reviews.
- Claude Opus MAIN in VS Code: local engineering orchestrator, test/QA plan, one writer delegated Builder, deterministic independent checks, evidence ledger, safety gates. Maximum 3 agents **including MAIN**; Specialist and independent Red-Team **read-only**; one globally writing Builder. Don't create parallel writing agents or weaken tests to gain speed.
- Codex: separate independent **read-only** reviewer launched manually by Founder, exact candidate SHA, full source review not blind trust in Claude's pass or summary; returns ACCEPTED/REJECTED with independent evidence. Codex should NOT fix/rewrite source in the same reviewer session.
- Rejected candidate remains in Git history; for fix-forward first demonstrate failing tests against rejected SHA, commit the minimal patch separately, full integrated test gates, Red-Team, and fresh Codex Rn on **new exact SHA**. Documentation/report-only HEAD is not reviewed code SHA.
- Automated tests run disposable local PostgreSQL, mocks/stateful fake providers, deterministic native SQL concurrency tests and isolated E2E. Never imply simulated tests prove actual live Shopify, Wix, WhatsApp, Delhivery, SMTP, bank/payment processors or staged release.
- Manual Codex ordering in current scope: Wave 5 R3 **ACCEPTED**, Wave 6 R1 **REJECTED**, SEC-8c R1 **REJECTED** and R2 **ACCEPTED**, SEC-2 merge to new SHA and independent Codex PENDING, Wave 6 R2 security/staff fix pending, final integrated Codex pending. Every accepted verdict applies **only to its exact reviewed SHA**.

## OmniRoute / model orchestration history and freeze
- Founder experimented with Claude/Codex subscription orchestration, OmniRoute `coding-auto` Builder gateway, OpenRouter, model fallbacks and staged test harnesses. Tests had mixed verified and failed cases, including auth/token limits; QA not a blanket certification.
- Later Founder explicitly **LOCKED existing P2 development architecture**: VS Code native Claude Opus MAIN and direct/native independent read-only Opus Red-Team, existing single Builder role; OmniRoute model source changes only where already approved, no P2 architecture alteration. ChatGPT strategic advisor is optional, not a required runtime node. No unapproved effort-level/routing investigation or model settings changes during Pre-P3 work.
- claude-wake watcher previously used to resume VS Code Claude after usage-limit reset; user reported daemon functioning and resume events. It is not a guarantee of unattended execution or permission to create agents/deploy.
- Mac dev environment reported VS Code on MacBook Air M1 16GiB; 16 Nov local disk ~26GiB available, prior 14 Nov ENOSPC historical and resolved. These are historical diagnostics; re-check when storage matters. Do not delete caches, temp DB, logs or worktrees without explicit approval and evidence they are unused.
- No real production provider messages, ecommerce edits, WhatsApp sends, PostgreSQL migrations, flag flips or GitHub application-repo pushes from documentation maintenance. Keep private customer PII and credentials out of this public repo.

## Launch/release governance (NOT solved by code review)
- Frozen V10.4 Founder decisions and current scoped approvals govern; a read-only production count/check is itself **approval-controlled** for SEC-8c and SEC-5.
- SEC-8c migration 474 has Codex R2 accepted code but **not** applied to prod; real existing-data cross-company link count is unknown; migration should fail loudly if violations exist; migration blocks writes, requires controlled window.
- SEC-2 migration 479 locally approved by Red-Team but needs accepted SEC-8c base merge, new exact SHA, native tests, independent Red-Team and Codex; production retirement of old finance triggers is Founder release action.
- SEC-5 migration 367 production email-based order RLS verification still unknown; do not infer no legacy security gap from local tests.
- Release pins `verify-pins` RED (reported 139 refusals after SEC-8c R2, 137 on older base) and migration 333 rollback governance requires Founder approval; cannot silently regenerate pins, sign or alter trust anchors.
- Pre-P3 migrations 454–479 and final integrated candidate not applied to production; staging Supabase not ready at last status; full J1–J11 real provider proof absent; Vercel fresh build/deploy, C0/C1/soak, monitoring, merchant controls, safe rollback and Founder approval mandatory.
- Wave6 MS-10 abandoned-cart worker Post-Pre-P3 deferred; Delhivery out-for-delivery mapping external verification later; Staff supplemental vendor WhatsApp permission issue **confirmed and open**, not exempt by prior preference against Staff UX work.
- Production release stays **HOLD**. Do not convert Codex review success into go-live approval.

## Handoff requirements for a new ChatGPT conversation
- Consult [CURRENT_STATE](../CURRENT_STATE.md), [review history](../REVIEW_HISTORY.md), [full Nov 8–16 timeline](2026_11_16_FULL_DELTA.md), [completeness audit](CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md), and V10.4 canonical docs.
- Return brief correct status with accepted/rejected/pending SHAs and next approved action; preserve Founder scope/holds; proactively update docs only when user provides actual new verified results. Don't invent missing Mac report bytes.
