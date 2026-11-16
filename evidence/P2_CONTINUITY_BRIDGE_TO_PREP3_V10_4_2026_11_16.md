# Historical P2 → Pre-P3 decision bridge and protected mature capabilities
**Compiled 2026-11-16** from user-provided Nov7 P2 full-chat continuity, program-context uploads and prior conversation recollections. This is dated historical and partly design-decision evidence, NOT latest code inspection, live DB state or a new Founder decision.

## P2 production foundation and Pre-P3 separation
- P0 closed; P1 operationally complete; P2 CLOSED before Pre-P3. Original P2 production baseline **`7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`**; 23/23 P2 closure migrations applied and verified, owner parity **0 violations / 10 linked companies**, provider execution **Enabled intentionally**. Pre-P3 changes have *not* been approved for production.
- P2 focus was self-serve SaaS, identity/security, company boundaries, plan/entitlement architecture, commerce and provider integration foundations. Public onboarding remained dark; external real provider writes and live webhook sync gated. P1 production had earlier distinct release baseline; don't mistake dated staging/branch SHAs as current production proof.
- Earlier 5–7 Nov Pre-P3 plan called it one integrated programme (17 workstreams), not a collection of prematurely individually go-live CRs. A frozen CR-1 marker `2fcd9540` and CR-2 lane dependency were historical intermediate milestones, **not** the current Wave 6 status. Canonical V10.4 later organized Pre-P3 into 23 WPs, Wave 0A→6, with internal independent per-wave Codex and a **final integrated Codex**. Both process commitments reconcile: per-wave safety reviews happen, **final end-to-end release still requires one integrated review and separate Founder permission**.
- Old provider-execution 'Enabled' UI state was intentionally approved; never turn it OFF to satisfy an audit, and never infer actual provider write permission from display status.

## Order status, vendor and shipping frozen semantics
- `commerce_status` business truth distinct from internal `bk_status`; `placed` at creation, explicit Owner/Admin Confirm only; assignment vendor **does not confirm order**. Shipping and business truth are separate; don't silently generate orders, shipment labels, courier claims or WhatsApp sends on import or background sync.
- Earlier historical audit snapshot reported 707 orders with NULL canonical fields; that number is historical diagnostic, not the current production count, and should not be read as present-state proof.
- Supplier/vendor is source for pickup; company pickup locations retired from intended fulfilment UX; real Delhivery channel mapping required, not vendor-name fallback; support valid Delhivery and Own Courier. Manual dispatch/payment conditions must preserve prepaid safety, truthful COD; no Staff shipping consequential privileges where reserved to Owner/Admin; reassignment cannot erase live/historical shipment claims or AWB.
- Legacy Razorpay/manual pathways for **new** order input retired where Founder decided; historical payment methods and finance retention remain readable, not rewritten. Old payment-due UI/payment gating must be retired coherently to avoid locking order status changes when no repayment path exists. No fake refund from RTD state.
- Mini-Store realized revenue only after real Delivered, not mere manual dispatch/in-transit. Customer-facing messages must use source/tenant-approved sender, valid recipient, opt-out and live event, with no double-send or accidental history replay.

## WhatsApp operational semantics
- Evolution/Baileys transport used in P2/Pre-P3 beta and local automation; its potential future official-provider migration is separate; no successful transport to a real customer is implied by mocked tests.
- Existing company WhatsApp account QR connect/send status, template catalog and Mini-Store event notifications are retained; Staff cannot independently message customers when Founder policy reserves actions to Owner/Admin. Manual supplemental vendor query revealed by Wave6 Codex is a *real* separate security finding (not covered by casual Staff no-new-feature instruction).
- Failed/held/uncertain transport cannot be auto-replayed after reconnect without explicit safe authorized recovery; one event one intended send, explicit manual resend with audit and checks, per-client send limits; failure alerts and opt-out enforcement at final send boundary.
- Real WhatsApp Status posting/video/status mentions are separate exploratory work outside the frozen Pre-P3 J1–J11 release scope unless explicitly authorized; don't bring it into production regression as a new must-build feature.

## P2 Trusted Commerce and Growth truth
- Meta attributed/claimed purchases are not real store orders, revenue or cash. Distinguish actual Shopify/Wix/Mini-Store orders, paid cash, COD/unpaid/provisional, refund/return, realized delivery, freshness and sync provenance. Unknown costs remain Unknown, never presumed zero.
- Growth Hub offers Meta/GA4/Wix/Shopify/WhatsApp integration and Ask AI approvals. Primary external Shopify OR Wix determines commerce context; brand-specific Wix labels never appear on Shopify paths; provider writes must be explicit merchant-authenticated approved and audited. Live provider permissions/re-authorization require later evidence.
- Retire client legacy Analytics only where replaced by Growth and later Founder decision; Admin Analytics held separately.

## Product Onboarding Q17 correction — historical authoritative founder continuity
- Previous broken P2 chat falsely suggested moving or deferring Product Onboarding's AI assistance. Founder correction and recovered existing Product Onboarding artifact establish these are **ALREADY WORKING CURRENT CAPABILITIES**: AI description helper, AI color helper, AI price helper.
- **Preserve all three** in current Product Onboarding. Do not migrate them into Growth Hub / Ask AI in a way that removes or breaks them. No new AI features are required just to centralize UX.
- Product Onboarding also retains single/variants, SKU/color/options/tags/media, vendor/category, draft/publish, pricing/cost/stock, user validation and existing source indicators. No draft overwrite/early submit lost data. Product module decision round reached **20/20 resolved Founder decisions** (not 20/20 tests).
- Exact turn-by-turn wording of historical Q1–Q16 and independent source-line proof for AI helper internals were not recovered in that archive; do not invent them or claim live code inspected from it.

## Self-serve onboarding and readiness truth
- P2 supports foundation but public activation dark. Email verification was universal hard gate in earlier guidance; supplier/vendor, shipping token and other setup guided after entry with feature-specific guards—not universal hard block for missing company pickup locations (those were retired). Don't retrofit an obsolete company-pickup prerequisite.
- Company Role/Admin and entitlements remain server enforced; user-facing availability guided but don't accidentally grant Staff privileged messaging or shipping.
- Legacy optional reseller/dropshipping/API routes may be retired only after static and native regression proof, preserving old financial/order history, vendor operations, product onboarding/AI assistance and working inventory source.

## Current precedence
Latest V10.4 explicit Founder registry and scoped latest decisions take precedence for feature behavior; this dated bridge provides original rationale and known protected historical implementation. Current [CURRENT_STATE](../CURRENT_STATE.md), [candidate ledger](../REVIEW_CANDIDATE_LEDGER.md), and [cross-chat audit](CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md) govern latest gate. No production permission is created by this file.
