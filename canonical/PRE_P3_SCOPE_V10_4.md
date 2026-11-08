# BHARAT LAUNCHPAD — PRE-P3 CONSOLIDATED FUNCTIONAL SCOPE & ACCEPTANCE DRAFT (V10.4)

**Created:** 2026-11-07  
**Candidate under static audit:** `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`  
**Status:** **V10.4 RECONCILED DRAFT FOR FOUNDER REVIEW / AUDIT & TEST PLANNING ONLY — NOT AN IMPLEMENTATION ORDER**  
**Decision source:** `BHARAT_LAUNCHPAD_FOUNDER_DECISION_REGISTRY_CANONICAL_V10_4_2026-11-08.md` (retains V10.1 Mini-Store stock + V10.2 Wix approved edit; adds Founder-approved single external store/primary Growth+Ask AI and Shopify/Wix READ+approval-gated WRITE parity). **Implementation NOT authorized.**  
**Evidence source:** Claude independent V9 Red-Team report and three evidence appendices; prior functional-reality audit; subsequent critical reconciliation.  
**Boundary:** No repository/production access in this reconciliation. Assertions about current SHA are **Claude's code-reading findings**; they are not independently rerun browser/API/DB tests here.

## 0. Founder executive summary — what is known, not what is assumed

- **Product goal:** a real client operates the entire ecommerce journey inside Launchpad, including existing mature systems and **live** WhatsApp order notifications. Shopify, Wix and Mini-Store must be operable without retyping data already available from the source. Growth, Ask AI, Products, Admin, privacy, public storefront and connected portals must also function; passing isolated tests does not prove launch readiness.
- **Mature functions exist:** older Shopify importer/Wix import and Mini-Store have operational order creation; vendor, Delhivery, Own Courier, order tracking, WhatsApp outbox and many Admin/AI features exist in code. **Existing ≠ currently reachable ≠ runtime PASS.** Preserve mature functionality until parity has been proved.
- **Core disconnection:** automatic Shopify/Wix flow creates blank `orders` rows, while provider facts live elsewhere and older complete import skips the already-created row. This is **one upstream root cause** with several downstream symptoms, not proof all Shipping/WhatsApp/Vendor modules were never built.
- **Independent additional risks:** browser-trusted Mini-Store money, wrong-brand payment fallback, public Publish/Paused enforcement, Growth triggering an old order writer, notification code modifying stock, WhatsApp activation lacking a verified writer, Admin/auth/cleanup issues. These are not mere order-wiring side effects.
- **Prior numbers are not launch sign-off:** `57/120` is an inventory-style capability PASS count; `21/23` was a narrower critical-journey static score; `10 FAIL / 9 PARTIAL / 2 PASS` is a **risk-selected** red-team sample. None is an audited Pre-P3 production readiness percentage.
- **Inventory Founder decisions LOCKED (V10.1 → V10.3):** Mini-Store retains vendor **Check Availability**, with no automatic numeric decrement/restore. Shopify/Wix inventory stays provider-owned; **no order-driven stock mutation or automatic write-back**. Wix retains explicit Owner-approved `wix_update_inventory`; V10.3 additionally authorises the **equivalent explicit merchant-initiated, Owner-approved Shopify inventory edit** through the gated/audited Growth action model. Historical P1 Confirm movement is not current authority. Unsafe vendor-notification `current_stock=5` remains a separate code risk. **Neither Shopify permission grant nor implementation is currently approved to execute.**
- **Latest decisions preserved:** order-specific sanitized Shopify/Wix JSON **Pre-P3**, complete operational orders, provider-owned COGS frozen per order line **Pre-P3**, WhatsApp live, Owner-only company export, Wix no blanket deletion just because of Shopify policy, and full Admin functional completion. Full cross-provider raw architecture is **Post-P3**.
- **New V10.3 Founder lock:** one external commerce provider per company (**Shopify OR Wix**) with optional Mini-Store; Growth AI/Ask AI external-commerce context is the selected primary provider. Shopify must match mature supported Wix Growth/Ask AI capability for **READ and human-approved WRITE** actions, without cross-provider targeting or unsafe automatic stock changes. Older Oct 29 `no Shopify write scopes` and the blanket V10.2 Shopify read-only statement are **narrowly superseded**; no grants or installations have been changed. Earlier 29-row Wix→Shopify static audit identified 3 already working, 9 small adapters, 7 genuine development and 9 previously blocked by old decisions; these are not post-approval implementation counts.

### Status/evidence legend

- `CODE-OBSERVED / STATIC`: present in Claude source inspection, no live runtime confirmation.
- `DIRECT FOUNDER`, `FOUNDER-ACCEPTED`, `PRESERVE`: authority classes, not implementation verification.
- `PARTIAL / DISCONNECTED / REGRESSION / MISSING / NOT PROVEN`: audit classifications, not a decision to rewrite.
- `MUST`: must be accepted for Pre-P3 if code evidence confirms applicable exposure. `VERIFY`: targeted proof first. `DEFER`: latest explicit Post-P3. `NO DESTRUCTIVE ACTION`: audit-only or controlled future release gate.

## 1. Mandatory stop-the-line work packages (independent failures)

| Work package | Evidence/current risk | Pre-P3 acceptance (not implementation approach) | Evidence status |
|---|---|---|---|
| **WP01 Provider → operational order** | `379/452` placeholders; mature import duplicate-skip | New Shopify/Wix order from sync OR webhook OR replay yields usable name, phone, address/pincode/city/state, items/SKU/variant/qty, correct amounts, currency, payment/COD, source and timestamps. No re-entry, no phantom `₹0/Manual`; no duplicate order. | CODE-OBSERVED; end-to-end NOT PROVEN |
| **WP02 Order writer ownership** | Growth refresh calls old Shopify order import; old and new writer race | Growth fetch/report **does not create/alter operational orders**. One explicit deterministic provider-order upsert contract. Mature import not retired until complete parity. | CODE-OBSERVED; race reproduction NOT PROVEN |
| **WP03 Provider JSON + normalized truth** | Fixed normalized fields omit useful data; old raw tables hold sensitive JSON | For **Shopify/Wix order ingestion only** sanitize and preserve useful versioned provider snapshot/event + normalized facts + operational snapshot; source identifiers/event timestamps, privacy erasure/export, no tokens/secrets; provider commercial truth remains read-only and shipping contact may be operationally overridden. | LATEST FOUNDER; shape/retention to audit |
| **WP04 Financial/fulfilment data integrity** | payment `Manual`/₹0 placeholder; limited item/refund pages; current time substituted; Wix variant id null | Correct prepaid vs COD, total/discount/tax/shipping/refunds/currency/order-date, complete lines/refunds via pagination or explicit blocked-incomplete state. No incorrect courier booking, no silent partial order. | CODE-OBSERVED/PARTIAL |
| **WP05 COGS** | Shopify/Wix cost not fetched or frozen; source capability details need verification | Provider cost source of truth, no reverse write; frozen line-cost snapshot when available, missing clearly unknown, later fill missing only; product later-cost change does not rewrite frozen order; profit only when valid. | FOUNDER-ACCEPTED, implementation absent per audit |
| **WP06 Mini-Store server-side money** | Client-submitted subtotal/shipping including negatives can be persisted | Server computes/reconciles line totals, product price, shipping rules and final payable; rejects tampered negative/out-of-range monetary payloads; a correct valid order still succeeds. | RED-TEAM FAIL (STATIC) |
| **WP07 Tenant-specific payment communication** | Default payment-pending message contains Bharat Karigar personal payment details | No customer of another tenant receives another brand's bank, phone, UPI or payee. Unconfigured payee => safe Needs Setup/blocked template; no silent fallback; tested in two-tenant setting. | RED-TEAM FAIL (STATIC) |
| **WP08 Store Publish/Paused and entitlements** | Public served content path misses state check | Unpublished/Paused/unentitled store cannot sell/serve the live merchant journey. Existing live stores remain safe through an explicit cutover test; no forced global disable. | RED-TEAM FAIL (STATIC) |
| **WP09 WhatsApp live setup & activation** | Config default OFF, no verified writer or merchant activation UI; flags not runtime inspected | Eligible invited new company can enable/configure actual order automation; older existing companies not silently opted in. QA sends only under approved safe provider/test mode. Automatic messages fire on real eligible events. | STATIC FAIL, PROD STATUS NOT PROVEN |
| **WP10 WhatsApp sender & suppression** | Fallback/held-replay/opt-out and Staff manual paths reported | Suppress customer who opted out; unavailable configured sender => held/Needs Attention, **no alternate number silently**; no auto-replay stale messages on reconnect; authorized Owner/Admin manual recovery preview/confirm/audit; Staff not granted new messaging rights. | Earlier audit + FOUNDER lock; runtime NOT PROVEN |
| **WP11 WhatsApp merchant alerts, limits, recovery** | Alert writers no UI reader; daily limit no send-time reader; potential outbox lost window | Merchant can see blocked/failed events and act. Intended per-account safety limits enforced at send boundary, with transactional-vs-marketing semantics verified. Dedupe and observable missing-event recovery both tested; do not promise delivery exactly once. | RED-TEAM FAIL/PARTIAL (STATIC) |
| **WP12 Retired-only notification stock writes (Point 3 CLOSED)** | Targeted audit confirmed `/api/inventory/notify-vendor*` are retired-only paths; not called by current fulfilment/Mini-Store notifications; Product Sales UI still reachable | Retire both obsolete handlers with 410 and zero DB/WhatsApp side effect; preserve active Step 4 and Mini-Store vendor notifications; historical tables/rows unchanged | TARGETED STATIC SOURCE AUDIT; no runtime execution observed |
| **WP13 Inventory / availability source ownership** | Historical P1 Confirm stock mutation; current candidate no-order-stock movement; separate unsafe legacy vendor-notification writer; Wix `wix_update_inventory` approved-action path exists in static audit | **Founder-locked:** Mini-Store enquiry/vendor reply with no numeric decrement/restore. Shopify/Wix inventory remains provider-owned; **neither has automatic order-driven stock changes**. Wix existing explicit merchant-initiated Owner-approved `wix_update_inventory` preserved. Shopify equivalent explicit Owner-approved inventory update is now **approved target**, subject to correct API/scopes/location identity and existing approval/gated/audit path; no provider scope/write changed yet. Reject unauthorized, wrong-store, mismatched or replayed requests; old unsafe writers remain a separate fix. | **FOUNDER DECISION LOCKED (FD-INV-01/05/06); SHOPIFY WRITE NOT BUILT; PROD GATES NOT PROVEN; NO IMPLEMENTATION AUTHORIZED** |
| **WP14 Public/session/Admin security** | Sign-out links; `/er-diagram` no page gate; DB export page no page role gate | Logout actually invalidates auth/session across all relevant portals; protected pages reject unauthorised access at server/page and API layers; no tenant data leak. | RED-TEAM STATIC findings; exploitability NOT PROVEN |
| **WP15 Admin functional completion** | `AdminLayout` drops `children`; five routes unreachable | Five Admin pages (privacy triage/jobs/DB export/client plan/client flags) truly render and work; reason+confirm+DB audit for dangerous actions; deactivate/reactivate/offboard; Admin mature views preserved; no active retired finance controls. | CODE-OBSERVED + FOUNDER lock |
| **WP16 Cleanup of live old writers/APIs/crons** | Scheduled `process-rtd`, `sync-products`, `sync-google-sheets`; Product Sales destruction/retired wallet; old manual admin CTA | Proven-unused/retired UI+endpoints cannot perform unsafe writes. Distinguish harmless 410 cron from active `sync-products`; remove schedule via separately authorised release config. Keep mature order/product/lot-code dependencies until replacement parity. No destructive DB drop without approval. | CODE-OBSERVED, runtime dependency audit needed |
| **WP17 Product Price Rules + edit integrity** | Extra charge and category lost on edit; cross-company category query; price matcher duplication | Existing product edits preserve `category_id`, `extra_charge`, correct computed price, shipping rules and form state; categories tenant-scoped or explicitly shared; matchers parity; no cross-tenant leakage. | RED-TEAM FAIL/PARTIAL STATIC |
| **WP18 Privacy/data rights** | Wix raw PII lacks known scoped erase; fallback can resolve removed provider; new JSON increases privacy surface | Preserve already-built Shopify redact/erase. Do not blanket delete Wix on disconnect absent valid requirement, **but** legitimate erasure/retention/offboarding must work and removed-provider old PII must not fuel live messages. New JSON included in rights workflows. Owner export functional, not parked indefinitely. | FOUNDER lock + static data risk; policy/runtime verify |
| **WP19 Full merchant operations parity** | Home navigation, Plans/usage, Mini-Store publish, AI access, Growth truth, Company/Team/Connections remain partly implemented | All V10-preserved screens/workflows reachable and functionally truthful: operational Home cards/filters, final lifecycle, visible locked modules, honest usage, provider disconnect safety, data-access master, no fake cost/ROAS/currency. | V9 contracts; specific runtime NOT PROVEN |
| **WP20 Complete P0/P1/P2/Pre-P3 regression** | Prior tests asserted blank order and omitted full journey | Realistic integration/E2E and adversarial tests for source→customer→vendor→shipping→WhatsApp→tracking/delivery, money, privacy, role, concurrency, failure/retry, retained mature capabilities, **and J10/J11 Growth/Ask AI read+write parity**. Fresh Codex review only against new final SHA. | LAUNCH GATE; not current PASS |
| **WP21 Single primary external commerce provider** | Secondary external connection can be accepted while non-primary ingestion is silently ignored; Wix-first Growth paths still execute under Shopify primary | Enforce **Shopify OR Wix**, with optional Mini-Store, at UI, connection, source routing, ingestion, stored config and provider execution. Existing disconnected/historical rows cannot drive live reads/writes. Shopify-only merchant never sees Wix-only CTAs or Wix labels; rejected second connect is explicit. | DIRECT FOUNDER (FD-CONN-07); CODE-OBSERVED gaps; NOT IMPLEMENTED |
| **WP22 Growth/Ask AI READ parity** | Wix Store Doctor/workspace/planner/product picker and Wix-specific Ask AI tools have no Shopify UI callers; some Shopify GraphQL reads exist but unused | Implement provider-aware catalog/variants/stock/Store Doctor/planner/Meta product mapping where supported; Shopify Ask AI read tools, product picker, source guards; source/unknown/permissions/pagination truth. Preserve Wix feature parity and shared Meta/GA4/Creative Studio. | DIRECT FOUNDER (FD-GROW-12/FD-AI-04); PARITY AUDIT 29 rows; NOT IMPLEMENTED |
| **WP23 Growth/Ask AI approved WRITE parity + permissions** | Wix has several gated actions while Shopify has no write scopes/actions; Wix cancel/refund provisional risk | Build safe/mature supported Shopify equivalents of Wix **product edit, coupon/discount, blog/article, explicit Owner-approved stock edit** through existing preview/approval/execution/audit/reconcile model; scope/reauthorisation checks; fail closed if not granted. Audit additional Wix actions (cancel/refund, analytics access) for real, lawful functional parity without copying unsafe/provisional flows. No broad AI write permission or order-driven inventory. | DIRECT FOUNDER (FD-GROW-13/FD-INV-06); NEW DEVELOPMENT AND EXTERNAL SCOPE DEPENDENCIES; NOT AUTHORIZED |


**Prioritisation:** WP06/07/08/12/14 and exposed unsafe writers are launch-safety blockers in parallel with WP01/02/04/09/10/11. Do **not** call Mini-Store fully PASS until the new money/payment/public-gate cases are verified. WP13 is a distinct source-authority stop gate for stock behavior, not an invitation to change P1/P2 stock code blindly.

## 1A. Growth parity source audit → V10.3 work crosswalk (not implementation)

**Authority:** direct Founder approval after the 29-row Wix→Shopify parity audit: exact **supported functional** parity for both providers (READ + approved WRITE), one external provider selected, Mini-Store optional; do not blindly implement unsafe/provisional Wix operations.

| Audit rows (W-xx) | Actual source audit observation | V10.3 contract / work package |
|---|---|---|
| 01, 05, 17, 18, 20, 22, 27 | Store Doctor/Shopify catalog, planner, picker/Ask AI were Wix-first; Shopify queries were unused | WP22 provider-aware read/AI/UX adapter; full pagination, multi-location truth |
| 02, 04, 24, 25 | order windows, lifecycle/health/freshness/history | WP21/22; require correct primary source and truthful state; recheck optional audit labels under latest parity approval |
| 03, 23, 26 | shared import/install/canonical pipeline present but blank-order/queue problems | WP01/02/04/16 + WP21; do not count same root cause again |
| 06, 07, 08 | Shopify→Meta mapping/product sets and selection drafts were previously marked optional | WP22/23: parity target if Wix comparable functionality is mature; don't silently drop approved parity; preserve Meta approval semantics |
| 09, 11, 12, 16, 28 | Shopify product edit, coupon, blog actions blocked by old no-write-scope decision | WP23: Founder has now approved **approved-gated write parity**; assess scopes, grant/reauth, source targeting and execution. Old prohibition superseded as necessary, not an unconditional grant |
| 10 | Wix stock edit existed; Shopify inventory write formerly forbidden | WP13/23: comparable merchant-initiated **Owner-approved** Shopify stock edit, correct location/inventory identifiers, no automatic changes |
| 13, 14 | cancel/refund potentially reachable in Wix yet provisional/unsafe | WP23: **do not silently enable** Shopify equivalents; safety and real Wix contract review first, escalate specific unresolved scope only if necessary |
| 15 | Wix analytics access check; ShopifyQL/read_reports differs | WP22: match truthful insight/business value where technically supported; no automatic permission grant or invented ShopifyQL promise |
| 19 | Wix semantic analyst tools, Shopify none | WP22: Shopify sourced AI read tools, safe guards, no fabricated equivalent semantics |
| 21 | “In stock” constant was non-user-visible matching behavior | Preserve; no invented user-visible bug or feature scope |
| 29 | Wix old order ops not fully traced | NOT PROVEN; retain evidence question instead of assuming new capability |

**Specific integration tests to add after implementation approval:**
- Shopify-only and Wix-only separately: each gets usable Store Doctor, Product workspace, Ask AI source-aware queries and approved provider actions; forbidden/unavailable operation visibly honest, not silent success.
- Shopify primary must not require `wix_store` permission or use Wix tool/operation, labels or customer data.
- No second external provider can be connected/activated; historical inactive other-provider data cannot drive current actions. Mini-Store continues independently.
- Product/discount/blog/stock actions need correct minimum scopes, fresh merchant grant, explicit preview + Owner/human approval as required, correct provider/store IDs, role/plan gates, audit, failure/retry safety. No scopes granted or production writes in audit.
- Shopify inventory edits target correct location/inventory item and cannot result from order events, sync or vendor notification; Wix workflow remains unchanged.
- Shopify and Wix return truthful errors on missing scope, rate limits, stale inventory, unsupported provider functionality; no false AI conclusions.
- Provider-write risk review distinguishes mature Wix actions from provisional Wix cancel/refund; no blanket parity override of existing finance/commerce safety.

## 1B. Point 3 final disposition — legacy Product Sales APIs (not a new Founder question)

**Audit fact, not production incident:** on `5bc0e1b3`, `notify-vendor-product-sales` has one known UI caller (retired Admin Product Sales tab), while `notify-vendor` has no in-repo UI/lib/cron caller but direct Platform Admin HTTP access. Both set old-table `current_stock=5` before attempting a platform WhatsApp message. These tables are not the canonical stock source.

**Future authorised change only:** return HTTP 410 from both endpoints without DB or WhatsApp activity. Remove Product Sales sidebar/tab. After reconfirming caller map, retire old Product Sales-only `sales-from-orders`, `sync-product-sales`, `clear-product-sales` and `sales-summary` endpoints. Preserve historical database rows; do not drop old tables/migrations.

**Protected live paths:** Order Fulfilment Step 4 `/api/whatsapp/notifications/send-to-vendor`, Mini-Store `lib/mini-store-whatsapp.ts`, Vendor query responses in `vendor-product-queries.ts`. Product Sales retirement must not change these.

**Acceptance tests:** (1) all Product Sales-only routes refuse and make no state/message changes; (2) no Product Sales navigation/tab; (3) real vendor Step 4 sends once and updates vendor-notified state but no inventory; (4) Mini-Store enquiry/availability still sends and records vendor responses; (5) Staff cannot trigger prohibited manual vendor send; (6) two tenants isolated; (7) historical row counts unchanged.

**Source:** `PRE_P3_POINT3_VENDOR_NOTIFICATION_RETIREMENT_AUDIT_5bc0e1b3.md` (static code findings only).

## 2. Merchant journey — minimum real acceptance scenarios

Every scenario must show **what the merchant sees and can do**, plus source-to-consumer data fields and backend assertions. Real external provider writes must only occur in approved test environments, not uncontrolled production.

### J1. New Shopify order — webhook path
1. Shopify authorized app/connection produces a valid paid and a valid COD order with buyer/shipping address, phone, distinct variants/SKUs/quantities, tax/discount/shipping, provider timestamps.
2. A complete `orders` operational record exists with unambiguous provider link; provider commercial facts remain read-only; relevant sanitized snapshot exists and has proper tenancy/event version.
3. Owner/Admin sees full Orders detail, can assign valid vendor, explicitly confirm, create correct shipment (Delhivery) or valid eligible Own Courier dispatch, print label, track, complete delivery and see real audit/activity.
4. Exactly one operational order for each provider order; no second competing Growth/import writer, no fabricated COD or zero price; actual source-specific stock treatment is verified, not inferred.
5. WhatsApp uses the intended company sender/recipient, live activation boundary, correct template; no duplicates/unsafe fallback; manual recovery exists for failure.

### J2. New Shopify order — sync without webhook
Repeat J1 with webhook deliberately absent. **Phone/name/shipping and complete order facts must not depend on which technical transport arrived first.** Any protected-customer-data field genuinely not authorized by Shopify must produce explicit needs-access/blocked state rather than a fabricated recipient. Founder reports Shopify approval previously completed; verify actual app/dashboard state before blaming policy.

### J3. New Wix order — sync and webhook; disconnected store
Repeat J1 including Wix variant identity, payment and shipping. Then remove/disconnect provider in a safe test: no subsequent staging/raw phone fallback to live messaging; deliberate privacy-rights erase and retention rules tested separately (do not auto-delete everything on normal disconnect without authority).

### J4. Mini-Store — full cart/enquiry/order journey
Browse, gallery, availability, lead/cart, vendor communication, product/service price + extra charge + valid shipping rules, order creation, confirmation, shipping, WhatsApp journey and delivery. Manipulated `shippingCharge=-500` / forged subtotal must not lower payable; no tenant-external payee; unpublished/paused storefront cannot transact. Keep mature Mini-Store customer/contact/product variants and supplier cost. **Check Availability/vendor reply remains authoritative; Confirm/Cancel must not auto-mutate numeric stock.**

### J5. Shipping states/exception paths
Delhivery vendor pickup readiness, company-specific Delhivery channel for shared vendor, Own Courier prepaid-only/manual dispatch, COD manual dispatch blocked; no fake six-digit pin or address. Shipment failure leaves Confirmed; AWB remains after label failure; manual Delivered Owner/Admin reason + confirm + DB audit; provider status remains truthful; resend tracking confirmation; no double book/reassign after AWB.

### J6. WhatsApp live customer journey
For each source test: order received (live only, no backfill), confirmed, tracking/shipped, OFD (provider-proven status), delivered, cancelled, failed/held/manual retry. Verify template master/individual switch/mini-store group switch, sender ownership, account limits, recipient suppression, disconnect, stale reconnect, merchant alert UI and data source fallback. Distinguish event *queued* vs *sent* vs *delivered* vs *failed*.

### J7. Company/tenant isolation & account lifecycle
Two unrelated merchants with different categories, payment bank/UPI, WhatsApp senders, vendors, domains and orders. Each sees only allowed data and correct messages. Owner-only company export, dangerous Admin actions audited, company deactivate does not delete retained orders, no Staff unauthorized customer send, logout invalidates session, Admin-only routes block deep-link bypass.

### J8. Growth/Ask AI/reporting truth
Loading and refreshing Growth does not create a new order or raw customer record. Real store orders differ from Meta claimed, missing cost ≠ zero profit, no ad spend ≠ 0.00x Cash ROAS, no currency mixing, stale/partial data visible. Ask AI mature history/attachments/product picker/image generation/approvals/actions intact and scoped. Client legacy Analytics gone; Admin useful Analytics retained.

### J9. Negative/concurrency/rollback
- Duplicate Shopify/Wix webhooks and sync overlaps; two writers racing; backfill vs live tagging; reconnect and held message behavior.
- Multi-page line/refund pagination; bad SKU/variant/phone/address/pincode; unproven status; missed webhook; null cost.
- Two clicks on product/media onboarding, failed file upload, stale media stamping, cross-tenant category/price rule, legacy lot-code uniqueness after cleanup.
- Missing vendor pickup/channel; tracking error; label error; conflicting payment method; cancelled/returned/refunded.
- Offboarding/privacy erasure while raw JSON and outbox data exist; removed-provider customer contact lookup.
- Admin deep-link without permission; feature locked but URL directly entered; failed invite email must not create fake accepted invite.

### J10. Shopify-only Growth + Ask AI full READ parity
Shopify primary, Wix not connected: Today/Store Doctor/Product Workspace/planner/product picker/AI business queries use Shopify facts and valid source permissions; no Wix API/tool/text, no secondary store. Test >25 variants and multiple locations/partial stock, costs/COGS, stale sync, missing grants, source-specific Meta mapping and correct campaign attribution. Mini-Store can stay enabled independently without being silently counted as external Shopify AI revenue.

### J11. Approved provider WRITE parity (Shopify versus Wix)
For Shopify and Wix separately, the merchant can prepare supported product edit, coupon, blog and explicit inventory edit as permitted, view preview and required permissions, obtain applicable Owner approval, execute only via existing audited provider-action path, and see success/failure/reconciliation. Test wrong provider, wrong inventory location, wrong tenant, Staff, missing grants, stale approval, duplicate execution and disabled gates. **No automatic order-triggered inventory write.** Provisional order cancel/refund safety is not silently green.

## 3. Capabilities to preserve by surface (not a rebuild checklist)

| Surface | Preserve / verify | Exceptions and redirects |
|---|---|---|
| Home | Setup, urgent exceptions, To Confirm/To Ship, click-through filtered Orders, connection/WhatsApp readiness, role-aware actions, mobile usable | No new dashboard customization/fake search |
| Orders | Mature order workbench, monitoring search/filter/export, step-by-step Fulfilment/Overview/Shipment/Messages/Activity, vendor assignment separate from Confirm, one source truth, exceptions | Retire old Admin/Sheets/CSV manual creation as current source; historical records safe/read-only until deleted |
| Products | Native Product Onboarding, media/stamp/code rules, variants, prices, Product Price Rules/Shipping Rules, edit form, shared vendor/product chain | No speculative Shopify/Wix catalog merge, no new ERP or Draft-Publish invention |
| Vendors & Shipping | Vendor create/readiness, company-scoped channel, shared vendor global pickup, Delhivery/Own Courier, AWB/label/tracking/cancellation | Navigation group only; preserve routes/business logic; no false fallback |
| Mini-Store + public | Catalog, gallery, cart, enquiries/availability, leads/abandoned carts, store design, homepage/pixels/entry gate, domain, first Publish/Live/Paused, notifications | No duplicated order/shipping implementation; public payee/money safe |
| WhatsApp | QR/accounts/templates, common transactional outbox, Broadcast separate from Message Activity, event switches, sender and delivery status, retries | Live Pre-P3 under explicit safe activation; Staff customer send not broadened |
| Growth | Today, truthful orders vs Meta claimed, partial/stale reports, ROAS/profit, AI Actions, provider approval/execution | Retire client legacy Analytics, preserve useful Platform Admin Analytics; no writes on report refresh |
| Ask AI | All mature conversations/history/retention, multilingual, attachments, picker, generation, quotas, approvals/action guardrails | Company Brain deeper integration Post-P3; preserve existing flows |
| Company/Team/Plans/Domains/Connections | Auth/invites, role/seat, brand/profile, primary store, hosted/custom domain, provider statuses, entitlements locked-visible, truthful usage | Full granular Roles & Permissions redesign Post-P3; retain deep-link auth |
| Privacy/History/Admin | Owner export and offboarding, rights requests, Shopify scrub, append-only activity, Admin pages/plan/flags/jobs/support, dangerous-action audit | Old Product Sales/Wallet/Payments and Finance UI retired; impersonation Post-P3 |
| Vendor + Influencer portals | Mature authenticated vendor views and influencer marketplace/recommendation consent | Influencer earnings/payout UI retired only where approved |

**Preservation proof required:** Source capability manifest contains **506 unique records**; that is not proof 506 workflows function. Every `PRESERVE` or later Founder-reorganised capability must have a reachable route/action/contract or a justified safe retirement classification. In particular five built Admin pages are unreachable because `AdminLayout` discards content, per static audit.

## 4. Red-Team 21-case crosswalk — every case accounted for

| RT | Static status | Work package(s) | Minimum proof |
|---|---|---|---|
| 01 Notification sets stock=5 | FAIL | WP12/13 | Notify vendor; stock remains unchanged |
| 02 Cross-company Price Rules categories | FAIL, metadata | WP17/J7 | Two tenant category-picker isolation or explicit shared-scope specification |
| 03 Personal payment details as fallback | FAIL, critical | WP07/J4/J7 | Missing client template cannot output wrong-payee bank/UPI |
| 04 Legacy Evolution allowlist fail-open | PARTIAL | WP10/11 | Enabled sender with empty allowlist safe; dry-run distinguished |
| 05 Product edit loses category/extra charge | FAIL | WP17 | Round-trip edit with price/extra charge preserved |
| 06 Double submit/orphan media | PARTIAL | WP17/J9 | Idempotent onboarding; rollback; orphan not presumed until reproduced |
| 07 No automatic updates writer | FAIL | WP09 | New eligible company has effective switch/setter; existing company consent gate |
| 08 `daily_limit` never read; consent unproven | FAIL / NOT PROVEN | WP11 | Send N+1 threshold/transactional exception defined; consent separately checked |
| 09 Common Mini-Store outbox | PASS static | WP10/J6 | Preserve plus duplicate event runtime proof |
| 10 Multiple settings writers | PARTIAL | WP18/Connections | Writer map + stale-write concurrency and audit |
| 11 Growth invokes old order sync | FAIL | WP02/J8 | Growth refresh zero unintended operational/raw-order writes |
| 12 Missing history emitters | PARTIAL | WP19 | Real event generates audit; no fabricated legacy events |
| 13 Alert writer without reader | FAIL | WP11 | Merchant UI visibly explains blocked sender/recovery |
| 14 DB export page role guard | PARTIAL | WP14/15 | Unauthorised page AND API blocked |
| 15 Public Publish/Paused gate | FAIL | WP08/J4 | Paused/unpublished cannot serve active checkout |
| 16 Browser money trusted | FAIL, critical | WP06/J4 | Invalid negative/tampered amounts rejected |
| 17 Duplicated price matchers | PARTIAL | WP17 | Matcher parity for same input |
| 18 Usage counter unwritten/false zero | PARTIAL | WP19 | Uninstrumented usage = unavailable, not zero |
| 19 Delhivery unknown OFD mapping | PARTIAL/external | WP04/J5/J6 | Provider-proven event only, unknown stays unknown |
| 20 Image transform OFF unless configured | PASS static | WP19 | Preserve; browser performance verified during release |
| 21 Legacy lot-code depends on products | PARTIAL | WP16/17 | After safe cleanup uniqueness still correct |

Other historical technical items **not traced:** `TI-02,03,06,29,31,32,33,37,39`. **Partly traced:** `TI-05,10,11`. These must be explicitly dispositioned in audit; `NOT PROVEN` is not `PASS`.

## 5. Manifest, contract and provenance corrections

The 506-row capability manifest needs an **overlay/crosswalk** rather than blind editing that erases historical context:

1. `GRW-A-01` — client legacy Analytics: latest Founder says retire **now**, not P5; old route still live per static report.
2. `CAT-L-01` / `PLT-097` — distinguish obsolete sheet-based Admin catalog from useful Admin Products still preserved. No blanket deletion.
3. `PLT-107` — impersonation is final planned **Post-P3**, not permanently retired.
4. `PLT-108` — ER diagram must be Platform Admin-only or disabled in production.
5. `PLT-065` — `/client/settings/whatsapp` route exists, but settings feature parity still requires proof; old provisional label stale.
6. Add customer-level `Do not WhatsApp` acceptance capability (avoid asserting exact code absence until complete search).
7. Five unreachable Admin pages correspond to six capability rows; row count is not a new distinct-page count.
8. Track `PRESERVE` reachability separately from `CODE-OBSERVED` and `END-TO-END PASS`.

**Authority reconciliation:** Mini-Store has no automatic numerical stock movement; Shopify/Wix inventory remains provider-owned and automatic/order-driven stock writes remain prohibited. **Wix preserves the Owner-approved action (FD-INV-05); Shopify now has an equivalent narrowly approved manual action target (FD-INV-06), not yet implemented or granted permissions.** Historical P1 stock mutation is superseded for these source groups. Provider JSON Pre-P3 is later-approved order-specific scope; Owner-only export supersedes Owner/Admin; Wix no automatic bulk deletion does not void privacy erasure. Do not reopen settled decisions.

## 6. Internal work vs external prerequisites

**Internal:** WP01–23; exact schema/mapper, routing, UI, test and release-config changes are to be designed only *after* audit approval. Preserve mature routes until parity. Provider-side actions never guessed.

**External / separately verified:** Shopify protected-customer-data status (Founder says completed ~3–4 months ago, repo cannot prove status); Shopify/Wix active app installation/granted scopes; Meta/GA4/provider freshness; Delhivery external OFD status semantics and merchant account credentials; approved Evolution sender/test WhatsApp numbers; DNS and domain verification; SMTP for invited cohort where needed. External UNKNOWN is not equivalent to missing internal functionality.

**Existing production-state cautions:** P2 provider execution enabled is Founder-approved. Other P2 feature flags, onboarding, provider webhook apply and SMTP gates must not be silently flipped by this draft. A *future* Pre-P3 go-live plan must explicitly authorize its intended final state; dark P2 regression baseline is not the same as Pre-P3 launch goal.

## 7. Proposed dependency order for future execution — plan only

1. **Audit close-out / locked inventory contract:** map real Mini-Store availability and provider read/sync callers against FD-INV-01; verify no order-triggered stock movements, identify unsafe legacy writers and historical P1 leftovers; collect verified red-team refs and establish acceptance matrix. Stock policy does **not** need another Founder question. No code changes.
2. **Block unsafe customer/money/privacy paths:** payment fallback, server-authoritative totals, public publish gate, sender fail-closed, forbidden stock notification writes, dangerous retired APIs, authenticated Admin pages/session. Keep order handling stable during corrections.
3. **Restore complete commerce ingress:** provider fields, normalized order/operational snapshot, source of truth, sanitized JSON, source timestamp/payment/refund/variant/pagination, one writer; no loss of mature imports until parity.
4. **Operational execution alignment:** vendor/readiness and Mini-Store Check Availability, valid pickup/channel, Delhivery/Own Courier, WhatsApp new-company activation, suppression, limits and merchant alerts, real customer order-state flows. Shopify inventory is read-only **except** an explicit approved merchant edit under FD-INV-06; Wix inventory writes occur **only via explicit merchant request + Owner approval + existing gated/audited Growth action**. No automatic/order-driven stock movements; no automatic Mini-Store stock mutations.
5. **COGS/profit + truthful reporting:** provider cost fetch/freeze, unknown cost handling, Growth no unintended writes, actual versus claimed, currency and event truth.
6. **Primary-store routing + Growth/Ask AI Shopify/Wix parity:** enforce one external store, preserve optional Mini-Store, provider-aware Store Doctor/Products/planner/AI reads and human-approved Shopify equivalent writes; integrate permissions/re-authorisation with safe test gates and preserve Wix.
7. **Admin/retirement and full retained UI parity:** restore pages, operator/offboarding, audit, Plans/Domains/Settings/Home/Products/Mini-Store, retire obsolete surfaces without removing mature dependencies. Distinguish code/config/cron release changes from destructive schema.
8. **Integrated test/release candidate:** strict scope isolation, new SHA, all inherited security/tests + new full business E2E, independent Red-Team, one final Codex review only after final code freeze; release gates C0 then C1 one-by-one, observation/soak and Founder sign-off. No production writes during audit.

This order prioritises safety and evidence, not a promise that all steps are trivial. Work packages are intentionally broader than individual bug tickets and require a precise engineer task contract **after** this plan is approved.

## 8. Explicit release acceptance / evidence expected

Before recommending `PRE-P3 CLIENT READY`, require:

- [ ] Every J1–J11 journey validated with source data and actual UI + API/DB assertions in safe test environment; negative tests run. Results mark PASS/FAIL/NOT PROVEN with links to traces; no broad confidence percentage.
- [ ] Zero unresolved wrong-payee, price tamper, unintended Growth write, unsafe customer send, incorrect courier data, unprotected page and duplicate stock-writer cases.
- [ ] Shopify/Wix ingress: webhook+sync parity, customer data, product lines, real payment classification, provider updates, GDPR/erasure/tenant separation, idempotency; no old-snapshot guessing.
- [ ] Mini-Store: no cross-brand payment default, Publish/Paused respected, totals server-authoritative, successful real-order flow intact.
- [ ] Live WhatsApp: activation setup, suppression, sender, safe reconnect, limits, alert UI, live/backfill and recipient truth; failed/missed event recovery demonstrable.
- [ ] COGS source/cost-freeze/profit “unavailable” states validated per provider source; Growth report safe and honest.
- [ ] **WP21–23:** exactly one primary external Shopify OR Wix, optional Mini-Store; Shopify/Wix Growth & Ask AI READ parity, correct provider-aware labels/data guards; supported product/discount/blog/inventory WRITE parity via correct scopes/merchant reauthorisation, human approval, tenant/store isolation, audit, failure recovery, and explicit safe refusal for unsupported/provisional actions. No invisible second-store ingestion.
- [ ] Auth/logout/Admin/deactivation/offboarding/export audit and tenant controls verified; old dangerous APIs/crons dispositioned by release gate.
- [ ] All protected mature 506-manifest capabilities reconciled: retained/reorganised functions still reachable, intentional retirements explicit; no silent product loss.
- [ ] **Founder stock policy verified in tests:** Mini-Store Check Availability remains functional without automatic numeric movement; Shopify is read-only for automatic/order-driven events but may execute a separately approved merchant edit under FD-INV-06. Wix can make a **merchant-initiated, explicitly Owner-approved** stock update only through existing gated/audited provider-action path and to the correct Wix store/item; unapproved, unauthorized or mismatched requests fail closed. No order-driven decrement/restore, automatic write-back, unsafe vendor-notification `stock=5`, cross-company effect or duplicate stock mutation. Historical paths dispositioned without unapproved destructive changes.
- [ ] No production DB, flags, provider auth, migrations, crons, secret/key rotation or destructive data cleanup changed without explicit approved release action.
- [ ] Fresh tests, Red-Team and Codex review against exact new final SHA; prior Codex approval `5bc0e1b3` does NOT automatically carry forward.
- [ ] Founder explicitly signs off any externally gated production activation, cohort rollout and 7-day soak plan after C0/C1 gates.

## 9. Do not build / do not assume

- No fresh generic Staff permission matrix or full Roles & Permissions design (Post-P3); enforce already-frozen minimum safety.
- No generic full cross-provider raw Meta/GA4/other provider events architecture (Post-P3); only authorized Shopify/Wix order snapshot scope now.
- No Admin impersonation now (Post-P3 security-reviewed feature).
- No new Product Draft→Publish workflow or Shopify/Wix catalog merge unless independent evidence/frozen decision changes scope.
- No automatic Wix raw-data deletion solely because Shopify requires redaction; **do** honour separately proven privacy/right-to-erasure and no removed-store phone lookup.
- No blanket deletion of mature Shopify/Wix import, vendor, shipping, product, WhatsApp or lot-code paths simply because called legacy.
- No invented Shopify lack-of-approval conclusion: Founder reports access was handled months earlier; inspect actual Partner dashboard/config in approved context.
- **Stock decisions are closed:** Mini-Store Check Availability/vendor response without numeric decrement/restore; Shopify/Wix remain provider-owned, with **explicit merchant-initiated Owner-approved stock edits** for Wix (existing FD-INV-05) and Shopify (new parity FD-INV-06), never automatic/order-driven stock changes. Historical P1 mutation is not authorization to revive it. Manual/native behavior beyond these decisions requires proof, not assumption.
- No fictitious live/prod test results or claims all 506 capabilities work. `NOT PROVEN` is not a failure, but also not a launch PASS.

---

**NEXT REQUIRED HANDOFF:** One-external-store and Growth/Ask AI full approved WRITE parity decisions are locked in **V10.3** along with previous stock decisions; no repeat parity/stock question. All other V10 decisions and technical findings remain subject to their existing evidence/acceptance checks. Only after explicit Founder approval of a separate implementation contract may Claude change code, tests, schema, DB, configuration, cron, flags or deployment. This document is not that approval.

**END — AUDIT/ACCEPTANCE DRAFT ONLY. NO IMPLEMENTATION PERFORMED.**

---

## V10.4 CLOSE-OUT ADDENDUM
- Point 1: Shopify/Wix source-owned inventory, Mini-Store Check Availability; Owner-approved Wix and Shopify explicit Growth action exceptions; no automatic order-related stock writes.
- Point 2: old P1 automatic stock rule historical only; production migration state remains unverified (release check, not new Founder question).
- Point 3: Product Sales-only notification endpoints and sibling APIs safely retire (410) without touching mature vendor workflows or historical DB.
- V10.3 Growth/Ask AI Shopify/Wix READ + approved WRITE parity and single Shopify OR Wix primary store rule preserved.
- Implementation **NOT AUTHORIZED**. This is an acceptance/implementation-planning document only.