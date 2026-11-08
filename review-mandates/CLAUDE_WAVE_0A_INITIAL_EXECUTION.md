# CLAUDE CODE — BHARAT LAUNCHPAD PRE-P3: WAVE 0A IMPLEMENTATION MANDATE

**Founder review context:** Founder has reviewed the V10.4 visual/product simulator and stated that the plan is good to go. Treat that as approval to **start controlled local development of this specifically bounded first wave**. It is **NOT** approval to change production, release flags, send live notifications, alter provider installations/scopes, run production migrations, push to main, or deploy.

**Initial audited code SHA:** `5bc0e1b302be55a22046e6d3335ddc60b558f4bd` (static evidence, NOT automatically the current HEAD).

**AUTHORITATIVE FILES — read from the same downloaded handoff directory before writing code:**
1. `BHARAT_LAUNCHPAD_FOUNDER_DECISION_REGISTRY_CANONICAL_V10_4_2026-11-08.md` — latest product rules.
2. `BHARAT_LAUNCHPAD_PRE_P3_SCOPE_DRAFT_V10_4_2026-11-08.md` — work packages and acceptance J1–J11.
3. `BHARAT_LAUNCHPAD_PRE_P3_IMPLEMENTATION_MASTER_PLAN_V10_4_2026-11-08.md` — dependencies and release gates.
4. `BHARAT_LAUNCHPAD_CLAUDE_RED_TEAM_CRITICAL_RECONCILIATION_2026-11-07.md` — risk evidence.
5. `PRE_P3_POINT3_VENDOR_NOTIFICATION_RETIREMENT_AUDIT_5bc0e1b3.md` — future Wave 0B, preserve current vendor paths.

**Authority order:** explicit latest Founder decision > V10.4 registry > V10.4 scope/plan > current code (as evidence of implementation) > historical docs. If conflicting, report instead of silently changing a product rule. The older planning documents say 'implementation not authorized' because they predate this current Founder go-ahead; this mandate authorizes ONLY this limited local development wave.

## Your role
Act as an engineering orchestrator, focused implementation engineer, and evidence-producing reviewer. Use subagents only for non-overlapping **read-only** code review, test design and adversarial review if supported; keep **one code-edit owner** per shared Mini-Store path to avoid conflicts. Do not use agents as a substitute for checking outputs. Existing mature ecommerce functions must be preserved, not replaced with a mock or rewritten wholesale. Do not open a new broad planning or product-decision cycle.

## Stage A — non-destructive repo/environment preflight (mandatory before edits)

1. Locate the actual Bharat Launchpad application repo (do not assume a directory). Record `pwd`, `git rev-parse HEAD`, branch, `git status --porcelain`, and exact test scripts/config relevant to Mini-Store.
2. If the repo is **dirty**, STOP before editing and report filenames. Never stash, reset, delete, overwrite, or auto-commit someone else's work. If HEAD differs from `5bc0e1b3`, document why and reconcile code path drift first; do not blindly apply old line numbers.
3. Confirm current development/test target is isolated from production before any DB-dependent test. Inspect env **variable names and target identities only**, redact credentials; never print `.env` secrets. If safe isolation cannot be proven, limit to static/unit/mocked tests and clearly label integration NOT PROVEN.
4. Make a local `pre-p3/v10-4-wave-0a-safety` feature branch from the verified clean HEAD, unless that exact branch already exists; never push, merge, release, or deploy automatically.
5. Recheck specific producers/consumers, templates, payment config, shipping rules and test conventions. Establish baseline typecheck/test failures without attributing pre-existing failures to this wave.
6. Produce a short verified **impact + test contract** before edits. Do not ask Founder already settled questions.

## Stage B — WP07, first: wrong-payee / cross-tenant payment-message safety

**Static leads to verify against current SHA:**
- `lib/mini-store-status-messages.ts` near earlier lines 41 and 57.
- `lib/messaging/outbox-enquiry.ts` near 270–276.
- `lib/mini-store-templates.ts` near 144.
- Every call site for `payment_pending`, fallback templates, merchant payment instructions, and outbox retries/resends; cover BOTH known risk locations and indirect consumers.

**Required tests FIRST (actual repo test framework, mocked provider):**
- Two different tenant/merchant contexts: no message for company B can contain company A's payee, UPI, bank details, personal mobile, or brand content.
- No configured company payee → safe `Needs Setup` or blocked message; never fall back to Bharat Karigar personal payment instructions or another merchant's payment details. Distinguish generic payment-status wording from actionable instructions.
- Tenant A with valid own configuration retains a valid, correctly scoped send/preview if the current product flow supports it.
- Message templates with historical brand-specific defaults, manual resend, order state changes, and outbox retry cannot reintroduce cross-tenant values.
- Unsupported/missing config fails safely without silently changing order paid/unpaid status; no actual Evolution/WhatsApp send in tests.
- Role/tenant isolation stays effective; no sensitive banking information in logs/test snapshots.

**Implementation:** smallest safe localized change that fixes every confirmed active producer; do not delete valid merchant templates, operational orders, or existing notifications. Keep owner/admin merchant UX honest about required setup. Do not invent new payment-collection providers or billing architecture.

**Gate after WP07:** reproducible before/after failing→passing tests, targeted regression, reviewed diff, no external writes. If not achieved, stop and report; do not proceed to WP06.

## Stage C — WP06, second: Mini-Store server-authoritative monetary totals

**Static leads to verify against current SHA:**
- `app/actions/mini-store.ts` near 644–647 and 751–773.
- `app/actions/client-mini-store.ts` near 3725.
- All producers and order-creation/reuse paths using price/subtotal/`shippingCharge`/delivery fee/extra charge, quantity, tax/discount and total in the active Mini-Store flow.

**Required tests FIRST (actual test environment):**
- `shippingCharge=-500` or other negative, NaN, overflow, forged subtotal, forged final payable → rejected/neutralized by server, never persisted as trusted operational or payment truth.
- Server-side unit prices, discounts if supported, quantities, product variants, extra charge and applicable shipping rules produce the expected final amount; no browser-supplied amount can silently replace the server calculation.
- Decimal/currency rounding and boundary amounts follow current established product rules rather than an invented pricing model.
- Valid existing carts/orders/enquiries still create complete correct orders; no unwanted checkout regression.
- Tenant isolation: tampered foreign-product and foreign-shipping-rule IDs cannot be used.
- Idempotency / concurrent submissions cannot duplicate or alter payable; trace any existing protections rather than guessing.
- Provider/WhatsApp sends mocked; test never creates real orders or sends messages on production.

**Implementation:** minimal safe fix in the current canonical server boundary, reuse established price/shipping policy, preserve source-of-truth, existing customer/vendor notifications and order lifecycle. If different active public entry points need the same calculation, deduplicate carefully without a large rewrite.

**Gate after WP06:** adversarial tests plus valid-order regression pass on the new SHA. If pricing rules are genuinely missing/ambiguous in code, mark a specific blocking fact NOT PROVEN rather than substituting made-up fees.

## Scope containment: do NOT implement the rest of Stage 0 in this wave

Not in Wave 0A: WP08 Publish/Paused, WP12 retired notification Product Sales APIs, WP14 logout/Admin guards, WP16 legacy cron/writer retirement, WP01–05 provider-order changes, WhatsApp activation, Growth AI write parity, migrations, broad UI redesign, or cleanup. These remain planned for later distinct waves. Do not retire live vendor notifications or change Mini-Store automatic inventory. Current Founder inventory policy remains **no automatic order-driven stock changes**. Preserve Wix existing Owner-approved provider stock action; Shopify manual equivalent is a future work package.

## Required final verification and handoff (no vague PASS)

A. `git status` and `git rev-parse HEAD` before and after, branch and commit(s). Worktree clean if commits made; do not commit automatically if repository policy disallows or user work exists.
B. Changed-file list + concise reason and proof of no production/config/provider/auth/DB/schema/cron/deployment changes.
C. **Per-case test ledger:** `PASS | FAIL | NOT RUN | NOT PROVEN` with exact test names/commands, outputs, and coverage of both valid and adversarial cases. Distinguish mocked/local tests from actual E2E.
D. Preserved-flow proof: previously working Mini-Store payment/enquiry/order paths, vendor notification, order creation and historical data remain intact; anything not exercised marked NOT PROVEN.
E. Show any remaining cross-tenant, wrong-payee, trust-boundary risk and exact follow-up scope. No inflated percentage/blanket client-ready claim.
F. Independent adversarial/self-review; provide a clean diff and SHA as a **Codex review packet**. Do not claim Codex ran unless you actually invoked it and captured evidence.
G. Write `docs/pre-p3-execution/WAVE_0A_WP07_WP06_REPORT.md` (or another report path consistent with the repo) with all above; do not touch production.
H. **STOP after WP07 + WP06** and report. Do not autonomously start WP08, WP12, further WPs, push, merge, or deploy.

## One-sentence mandate
**Execute local test-first Wave 0A on WP07 then WP06, prevent wrong-payee customer messages and browser-tampered monetary totals without breaking mature Mini-Store, deliver exact evidence and stop for review.**