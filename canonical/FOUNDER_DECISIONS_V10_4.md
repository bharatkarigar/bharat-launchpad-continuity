# BHARAT LAUNCHPAD — CANONICAL FOUNDER DECISION REGISTRY

**Date:** 2026-11-08  
**Purpose:** Founder-decision authority for the NEXT evidence audit/acceptance review; not a proof that code is functional or permission to implement.  
**Current code candidate being audited:** `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`  
**Status:** V10.4 — V10.3 DECISIONS PRESERVED; POINT 3 RETIRED PRODUCT SALES ROUTES RECONCILED; FOUNDER-APPROVED ONE EXTERNAL STORE + PRIMARY-STORE GROWTH/ASK AI + SHOPIFY/WIX FULL SUPPORTED GROWTH PARITY (READ + APPROVAL-GATED WRITE); V10.2 WIX EXCEPTION AND V10.1 MINI-STORE STOCK DECISION PRESERVED; DOCUMENTS ONLY; NO IMPLEMENTATION AUTHORIZED.

---

**Completeness pass:** 2026-11-07 — reconciled against the P2 master continuity and full Pre-P3 chat-continuity record; shipping micro-rules and latest overrides explicitly carried forward.

**Correction pass 2:** 2026-11-07 — added previously compressed/missed frozen details for canonical order truth, provider live/initial/backfill boundaries, returns/refunds, detailed legacy retirement, Product Onboarding preservation, WhatsApp beta transport/activation defaults, shipping micro-actions, beta module defaults, inherited Phase-0 irreversible safeguards, shared-vendor controls, merchant-owned Delhivery, legacy order columns, test-company exclusion, and beta store-app distribution details.

**Critical review pass 3 (V5):** 2026-11-07 — rechecked explicit Founder UX locks against the detailed conversation dump and final records; restored guided Orders fulfilment UX, Product 20-question outcomes, Mini-Store shared-product/storefront rules, Home Vendor-readiness, exact per-template WhatsApp sender selection, WhatsApp Template/Activity/Broadcast UX, phase-closure-vs-regression semantics, manual-order retirement clarity, and a strict no-assumption/provenance taxonomy.

**Critical review pass 4 (V7):** 2026-11-07 — corrected shared-vendor pickup/channel semantics, restored the frozen Shopify/Wix operational shipping-contact override rule, restored exact vendor optional fields and tracking-resend confirmation semantics, hardened WhatsApp template-OFF/manual-send behaviour and Orders step progression, and added critical-decision traceability so technical defaults cannot masquerade as Founder choices.

**Critical review pass 5 (V8):** 2026-11-07 — added provider-ingestion completeness across webhook/sync/replay, no silent line/refund truncation, complete normalized financial facts, safe client deactivation semantics, and multi-currency Growth truth; these are implementation consequences of already-frozen end-to-end/truth rules, not new Founder product choices.

**Independent red-team pass 6 (V9):** 2026-11-07 — compared the registry against the final UX contracts/screen index and added an explicit capability-manifest preservation rule plus previously under-specified mature sub-systems: Product Price/Shipping Rules, Product media/stamping safeguards, Mini-Store carts/leads/store-design/tracking configuration, Connections primary-store semantics, Influencer recommendation consent, and global shell/truthful-state protection.


**V10 targeted correction (2026-11-07):** reconciled Claude independent Red-Team report against Founder messages that were not on Claude's machine. Corrected the misleading universal/latest-stock assertion (FD-INV-01); preserved latest explicit Pre-P3 Shopify/Wix order-only sanitized JSON approval, Owner-only export and narrow Wix deletion rule; added 21 technical verification cases, privacy/new-snapshot gates, manifest drift, and a source-conflict register. **Technical code findings are hypotheses supported by Claude's static source review, not Founder decisions and not observed runtime incidents.**

**V10.1 stock decision lock (2026-11-07, direct Founder confirmation):** Mini-Store uses existing Check Availability / vendor-response workflow and **does not automatically decrement or restore numerical stock** on order creation, assignment, Confirm, shipping or cancellation. Shopify/Wix inventory remains **provider-owned**, with no automatic order-driven stock movement/write-back. **V10.2** added the existing Owner-approved Wix `wix_update_inventory` exception. **V10.3** adds the analogous Owner-approved Shopify inventory-adjustment target under FD-INV-06 (not implemented). Historical P1 Confirm/Cancel stock movement is retained as historical evidence, **not** live Pre-P3 authority. Q-STOCK remains CLOSED. Existing unsafe stock writers (for example vendor-notification `current_stock=5`) remain audit/fix candidates; none of this authorizes implementation. Manual/native source-specific stock behavior not covered by this decision remains NOT PROVEN.

**Required accompanying material:** `BHARAT_LAUNCHPAD_PRE_P3_SCOPE_DRAFT_V10_4_2026-11-08.md` (current companion; V10.3 and earlier preserved), original V9 red-team report + 3 evidence appendices, source capability manifest, original Founder conversation excerpts. If a purported direct decision's original message cannot be located, mark provenance `NOT PROVEN` rather than fabricating a quote.

**V10.2 direct Founder approval (current conversation):** "Wix inventory write action ka final Founder decision Option A. Isko V10.1 se reconcile karo. Implementation abhi authorized nahi hai." This is **Founder-accepted recommendation**, specifically the already-built `wix_update_inventory` operation initiated by the merchant and **explicitly approved by Owner**, under existing role/company/provider execution gates and audit trail. It was **not** permission (at V10.2) for order-triggered writes, ungated writes, automatic sync write-back or a Shopify inventory write; V10.3 subsequently authorises only the explicit Owner-approved Shopify action under FD-INV-06. The preceding direct V10.1 read/sync-only preference governs **automatic/order-driven** stock behavior; its blanket wording is superseded only for this narrow Wix approved action. Runtime/production gate values remain `NOT PROVEN`; no toggles or execution authorized.

**V10.3 direct Founder direction (2026-11-08, after the Wix→Shopify Growth parity audit):** (1) Only **one external commerce store per company**, either Shopify OR Wix, with Mini-Store optional; (2) Growth AI and Ask AI's **external-commerce context** uses that selected primary store, not both external providers or a silently substituted Wix source; (3) **Shopify receives comparable functional Growth and Ask AI capability to mature Wix features, including READ and approved WRITE operations**, not merely reporting; (4) preserve the mature provider-action / Owner-approval / execution / audit safety model, verify provider-specific API/scopes and reauthorisation; (5) explicit, approved merchant-originated **Shopify inventory adjustments may be supported** as the narrow exception to the older Shopify inventory read-only policy, just as Wix's existing Owner-approved inventory workflow is preserved; **no automatic/order-driven stock write for any provider**. This approval **supersedes** the Oct 29 Shopify no-write-scope rule and the V10.2 blanket Shopify read-only rule **only where necessary for these approved provider actions**. It does not approve speculative, unsafe, unproven or provisional Wix writes (e.g., cancel/refund) for Shopify without case-specific capability/safety review. ShopifyQL or other proprietary API parity is **functional**, not a mandate to copy a provider-specific endpoint. Implementation, scope changes, installations, reauthorisation and provider writes remain **NOT AUTHORIZED**.

**V10.3 audit context:** `PRE_P3_GROWTH_WIX_SHOPIFY_PARITY_AUDIT_5bc0e1b3.zip` (29 Wix rows, 11 separate provider-neutral Growth features). Static audit: 3 current Shopify working, 9 reuse/small adapter, 7 medium/large, 9 previously blocked by Founder restrictions, 1 not proven. These classifications predate V10.3 approval: "blocked by old Founder scope" is now **authority superseded**, not proof features are implemented or permitted by provider grants. Live Shopify grant/runtime/flag status unverified. No code changes.

**V10.2 historical baseline:** V10.2 changed only Wix's explicitly Owner-approved inventory exception. **V10.3 adds newer explicit Founder decisions** on one external store, primary-only Growth/Ask AI and Shopify/Wix READ+WRITE parity; otherwise preserve prior decisions/technical findings.


**V10.4 Point 3 close-out (2026-11-08):** Founder previously approved retiring Platform Admin Product Sales. A targeted Claude source review on candidate `5bc0e1b3` traced both `/api/inventory/notify-vendor` and `/api/inventory/notify-vendor-product-sales` to **retired-only** paths. The latter remains reachable through the old Product Sales Admin tab; the former has no in-app caller but remains directly HTTP-callable by Platform Admin. Both set `current_stock=5` in old non-canonical tables. Legitimate Order Fulfilment Step 4, Mini-Store vendor queries and vendor responses use separate paths with no dependency on these two routes. Founder accepted the targeted retirement recommendation in chat. **Decision: retire the unsafe old endpoints and their proven-unused Product Sales sibling APIs via non-writing 410 responses; remove the Admin Product Sales tab/sidebar; preserve historical rows/tables and preserve live vendor workflows.** Code evidence is static; production incidence not proven. This is a cleanup/safety task for *future approved implementation*, not permission to change code now. Do not generalize this decision to every route with 'vendor' in its name.

## 0. AUTHORITY / CONFLICT RULE

When two decisions conflict, use this order:

1. Latest direct Founder decision in the current/recent Pre-P3 review.
2. Newer Founder Decision reconciliation decisions (post-wireframe).
3. Frozen Pre-P3 continuity decisions.
4. P2 frozen architecture/Founder decisions.
5. P1/P0 inherited decisions.
6. Wireframes/recommendations only where they do not conflict with the above.

**Critical rule:** a newer Founder decision supersedes an older phase assumption. Old P2 constraints must not silently override the current Pre-P3 client-ready goal.

## 0A. DECISION PROVENANCE / NO-ASSUMPTION RULE

Every statement used from this registry must be interpreted as one of these classes:

1. **DIRECT FOUNDER DECISION** — the Founder explicitly chose/confirmed it.
2. **FOUNDER-ACCEPTED RECOMMENDATION** — an option/recommendation was presented and the Founder accepted it.
3. **GLOBAL PRESERVATION RULE** — mature working capability is protected unless explicitly retired/superseded.
4. **TECHNICAL / SECURITY CONSEQUENCE** — required to implement a frozen decision safely; this is not a new product preference.
5. **AUDIT / NOT PROVEN** — evidence question only; must not be promoted into a Founder decision.

Hard rules:
- Claude/ChatGPT must separate **fact/evidence**, **Founder decision**, **recommendation**, and **assumption**.
- An assistant recommendation is NOT a Founder decision until the Founder accepted it.
- An audit finding is evidence, not automatically a product decision.
- If evidence is insufficient, use `NOT PROVEN`; do not guess.
- Do not re-ask already frozen decisions unless new evidence creates a real contradiction.
- Wireframes, prototypes and UX Digital Twin artifacts are review tools only. They never authorize removal of mature functionality or override later Founder decisions.
- Current code behaviour is evidence of implementation, not authority to override a newer Founder decision.


## 0A.1 CRITICAL DECISION TRACEABILITY

For high-risk/latest rules, use these source families when provenance must be checked. This is a **decision traceability map**, not evidence that the code implements the decision:

| Decision family | Primary decision source |
|---|---|
| Vendor + Shipping exact frozen rules | `03_FOUNDER_DECISION_RECORDS__VENDOR_SHIPPING_FOUNDER_DECISIONS_2026-11-07.md` |
| Retained micro-capability manifest / final screen contracts | `01_FINAL_FULL_SYSTEM_WIREFRAMES__CAPABILITY_COVERAGE_MATRIX.md` + `01_FINAL_FULL_SYSTEM_WIREFRAMES__SCREEN_AND_ROUTE_INDEX.md` + `02_UX_CONTRACTS__00...19` |
| Detailed Orders / Products / Mini-Store / WhatsApp UX freezes | `Pasted text(20261106-211340).txt` |
| Product mature-capability preservation | `Pasted text(20261106-201224).txt` + current Founder preservation rule |
| WhatsApp continuation / activation details | `Pasted text(20261106-201521).txt` + `Pasted text(20261106-211340).txt` |
| P0/P1/P2 inherited programme decisions and cleanup scope | `BHARAT_LAUNCHPAD_P2_CHAT_CONTINUITY_PLAN_FULL_CONTEXT_2026-11-07.md` + P2 master continuity |
| Shopify/Wix complete operational-order wiring | Current Founder review, 2026-11-07, after the new-order forensic audit |
| Shopify/Wix sanitized provider JSON preservation | Latest direct Founder approval AFTER the 13:11 UTC deferral: “Thk h ur recommendation jo json store karna tha normalised and seprate wala bhi isi me karo” (7 Nov conversation; Shopify/Wix order-only Pre-P3 carve-out) |
| COGS = Pre-P3 | Current Founder review, 2026-11-07 (Option A accepted; product-provider cost frozen at order-line, no write-back) |
| Single external store + primary Growth/Ask AI context (FD-CONN-07) | Latest direct Founder message: “ABHI KE LIYE OPTION A RAKHTE H LEKIN PRIMARY STORE PE HI GROWTH AI KAAM KARE”, followed by assistant confirmation and “OK”. |
| Shopify/Wix Growth+Ask AI READ/WRITE parity (FD-GROW-12/13, FD-AI-04, FD-INV-06) | Latest direct Founder request: “EXACT CAPABILITY SHOPIFY KO BHI MILNI CHAHIYE JITNA WIX KO H WRITE BHI HOGA”, followed by assistant reconciliation/confirmation and Founder “OK”. 29-row parity audit is supporting technical evidence, not the decision itself. |
| Owner-approved Wix inventory edit exception (FD-INV-05) | Direct Founder acceptance of Option A in current conversation; `PRE_P3_DUAL_PROVIDER_INVENTORY_AUDIT_5bc0e1b3/08_FOUNDER_QUESTIONS_ONLY_IF_REQUIRED.md`, `02_WIX_READ_SYNC_TRACE.md` (code evidence; runtime not checked) |
| WhatsApp live Pre-P3 + suppression + no silent sender fallback + no reconnect replay | Current Founder review, 2026-11-07 |
| Wix privacy scope / Shopify scrub preservation | Later Founder: “Jyda kaam ni agar wix ki policy ni bolta h delete karne ko to ni delete karo”; keep Shopify existing scrub, block removed-provider live phone lookup; distinguish privacy-rights erase from disconnect |
| Admin functional completion + Vendors & Shipping grouping | Current Founder review, 2026-11-07 |
| Client Analytics retire / Admin Analytics preserve / Product Sales retire / impersonation Post-P3 / company export Owner-only | Latest Founder reconciliation decisions, 2026-11-07; export Owner-only supersedes old Owner/Admin |

If a future audit finds a conflict between this registry and a primary decision source, **do not silently choose one**. Report the exact conflict. The latest direct Founder decision still wins under §0.

## 0A.2 CAPABILITY-MANIFEST PRESERVATION RULE

This registry is the decision authority, but it is **not allowed to accidentally retire a mature micro-capability merely because that micro-capability is not repeated as its own FD bullet**.

Use the final Pre-P3 handoff package as the secondary capability manifest:
- `01_FINAL_FULL_SYSTEM_WIREFRAMES__CAPABILITY_COVERAGE_MATRIX.md`
- `01_FINAL_FULL_SYSTEM_WIREFRAMES__SCREEN_AND_ROUTE_INDEX.md`
- `02_UX_CONTRACTS__00...19`
- `BHARAT_LAUNCHPAD_PRE_P3_COMPLETE_HANDOFF_2026-11-07__00_READ_ME_FIRST.md`

Rules:
- Any capability marked **PRESERVE** remains protected unless this registry explicitly RETIRES or supersedes it.
- An item marked **UX REDESIGN / MERGE** may change placement/presentation, but its mature business behaviour must not disappear unless explicitly retired.
- **PROVISIONAL / DECISION REQUIRED / NOT PROVEN** items are not silently promoted into Founder decisions. Audit them and preserve safe current behaviour until resolved.
- If the handoff package and this registry conflict, the authority order in §0 applies; the latest direct Founder decision wins.
- A forensic audit must therefore check both: **decision compliance** and **capability preservation**.

- **Status:** GLOBAL PRESERVATION GUARDRAIL — LOCKED.


**Manifest drift identified 7 Nov (not current functionality proof):** `GRW-A-01` holds client Analytics until P5 although newer Founder retired it now; `CAT-L-01/PLT-097` blanket Admin Products retirement conflicts with retaining useful Admin Products; `PLT-107` impersonation is Post-P3 rather than permanently retired; `PLT-108` must not expose unguarded ER diagram; `PLT-065` WhatsApp settings route exists though manifest provisional; add an explicit `Do not WhatsApp` Pre-P3 test entry. The 506 IDs are unique, but status wording is inconsistent. Reconcile these in acceptance/manifest *without rewriting historical source evidence*.

## 0B. PHASE-CLOSURE DOES NOT SHIELD REGRESSIONS

- P0/P2 being historically CLOSED means do not casually reopen those programmes or rerun waived/destructive work.
- It does **not** mean the forensic audit must assume every old `PASS/CLOSED/DONE` claim is still functionally true.
- The audit may classify a prior claim as `STILL TRUE`, `TRUE THEN — LATER REGRESSED`, `PARTIAL`, `DISCONNECTED`, `TEST PASSED BUT JOURNEY FAILED`, or `NOT PROVEN`, with evidence.
- This distinction is mandatory so historical governance does not hide current Pre-P3 regressions.

---


> **V5 critical-review note:** V4 was re-audited against the detailed Founder UX conversation, the frozen Vendor/Shipping decision record, the final handoff/KB, recent audit overrides, and the current conversation. V5 corrects misclassified decisions, restores explicit frozen UX/operational rules that V4 compressed, and adds a strict provenance/no-assumption rule. Where an older decision was later superseded, only the latest Founder-approved rule remains authoritative.

# 1. PROGRAMME / PHASE AUTHORITY

## FD-PROG-01 — P0 remains closed
- **Decision:** Do not reopen Phase 0 or chase waived residual local checks.
- **Carry forward:** tenant isolation, least privilege, token safety, privacy, deletion/retention, auditability, webhook verification, safe scaling, no plaintext credentials, no destructive smoke tests.
- **Phase:** inherited safety baseline.
- **Status:** LOCKED.

## FD-PROG-01A — Inherited Phase-0 irreversible safeguards
These remain active unless the Founder explicitly supersedes them:
- Migration `294` must NEVER be applied remotely.
- Do not rerun Phase-0 migrations merely for cleanup/verification.
- No destructive smoke tests.
- Do not reintroduce plaintext credentials.
- Do not casually rotate/delete the active Delhivery encryption key merely during Pre-P3 cleanup.
- Do not manually revoke sessions/recovery tokens or send the deferred recovery emails without fresh Founder approval.
- Do not modify payment/refund/shipment state merely to prove a closeout check.
- **Status:** LOCKED SAFETY INHERITANCE.

## FD-PROG-02 — P1 mature capability must be preserved
- **Decision:** P1 introduced mature company membership, roles, Team foundation, entitlements, order transitions, stock protection, WhatsApp templates, tracking restoration, Growth foundations, and release discipline. Later work must not casually rebuild or break these.
- **Phase:** inherited mature system.
- **Status:** LOCKED.

## FD-PROG-03 — P2 remains historically closed; closure does not shield regressions
- **Decision:** P2 production closure remains an authoritative **release-governance/history fact**. Pre-P3 is not a request to casually reopen or rebuild P2.
- **Critical qualification:** P2 CLOSED is **not** proof that every P2-era capability is still correct today. The forensic audit may classify a P2 item as `STILL TRUE`, `TRUE THEN / LATER REGRESSED`, `PARTIAL`, `DISCONNECTED`, `TEST PASSED BUT JOURNEY FAILED`, or `NOT PROVEN` when current code/evidence supports that conclusion.
- **P2 role:** self-serve SaaS foundation, multi-company, onboarding, Team activation foundations, Company/Brand, Connections, Domains, Privacy, Plans/Entitlements.
- **Status:** LOCKED GOVERNANCE + FORENSIC QUALIFICATION.

## FD-PROG-04 — Pre-P3 definition
- **Decision:** Pre-P3 must be a **real client-ready ecommerce operating system for the invited cohort**, not a demo, analytics shell, or collection of disconnected modules.
- **Acceptance:** a normal client can run day-to-day ecommerce operations end-to-end inside Bharat Launchpad.
- **Status:** LOCKED — TOP-LEVEL ACCEPTANCE RULE.

## FD-PROG-05 — Mature capability first
- **Decision:** Preserve mature existing capability, then respect Founder decisions, then improve UX; redesign only where genuinely necessary.
- **Rule:** if a mature system already works, reconnect/reuse it instead of rebuilding it.
- **Status:** LOCKED.

## FD-PROG-06 — Evidence before new implementation
- **Decision:** Before further Pre-P3 implementation, reconcile what is already PASS / PARTIAL / DISCONNECTED / REGRESSED / MISSING. Do not assume a feature is missing just because one new path is broken.
- **Status:** CURRENT GOVERNANCE LOCK.

---

## FD-PROG-07 — Every retained mature system must remain operational
- Pre-P3 acceptance is not limited to the core Orders screen. Any mature capability that remains in the product must still work end to end unless explicitly RETIRED or DEFERRED.
- This includes merchant UI, public storefront, Vendor Portal, Influencer surfaces, auth/recovery/invites, legal/privacy routes, Admin operational tooling, Broadcast and other protected mature paths.
- A route/component merely existing is not enough; its real actions, permissions, states and downstream contracts must be usable.
- **Status:** LATEST FOUNDER OPERATING PRINCIPLE.

---

# 2. END-TO-END CLIENT ACCEPTANCE CONTRACT

## FD-E2E-01 — Required real merchant journey
A real merchant must be able to complete:

`Company/Brand setup → Connections → Products → Vendor → Inventory → New Order → Complete Operational Order → Customer Communication → Vendor Assignment → Confirm → Stock Handling → Shipping Readiness → Delhivery/Own Courier → AWB/Label → Tracking → WhatsApp Journey → Delivered/Cancelled → Growth/COGS Truth → History/Audit`

Sources to support in Pre-P3:
- Shopify **OR** Wix (one active external commerce connection per company for Pre-P3)
- Mini-Store (optional, independent native sales channel)

Legacy Google Sheets / CSV / Admin manual-order creation is a retirement/cleanup concern, not a required current sales channel. Audit those historical paths for safe close-out and mature-capability dependencies, but do not count them as a required Pre-P3 order-ingestion source unless a newer Founder decision explicitly restores one.

**Rules:**
- No manual DB edits.
- No retyping provider data that the provider already supplied.
- No fake/default fulfilment values.
- No silent fallback that changes business meaning.
- “Stored somewhere” is not enough; the operational flow must be able to use the data.

**Status:** LOCKED.

---

# 3. ORDERS / PROVIDER INGESTION / ORDER TRUTH

## FD-ORD-01 — Assign Vendor is not Confirm
- Assign Vendor only assigns.
- Explicit Owner/Admin Confirm remains separate.
- Confirm requires a vendor.
- Confirm does not create a shipment.
- **Status:** LOCKED.

## FD-ORD-02 — Operational lifecycle
- Tabs: **New / Confirmed / Shipped-In Transit / Delivered / Cancelled**.
- Ready to Ship = readiness badge, not lifecycle status.
- Cancelled orders remain visible in Orders.
- **Status:** LOCKED.

## FD-ORD-03 — Complete provider order must become operationally usable
**LATEST FOUNDER OVERRIDE.**

For new Shopify/Wix orders, the automatic pipeline must create/reconnect a **complete operational order** usable by the mature ecommerce system without manual retyping.

Required operational data includes at least:
- customer name;
- phone/shipping phone;
- email where provider access and source data make it available;
- full shipping address + pincode/city/state/country where available;
- item lines;
- SKU;
- variant/product identity;
- quantity;
- correct selling amount/total;
- normalized provider financial facts needed by operations/Growth, including subtotal, discounts, tax, shipping amount, refunds and currency where supplied;
- correct payment/COD/prepaid truth;
- provider order/source identifiers;
- provider creation time;
- fulfilment-relevant provider facts.

**This supersedes the practical result of the older P2-shaped “blank operational order” implementation.**

Provider commercial truth remains provider-owned; **the operational-order creation/snapshot does not write back** to Shopify/Wix. This does not prohibit **separate, explicitly approved Growth provider actions** under FD-GROW-13 (product/coupon/blog/inventory).

- **Phase:** Pre-P3 MUST.
- **Status:** LOCKED.

## FD-ORD-03A — Every current ingestion path must satisfy the same complete-order contract
- Background/manual sync, webhook and replay/reconciliation paths for the same current Shopify/Wix source must converge on the same fulfilment-required data contract; a legitimate order must not become incomplete merely because a webhook was missed or because sync requested fewer fields.
- Webhook is an event transport, not a special business source for phone/address/items that normal order fetch intentionally omits. If the provider/API permits a required field for the approved use case, current-source sync must request/map it or fail truthfully.
- Provider pagination must not silently truncate fulfilment-critical line items or financial/refund facts. Fetch all required pages within the supported contract, or persist/raise a truthful `incomplete` state that blocks unsafe fulfilment rather than pretending the order is complete.
- **Class:** TECHNICAL / SECURITY CONSEQUENCE of FD-E2E-01 + FD-ORD-03; not a new Founder UX preference.
- **Status:** PRE-P3 MUST.

## FD-ORD-04 — Reuse mature order fulfilment model
- Prefer reconnecting the new automatic Shopify/Wix ingestion to the mature operational order model already proven by older Shopify/Wix/Mini-Store flows.
- Do not rewire every downstream system to compensate for a deliberately blank order unless evidence proves that is safer/necessary.
- **Status:** LOCKED.

## FD-ORD-05 — Provider facts and operational snapshot
- Shopify/Wix remain source of truth for provider-owned commercial data.
- Launchpad may maintain normalized provider copies and a fulfilment-ready operational snapshot.
- No manual editing **of Launchpad snapshots** that pretends to change provider truth; independent, approved Growth provider write actions under FD-GROW-13 target the real provider explicitly.
- **Status:** LOCKED.

## FD-ORD-05A — Operational shipping-contact override is allowed
- For Shopify/Wix orders, the provider remains source of truth for provider-owned commercial facts, but the **operational shipping contact may be corrected/overridden** for fulfilment by the authorised merchant role under the mature order-contact flow.
- A shipping-contact correction must not masquerade as a write back to Shopify/Wix or mutate provider commercial truth.
- Preserve attribution/audit of the operational correction where the mature system already supports it; do not use this permission to make price, payment, line-item or provider-status facts manually editable.
- **Source:** frozen L4 / Amendment-7 order decision.
- **Status:** LOCKED.

## FD-ORD-06 — Reassignment
- Vendor reassignment allowed before shipment activity under controlled Owner/Admin flow.
- Reassignment does not replay stock/payment/message side effects.
- Any shipment claim/booking/AWB/ambiguous shipment activity blocks reassignment.
- **Status:** LOCKED.

## FD-ORD-07 — Shipment failure / label failure
- Shipment creation failure leaves order Confirmed.
- Label generation is separate; label failure must not invalidate a successfully created shipment/AWB.
- **Status:** LOCKED.

## FD-ORD-08 — Manual Delivered
- Delhivery delivery status normally follows provider truth.
- Exceptional manual Delivered is allowed for Owner/Admin where required, including Own Courier/manual scenarios.
- Mandatory reason + confirmation + audit.
- Impossible lifecycle transitions must be blocked.
- **Status:** LOCKED.

## FD-ORD-09 — Cancellation
- Preserve smart cancellation.
- Customer cancellation communication may be automatic where configured.
- Vendor cancellation messaging remains controlled/manual where applicable.
- **Status:** LOCKED.

## FD-ORD-10 — Canonical business truth vs Internal Status
- `commerce_status` is the canonical business/order truth for current-source orders.
- Current-source orders are created as `placed`; only explicit Owner/Admin Confirm moves business truth to `confirmed`.
- `bk_status` remains **Internal Status only**: merchant labels/workflow notes, never canonical commerce truth.
- Internal Status changes must not trigger stock, payment, shipping, customer messaging, cancellation, Delivered or refund side effects.
- Business truth and shipping/delivery truth remain separate.
- **Status:** LOCKED.

## FD-ORD-11 — Source provenance + one provider order → one operational order
- `orders.source` must truthfully identify Shopify / Wix / Mini-Store / retained historical source; new current orders must not silently inherit a legacy `google_sheet` default.
- Shopify/Wix sync, webhook and replay for the same provider order must converge on **one** provider identity and one linked operational order.
- Duplicate provider events must not create duplicate operational orders or duplicate downstream side effects.
- **Status:** LOCKED.

## FD-ORD-12 — Payment classification fails closed
- Never guess COD vs prepaid/online-paid.
- If payment truth is unavailable/ambiguous, fulfilment must stop with a truthful actionable state rather than defaulting to COD, `Manual`, or zero amount.
- New orders must not depend on retired Razorpay infrastructure.
- Historical Razorpay labels may remain as history but are not valid payment truth for new fulfilment.
- Mini-Store `Prepaid` means payment collected outside Launchpad; Launchpad is not the payment processor.
- **Status:** LOCKED.

## FD-ORD-13 — Return / DTO / refund truth
- DTO/return movement from the customer location is **return in progress / revenue at risk**, not automatically a refund.
- Realized revenue reverses only when a successful return completion is confirmed by trustworthy truth.
- Refund truth comes from provider refund facts where applicable.
- Mini-Store does not invent a Launchpad refund fact/payment flow.
- Retired `after_sale_status` / legacy refund-obligation logic must not become a second financial truth.
- **Status:** LOCKED.

## FD-ORD-14 — Legacy order columns / labels
- `orders.notes` remains a valid retained operational field.
- Legacy `orders.aging` is retired.
- Legacy `orders.payment_status` is retired where normalized/source-specific payment truth replaces it; do not use it as a second payment truth.
- `Hold` remains an Internal Status/label only and must not acquire canonical commerce side effects.
- **Status:** LOCKED CLEANUP / TRUTH.

## FD-ORD-15 — Orders workbench UX and mature controls
- Orders list is primarily for monitoring/navigation; **no consequential quick-action clutter**.
- Use lifecycle tabs plus advanced filters inside the selected lifecycle; preserve mature search, source visibility and export capability.
- CSV/export must not resurrect retired finance/margin fields as current truth; unknown supplier cost is shown as Unknown/Unavailable, never zero.
- Detail experience keeps operational context separated: **Fulfilment / Overview / Shipment / Messages / Activity**, with a smart context-aware default.
- `Messages` is the communication center for customer/vendor communication history and relevant send/delivery state; consequential journey CTAs stay in the guided Fulfilment flow rather than being duplicated here.
- `Activity` is the full audit/history timeline for meaningful order changes such as status transitions, vendor assignment/reassignment, shipment/tracking events, message actions, actor attribution and provider-sync truth where available.
- Ready to Ship stays readiness, not a lifecycle status.
- **Status:** LOCKED UX/PRESERVATION CONTRACT.

## FD-ORD-16 — Guided Fulfilment experience
**DIRECT / ACCEPTED FOUNDER UX FREEZE.**

Within one Order Detail, the Fulfilment experience is a guided progressive journey rather than disconnected mini-systems:

`1 Assign/Reassign Vendor → 2 Confirm Order → 3 Shipment/Manual Dispatch → 4 Notify Vendor → 5 Customer Tracking`

Frozen interaction rules:
- Confirm Order is available in the guided fulfilment step and may also have a top/sticky fast action; both invoke the same canonical action.
- A visible controlled `Reassign Vendor` action remains available after Confirm only while shipment activity has not started, subject to FD-ORD-06 / FD-SHIP-07.
- Once shipment activity blocks reassignment, the frozen user-facing guidance is: **“Shipment already created. Cancel/close the shipment before changing vendor.”**
- The company's preferred shipping method is preselected; Owner/Admin may `Change Method` for that order only.
- Shipment failure keeps the shipment step open with a truthful error and controlled Retry / Change Method; no rollback of Confirmed truth.
- Shipment success and label generation are separate; label failure gets its own retry without rebooking.
- After successful shipment/AWB creation, **Step 4 automatically expands** with a ready-to-send Vendor WhatsApp preview and manual `Send WhatsApp to Vendor` action for Owner/Admin.
- After Vendor notification is successfully sent, **Step 4 collapses into a completed summary and Step 5 `Send Customer Tracking` automatically expands**.
- Step 5 is smart/state-based: it shows current real tracking when available, allows the frozen Add/Update Tracking flow where applicable, and exposes the appropriate Send/Resend Tracking action without fabricating tracking.
- Own Courier Manual Dispatch moves the order to **Shipped / In Transit** even if tracking is not yet available; optional tracking can be added/updated later.
- Customer tracking uses current real tracking details; prior tracking changes/sends remain in Activity/History.
- Shipment area exposes truthful `Last synced` plus current-order `Refresh Status`.
- Real courier events may trigger the frozen automatic customer journey; the UI should show latest relevant send/event truth.
- Cancellation is a guided/smart flow with reason, consequences, sequencing and audit; customer cancellation communication may be automatic where configured, vendor communication remains controlled/manual.
- **Status:** LOCKED FOUNDER UX / FUNCTIONAL CONTRACT.

---

---

# 4. PROVIDER DATA PRESERVATION

## FD-DATA-01 — Shopify/Wix order JSON preservation is Pre-P3 scope (later direct Founder override)
**LATEST FOUNDER DECISION.**

For Shopify/Wix order ingestion:

`Provider → sanitize/filter → preserve useful structured provider snapshot/event → normalized provider tables → complete operational order → downstream operations`

Preserve useful structured provider-native information needed for future Growth/Ask AI/product evolution, including appropriate IDs, event type, timestamps, useful metadata, and schema/API version where practical.

Do NOT blindly persist:
- access tokens;
- secrets;
- credentials;
- auth headers;
- unnecessary huge media/blobs;
- prohibited/unneeded sensitive data.

Privacy/redaction/tenant isolation override data preservation.

- **Status:** LOCKED — Pre-P3 for Shopify/Wix order ingestion.

## FD-DATA-02 — Full cross-provider raw-data architecture remains Post-P3
- Do not turn Pre-P3 into a full Meta/GA4/WhatsApp/all-provider raw-data redesign.
- The architectural principle remains a future guardrail.
- **Status:** POST-P3.

---

# 5. PRODUCTS / PRODUCT ONBOARDING

## FD-PROD-01 — Product Onboarding is protected mature capability
Preserve:
- create/edit;
- single/variant products;
- Vendor, Category, Sub-category, Vendor Price, Selling Price, Product Type, Check Availability and Additional Info fields/workflows where already supported;
- Description + existing AI Enhance/Description behaviour;
- color/options/SKU/tags/featured/ready-to-ship behaviour where already supported;
- categories/subcategories;
- shared-vendor product master;
- client-created product privacy;
- visibility / Hide from Store;
- media upload/reorder rules, including mature image + video upload behaviour;
- stock/inventory/price/cost behaviour;
- contextual Broadcast actions/status;
- Shopify/Wix source badges and read-only provider commercial facts;
- AI Description, AI Color and AI Price helpers;
- validation that prevents in-progress form data being overwritten or lost on early submit;
- explicit manual-vs-provider source truth where already supported.

Do not rewrite business logic merely for visual simplification.
The exact historical Q1–Q16 wording is not fully recoverable from retained continuity, so do not invent additional Product rules; preserve current mature capability unless a later explicit Founder decision supersedes it.
- **Status:** LOCKED.

## FD-PROD-01A — Products list must not oversimplify mature capability
- User-facing module name may be `Products`, while mature Product Onboarding/upload capability remains intact.
- Preserve a useful detailed Products list with real search/filters/status/source context rather than replacing the mature workflow with a shallow 4-field catalog form.
- Contextual Broadcast actions/status and product visibility remain available where mature.
- **Status:** LOCKED PRESERVATION RULE.

## FD-PROD-02 — No provider-catalog merge project in Pre-P3
- Do not merge Shopify/Wix catalog into Launchpad Products as a new architecture project now.
- Preserve existing Launchpad Products and provider catalog behaviour.
- **Status:** LOCKED.

## FD-PROD-03 — No ERP-style inventory / no new product Draft-Publish lifecycle
- Keep product UX clean and operational, not ERP-heavy.
- **Do not introduce a separate Product Draft → Publish lifecycle.**
- Preserve existing form-state/save protection and mature create/edit behaviour, but do not reinterpret that as a new catalog lifecycle state.
- **Status:** LOCKED / V3 CONTRADICTION CORRECTED.

## FD-PROD-04 — Final Product UX decisions (20-question reconciliation)
These are the final outcomes of the Product Founder review and supersede earlier mock/wireframe simplifications:

- User-facing module name = **Products**; mature Product Onboarding capability remains underneath.
- Preserve current create/edit flow; no forced new wizard.
- Preserve existing Single/Variants product-type behaviour; no new variant architecture.
- Preserve existing Category/Sub-category behaviour; no taxonomy redesign in Pre-P3.
- Shared/admin-vendor product master facts remain protected/read-only to ordinary clients as already designed; client-created products stay company-private by default.
- Normal storefront action is **Hide from Store**; permanent delete only when dependency-safe.
- Product visibility remains an obvious controllable state; hiding does not erase system/history.
- Preserve mature image/video selection, upload and reorder behaviour.
- Products screen retains contextual Broadcast actions/status where mature: Add to Broadcast Queue, Rebroadcast and eligibility/status context; user is not forced to enter WhatsApp first.
- Provider-owned Shopify/Wix commercial facts remain read-only and source/provenance is shown clearly.
- Preserve current stock/inventory and pricing/cost behaviour; no new ERP/pricing architecture solely for UX redesign.
- Existing Product Onboarding AI helpers (description/color/price assistance where actually built) are preserved; do not remove them or invent unrelated new AI capability.
- No new Product Draft → Publish lifecycle.
- Final Products list direction is **clean structured information-rich list/table**, not a simplistic 4-field modal and not the earlier accidentally-selected dense-table variant: real Search + useful filters + essential operational columns + compact actions.
- Overall rule: **organize current capability; do not rewrite business logic.**
- **Status:** LOCKED — LATEST PRODUCT FOUNDER REVIEW.

## FD-PROD-05 — Mature Price Rules / Shipping Rules remain functional
- Preserve existing Price Rules capability: list/stats, create/edit, activate/deactivate, delete with confirmation, category scope/picker and truthful matched-rule preview.
- Preserve the mature rule-application contract: saving a rule must not silently reprice historical/current products; any re-apply action is explicit and shows the affected-product count where supported.
- Preserve Shipping Rules / free-shipping rule configuration where mature; do not conflate these store pricing/shipping rules with the Delhivery connection master.
- Existing order/enquiry snapshots must not be silently repriced by a later rule edit.
- **Status:** PROTECTED MATURE CAPABILITY.

## FD-PROD-06 — Mature media / stamping safeguards remain functional
- Preserve image + video upload, main image/video selection, per-image colour metadata, AI colour detection where mature, product/lot-code reservation, image stamping, progress, and failed-stamp/drift guards.
- Price/category/code changes that make a stamp stale must not allow a knowingly stale stamped image to be silently published where the mature guard already prevents it.
- Preserve rollback/uniqueness/error handling around product save/upload rather than simplifying the UI in a way that loses data integrity.
- **Status:** PROTECTED MATURE CAPABILITY.

---

# 6. COGS / COST / PROFIT

## FD-COGS-01 — COGS is Pre-P3
**LATEST FOUNDER OVERRIDE.**
- COGS is not deferred.
- Shopify/Wix order COGS capture must be available for Pre-P3.
- **Status:** LOCKED — MUST BUILD/CONNECT.

## FD-COGS-02 — Provider is cost source of truth
- Shopify/Wix provider cost is source of truth.
- Launchpad does not write cost back to provider.
- **Status:** LOCKED.

## FD-COGS-03 — Freeze order cost
- At order ingestion, capture available cost per order line.
- Once historical order cost is frozen, later product cost changes must not rewrite it.
- If cost was missing, later provider sync may fill only the missing cost.
- **Status:** LOCKED.

## FD-COGS-04 — Missing cost is not zero
- `COGS missing` / profit unavailable when cost is unknown.
- Never silently use 0 and inflate profit.
- Profit where known: Revenue - frozen COGS.
- **Status:** LOCKED.

---

# 7. VENDORS

## FD-VEN-01 — Vendor creation/readiness
- Only Vendor Name required to create.
- Missing shipping data = Setup Incomplete, not blocked creation.
- Delhivery readiness enforced at shipping time.
- Status = Active / Inactive.
- **Status:** LOCKED.

## FD-VEN-02 — Remove Vendor, preserve history
- User action is Remove Vendor, not blind Delete.
- Historical references preserved.
- Removal blocked when open orders depend on vendor.
- **Status:** LOCKED.

## FD-VEN-03 — Vendor privacy/sharing
- Platform-created vendors may be shared.
- Client-created vendors stay tenant-private.
- Promotion to shared = Platform Admin only.
- For shared vendors, the **global physical pickup master** (pickup address, city, pincode and pickup phone) is read-only to ordinary clients; Platform/Admin/Support-level operators manage that shared physical pickup master.
- The **Delhivery Channel is not one global shared channel**: each linked company uses its own company-specific Delhivery Channel mapping for that shared vendor; missing mapping blocks booking rather than falling back to a global/vendor-name channel.
- **Status:** LOCKED.

## FD-VEN-04 — Preserve Vendor → Product → Mini-Store chain
- Do not redesign taxonomy or mature vendor/product relationships unnecessarily.
- **Admin-onboarded shared-vendor products must continue reaching the already-linked client Mini-Stores/catalogs according to the mature working distribution behaviour.**
- Category/Sub-category normalization must not become a new hard visibility gate that makes existing shared products disappear.
- Client-created private-vendor/product behaviour remains tenant-private.
- **Status:** LOCKED.

## FD-VEN-05 — Inactive / sensitive vendor safeguards
- A vendor with active/open dependent orders must not be made inactive/removed in a way that breaks fulfilment; resolve/reassign/complete dependencies first.
- Historical vendor attribution on completed/cancelled orders remains visible.
- Sensitive vendor fields remain restricted to the already-frozen higher-trust roles; Staff must not gain sensitive data merely because a screen is simplified.
- **Status:** LOCKED.

## FD-VEN-06 — Staff vendor micro-permissions are not a new role-design project
- Existing frozen rule: vendor assignment/reassignment and consequential fulfilment actions follow the Owner/Admin safety boundary.
- Whether Staff may edit non-sensitive vendor profile fields is an implementation/audit question unless a direct security conflict appears.
- Do not invent a granular Roles & Permissions redesign in Pre-P3.
- **Status:** LOCKED SCOPE BOUNDARY.

## FD-VEN-07 — Vendor screen structure and fields
- Compact list: Vendor Name, Contact, City, Pickup Readiness, Delhivery Channel, Status, Actions; Category/Sub-category are filters, not main columns.
- Desktop may use table; mobile uses usable cards. Full details belong in detail/edit, not a 20+ column list.
- Detail is read-oriented; Edit is a separate form. Preserve sections: Basic Details, Product Category, Pickup & Shipping, WhatsApp & Broadcast, Business & Payment Details, Operational Details, Additional Details.
- Business/payment fields such as GST/PAN/bank/IFSC/UPI/Payment Terms remain where mature, with sensitive visibility restricted.
- Existing Vendor `Phone` is the Delhivery pickup phone. Do not substitute a WhatsApp group/JID field. Country remains supported; default India where the mature form does so.
- Vendor Broadcast configuration stays with Vendor operations rather than being collapsed into generic account WhatsApp settings.
- Preserve the already-frozen optional Vendor fields where the mature form supports them: **Preferred Courier, Average Dispatch Time, Return Handling Type, Vendor Registration Date and Remarks**.
- **Status:** LOCKED PRESERVATION/UX CONTRACT.

## FD-VEN-08 — Pickup-incomplete and shared-vendor behaviour
- Active but pickup-incomplete vendor remains assignable and is labelled `Setup incomplete`; it cannot create a Delhivery shipment until fixed.
- Inactive vendor is hidden from new assignment. Status model is Active / Inactive; `Suspended` is not a target state except temporary migration compatibility.
- When shipment is blocked, show exact missing fields and a direct Fix Vendor Setup path; after fixing, user retries Create Shipment manually—no automatic booking retry.
- Shared vendor physical pickup is one global master; client sees it read-only. A shared vendor requires a company-specific Delhivery Channel mapping for booking.
- **Status:** LOCKED.

---

---

# 8. SHIPPING / DELHIVERY / OWN COURIER

## FD-SHIP-01 — Navigation/master
- Parent navigation: **Vendors & Shipping**.
- Children: Vendors, Shipping Settings.
- Delhivery master configuration lives in Shipping Settings.
- Connections may show status, not duplicate the master.
- **Status:** LATEST LOCKED.

## FD-SHIP-02 — Vendor pickup is fulfilment source
- Company pickup locations are retired for this supplier-fulfilment model.
- Pickup must be based on assigned vendor.
- Required real **Delhivery Channel**, pickup address, city, **6-digit pincode** and pickup phone; no fake/default fallbacks.
- Delhivery Channel is mandatory. Vendor-name-as-Delhivery-channel fallback must not be used.
- **Status:** LOCKED.

## FD-SHIP-03 — Delhivery journey
Preserve/complete:
`Assign Vendor → Confirm → readiness validation → Create Shipment → AWB → Label → Tracking → provider delivery truth`

- Assign Vendor only assigns; it must not confirm, move stock, message the customer, or create shipment.
- Explicit Confirm requires an assigned vendor, but pickup-readiness is checked at shipment time rather than being a Confirm gate.
- COD/prepaid mapping must be correct.
- Provider cancellation blocks inappropriate booking.
- Duplicate shipment prevention required.
- Shipment/API failure keeps the order safely recoverable in Confirmed state; do not invent shipment success.
- If AWB creation succeeded but label generation fails, preserve the valid shipment/AWB and allow label retry; do not invalidate/rebook blindly.
- Ambiguous provider outcome must reconcile before retry; no blind duplicate booking.
- **Status:** LOCKED.

## FD-SHIP-04 — Own Courier
- Own Courier stays supported.
- Manual Dispatch remains supported.
- Pre-P3 frozen rule: Own Courier Manual Dispatch is prepaid-only; COD manual dispatch is blocked unless a later explicit Founder decision supersedes this.
- No fake tracking; if no tracking exists, tracking message is suppressed.
- Owner/Admin may override the default shipping method for one order where supported; that override affects that order only.
- Switching the company default between Delhivery and Own Courier affects future shipments only; never migrate, rewrite, cancel, or recreate existing shipments automatically.
- **Status:** LOCKED.

## FD-SHIP-05 — Consequential shipping permissions
- Vendor assignment/reassignment, Confirm, Create Delhivery Order, Manual Dispatch, Vendor WhatsApp/Resend Tracking where frozen, Cancel and Manual Delivered are Owner/Admin consequential actions unless a narrower mature rule is explicitly proven.
- Staff must not accidentally gain these through UI or direct API; server-side enforcement is required.
- Disabled UI may explain `Owner/Admin only` where the action is visible.
- Do not expand this into a granular Roles & Permissions redesign.
- **Status:** LOCKED SAFETY BOUNDARY.

## FD-SHIP-06 — Shipping setup truth
- Each merchant/company uses its own Delhivery account/token for its shipments.
- Delhivery token saved = configured/ready unless an explicit health check proves a problem.
- Test Connection is useful but is not a universal onboarding gate.
- If an explicit Test Connection fails, show Needs attention truthfully.
- Removing the Delhivery token does NOT silently switch the company to Own Courier; remain in Delhivery mode with Needs setup until the merchant explicitly changes method.
- Company pickup-location fallback remains retired; pickup setup belongs to the assigned vendor.
- Own Courier / Manual Shipping remains the explicit alternative/fallback chosen by the merchant, not an automatic token-removal fallback.
- **Status:** LOCKED.

## FD-SHIP-07 — Vendor reassignment after confirmation
- Before provider shipment activity/AWB/claim, Owner/Admin may perform a controlled audited vendor reassignment where the frozen flow allows it.
- Reassignment must not unconfirm the order, re-run Confirm, change stock/payment truth, send duplicate WhatsApp, or create a shipment by itself.
- After shipment/provider booking activity begins, reassignment is blocked.
- **Status:** LOCKED.

## FD-SHIP-08 — Shipment status refresh is per-order
- Background tracking sync may continue automatically.
- Manual `Refresh Status` must refresh the current order/shipment only; it must not unexpectedly refresh/change every company shipment.
- A refresh must not invent order state; only real courier truth changes shipping/delivery state.
- **Status:** LOCKED.

## FD-SHIP-09 — Tracking resend and Vendor WhatsApp
- `Resend Tracking` is a controlled Owner/Admin action when real tracking exists.
- If tracking was already sent, require confirmation before sending again and show the **last sent time** when available (for example: `Tracking was already sent at 4:30 PM. Send again?`).
- Never invent tracking solely to send a message.
- Vendor WhatsApp after shipment/AWB information exists remains manual/controlled; do not silently auto-send unless a separately frozen automation exists.
- **Status:** LOCKED.

## FD-SHIP-10 — Label is a separate artifact
- Shipment/AWB creation and label generation are separate.
- Generate Label / Print / Download must operate on the existing successful shipment rather than re-booking.
- Exact Staff permission for label print/download remains an audit/current-policy question; do not broaden roles by assumption.
- **Status:** LOCKED BEHAVIOUR / PERMISSION AUDIT.

## FD-SHIP-11 — Shipping page/setup visibility and method selection
- Owner/Admin Delhivery setup must be reachable; do not hide the real setup page behind an obsolete self-serve 404/flag behaviour.
- Fully retire `company_pickup_locations` from active fulfilment/readiness/UI once dependency-safe; any production table/data drop remains a separately approved destructive migration.
- Shipping Settings begins with **How do you ship orders?** → Delhivery OR Own Courier / Manual Shipping, then shows only relevant configuration.
- **Status:** LOCKED.

## FD-SHIP-12 — Exact confirmation/readiness boundaries
- Vendor is mandatory before Confirm. Pickup readiness is **not** required to Confirm; it is required when creating a Delhivery shipment.
- Own Courier / Manual Dispatch also requires an assigned vendor and a Confirmed order.
- Active pickup-incomplete vendor may be assigned but shipment is blocked until setup is fixed.
- **Status:** LOCKED.

## FD-SHIP-13 — Manual dispatch and tracking fields
- Own Courier tracking/AWB number is optional; courier name is optional.
- Without real tracking, suppress tracking communication. Tracking may be added later where the mature flow supports it.
- Manual Dispatch never fabricates tracking or delivery truth.
- **Status:** LOCKED.

## FD-SHIP-14 — Existing shipment immutability
- Changing vendor Delhivery Channel or pickup address applies to future bookings only. Existing AWBs/shipments remain untouched; never auto-rebook.
- After any AWB/booking/ambiguous shipment activity, normal vendor editing/reassignment is blocked until the shipment is safely cancelled/closed/reconciled under the controlled flow.
- **Status:** LOCKED.

## FD-SHIP-15 — Explicit label and action UX
- Generate Label is an explicit action after AWB creation; do not auto-generate it as a hidden side effect.
- Print/Download is separate from Generate Label.
- Owner/Admin-only consequential actions must be enforced server-side; disabled UI should communicate the restriction where the screen exposes the action.
- **Status:** LOCKED.

---

---

# 9. INVENTORY / STOCK

## FD-INV-01 — FINAL LOCK: Mini-Store availability; provider-owned inventory with narrow Wix Owner-approved edit exception
- **Latest direct Founder decision (2026-11-07):** "Mini-Store inventory ke liye final Founder decision: Option A. Shopify/Wix provider-owned stock read-only rahega. Is decision ko V10 ke saath reconcile karo; bina meri next authorization ke implementation mat shuru karna."
- **Mini-Store / Launchpad native enquiry:** preserve the existing **Check Availability → vendor reply → merchant confirmation** workflow. This flow does **NOT** require a new numeric-stock table or quantity-based inventory subsystem in Pre-P3. Creating, assigning, confirming, shipping, delivering or cancelling a Mini-Store order does **NOT** automatically decrement/replenish numeric stock.
- **Shopify/Wix:** each provider remains inventory source of truth. Launchpad may read/sync inventory information as needed; **no order lifecycle event** may automatically decrement/restore a local ledger or write stock back to either provider. **Wix retains its merchant-initiated, explicitly Owner-approved edit under FD-INV-05. Shopify now has a corresponding narrowly authorised, merchant-initiated, explicitly approved edit as part of FD-INV-06 / FD-GROW-13, not automatic write-back.** The broad V10.2 Shopify read-only prohibition is superseded only for that explicit approval-gated action. All other provider stock writes remain unauthorised until separately verified/approved.
- **Universal safety:** vendor notification, vendor assignment, WhatsApp, shipments and status-only actions must not mutate stock as side effects. No arbitrary `current_stock=5`, double-decrements, cross-tenant stock effects or unsourced quantities.
- **Historical evidence, not current instruction:** P1's Confirm-reduces/Cancel-restores rule and the CR2/370 changes remain part of the forensic history. The latest direct Founder choice supersedes P1's stock-mutation rule for the two explicitly decided source groups.
- **Manual/native orders beyond the Mini-Store enquiry workflow:** no new stock-mutation permission is inferred. Audit whether any mature current behavior exists and report exact evidence before proposing a change.
- **Important:** this locks the *business behavior*, not a claim that every old API/DB writer is safe or retired. Existing unintended stock writes remain separate Pre-P3 remediation findings, to be fixed **only after explicit implementation authorization**.
- **Status:** LOCKED DIRECT FOUNDER DECISION — Q-STOCK CLOSED; NO IMPLEMENTATION AUTHORIZED.

## FD-INV-02 — No automatic order-driven restoration under the locked no-decrement model
- Because Mini-Store does not automatically decrement numeric stock, cancellation/return must not invent a compensating numeric restore. The existing vendor-availability process remains authoritative for availability enquiries.
- For Shopify/Wix, no second local restore and **no automatic provider write-back** on cancellation, returns or failed shipments. This does not prohibit the explicitly authorised Wix Owner-approved edit under FD-INV-05 or the newly approved Shopify equivalent under FD-INV-06.
- Historical P1 stock movement/restore code must be audited for active callers, old paths and cleanup implications. Do not delete schemas or historical information merely because they are old; follow the non-destructive cleanup/approval guardrails.
- **Status:** LOCKED CONSEQUENCE OF FD-INV-01; HISTORICAL PATH CLEANUP STILL REQUIRES EVIDENCE AND AUTHORIZATION.

## FD-INV-03 — Stock-safe idempotency and missing mapping
- Duplicate provider orders/events must not create duplicate orders, customer messages, vendor notifications or other effects; **no order-triggered stock movement is authorised** by this registry.
- Missing SKU/product/source mapping must produce a truthful warning or fail-safe state, not fabricated stock or a hidden inventory write. Preserve company isolation and correct product identity.
- **Status:** LOCKED SAFETY INVARIANT.

## FD-INV-04 — Old historical orders
- Old historical orders are not the active stock truth focus; Founder plans to delete them.
- Do not build large compatibility architecture around them.
- **Status:** LOCKED.


## FD-INV-06 — Shopify inventory: newly approved, explicit merchant-initiated Owner-approved WRITE exception
- **Authority:** latest direct Founder approval of exact Shopify/Wix Growth READ+WRITE parity, including the prior assistant's explicit Shopify inventory-update proposal, followed by Founder "OK".
- Shopify inventory stays Shopify-owned. **No** automatic order-created/confirmed/cancelled/delivered stock decrement/restore, sync write-back, vendor notification mutation or scheduled stock reconciliation writes.
- Shopify may receive a **merchant-requested, previewed, explicitly Owner-approved inventory adjustment** comparable to Wix's current workflow, using Shopify's correct inventory item/location and supported API semantics, scopes, company/connection guards, action audit and failure reconciliation.
- This supersedes the broad older phrase "Shopify inventory read-only" **only for the explicit approved write action**. It does NOT authorize arbitrary inventory modification, independent AI writes, Shopify API scope changes right now, or provider execution in production during audit.
- Minimum-scope permission/reauthorization and location/compare-and-swap safety details need implementation-time evidence. Missing permissions/state => truthful disabled/Needs Setup; do not fall back to another store/provider.
- **Status:** FOUNDER-LOCKED PRE-P3 PARITY TARGET; NOT BUILT/NOT PROVEN; IMPLEMENTATION NOT AUTHORIZED.

## FD-INV-05 — Wix inventory write: existing explicit Owner-approved action PRESERVE (Option A)
- **Authority:** Latest direct Founder approval: **"Wix inventory write action ka final Founder decision Option A. Isko V10.1 se reconcile karo. Implementation abhi authorized nahi hai."** This narrows V10.1's blanket "read-only" wording for Wix, **without** changing the Mini-Store decision; Shopify was read-only at V10.2, but a new approved-action exception is locked in V10.3 under FD-INV-06.
- **What is permitted:** Preserve the existing **merchant-initiated** Wix inventory edit via **Growth → Store Doctor → Prepare stock request / approval workflow → `wix_update_inventory`**. Execute **only after explicit Owner approval**, with current server-side authorization, company/tenant isolation, provider-action gating, request/payload integrity, confirmation and audit/history. A request existing in the UI is **not** execution permission. Audit what is already implemented versus merely expected; do not claim production activation.
- **What is NOT permitted:** No order-Confirm/Cancel/Delivered-triggered stock mutation, no background auto-write/reconciliation, no silent provider writeback, no cross-store/company target, no ungated Wix/Shopify inventory writes. The **earlier no-Shopify-write phrase is superseded** by FD-INV-06, which allows an explicit approved Shopify inventory action only. No arbitrary legacy `stock=5` mutations. Any unavailable gate/permission must fail closed.
- **Runtime caveat:** Static audit found `wix_update_inventory` PATCH path and provider execution gates; **actual production flag values, approvals and live execution have not been verified**. The existing P2 provider-execution-enabled state is a separate Founder-approved condition; **do not change any flags** merely to satisfy this decision.
- **Acceptance checks for eventual implementation/review:** (1) no owner approval → no PATCH; (2) explicit Owner-approved action + existing gates + correct Wix store/inventory-item identity → permitted action, audited; (3) wrong company/store, denied role, modified request, disconnected provider or gate unavailable → fail closed; (4) normal order events never write stock; (5) Shopify inventory is unchanged **unless** a separate, explicit approved Shopify action under FD-INV-06 is authorised; (6) preservation of mature Growth action and Ask AI approval/execution guardrails. These are **future tests, not claims of current PASS**.
- **Status:** LOCKED — FOUNDER-ACCEPTED OPTION A; NARROW V10.1 OVERRIDE; **NO IMPLEMENTATION / PROVIDER EXECUTION AUTHORIZED**.

---

# 10. WHATSAPP — LIVE PRE-P3

## FD-WA-01 — WhatsApp customer order journey is live capability in Pre-P3
**LATEST BASELINE CORRECTION.**
- Do not treat customer messaging as a Post-P3 or permanently dark feature.
- Product must be safe and functional for live order messaging in Pre-P3.
- Per-client activation may still be explicit; connecting an account alone does not have to auto-enable automation.
- **Status:** LOCKED.

## FD-WA-02 — Common journey / no duplicate Order Placed
- Customer order journey uses common event/outbox architecture.
- Retire duplicate direct Mini-Store Order Placed sender.
- Deduplication/idempotency required.
- **Status:** LOCKED.

## FD-WA-02A — All Mini-Store customer-facing messaging uses the common outbox
- Not only Order Received: enquiry-stage customer messages that remain active (for example enquiry confirmation/received, availability update, address request and approved follow-up/clarification events) must use the common outbox architecture.
- Keep enquiry events in their own event domain such as `enquiry.*`; do not force them into the six-step order journey.
- Retire direct customer-send paths wherever the outbox can own idempotency, retries, logging/status and provider delivery.
- **Status:** LOCKED FOUNDER CLARIFICATION.

## FD-WA-03 — Journey events
Required functional customer journey includes the applicable events:
- Order Received;
- Confirmed;
- Shipped/Tracking;
- Out for Delivery;
- Delivered;
- Cancelled where configured.

No fake tracking events.
- **Status:** LOCKED.

## FD-WA-04 — Customer suppression
**LATEST FOUNDER RE-APPROVAL AFTER PRE-P3 MESSAGING WAS CONFIRMED LIVE.**
- Build a customer/order-level `Do not WhatsApp` / suppression control before live Pre-P3 automated order messaging.
- At minimum, suppression must block future **automatic transactional order-journey messages** for that customer/order.
- Do **not** assume broader manual-send or Broadcast semantics from the older deferred discussion. Audit the current model and implement the smallest safe behaviour; if a manual override is retained, it must be explicit and auditable rather than silently bypassing suppression.
- **Status:** LATEST LOCKED — PRE-P3 MUST FOR AUTOMATIC JOURNEY.

## FD-WA-05 — Per-template sender + sender safety
- **Each template has an explicit selected connected WhatsApp sender/account.** This supersedes the earlier default-account + group-override recommendation.
- Only connected accounts are selectable.
- The template remembers its selected sender.
- If that sender disconnects: **no silent fallback to another number**; automatic/manual send through that template is blocked until corrected and the template/account shows **Needs attention**.
- Manual preview clearly shows the sender identity/number.
- **Status:** LOCKED FOUNDER DECISION.

## FD-WA-06 — Reconnect / held messages
- Old held/blocked messages do not automatically replay after reconnect.
- Recovery/resend is manual/controlled.
- **Status:** LOCKED.

## FD-WA-07 — Message truth and retry
- Truthful statuses only: Waiting / Sent / Could not send unless stronger delivery evidence exists.
- Limited auto-retry, then manual.
- Ambiguous outcome blocks blind resend.
- **Status:** LOCKED.

## FD-WA-08 — Templates
- Grouped templates, variables/chips and preview.
- Reset requires confirmation.
- Template OFF cancels/stops **unsent automatic queued messages**; re-enable does not replay history.
- If the **specific template itself is OFF**, automatic sends remain blocked, but authorised Owner/Admin may still perform an explicit **manual send after preview + explicit confirmation**; the manual action must be visible/auditable and must not silently re-enable automation.
- Template edits affect future/new messages. Preserve the existing safe rendered/versioned content for already queued messages where that behaviour already exists; per the later gap review, do not create a large new template-versioning subsystem solely for Pre-P3 unless current runtime behaviour is unsafe.
- **Status:** LOCKED.

## FD-WA-09 — Broadcast preserve
Preserve mature Broadcast capability: Bulk Add eligibility, queue/active state, Rebroadcast, Bulk Remove, media/templates, Send Test, pause/reconnect/resume, recent activity.
- No Broadcast redesign.
- **Status:** LOCKED.

## FD-WA-10 — Staff scope
- Do not start a granular Roles & Permissions redesign in Pre-P3.
- Preserve the already-frozen safety boundary that Staff must not gain customer messaging authority through accidental paths; fix direct security holes minimally if found.
- **Status:** LOCKED / NO ROLE REDESIGN.

## FD-WA-11 — Live vs initial/backfill boundary
- Provider ingestion must explicitly distinguish `live` vs `initial` vs `backfill` (or an equivalent persisted business contract).
- `Order Received` is eligible only for genuinely live new orders after the activation boundary.
- Initial sync, backfill, legacy/CSV/Sheet/admin historical imports must not accidentally message customers as a new order.
- Do not infer “live” merely from whichever technical path happened to deliver the order.
- **Status:** LOCKED — PRE-P3 SAFETY.

## FD-WA-12 — Beta transport and activation defaults
- Evolution/Baileys transport is accepted for the limited beta cohort under the existing risk acceptance; migration to an official channel/provider remains later work.
- New invited-cohort companies may have automatic order updates enabled according to the frozen onboarding default.
- Existing production companies must not receive newly activated automatic customer messaging silently; their Owner must explicitly activate where the prior rollout default kept them OFF.
- Connecting a WhatsApp account alone must not retroactively replay old messages.
- **Status:** LOCKED / BETA RISK ACCEPTANCE.

## FD-WA-13 — Automation masters vs manual actions
- Settings → WhatsApp has an **Automatic customer updates** master for order-journey automation.
- Mini-Store automatic customer messaging has its own **Mini-Store Messages** group master plus individual event switches; turning the group master OFF preserves individual settings but stops automatic sends in that group.
- Master OFF means **automation OFF**, not an absolute communication ban: authorised Owner/Admin may still manually Send / Resend / Retry after the applicable preview/confirmation/safety checks.
- Staff must not gain customer-message authority through these manual paths.
- Manual sends/retries are recorded in History/Audit.
- **Status:** LATEST LOCKED.

## FD-WA-14 — WhatsApp information architecture and mature account controls
- Client sidebar WhatsApp is operational: **Broadcast + Message Activity**. Durable connection/template/automation configuration belongs in **Settings → WhatsApp**.
- Preserve mature account management: account list/status, QR connect/poll, reconnect/disconnect, Send Test and any already-supported official-account connection path.
- Transactional Message Activity is distinct from Broadcast history.
- Templates are organized into clear groups (Order Messages, Mini-Store Messages, and other real active groups) rather than one undifferentiated long list.
- **Status:** LOCKED PRESERVATION/UX CONTRACT.

## FD-WA-15 — Template editor / activity UX
**DIRECT FOUNDER UX FREEZE.**
- Use a **Guided Template Editor**, not a raw/unstructured long form.
- `Reset to Default` requires confirmation.
- New-client automation uses the frozen **guided activation** approach; do not silently treat connection alone as consent for every automation.
- Merchant-facing message status stays simple, with expandable technical detail when needed.
- Failed automatic messages use limited safe auto-retry, then manual Retry; ambiguous outcomes block blind resend.
- Message Activity defaults to **recent-first activity**, with useful operational filters, search/date handling and scalable pagination for older records.
- Clicking a Message Activity row opens a **detail drawer** showing the rendered message, recipient, related Order/Enquiry where applicable, sender account, manual/automatic origin, attempts and safe failure detail.
- Manual Send/Resend shows a preview before consequential send.
- Transactional Message Activity and Broadcast history remain separate surfaces.
- Already-queued/template-version behaviour should preserve the existing safe version semantics where present; per the later gap review, do not turn template-versioning into a large Pre-P3 rework/blocker unless evidence shows an unsafe runtime bug.
- **Status:** LOCKED UX / MINIMAL SAFE IMPLEMENTATION.

## FD-WA-16 — Broadcast UX freeze — preserve backend/state machine
**DIRECT FOUNDER UX FREEZE.**
- Do **not** invent a new campaign/batch backend. Preserve the mature product-broadcast queue → scheduler/business-hours/cooldown → worker → completed/retry/dead-letter model.
- Broadcast operational page uses the frozen simple structure: **Overview / Queue / Schedule & Controls**.
- Overview is operational, not a new analytics product.
- Queue exposes only safe actions supported by the existing state machine.
- Schedule & Controls exposes existing scheduler/business-hour/cooldown behaviour in merchant language.
- Broadcast uses an explicit selected sender account; do not silently reroute.
- Products screen may add eligible products to the existing Broadcast Queue; bulk selection/add is supported through the same queue/state machine.
- Existing Rebroadcast and Bulk Remove behaviour is preserved.
- Filter/search changes clear transient product selection so hidden items are not accidentally acted on.
- Preserve Send Test, pause confirmation, friendly failure reasons and explicit Resume after reconnect where already frozen.
- Preserve existing history/status visibility, but do **not** invent a new heavy standalone Broadcast History product in Pre-P3.
- No new Broadcast analytics/charts are required by this UX review.
- **Status:** LOCKED — PRESERVE + SIMPLIFY UX.

---

---

# 11. MINI-STORE

## FD-MS-01 — Mature storefront capability preserved
Preserve:
- collage/gallery;
- per-image Add to Cart;
- Check Availability;
- visitor WhatsApp capture;
- current pricing;
- enquiry and availability workflow;
- vendor query;
- enquiry → order linkage;
- supplier/vendor cost behaviour;
- hosted/custom-domain behaviour.
- **Status:** LOCKED.

## FD-MS-02 — First Publish + Live/Paused
- Existing stores remain live.
- New store requires first explicit Publish by Owner/Admin.
- Subsequent changes may go live automatically.
- States: Live / Paused.
- Pause keeps URL/data and shows temporary unavailable state to visitors.
- **Status:** PRE-P3 MUST.

## FD-MS-03 — Enquiry behaviour
- Each item can be Available / Not Available.
- Partial availability allowed.
- One combined customer response.
- Only available items convert to orders; separate supplier orders per vendor where applicable.
- Enquiry itself does not reduce stock.
- **Status:** LOCKED.

## FD-MS-04 — No duplicate fulfilment system
- Mini-Store shows order summary/status and Open Order.
- Fulfilment remains in the core Orders system.
- Tracking only when real.
- **Status:** LOCKED.

## FD-MS-05 — Mini-Store onboarding independence
- Merchant can onboard/use Mini-Store without requiring Shopify/Wix connection.
- **Status:** LOCKED.

## FD-MS-06 — Mini-Store configuration ownership
- Do not add a separate Mini-Store Integrations tab. Core flow remains Products → Enquiries → Orders.
- Mini-Store-specific presentation/configuration such as homepage/storefront settings, pixels and entry-gate/visitor behaviour stays with the Mini-Store/store configuration domain.
- Global provider/account masters remain in their frozen Settings/Connections locations.
- WhatsApp templates are edited in Settings → WhatsApp, not duplicated inside Mini-Store.
- **Status:** LOCKED.

## FD-MS-07 — Store product removal
- Normal storefront removal is **Hide from Store** / visibility change.
- Permanent delete is only used where dependency-safe; do not destroy shared/vendor/product history as a routine hide action.
- **Status:** LOCKED.

## FD-MS-08 — Shared/admin product presentation
- For a shared/admin-vendor product, protected master product facts stay read-only to the client.
- Company-specific Mini-Store presentation/visibility may remain editable where the mature architecture supports it.
- Do not create a new independent product-master copy merely for presentation.
- **Status:** LOCKED FOUNDER UX.

## FD-MS-09 — Storefront CTA / price preservation
- Founder froze the storefront direction as **Add to Cart + Check Availability with smart priority**, while immediately clarifying that the current working business logic must not be unnecessarily rewritten.
- Known price remains truthful; unknown/confirmation-required price must never become fake/zero solely to satisfy UI.
- Preserve current collage/gallery, per-image Add to Cart, Check Availability, WhatsApp capture and customer journey behaviour first; UX may improve clarity without changing the underlying commerce rule.
- No mandatory customer login is introduced by this UX review.
- **Status:** LOCKED PRESERVATION + UX DIRECTION.

## FD-MS-10 — Publish/paused gate is real storefront state
- Existing stores remain live.
- A new store must not behave publicly as Live before the one-time Publish decision is satisfied.
- `Paused` keeps the same URL/data but returns the clean temporary-unavailable customer state rather than silently serving a normal live storefront.
- Any entitlement/publish-route enforcement inconsistency is a technical defect to audit, not a reason to ignore the frozen Live/Paused model.
- **Status:** LOCKED / TECHNICAL ENFORCEMENT REQUIRED.

## FD-MS-11 — Mature carts / leads / store-design capability remains functional
- Preserve Abandoned Carts and Leads operational surfaces where mature, including useful filters/status and customer follow-up actions.
- Preserve Store Design capability: homepage/brand presentation, testimonials, tracking pixels/settings and entry-gate/form-visibility controls where mature.
- Storefront tracking configuration (Meta Pixel/CAPI, GTM, GA/other mature tracking integrations) must remain separate from the Meta Ads account connection; saving pixels must not mutate the Meta Ads connection.
- Entry-gate changes affect future visitor prompts; they do not rewrite existing visitor/lead history.
- **Status:** PROTECTED MATURE CAPABILITY.

---

# 11A. PUBLIC STOREFRONT / VENDOR PORTAL / INFLUENCER SURFACES

## FD-PUBLIC-01 — Public storefront is protected mature capability
Preserve the working shopper journey and domain routing, including where currently supported:
- homepage configuration / brand presentation;
- catalog/category grid, search, price filter, load-more/pagination;
- product page / lot-code route;
- entry gate / visitor capture;
- cart add/remove, shipping-charge calculation where currently supported, and server-side revalidation;
- Check Availability, with totals/value recomputed server-side rather than trusted from browser input;
- Find Product / requirement lead;
- customer address capture;
- product WhatsApp share/card;
- hosted/custom-domain routing and unknown-domain state;
- mobile-first storefront behaviour.
Public data must not expose vendor cost, margin, internal-only IDs or other protected operational facts.
- **Status:** PROTECTED MATURE CAPABILITY.

## FD-PUBLIC-02 — Public legal/privacy routes remain functional
- Preserve required public legal/privacy/data-deletion routes and provider-required deletion/deauthorization status surfaces.
- Final legal wording may depend on approved external text; do not fabricate approval.
- **Status:** PRE-P3 FUNCTIONAL / EXTERNAL COPY INPUT WHERE APPLICABLE.

## FD-PORTAL-01 — Vendor Portal stays functional
Preserve the mature Vendor Portal for approved linked vendors:
- vendor login/approval gate;
- assigned-order list/counts/filters;
- order details needed for fulfilment;
- vendor status update within allowed states (vendor cannot invent Delivered/Cancelled);
- shipped/in-transit update only with real AWB where required;
- label download/print;
- Mini-Store availability-query reply.
Retired vendor wallet/payment/payout surfaces do not return.
- **Status:** PROTECTED MATURE CAPABILITY.

## FD-PORTAL-02 — Influencer product/portal preserved; earnings retired
- Preserve useful Influencer marketplace/detail/enquiry flows and the approved Influencer Portal capabilities already in product: profile, packages, insights, enquiries, settings/Instagram connection where mature.
- Preserve mature client-side AI influencer recommendations only behind the existing required AI consent/data-access boundary; do not expose recommendation scoring without consent.
- Preserve influencer signup/application/approval states where mature.
- Influencer earnings/payout ledger remains retired per FD-RET-04.
- **Status:** PROTECTED EXCEPT EXPLICIT RETIREMENT.

---

---

# 12. HOME

## FD-HOME-01 — Purpose
- Home answers: **“Aaj mujhe kya karna hai?”**
- Setup + daily operations; not analytics dashboard.
- **Status:** LOCKED.

## FD-HOME-02 — Readiness
- Compact/collapsible.
- Complete = “Setup complete ✅”.
- No universal hard block except true feature-specific gates.
- **Vendors has its own readiness row/card** in Home readiness; this was explicitly frozen during the Vendor UX review and is not an unresolved UX question.
- **Status:** LOCKED.

## FD-HOME-03 — Today’s Work
Priority:
1. exceptions/blocked;
2. To Confirm;
3. To Ship.

- Top 3–5 exceptions with reason + Open/Fix.
- Home cards open correctly filtered Orders.
- No mini order-table duplication.
- **Status:** PRE-P3 functional requirement.

## FD-HOME-04 — Counts / connection / WhatsApp
- Lifecycle counts use New / Confirmed / Shipped-In Transit / Delivered / Cancelled and open filtered Orders.
- Connections shows only most important next action + View all.
- WhatsApp compact status: Connected / Needs attention.
- **Status:** LOCKED.

## FD-HOME-05 — Role-aware actions
- Staff may see operational information needed for their work, but Owner/Admin-only action buttons must not appear for Staff.
- This is a minimal frozen safety boundary, not a new granular-role redesign.
- **Status:** LOCKED.

## FD-HOME-06 — Analytics stays in Growth
- Revenue/profit do not belong on Home.
- **Status:** LOCKED.

## FD-HOME-07 — No Home customization project in Pre-P3
- Keep Home opinionated around setup + today's work.
- Do not add dashboard-widget customization/personalization as Pre-P3 scope.
- **Status:** LOCKED.

## FD-HOME-08 — Failure isolation and mobile priority
- Zero-count sections stay compact.
- A failure in one Home card must not make the whole Home unusable; show truthful per-card failure and Retry where appropriate.
- Mobile information priority: critical action → Today’s Work → lifecycle counts → connections/WhatsApp → collapsed readiness.
- **Status:** LOCKED UX/RESILIENCE.

---

---

# 13. NAVIGATION

## FD-NAV-01 — Desktop order
`Home → Orders → Products → Mini-Store → Vendors & Shipping → WhatsApp → Growth → Influencers → Settings`

- Ask AI inside Growth.
- Company/Brand/Team/Connections/Store & Domain/Plan & Usage/Privacy/History/WhatsApp configuration under Settings.
- **Status:** LOCKED.

## FD-NAV-02 — Company switcher
- Single company: compact company name.
- Multiple companies: visible switcher.
- Add Company lives inside switcher.
- **Status:** LOCKED.

## FD-NAV-03 — Mobile
Target bottom nav: Home | Orders | Mini-Store | Growth | More.

**Timing override:** perfect bottom-nav implementation is not a Pre-P3 blocker if current responsive drawer/navigation is usable.
- **Status:** TARGET / POST-P3 POLISH IF NEEDED.

## FD-NAV-04 — No fake search
- Do not show global search unless it really works.
- **Status:** LOCKED.

## FD-NAV-05 — Sidebar behaviour
- Desktop sidebar may collapse but defaults to the normal expanded operational navigation.
- Do not let navigation refactoring hide functional modules/routes that are still part of the product.
- Parent navigation remains visibly active/highlighted on child pages.
- **Status:** LOCKED UX.

## FD-NAV-06 — Global shell and truthful screen states
- Preserve a usable authenticated app shell across retained client routes and a usable mobile drawer/navigation even where the ideal bottom bar is deferred.
- Critical screens must not convert loading/error/empty/module-off/permission-denied states into fake success or blank dead pages.
- A broken child/card/module should fail truthfully and locally where practical rather than making the whole shell unusable.
- **Status:** PRE-P3 RESILIENCE / CAPABILITY-PRESERVATION RULE.

---

# 14. ENTITLEMENTS / PLANS / USAGE

## FD-ENT-01 — Locked modules stay visible
**Founder override.**
- Unavailable/not-included module remains visible in sidebar in LOCKED state.
- Click opens clear plan/not-enabled state.
- **Status:** PRE-P3 MUST.

## FD-ENT-02 — Usage honesty
- Show usage only where reliable.
- If counter is unavailable/unwritten: `Usage data not available yet`.
- Never fake `0 / limit`.
- **Status:** PRE-P3 MUST.

## FD-ENT-03 — No fake billing
- Plan/entitlement truth without pretending payment collection exists where it does not.
- Show module names in merchant language rather than raw internal entitlement keys.
- **Status:** LOCKED.

## FD-ENT-04 — Beta module defaults
- Core beta product includes Orders, Products, Mini-Store, Vendors, WhatsApp (including Broadcast), Growth and Ask AI subject to entitlement/configuration.
- Influencers is not universally enabled by default; it may be enabled per company/plan.
- **Status:** LOCKED.

---

# 15. COMPANY / BRAND

## FD-COMP-01 — Separate Company and Brand
- Company and Brand are separate settings areas.
- Brand Profile is identity master; avoid duplication.
- **Status:** LOCKED.

## FD-COMP-02 — Company page
- One page with Business Details / Contact Details / Tax-Legal.
- Explicit Save Changes.
- Owner/Admin edit; Staff view-only.
- Protected/platform fields not client-editable.
- Do not present Company/Brand pickup-address configuration as the source of supplier fulfilment; pickup truth belongs to the assigned Vendor/Shipping model.
- **Status:** PRE-P3 functional requirement.

---

# 16. TEAM / ACCESS / ROLES

## FD-TEAM-01 — Fixed roles
- Owner / Admin / Staff only.
- No custom/granular role redesign in Pre-P3.
- **Status:** LOCKED.

## FD-TEAM-02 — Invite authority
- Owner invites Admin/Staff.
- Admin invites Staff.
- Staff cannot invite.
- **Status:** LOCKED.

## FD-TEAM-03 — Staff Team visibility
- Team & Access hidden from Staff navigation.
- Staff deep-link = clean no-access state.
- **Status:** LOCKED.

## FD-TEAM-04 — Invite truth
- Pending invite shows role/time/expiry/resend/revoke.
- Seat-full state blocks before submit.
- Email/origin failure must not create fake invite row.
- Friendly duplicate/rate-limit states.
- **Status:** PRE-P3 hardening.

## FD-TEAM-05 — Role/remove changes
- Full email visible to Owner/Admin.
- Role change confirmation old → new.
- Removal confirmation; immediate access end; historical attribution retained.
- Audit access changes where architecture supports it.
- **Status:** PRE-P3 hardening.

---

# 17. STORE / DOMAIN

## FD-DOM-01 — Hosted address default
- Every company receives Launchpad-hosted address.
- Domain ownership never blocks onboarding.
- **Status:** LOCKED.

## FD-DOM-02 — Custom domain
- Optional, plan-controlled.
- Guided DNS and truthful states: Pending verification / Check Again / Verified / Failed with reason.
- Existing hosted URL remains available.
- **Status:** LOCKED.

## FD-DOM-03 — Hosted slug change
- Confirmation + new-URL preview + old-link warning.
- Preserve the mature retired-slug redirect behaviour (for example HTTP 308) where already implemented so old hosted links do not silently break.
- **Status:** PRE-P3 target where capability is exposed.

## FD-DOM-04 — Custom-domain removal
- Confirmation required.
- Hosted URL continues working.
- **Status:** PRE-P3 target where capability is exposed.

## FD-DOM-05 — Protect existing live domains
- Existing working custom domains/links must not regress while self-serve domain controls are added or simplified.
- **Status:** LOCKED REGRESSION RULE.

---

# 18. CONNECTIONS

## FD-CONN-01 — Central status hub
- Cards show provider, status, health, last check, one next action.
- States: Connected / Setup incomplete / Needs reconnect / Needs attention.
- Check Health Now / last checked preserved where supported.
- **Status:** LOCKED.

## FD-CONN-02 — Disconnect safety
- Disconnect confirmation explains consequences.
- Disconnect does not delete imported history by default.
- **Status:** PRE-P3 MUST.

## FD-CONN-03 — Master ownership
- Delhivery master = Vendors & Shipping → Shipping Settings.
- WhatsApp master = Settings → WhatsApp.
- Meta/GA4/OpenAI setup truth = Connections.
- Growth may deep-link, not duplicate master config.
- **Status:** LOCKED.

## FD-CONN-04 — Permissions
- Staff view-only for connection management.
- **Status:** LOCKED; no broader role redesign.

## FD-CONN-05 — Integration architecture principle
- For future/new integrations, prefer an official/capable MCP/connector when it genuinely covers the needed workflow; retain direct provider APIs where MCP is incomplete, unavailable or deeper backend control/reliability is required.
- Avoid forcing merchants through duplicate authorization for one logical connection; preserve a one-connect product experience where architecture permits.
- Do **not** refactor proven Pre-P3 provider integrations merely to satisfy this principle.
- **Status:** LOCKED ARCHITECTURE GUARDRAIL.

## FD-CONN-06 — Primary store and connection-health semantics
- Preserve the ability to designate one **primary** external commerce store where supported, while making the **one-external-store limit** explicit under FD-CONN-07.
- Primary store determines Growth/Ask AI's external-commerce source, links, catalog, provider actions and merchant-facing wording. It never silently rewrites historical imported order/source truth; a historical/disconnected other-provider row is not permission to ingest or execute on it.
- Preserve Check Health Now / health-job behaviour and truthful states such as reconnect/grant-missing/unhealthy; a green connection card alone is not operational-readiness proof.
- **Status:** SUPERSEDED IN PART BY FD-CONN-07; provider-health protection remains.

## FD-CONN-07 — ONE external commerce store + optional Mini-Store (latest direct Founder lock)
- Per company in Pre-P3: **Shopify OR Wix** as the one active external commerce provider; **not both simultaneously**. Mini-Store can independently be enabled, so two selling channels may operate (one external + native Mini-Store).
- Enforce in merchant UI **and server/provider connection & ingestion/action boundaries**; second external connection attempts must be clearly refused rather than accepted while their orders are silently ignored. Historical other-provider rows/data must not silently become active; preserve any lawful history/erasure and safe disconnect/migration behavior.
- `Primary Store` is the selected external store and sole external-commerce source for Growth AI/Ask AI; no hidden Wix default, Wix-only source guard, or cross-provider action when Shopify is primary (and vice versa).
- Native Mini-Store operational orders/fulfilment/communications continue. This does **not** authorize merging Mini-Store data invisibly into primary-external-store AI conclusions or conflating channels in Growth/ROAS. Existing truthful company-wide summaries may retain explicitly separated source context.
- **Authority:** latest direct Founder decision accepting Option A and primary-only Growth AI; supersedes old language that allowed both external stores as live operational sources.
- **Status:** FOUNDER-LOCKED PRE-P3.

---

---

# 19. GROWTH

## FD-GROW-01 — Default = Today / Truth + Action
- Business truth before vanity metrics.
- Actual store orders separate from Meta-attributed purchases.
- Never merge attributed marketing claims into financial truth.
- **Status:** LOCKED.

## FD-GROW-02 — Revenue truth
- Realized revenue separate from provisional/at-risk revenue.
- Cash ROAS only where valid.
- If ad spend is zero/invalid, show Not available rather than `0.00x`.
- **Status:** PRE-P3 hardening.

## FD-GROW-02A — Currency truth
- Do not silently add unlike currencies into one INR revenue/profit/ROAS truth.
- Where the current Growth contract is INR-only, non-INR provider orders must be clearly warned/excluded from INR-valued aggregates unless an approved conversion rule actually exists.
- Never invent an FX conversion or silently treat foreign currency values as INR.
- **Class:** TECHNICAL TRUTH CONSEQUENCE, carried from the canonical Growth data contract.
- **Status:** PRE-P3 TRUTH REQUIREMENT.

## FD-GROW-03 — Cost truth
- Unknown cost never 0.
- Founder-frozen merchant labels for incomplete cost coverage: **`Cost coverage incomplete`** and **`Profit shown only for known costs`**.
- With Pre-P3 COGS implementation, profit uses known frozen COGS; do not display a misleading total profit as if unknown-cost orders had zero cost.
- **Status:** LOCKED.

## FD-GROW-04 — Partial/stale/no-data states
- Partial report allowed.
- Stale snapshot stays visible with warning + Last synced.
- No-data = onboarding/empty state, not zeros.
- **Status:** LOCKED.

## FD-GROW-04A — Growth action density and mobile truth
- Today surfaces the top 3–5 useful actions rather than an unbounded feed.
- Merchant-facing labels must use business language, not internal/provider implementation keys.
- Mobile priority: warnings/health → key truthful metrics → actions → source status.
- Safe manual Refresh may exist where the mature provider snapshot supports it; refresh must not fabricate freshness.
- **Status:** LOCKED UX/TRUTH.

## FD-GROW-05 — Internal nav
Today / Ask AI / Ads & Creatives / Store & Products / Approvals & Activity / Setup.
- Analytics belongs inside Growth.
- **Status:** LOCKED.

## FD-GROW-06 — Existing provider execution model preserved
- Preserve mature provider action/approval/execution architecture.
- Do not replace with a new generic workflow or add unnecessary approvals.
- Provider Execution = Enabled is intentional.
- **Status:** LOCKED.

## FD-GROW-07 — Snooze
- Do not add a new Snoozed state in Pre-P3 merely because a mockup mentions it.
- Preserve existing states.
- **Status:** LOCKED.

## FD-GROW-08 — Growth access
- Staff remains read-only under the current role model for consequential Growth/provider actions.
- Existing financial-view/source-permission controls must continue to gate sensitive financial facts.
- Do not redesign granular roles here.
- **Status:** LOCKED.

## FD-GROW-09 — Client legacy Analytics
- Remove client legacy Analytics now.
- Merchant analytics lives in Growth.
- **Status:** PRE-P3 RETIREMENT LOCK.

## FD-GROW-10 — Realized revenue / returns / value truth
- Mini-Store revenue becomes realized only on trustworthy Delivered truth (courier Delivered or an audited manual Delivered decision), not merely Manual Dispatch or In Transit.
- Return/DTO in progress is revenue at risk, not automatically reversed/refunded.
- Provider refund facts determine provider refunds.
- Where the frozen Growth contract defines order value, do not silently include shipping/tax in merchandise/revenue metrics that are meant to exclude them.
- **Status:** LOCKED.

## FD-GROW-11 — Test-company exclusion
- Companies explicitly marked as test/QA companies must not pollute merchant Growth/KPI/dashboard truth.
- Test-company identification is an operational configuration concern; do not infer production business performance from QA rows.
- **Status:** LOCKED TECHNICAL DEFAULT.

## FD-GROW-12 — Shopify/Wix Growth + Store Doctor FUNCTIONAL PARITY (READ)
- **Latest direct Founder decision:** a Shopify merchant must receive genuinely comparable mature Wix Growth capabilities, not a degraded Wix-only experience. This applies to Growth Today/Store Doctor/Store & Products, actionable product/catalog health, store signals/planner, connection health, and Ask AI via FD-AI-04.
- Select the **one primary external store** using FD-CONN-07. Shopify reads its Shopify order/catalog/inventory facts; Wix reads Wix facts. UI labels/CTAs, permissions, freshness, product IDs, variants and company/source isolation must match the source. No misleading “Wix shows” or “Connect Wix” for Shopify primary, and no Wix API calls on Shopify paths.
- Reuse existing shared Meta/GA4/Creative Studio/Approvals/BYOK models and mature Wix feature surfaces; build Shopify adapters only where absent. Meta product mapping/sets and any provider-specific store intelligence must be evaluated for **comparable business functionality**, not blindly identical APIs. Do not silently ignore a mature Wix capability only because the old audit called it optional.
- Shopify stock/location/multi-variant quantities, pagination, deleted products, COGS, currency, unknown/partial/stale states must be truthful; no stock claims unsupported by the source. API availability/permissions and exact runtime access must be verified before PASS.
- **Evidence:** 29-row Wix→Shopify audit; 3 already working, 9 adapter/reuse, 7 medium/large new development, 9 previously frozen-scope blocked, 1 unproven; 11 provider-neutral Growth features tracked separately. These counts are audit buckets, not implementation completion metrics.
- **Status:** FOUNDER-LOCKED FUNCTIONAL TARGET; CODE IMPLEMENTATION NOT VERIFIED.

## FD-GROW-13 — Shopify/Wix APPROVAL-GATED WRITE functional parity
- Existing safe/mature Wix Growth provider actions must have a Shopify equivalent **where Shopify API and granted scopes support the same business outcome**. Founder explicitly approved **READ + WRITE** parity; this supersedes the 2026-10-29 blanket `no write_*` Shopify-scope restriction for **the required approved actions**.
- Explicit approval-gated parity candidates include **product edits, discount/coupon creation, blog/article actions, and merchant-initiated inventory adjustment** (FD-INV-06). Preserve Owner approval where the current Wix action requires it, provider-execution gates, company/store targeting, preview of changes, audit/history, failure/retry reconciliation, and existing Staff restrictions. Never grant an LLM unilateral write authority or broaden existing role permissions.
- **Important safety boundary:** Older audit identifies Wix order cancellation/refund as reachable but provisional/possibly unsafe; Shopify cancellation/refund are **not implicitly cleared for launch merely by saying parity**. First trace exact Wix contract + actual execution/risk + existing frozen commerce/refund rules; include safe mature functional equivalents where explicitly supported, but block/defer unsafe or unproven actions until a separately verified decision. Likewise ShopifyQL/read_reports or provider-specific access checks are not assumed mandatory as exact API clones; audit business-value parity separately.
- Only request **minimum necessary Shopify write scopes** for the approved actions and verify merchant reauthorization/Partner configuration. Merely adding a scope does not implement a feature. Real provider calls require explicit approved test/release plan; do not alter existing app scopes now.
- **Status:** FOUNDER-LOCKED FUNCTIONAL TARGET; PERMISSIONS/IMPLEMENTATION/RUNTIME NOT PROVEN; IMPLEMENTATION NOT AUTHORIZED.

---

# 20. ASK AI / COMPANY BRAIN

## FD-AI-01 — Highest-priority preserve rule
Everything mature in Ask AI stays. No unnecessary rework.

Preserve:
- current role behaviour; in particular, do not broaden Staff Ask-AI send authority merely because Staff can read Growth if the current/frozen behaviour keeps Staff read-only;
- Hinglish/Hindi/English chat;
- history/New Chat/delete/retention;
- image/video/product attachments;
- product picker and Wix catalog source as built;
- image generation flow + quota/cost;
- structured proposals/request cards;
- existing provider action/approval/execution behaviour;
- guardrails;
- refresh recovery/retry/deduplication;
- AI usage/quota;
- business/profile context;
- corrections/learning;
- mobile full-screen chat.

- **Status:** LOCKED.

## FD-AI-02 — Data-source master after onboarding
- Settings is the durable master for AI data access.
- Growth Setup shows status and links to Settings.
- Source OFF = not used silently.
- **Status:** PRE-P3 MUST.

## FD-AI-04 — Primary-store-aware Ask AI parity (READ + proposals + approved actions)
- With Shopify primary, Ask AI must use Shopify source-guard permissions, Shopify catalog/product picker, inventory where available, order/sales data and supported provider actions. With Wix primary, preserve mature Wix equivalent. A Shopify-only merchant must not require the `wix_store` source to be enabled for `growth_summary`.
- Reuse mature chat, context, images/video, proposals, quota, approval/execution controls. Source names and claims are accurate; no cross-store data or action fallback. The default external commerce analysis is **primary only**; Mini-Store can remain its own separate operational source and should not be invisibly merged into the selected provider's AI learning.
- Human/Owner approval and existing provider execution safeguards apply to consequential writes, per FD-GROW-13; unknown or unavailable data is not invented.
- **Status:** FOUNDER-LOCKED PARITY; NO IMPLEMENTATION AUTHORIZED.

## FD-AI-03 — Company Brain deeper merge deferred
- Do not merge/rebuild Ask AI profile + Company Brain in Pre-P3.
- Preserve current Ask AI profile/capabilities.
- Deeper additive context use can come later.
- **Status:** LOCKED / LATER.

---

# 21. SETTINGS

## FD-SET-01 — Settings hub
Areas:
- Company
- Brand
- Company Brain / AI & Data
- Team & Access
- Store & Domain
- Plan & Usage
- Connections / Sales Channels
- Shipping deep-link/master ownership as frozen under Vendors & Shipping
- WhatsApp
- Orders / Internal Status labels where the mature capability exists
- Privacy
- History / Activity
- Account Security

- One durable master per configuration; no duplicate masters.
- Role-aware.
- **Status:** PRE-P3 functional organization.

---

# 22. PRIVACY / DATA RIGHTS / OFFBOARDING

## FD-PRIV-01 — Preserve mature privacy capability
Preserve:
- export;
- Access/Correction/Erasure/Grievance/Portability requests;
- export expiry;
- offboarding;
- provider privacy responses;
- Shopify redact/erase/data-request handlers already built.
- **Status:** LOCKED.

## FD-PRIV-02 — Company export Owner-only
**Latest Founder override.**
- Company privacy export = Owner only.
- This supersedes the older Owner/Admin wording in Appendix D.
- **Status:** LOCKED.

## FD-PRIV-03 — Offboarding Owner-only
- Safe controlled request; no instant destructive delete.
- Can be cancelled while reversible.
- **Status:** LOCKED.

## FD-PRIV-04 — Wix deletion scope
**Latest Founder decision.**
- Do not create extra Wix raw-data deletion/scrub work solely because Shopify has a deletion requirement.
- Require Wix deletion only if Wix policy, product privacy requirement, or an actual security/privacy risk proves it necessary.
- Regardless, disconnected/removed Wix/provider data must NOT be used for active phone resolution or live customer messaging.
- **Status:** LOCKED.


## FD-PRIV-04A — Separate disconnect retention from privacy-rights erasure
- `Do not automatically delete all Wix data on disconnect` is NOT permission to disregard a valid erasure, retention, offboarding, legal or customer-rights request.
- Current static audit reports `wix_raw_orders.raw_payload` can retain PII and lacks a scoped erase/scrub path; this is an **AUDIT FINDING pending runtime/privacy-flow verification**, not a new direct Founder choice.
- Any new sanitized provider JSON/event store must participate in tenant-scope export/erasure, retention controls, data-minimization and removed-store live-message exclusion. Never persist auth secrets or unbounded prohibited customer data.
- **Class:** technical privacy consequence of FD-PRIV-01/04/05 and FD-DATA-01.
- **Status:** MANDATORY AUDIT / IMPLEMENTATION-ACCEPTANCE GATE, not an independent automatic-disconnect-delete decision.

## FD-PRIV-05 — Shopify scrub/redaction
- Existing Shopify privacy scrub/redaction implementation should be preserved and verified, not rebuilt without evidence.
- **Status:** LOCKED.

## FD-PRIV-06 — Exceptional hard delete
- Platform Admin hard delete may exist as exceptional tooling only with reason + confirmation + DB audit + dependency safeguards.
- Normal retained-order cases prefer deactivate/offboard rather than blind delete.
- **Status:** LOCKED.

---

# 23. HISTORY / AUDIT

## FD-HIST-01 — Append-only company history
- What / when / who / subject.
- Merchant cannot edit/delete audit history.
- Simple filters are fine.
- Do not fabricate missing events or fake backfills.
- **Status:** LOCKED.

## FD-HIST-02 — Consequential actions audited
- Role/access changes, dangerous Admin operations, manual Delivered, privacy operations, and other high-risk actions should use real audit emitters where required.
- **Status:** PRE-P3 hardening.

---

# 24. ACCOUNT SECURITY

## FD-SEC-01 — Real logout
- Logout must actually terminate the session, not merely navigate to Login.
- Applies across relevant portals.
- **Status:** PRE-P3 MUST.

## FD-SEC-02 — `/er-diagram`
- Protect as Platform Admin-only if needed.
- If production use is unnecessary, disable/retire it.
- **Status:** PRE-P3 MUST.

## FD-SEC-03 — No fake security centre
- Keep real security functionality such as password change.
- Do not invent fake 2FA/session controls.
- **Status:** LOCKED.

## FD-SEC-04 — Tenant/security foundations never weakened
- RLS/tenant isolation/least privilege/token safety remain non-negotiable.
- Do not loosen for speed.
- **Status:** LOCKED.

## FD-SEC-05 — Remove unsafe legacy own-order RLS path
- The legacy email-based `users_view_own_orders` policy/path is not an acceptable long-term tenant boundary and must be removed/retired as planned.
- Provider-owned commercial facts must not rely only on UI discipline for immutability; DB/server enforcement should preserve provider truth where already required by the frozen architecture.
- **Status:** LOCKED SECURITY CLEANUP.

---

# 25. PLATFORM ADMIN

## FD-ADMIN-01 — Admin must be functionally complete in Pre-P3
**Latest Founder decision:** do not defer the Admin operational cleanup.

Preserve mature useful Admin capability, including clients/users/orders/vendors, plan/module controls, feature flags, domains, broadcast control, Growth/provider controls, privacy triage, jobs, exports, Delhivery tools and system settings. Regrouping is allowed; capability loss is not.
- **Status:** LOCKED — PRE-P3.

## FD-ADMIN-01A — Preserve mature useful Platform Admin capability
- Admin cleanup/reorganization must not erase mature useful operational controls merely because the client UX is simplified.
- Preserve useful user/company management, provider/support operations, privacy triage, jobs/exports, plan/flag/module controls and other mature Admin functions unless explicitly RETIRED.
- Every retained Admin route/action must be reachable, permission-protected and truthful.
- **Status:** LOCKED PRESERVATION CONTRACT.

## FD-ADMIN-02 — Restore/reconnect five built pages
Restore/reconnect the intended Admin pages:
- Privacy Triage
- Jobs Monitor
- DB Export
- Client Plan
- Client Flags

Do not rebuild if pages already exist.
- **Status:** PRE-P3 MUST.

## FD-ADMIN-03 — Dangerous actions
- Confirmation + mandatory reason + DB audit + permissions.
- No console-only audit for consequential operations.
- Exceptional Admin hard-delete of junk/test orders may remain only behind these safeguards and dependency checks; normal business history uses cancel/archive/deactivate-style flows rather than silent deletion.
- **Status:** PRE-P3 MUST.

## FD-ADMIN-04 — Client lifecycle tooling
- Complete deactivate/reactivate operator functionality.
- Complete offboarding operator flow.
- Deactivation/offboarding must preserve retained order/audit/history truth. A company/client with dependent orders/history must **not** be silently hard-deleted as a normal lifecycle action.
- Exceptional destructive deletion, if ever allowed, is governed separately by FD-PRIV-06 / FD-ADMIN-03 safeguards rather than being the normal deactivate path.
- **Status:** PRE-P3 MUST.

## FD-ADMIN-05 — Admin Products / Product Sales
- Keep useful Admin Products capability.
- Retire Product Sales.
- Historical data need not be deleted solely because UI is retired.
- **Status:** LOCKED.

## FD-ADMIN-06 — Admin Analytics
- Preserve temporarily.
- Retire only after useful admin views are re-homed with proven parity.
- **Status:** LOCKED.

## FD-ADMIN-07 — Admin impersonation
- Final product should support secure impersonation with reason/banner/audit/attribution/permission ceiling and privacy blocks.
- **Timing:** separate Post-P3 security-reviewed feature.
- **Status:** POST-P3 — NOT A PRE-P3 BLOCKER.

---

# 26. RETIRED / LEGACY SURFACES

## FD-RET-01 — Client finance/payment/wallet surfaces
- Retire active client Payments / Wallet / legacy Finance surfaces and obsolete finance business logic.
- Preserve historical records where required.
- Ensure retirement does not leave old payment-due gates blocking order operations.
- **Status:** PRE-P3 CLEANUP.

## FD-RET-02 — Client legacy Analytics
- Retire now; Growth is merchant analytics home.
- **Status:** LOCKED.

## FD-RET-03 — Product Sales
- Retire Admin Product Sales UI.
- **Status:** LOCKED.


## FD-RET-03A — Retire only the proven-unused Product Sales notification/API family; preserve active vendor journeys
- **Authority:** Previously locked Founder retirement of Platform Admin Product Sales; targeted 2026-11-08 Point 3 audit; Founder acknowledgement.
- **STATIC CODE FACT:** `app/api/inventory/notify-vendor/route.ts` and `app/api/inventory/notify-vendor-product-sales/route.ts` set `current_stock=5` in old `product_inventory`/`product_sales` data. Product Sales UI still mounts and calls the latter; first route is direct-HTTP callable but no in-repo caller was found. No evidence of real production execution.
- **PRE-P3 DISPOSITION:** Disable these two retired handlers using explicit non-writing HTTP 410 behavior. Also retire the proven-Product-Sales-only `sales-from-orders`, `sync-product-sales`, `clear-product-sales` (destructive) and `sales-summary` APIs after final caller/dependency proof; remove Product Sales Admin tab/sidebar and direct navigation entry. No service-role stock writes, no WhatsApp platform send through retired APIs.
- **PRESERVE:** Historic `product_sales` and `product_inventory` rows/tables untouched without separate approved destructive change. Keep current Order Fulfilment Step 4 `app/api/whatsapp/notifications/send-to-vendor/route.ts`, Mini-Store `lib/mini-store-whatsapp.ts`, `vendor-product-queries.ts` and their legitimate templates/messages untouched except necessary regression fixes.
- **ACCEPTANCE:** Any user invoking retired routes receives 410 and zero stock/message side effects; active vendor request, vendor responses, Staff access denial and message idempotency still work. Test that no company-crossing writes or disabled Product Sales UI remain. Explicitly verify obsolete endpoints do not have external supported callers before retirement; if unexpectedly found, mark `NOT PROVEN` and preserve until safe replacement.
- **Scope class:** FOUNDER-ACCEPTED RETIREMENT + TECHNICAL CONSEQUENCE; not a new inventory rule. **Implementation remains unauthorized.**

## FD-RET-04 — Influencer earnings/payout ledger
- Retire payout/earnings UI/ledger where it belongs to the old model; preserve historical data.
- Influencer product area itself may remain where useful.
- **Status:** LOCKED.

## FD-RET-05 — Legacy cleanup must not delete mature working capability accidentally
- Cleanup must distinguish dead/obsolete code from mature order/shipping/vendor/WhatsApp paths still required for functionality.
- **Status:** LOCKED GOVERNANCE.

## FD-RET-06 — Detailed legacy-retirement scope that must be audited to completion
The frozen retirement programme includes, where still present/reachable. Surface retirement must be paired with removal of any hidden runtime guard/dependency that would otherwise strand the merchant (for example, the old payment-due gate must not survive after Payments/Wallet are removed):
- client Payments / Wallet / Finance / payment dashboard;
- client invoice/payment-screenshot/payment-settings surfaces tied to the retired payment model;
- old Vendor Wallet/Payment surfaces;
- retired Razorpay infrastructure for new operations;
- old ebook / saree-catalog product-surface routes unless explicitly retained outside Launchpad;
- old Client Analytics (current Founder override: retire now);
- Admin Product Sales;
- influencer earnings/payout ledger;
- obsolete `client_price` / `bk_price` / legacy margin logic;
- legacy stock-mutation/restore code and accidental stock writers (audit active callers and required history before safe retirement/guarding under final FD-INV-01; no destructive database drops without separate approval);
- legacy product catalog/table readers once Product Onboarding parity is proven;
- Google Sheets / CSV / Admin manual order creation paths as **current ingestion sources** (historical rows may remain read-only until Founder cleanup);
- Sheets product-media mirror;
- legacy WhatsApp templates/notifications that exist only for retired finance/ebook/vendor-wallet/Sheets features.

Do not remove a mature path merely because its file is old. Prove replacement/parity first where the capability is protected.
- **Status:** LOCKED CLEANUP SCOPE.

## FD-RET-07 — Interim legacy-order safety
- Founder plans to delete old historical orders, so do not build large compatibility architecture around them.
- Until deletion, legacy historical orders must not enter current Growth truth, automatic customer journey, current-source fulfilment, or silently mutate stock/payment/provider state.
- If exposed for support/history, keep them read-only/clearly identified.
- **Status:** LOCKED TEMPORARY SAFETY.

## FD-RET-08 — Interim retained legacy-order UI
- Until Founder deletion/cleanup is actually executed, retained `google_sheet`/historical orders are hidden from the default current Orders view, available only through an explicit Legacy/history filter where support access is needed, read-only for normal merchant operations, and excluded from Growth/KPIs/automatic messaging/current-source fulfilment.
- Only the controlled admin/support close-out path may alter such retained history where that capability still exists.
- **Status:** TEMPORARY SAFETY UNTIL DELETION.

## FD-RET-09 — Controlled route/API retirement, no surprise destructive cleanup
- Founder-approved retired pages/routes may redirect/retire and obsolete APIs may become explicit 410 stubs so hidden direct routes do not stay accidentally live.
- Do **not** perform destructive legacy DB/table drops merely as part of UI cleanup; destructive schema/data removal and production cron/provider deregistration require their own approved safe step.
- Preserve mature replacement parity before deleting an old path that still carries required functionality.
- **Status:** LOCKED CLEANUP GOVERNANCE.

---

---

# 27. ONBOARDING / SELF-SERVE

## FD-ONB-01 — Client-ready invited cohort
- Pre-P3 target is self-serve/client-ready for limited invited cohort.
- Public-open launch is not automatically implied.
- **Status:** LOCKED.

## FD-ONB-02 — Email verification hard gate; setup guided
- Email verification universal hard gate.
- Other setup uses guided readiness + feature-specific gates rather than blocking dashboard entry universally.
- **Status:** LOCKED.

## FD-ONB-03 — Domain/provider connection not universal blockers
- Hosted Launchpad address exists by default.
- Shopify/Wix not required to use native Mini-Store.
- Vendor/Delhivery readiness enforced where operationally needed, not as universal onboarding block.
- **Status:** LOCKED.

## FD-ONB-04 — Guided readiness facts
- Sales channel readiness may be satisfied by a published Mini-Store with at least one visible product OR a connected Shopify/Wix source whose first sync has reconciled successfully.
- For a connected Shopify/Wix sales channel to count as operationally ready for Pre-P3, current-source automatic order ingestion must actually produce the complete usable order contract; a green connection card alone is not enough.
- Products can remain a guided setup item rather than a dashboard hard gate.
- Shipping readiness is truthful: Delhivery token saved/configured under the frozen rule or Own Courier explicitly selected.
- WhatsApp readiness reflects connected + automatic updates configured, or an explicit OFF decision; never infer readiness from account connection alone.
- Ask AI/data usage must fail closed for sources the company has not allowed.
- **Status:** LOCKED GUIDED-READINESS CONTRACT.

## FD-ONB-05 — Client-ready email plumbing
- Because email verification is the universal hard gate and Team invites/recovery rely on email, the invited-cohort launch requires working verification/invite/recovery email delivery.
- SMTP/sending-domain/provider setup is an external readiness dependency; code must expose truthful failure rather than fake success.
- **Status:** PRE-P3 READINESS / EXTERNAL DEPENDENCY.

---

## FD-ONB-06 — Preserve mature auth/account-entry capability
Preserve and verify the real account-entry flows already in product:
- login by supported e-mail/phone path;
- role-based landing and invalid-role handling;
- signup + honeypot/abuse controls where mature;
- verify-email + resend;
- forgot/reset password and the real signed-in Change Password capability;
- invite landing/acceptance, expired/revoked states;
- pending-account state;
- multi-company picker + Add Company;
- resume onboarding at the correct step;
- double-submit protection for company creation;
- store-step switch-company guard;
- per-source AI access consent + notices/review.
- **Status:** PROTECTED MATURE CAPABILITY.

---

# 27A. CARRIED-FORWARD TECHNICAL DEFAULTS (NOT NEW FOUNDER QUESTIONS)

These were recorded in the frozen Pre-P3 continuity and should be audited/preserved unless a newer direct Founder decision overrides them:

- Automatic order updates: new invited-cohort companies may start with the configured automatic-update default; existing production companies must not be silently opted into newly introduced customer messaging.
- Shopify custom distribution: one invited-store install path/link is an explicit onboarding/admin-managed step.
- Test companies: mark/exclude them from Growth/dashboard business truth.
- These are technical defaults, not permission to perform live activation without the required production/provider approval.

---

# 28. EXTERNAL PROVIDER STATUS

## FD-EXT-01 — Shopify protected customer data
- Founder states protected-customer-data setup was done ~3–4 months earlier.
- Repository absence is not proof that it is missing.
- If code cannot verify dashboard state, classify `EXTERNAL STATUS NOT PROVEN FROM REPOSITORY`, not `MISSING`.
- **Status:** LOCKED EVIDENCE RULE.

## FD-EXT-02 — External dependencies do not reduce internal completion score
Examples:
- provider approvals;
- production credentials;
- DNS;
- dashboard declarations.

Keep separate from internal app work.
- **Status:** LOCKED.

## FD-EXT-03 — Beta store-app distribution
- Shopify beta connection uses the approved invited-store/custom-distribution approach.
- Shopify custom distribution is an explicitly labelled/admin-managed onboarding step (for example, preparing the store-specific install link), not a fake fully-public self-serve flow.
- Wix uses the private/unlisted invited-client approach where already frozen.
- Treat provider-dashboard install/approval state as external activation evidence, not as an internal-code failure.
- **Status:** LOCKED BETA DISTRIBUTION.

## FD-EXT-04 — External legal/email activation inputs
- Legal/privacy wording and verified sending-domain/provider configuration may be external inputs.
- They must be tracked separately from code completeness and must not be silently fabricated.
- **Status:** LOCKED EVIDENCE SEPARATION.

## FD-EXT-05 — Delhivery status meanings must be provider-documented
- Do not guess ambiguous Delhivery status codes (including OFD/RTO/DTO/NDR-style states). Unknown/undocumented mappings stay unknown and must not trigger false business truth or customer messages.
- Provider-documented status mapping is an external activation/readiness input; code should fail safely until evidence exists.
- **Status:** LOCKED TRUTH RULE / EXTERNAL EVIDENCE.

---

---

# 29. MOBILE

## FD-MOB-01 — Critical workflows must be usable
- Home, Orders, order detail, Vendor/Shipping, Mini-Store, WhatsApp, Growth, Ask AI, Settings must be usable on mobile.
- **Status:** PRE-P3 usability requirement.

## FD-MOB-02 — Perfect mobile nav polish not blocker
- Bottom-nav target may be deferred if current responsive drawer is functionally usable.
- **Status:** POST-P3 POLISH IF NEEDED.

---

# 30. TESTING / REVIEW / RELEASE DISCIPLINE

## FD-QA-01 — Business-journey tests, not only component/security tests
Critical E2E must prove real contracts such as:
`provider payload → ingestion → operational order → vendor → inventory → shipping → WhatsApp → tracking → delivered`

- Tests must not assert blank placeholders as “correct” when business journey requires real data.
- **Status:** PRE-P3 QA REQUIREMENT.

## FD-QA-02 — Pre-development test cases
- Pre-dev acceptance and adversarial/sibling tests are mandatory for consequential work.
- Security/tenant/data isolation tests remain continuous.
- **Status:** LOCKED.

## FD-QA-03 — Fresh review for changed SHA
- Codex approval of `5bc0e1b3` applies only to that exact candidate.
- Any implementation creates a new SHA and requires full regression + fresh final Codex review.
- **Status:** LOCKED.

## FD-QA-04 — No production/destructive action without explicit approval
- Do not change production DB/flags/release trust/provider writes merely to prove functionality unless explicitly authorized.
- **Status:** LOCKED.

## FD-QA-05 — Audit cross-boundary data contracts
Pre-P3 regression must explicitly verify producer→consumer boundaries, including:
- provider ingestion → operational order;
- order → inventory;
- order → vendor;
- order → Delhivery/Own Courier;
- order → WhatsApp template variables;
- courier events → tracking/delivery;
- COGS → Growth profit.

Also audit provenance/timestamp correctness (`orders.source`, provider created time, timezone-safe timestamps) rather than accepting placeholders/default dates.
Also audit provider pagination/completeness boundaries (line items, refunds, product/variant pages and any other fulfilment-critical collections) so API page-size defaults cannot silently create partial business truth.
- **Status:** PRE-P3 QA REQUIREMENT.

## FD-QA-06 — One integrated Pre-P3 acceptance path
- Do not treat internal CR/workstream labels as separate Founder release stops.
- Build/fix into one integrated candidate, then run the full P0/P1/P2 + Pre-P3 regression, security/tenant-isolation checks and Red-Team/fix-forward cycle, followed by **one fresh final Codex review** on the exact release SHA.
- **Status:** LOCKED DELIVERY DISCIPLINE.

## FD-QA-07 — Client-ready rollout gate
Pre-P3 release is not considered client-ready merely because tests compile/pass. Recorded evidence must prove:
- invited self-onboarding + e-mail verification + company creation without hidden DB intervention;
- at least one usable sales channel;
- automatic current-source orders with truthful source;
- order truth + fulfilment + WhatsApp + Growth + Team + hosted address + privacy;
- no dead consequential CTA, silent failure, misleading success or cross-tenant exposure;
- all required regression suites green on the release SHA.
Rollout sequence remains controlled: **C0 test company → C1 companies one at a time → 7-day soak with no blocker → Founder sign-off** before broader continuation.
- **Status:** LOCKED RELEASE GATE.

---

---

# 31. CURRENT PRE-P3 IMPLEMENTATION-ONLY REQUIREMENTS ALREADY DECIDED

These should NOT trigger another Founder design round unless implementation evidence creates a genuine contradiction:

1. Reconnect new Shopify/Wix automatic orders to complete mature operational order data.
2. Preserve sanitized useful Shopify/Wix order JSON/event snapshot alongside normalized data.
3. Add/fix Shopify/Wix COGS capture and frozen order-line cost.
4. Make customer WhatsApp live journey safe: suppression, no sender fallback, no auto-replay, complete lifecycle triggers.
5. Real logout.
6. Protect/disable `/er-diagram`.
7. Removed/disconnected provider data must not be used for live recipient resolution.
8. Complete Blocker-5 Admin + client operational hardening.
9. Restore five Admin pages.
10. Dangerous Admin reason/confirmation/audit.
11. Client deactivate/reactivate + offboarding operator tooling.
12. Retire old finance/wallet/payment active controls and Product Sales; preserve history.
13. Home cards open correct filtered Orders.
14. Mini-Store first Publish + Live/Paused.
15. Locked modules visible.
16. Usage unavailable != zero.
17. Provider disconnect confirmation.
18. AI data-access master after onboarding.
19. Growth truthful labels/zero-spend ROAS behaviour.
20. Vendors & Shipping navigation grouping.
21. Verify/implement frozen Orders/Shipping/Inventory lifecycle rules rather than re-deciding them.
22. Preserve Ask AI and mature provider execution model.
23. Preserve all retained micro-capabilities from the final capability manifest unless explicitly superseded/retired, including Product Price/Shipping Rules, Mini-Store Carts/Leads/Store Design, connection Primary Store/health semantics and Influencer AI recommendations behind consent.

---

# 32. EXPLICIT POST-P3 / DEFERRED ITEMS

Do NOT count these as Pre-P3 missing:

- full cross-provider raw-data architecture beyond Shopify/Wix order-ingestion preservation;
- secure Platform Admin impersonation;
- granular/custom Roles & Permissions redesign;
- perfect mobile bottom-nav polish when current mobile navigation is usable;
- deeper Company Brain ↔ Ask AI profile merge/rearchitecture;
- new Growth Snoozed state;
- provider-catalog merge project;
- ERP-style inventory redesign;
- large compatibility architecture for old historical orders;
- migration from accepted beta Evolution/Baileys transport to an official WhatsApp provider/channel unless separately pulled forward.
- P8-only shell/identity cleanup such as broad `/client` → `/dashboard` redirect migration and `clients.user_id` resolver replacement, unless a current Pre-P3 bug specifically requires a bounded fix.

---

# 33. SUPERSEDED / IMPORTANT OVERRIDES

## Override A — P2 messaging dark state vs Pre-P3
- Old P2 messaging activation OFF was valid for P2 release/testing.
- **Current Pre-P3 requirement:** WhatsApp customer journey must be live-capable and safe.

## Override B — blank provider operational orders
- Old P2 analytics/minimization architecture intentionally avoided PII and operational fulfilment.
- Pre-P3 now requires complete operational provider orders.

## Override C — COGS
- Earlier audit treated Shopify/Wix COGS as later/non-blocking.
- **Current Founder decision:** COGS is Pre-P3.

## Override D — company privacy export
- Earlier decision text said Owner/Admin.
- **Latest Founder decision:** Owner only.

## Override E — locked modules
- Earlier recommendation to hide unavailable modules is superseded.
- **Latest:** visible + locked.

## Override F — client legacy Analytics
- Earlier “retire after parity” for client Analytics is superseded.
- **Latest:** remove client legacy Analytics now. Platform Admin Analytics stays temporarily.

## Override G — Admin impersonation
- Final product requirement remains, but **Post-P3**, not current launch blocker.

## Override H — Wix raw deletion
- Do not blindly mirror Shopify deletion requirements.
- Fix active-use/privacy risk; require deletion only where policy/product privacy actually requires it.

## Override I — WhatsApp customer suppression
- An earlier UX discussion briefly deferred customer suppression.
- After the Founder clarified that customer WhatsApp messaging is definitely LIVE in Pre-P3, suppression was explicitly re-approved as part of Pre-P3 WhatsApp hardening.
- Latest rule: automatic order-journey suppression is Pre-P3; do not extrapolate unapproved Broadcast/manual semantics.

## Override J — Manual/Admin order creation
- Older mature/manual order creation paths may still exist in code/history, but the frozen legacy-retirement scope removes Google Sheets/CSV/Admin manual creation as current ingestion sources.
- Do not count their retirement as loss of a required Pre-P3 sales channel.

---


# 33A. V10 RED-TEAM VERIFICATION GATES — NOT NEW FOUNDER DECISIONS

**Source:** Claude `PRE_P3_V9_INDEPENDENT_RED_TEAM_RESULT.md` + `evidence/PASS1/2/3` and subsequent `BHARAT_LAUNCHPAD_CLAUDE_RED_TEAM_CRITICAL_RECONCILIATION_2026-11-07.md` against exact candidate `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`.

**Confidence boundary:** Claude's high-severity code references were source re-checked by its primary reviewer, but there was NO runtime/browser/provider/DB production validation. A `FAIL` in the table below means *static code-logic failing a stated requirement*, NOT proof that a production merchant suffered the impact. Re-run on changed SHA and validate via non-destructive tests before launch.

| ID | Red-Team static result | Verification / acceptance required | Decision treatment |
|---|---|---|---|
| RT-01 | FAIL | Vendor notification cannot set `current_stock=5` or mutate stock as side effect; retire unsafe duplicate safely. | Verified cleanup risk; FD-INV-01 policy now LOCKED; no implementation without Founder approval. |
| RT-02 | FAIL | Price Rules categories visible only where company or intentional shared-taxonomy scope allows; verify intended taxonomy first. | Audit cross-tenant metadata, no invented taxonomy rewrite. |
| RT-03 | FAIL, critical | No Bharat Karigar/personal UPI, phone, bank or payee fallback to another client's customers; missing brand-specific payment config = safe blocked/readiness state. | Security/money must-fix. |
| RT-04 | PARTIAL | All enabled Evolution/legacy allowlist paths fail closed; distinguish dry-run and transactional sender. | Audit current use; do not assume production sending. |
| RT-05 | FAIL | Product edit preserves `category_id`, `extra_charge`, derived price/shipping rules and user-entered values. | Mature Product parity. |
| RT-06 | PARTIAL | Double-submit onboarding/idempotency and failed media upload rollback tested; orphan storage not presumed. | Audit/acceptance test. |
| RT-07 | FAIL | Automatic WhatsApp updates have real writer/owner controls and eligible onboarding/activation; old companies cannot silently opt in. | FD-WA-12/13 product contract. |
| RT-08 | FAIL for limit; consent NOT PROVEN | Read/enforce intended daily account sending limit at send-time; independently verify customer suppression/marketing consent semantics. | Do not conflate transactional and marketing approval. |
| RT-09 | PASS, static | Preserve Mini-Store common outbox; add runtime duplicate-event test. | Preservation; not proof of delivery. |
| RT-10 | PARTIAL | Delhivery-token and Shopify/provider setting multi-writers have consistent ownership, audit, concurrency; keep legitimate admin controls. | Audit before consolidation. |
| RT-11 | FAIL, high | Growth view/refresh cannot unexpectedly create operational orders/raw PII; one provider-order writer/idempotent upsert and read-only Growth truth. | Must-fix writer race. |
| RT-12 | PARTIAL | History events emit for real events; absent emitters truthfully disclosed; never fabricate past activity. | Match append-only contract. |
| RT-13 | FAIL | `whatsapp_merchant_alerts` visible/actionable in merchant UI incl Needs Attention. | WA go-live must-fix. |
| RT-14 | PARTIAL | DB export page itself has server-side Admin role gate; existing API guard preserved. | Security; don't claim raw cross-tenant export proven. |
| RT-15 | FAIL | Published/Paused and entitlement states enforced on PUBLIC Mini-Store reads including existing live-store compatibility. | Client launch must-fix. |
| RT-16 | FAIL, critical | Subtotal, shipping and payable money calculated/validated server-side, never trust browser negative/tampered totals. | Money integrity must-fix. |
| RT-17 | PARTIAL | All active Price Rule matchers produce same correct result (incl tie-breaks/extra charge), minimal reconciliation only. | Preserve mature logic. |
| RT-18 | PARTIAL | Plan Usage displays unavailable when no instrumentation; no fake zero/counter success. | Truthful usage. |
| RT-19 | PARTIAL / external mapping | Delhivery OFD mapping only from documented/provider-proven statuses; unknown stays unknown. | No guessed status. |
| RT-20 | PASS, static | Image transforms remain safe; browser/test evidence required for real performance. | Not implementation blocker absent failure. |
| RT-21 | PARTIAL | Lot-code uniqueness must not regress when legacy `products` table is retired; confirm migration order. | Cleanup dependency. |

**Additional mandatory gates not represented by a single RT ID:**

1. Shopify/Wix complete operational-order contract at sync, webhook and replay; valid customer contact/items/payment/COD/shipping, refund, currency and provider timestamp; preserve relevant sanitized JSON and clean privacy hooks. Old mature path retains parity until replaced; Growth must not act as a competing writer.
2. WhatsApp safe go-live: opt-out/suppression, exact sender without silent fallback, activation controls, live-vs-backfill boundary, no automatic held-message replay, admin/owner sending controls, account limit/merchant alerts and observable missed-outbox-event recovery. No promise of exactly-once delivery unsupported by evidence.
3. Entire public money and payment journey: server-authoritative amount, tenant-specific payee, tenant-scoped media and Product Price/Shipping Rule parity.
4. Security/Admin: real sign-out across portals; route/page guard `/er-diagram` and DB export; 5 Admin pages reachable; retired Product Sales destructive APIs and wallet controls inactive; offboarding/deactivation + reason/audit.
5. Cleanup: `vercel.json` scheduled `process-rtd`, `sync-products`, `sync-google-sheets`; distinguish 410 no-op from active mutating cron, require separate approved production cron deregistration; never drop legacy tables until dependent media/lot-code/current mature paths are replaced.
6. Data rights: actual Shopify scrub/redaction preserved; Wix retained PII appropriately erasable upon legitimate privacy action; new provider sanitized JSON included in erasure/export; disconnected/removed store cannot fuel live contact lookup.
7. Completeness: 506-row manifest rows are **catalog entries, not tested PASS**. Reconcile client Analytics retire-now, useful Admin Products preserved, impersonation Post-P3, ER diagram protection, WhatsApp settings status, and missing suppression row. All mature PRESERVE actions must remain reachable.
8. Missing-evidence ledger: historic TI-02/03/06/29/31/32/33/37/39 NOT TRACED; TI-05/10/11 PARTIAL; runtime, Shopify access state, WhatsApp activation, `P2_JOBS_ENABLED`, 381 preserved-row parity all NOT PROVEN. Do not silently pass them.

**No direct Founder decision is created by this appendix. Technical fixes still require reviewed implementation scope, test plan, rollout controls and Founder authorisation.**

---

# 34. ITEMS THAT SHOULD BE AUDITED, NOT RE-ASKED YET

These are implementation/evidence questions, not new Founder product questions unless a real contradiction emerges:

- multi-tenant `payment_pending` / payment-message defaults must never expose platform-owner bank/UPI details to a client; if the current default is unsafe, blank/default-safe content + readiness warning is a technical safety fix, not a new Founder choice;
- public Mini-Store entitlement/first-Publish/Paused route enforcement must be consistent with the frozen product state without breaking existing live stores;
- Mini-Store/enquiry monetary totals supplied by a browser must be server-side revalidated/recomputed before becoming operational truth;
- retained share-link (`/m/[shareCode]`) capability, if part of the protected mature Mini-Store contract, must either have a real creator/reachability path or be explicitly classified; do not leave a dead-but-exposed route by accident;
- Staff Internal Status-label editing and similar fixed-role micro-permissions must follow existing frozen role/security policy; do not infer expansion from UI convenience;
- current free-beta/platform-key AI cost treatment and any product/address-parse AI usage must be audited against the accepted beta plan rather than silently inventing billing;
- current Vendor category/sub-category text/list fields vs broader category master/storefront presentation layers have known drift/duplication risk; audit the real dependency graph, but do not replace the mature Vendor → Product Onboarding → shared-product distribution flow with a speculative taxonomy rewrite;
- exactly which mature Shopify/Wix mapper/path should be reused;
- exact reconciliation semantics between current provider truth and the operational snapshot after order creation (which provider-owned facts are read live from normalized provider tables vs safely refreshed in the snapshot), while preserving the frozen rule that merchant edits must not become a second provider-commercial truth;
- how provider updates reconcile with the operational snapshot while preserving provider truth;
- exact Shopify/Wix cost endpoint/query and permissions;
- exact migration shape for order-level sanitized provider snapshots;
- exact suppression schema/UI placement;
- exact cleanup/dead-code removals after mature-vs-obsolete classification;
- exact tests needed to close the provider-order integration blind spot;
- whether any old path can be safely removed after new path parity is proven;
- exact blocked-state/helper wording for reassignment / Own Courier;
- exact Growth wording for cost coverage / profit unavailable;
- whether Staff may edit non-sensitive vendor fields, print/download a label, or run per-order Refresh Status under the current fixed-role model — audit existing role policy first; do not invent a granular role system;
- exact provider/dashboard state for Shopify protected-customer-data access;
- whether source/provenance defaults, timestamps/timezones, old RLS paths or legacy route reachability still create runtime debt on the current candidate.

---

# 35. REGISTRY REVIEW GATE

Before sending another implementation prompt to Claude:

1. Founder reviews this registry for missing/incorrect decisions.
2. Any corrections are incorporated here first.
3. Claude receives this registry as authoritative context.
4. Claude performs the forensic audit against it.
5. Audit returns PASS / PARTIAL / DISCONNECTED / REGRESSION / MISSING / RETIRED / DEFERRED / EXTERNAL / NOT PROVEN.
6. Only then is a final implementation scope produced.

**No implementation is authorized by this registry alone.**

---

# 36. SOURCE SET USED TO BUILD THIS DRAFT

- `BHARAT_LAUNCHPAD_DEEP_CONTEXT_FULL_CHAT_2026-10-11.md`
- `BHARAT_LAUNCHPAD_P2_PLANNING_AUDIT_MASTER_CONTINUITY_FULL.md`
- `BHARAT_LAUNCHPAD_P2_CHAT_CONTINUITY_PLAN_FULL_CONTEXT_2026-11-07.md`
- `BHARAT_LAUNCHPAD_FOUNDER_RECONCILIATION_AUDIT_5bc0e1b3/appendices/APPENDIX_D_FOUNDER_DECISIONS_AS_AUDITED.md`
- `PRE_P3_FUNCTIONAL_REALITY_AUDIT_5bc0e1b3/PRE_P3_FUNCTIONAL_REALITY_AUDIT_5bc0e1b3.md`
- latest Founder decisions from the current Pre-P3 review, including the order-wiring, provider JSON, COGS, WhatsApp, privacy/security, Admin completion and Vendors & Shipping decisions.
- `BHARAT_LAUNCHPAD_PRE_P3_COMPLETE_HANDOFF_2026-11-07` Founder decision records and UX contracts (read-only cross-check)
- `Pasted text(20261106-201224).txt` Product Onboarding preservation discussion
- `Pasted text(20261106-201521).txt` WhatsApp Founder-decision continuation
- `Pasted text(20261106-211340).txt` detailed Orders → Vendors → Mini-Store → WhatsApp → Products Founder UX review and later corrections
- recent Shopify/Wix new-order and policy audits from 2026-11-07.



## 32. V10.3 implementation-only carry-forward (not implementation authorisation)

- Enforce one connected/active external commerce store **Shopify OR Wix** per company, with optional Mini-Store. Primary external selection controls Growth and Ask AI external-commerce context; secondary external connection must be refused clearly.
- Shopify and Wix receive comparable **supported, safe** mature Growth functionality, including READ analytics/Store Doctor/catalog/planner/Ask AI and **approval-gated provider writes** for product edits, coupons/discounts, blog/articles and explicit merchant-initiated inventory adjustments.
- Apply the 29-row audit crosswalk, preserve shared Meta/GA4/Creative Studio and Wix functionality, and keep unsafe/provisional Wix cancel/refund/ShopifyQL claims NOT PROVEN until separately verified.
- Review Shopify minimum additional scopes/merchant reauthorisation and correct execution/audit/failure recovery before any provider-write test; no permission, flag, database, source or production change now.
- Orders cannot auto-mutate provider inventory on Confirm/Cancel/etc. Native Mini-Store Check Availability remains.
- Updated companion: `BHARAT_LAUNCHPAD_PRE_P3_SCOPE_DRAFT_V10_3_2026-11-08.md` and `BHARAT_LAUNCHPAD_V10_3_GROWTH_PARITY_FOUNDER_ADDENDUM_2026-11-08.md`.

---

# 37. V10.4 NO-REOPEN RECONCILIATION
- Points 1/2/3 from the recent inventory discussion are **CLOSED**: (1) Mini-Store availability-based, provider-owned stock; explicit Owner-approved Wix and Shopify Growth write actions only; (2) old P1 Confirm/Cancel stock movement superseded, migration/production status still to verify at release gate; (3) retired Product Sales-only notification API family must be safely retired while keeping live vendor notifications.
- Latest **one external provider** Shopify OR Wix per company, optional Mini-Store, primary-only external-commerce Growth/Ask AI source, and comparable supported Shopify/Wix READ + Owner-approved WRITE parity remain unchanged from V10.3.
- `5bc0e1b3` is an **audited candidate**, NOT proof of final Pre-P3 readiness. No code changes, scope execution or provider permissions authorized by this document.
- Evidence: `PRE_P3_POINT3_VENDOR_NOTIFICATION_RETIREMENT_AUDIT_5bc0e1b3.md` and `PRE_P3_GROWTH_WIX_SHOPIFY_PARITY_AUDIT_5bc0e1b3/03_WIX_TO_SHOPIFY_PARITY_MATRIX.md`; source paths from static code audit must be revalidated on implementation SHA.