# Bharat Launchpad — Pre-P3 Implementation Master Plan (V10.4, DRAFT)

**Authority:** Founder Registry V10.4; Scope & Acceptance Draft V10.4; targeted Claude evidence on `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`.
**Status:** Planning-only. **No implementation, provider write, permission change, migration, cron modification or deployment authorised.**
**Method:** Existing mature capability first; fix source-to-consumer contracts; security and money safety; no redundant rebuild; test before development.

## Executive truth

- Existing ecommerce systems are substantial; newer canonical Shopify/Wix order ingestion has a verified *static-code* operational data gap, not proof that mature shipping/vendor/WhatsApp engines never existed.
- Shopify OR Wix (not both) is the sole external store per company; Mini-Store is optional. External-commerce Growth/Ask AI uses selected primary store. Shopify receives supported mature Wix Growth/Ask AI **READ + approval-gated WRITE** functional parity. Provider-specific permissions and safe execution must be validated.
- Inventory is **not** automatically decremented/restored by Launchpad on Confirm/Cancel for Mini-Store or provider orders. Mini-Store Check Availability remains. Both Wix (existing) and Shopify (approved target) can support **explicit merchant-initiated Owner-approved inventory edits** through gated auditable Growth actions only.
- Point 3 is CLOSED: the `stock=5` routes are old Product Sales-only paths and should be safely retired; legitimate vendor notification remains untouched.
- Current QA/review evidence is overwhelmingly static and **not equivalent to production or end-to-end PASS**. No objective launch percentage should be reported from these audit denominators.

## Evidence standard

`FOUNDER LOCKED` means product rule; `STATIC CODE-OBSERVED` means Claude traced a route; `NOT PROVEN` means runtime/production or missing code proof; `IMPLEMENTED` cannot be claimed without tests on a fresh SHA. In particular, prior assertions about Shopify protected-data grants, true webhook payload fields, P2 migrations and flags are **NOT PROVEN FROM LOCAL STATIC CODE**.

## Execution groups: dependency-based, not 23 independent rebuilds

| Stage | WP IDs | Engineering objective | Non-negotiable acceptance |
|---|---|---|---|
| 0. Safety containment | 06,07,08,12,14,16 | Wrong payee, Mini-Store pricing, Publish/Paused, logout/Admin role checks, retired unsafe writes/cron paths | Cross-brand payee cannot leak; totals server-authoritative; paused store unavailable; real logout; role guards; obsolete API 410 with zero DB/WhatsApp effect |
| 1. Commerce truth & ingestion | 01,02,03,04,21 | One external Shopify OR Wix + optional Mini-Store; complete provider→operational order; safe JSON; no Growth-triggered order writer | Name/phone/address, lines/variants, totals, payment, dates, source + event version correct; webhook/sync parity; safe redaction; source gate explicit; no duplicates |
| 2. Fulfilment & WhatsApp LIVE | 09,10,11,13,19 | Reuse real vendor, shipping, tracking; activate eligible customers' approved journeys; sender/suppression/reconnect/alerts/limits | Assign ≠ Confirm; valid Delhivery/Own Courier; live-only messages deduped; held stale messages not auto-replayed; no implicit stock movements; real merchant recovery |
| 3. Product economics & data truth | 05,17,18 | Provider COGS/frozen order costs; product edit/category isolation; privacy-rights coverage incl sanitized JSON | Cost missing ≠ zero; product updates don't erase charge/category; no unauthorized tenant visibility; privacy erase/export meets required scope |
| 4. Growth/Ask AI parity | 22,23,02,04,21 | Provider-aware Wix/Shopify Store Doctor, catalog/planner/AI read and approval-gated writes; remove legacy writer from Growth | Shopify doesn't call Wix tools/labels; shared Meta/GA4/Creative Studio intact; scope/consent/action target verified; unsupported actions visibly blocked; one primary source only |
| 5. Admin and retained operations | 15,16,19 | Restore five existing Admin pages; operator lifecycle, Settings/Plans/Home/Mini-Store/product capability preservation; retire obsolete financial UI | 506 capability manifest crosswalk, no silent feature loss; dangerous actions reason/confirm/audit; legacy APIs audited; no destructive data removal |
| 6. Full regression + release governance | 20 | Full real merchant path, negative tests, security, Codex fresh SHA | J1–J11 and additional Point 3 tests PASS; independent Red-Team; one final Codex review; release gates and Founder go-live approval |

**Cross-cutting:** WPs can overlap; avoid duplicate work packages or counting downstream fallout as separate root causes. `WP13` implementation must follow source-specific latest stock policy. `WP23` must not silently activate provisional Wix cancel/refund because Shopify parity was approved; verify risk/scope separately.

## Critical cross-module acceptance matrix

| Journey | Required result | Existing evidence / limitation |
|---|---|---|
| Shopify webhook → complete order → ship | Customer, phone, address, SKU/variants, amount, prepaid/COD, shipping labels, vendor, tracking & customer WhatsApp all work | New pipeline blank-shell static issue; old mature import exists; test integrated path, no manual retyping |
| Shopify background sync / missing webhook | Same complete order, no contact loss, no duplicates; clean reconciliation | Shopify GraphQL fetch/mapping gaps; verify protected data grant through authorised external check |
| Wix webhook + sync | Complete provider-normalized operational order with Wix identity, shipping and vendor; no second external connection | Current mapper/source gates and Wix variant identity need test |
| Mini-Store enquiry/cart → fulfilment | Availability, correct server-calculated totals, customer/vendor notifications, live Publish/Paused, shipping | Existing journey mature but payment/public-state red-team issues; don't call unconditional PASS before test |
| WhatsApp customer order journey | Sender correct, suppression, live-vs-backfill, dedupe, failure alerts, daily limits, held replay policy | Existing infrastructure; activation and alerts static gaps; runtime not verified |
| Shipping (Delhivery/Own Courier) | Vendor pickup, COD/prepaid safety, AWB/label/tracking, manual Delivered audit, valid exception flow | Existing mature functionality; source-to-shipping contract needs integration tests |
| Inventory & legacy Product Sales | No automatic Confirm/Cancel stock mutation; Owner-approved inventory edits only; old notify endpoints retired; live vendor flow works | Latest Founder rules locked; retired-only static evidence; production migration not verified |
| Shopify-primary Growth + Ask AI | Wix equivalent supported Store Doctor, product tools, approved product/discount/blog/stock actions; no Wix source fallback | 29-item Wix→Shopify parity static audit; Shopify scopes/reauthorisation external dependency |
| Wix-primary Growth + Ask AI | Existing mature Wix store functions and Owner-approved inventory edit preserved | Existing functionality must be regression-tested and safety-gated |
| Merchant and Platform Admin | Account access, roles, privacy export Owner-only, five built Admin pages, offboarding/deactivate, audit | Current auth/Admin static defects; runtime security review needed |

## Point 3 surgical retirement, not a vendor rewrite

- Source audit: `PRE_P3_POINT3_VENDOR_NOTIFICATION_RETIREMENT_AUDIT_5bc0e1b3.md`. Two retired paths: `app/api/inventory/notify-vendor/route.ts` and `.../notify-vendor-product-sales/route.ts` set old-table `current_stock=5`; the second has a Product Sales UI caller; the first is Platform Admin HTTP-callable with no in-repo UI caller.
- After rechecking consumers on the new development SHA, retire via nonwriting HTTP 410, remove Product Sales navigation/tab, and retire the proven-unused Product Sales-only `sales-from-orders`, `sync-product-sales`, `clear-product-sales`, `sales-summary` APIs. The clear route is particularly dangerous; ensure direct HTTP cannot destroy rows.
- **Do not** drop historical `product_sales` or `product_inventory`; **do not** retire Order Fulfilment Step 4, Mini-Store enquiry notifications, or `vendor-product-queries.ts`.
- Test no DB/WhatsApp side effect on 410, legitimate vendor notification and vendor response, permission denial for Staff, idempotency, company isolation and unchanged historic row counts.

## Critical pre-implementation engineering checklist (requires later authorization)

1. At new candidate SHA, re-establish every selected path/caller and live/old ownership; gather source and test evidence. Don't reopen Founder decisions absent contradiction.
2. Write tests FIRST for money/PII/stock, provider order completeness, one-external-store gate, primary-store AI, provider write approvals, WhatsApp LIVE and all existing Ops/Admin paths.
3. Make smallest non-overlapping edits; retain mature routes until migration parity is proven. No unsafe blanket deletion of a route merely labeled `legacy`.
4. Document exact migration, queue/schedule, provider permissions, Vercel, Evolution, and feature-flag changes separately. Nothing runs in production without explicit go-live release approval.
5. Capture all acceptance results as `PASS / FAIL / NOT PROVEN` with code and safe QA evidence; no fake success or broad PASS claim from isolated tests.
6. Regression against existing P0/P1/P2, wireframe/manifest protected capability, approved decisions and negative security tests; independent Red-Team and final Codex against exact new SHA.
7. Only after Founder sign-off: controlled production release and C0/C1/soak governance. Production-state unknowns remain to be measured safely.

## Exclusions / protected decisions

No full 3-external-channel architecture, no Shopify/Wix simultaneous connection; no generic all-provider raw retention; no broad Staff Roles redesign; no new Product Draft→Publish lifecycle; no destructive historical row cleanup; no unapproved Shopify/Wix app scope mutation; no ungated AI provider actions; no automatic order-driven inventory write; no admin impersonation now. Preserve mature Auth, Products, Vendor Portal, Influencer Portal, Mini-Store, Meta/GA4, WhatsApp and existing admin tooling unless specifically and explicitly retired.

## Review gate

**Prepared, not executed.** Founder approval to *review/freeze the plan* is distinct from explicit authorization to *implement*, *change environments* or *deploy*. The audit candidate SHA `5bc0e1b3` retains prior Codex decision only for that exact candidate; any changed SHA needs new review.