# 03: Wix → Shopify parity matrix (all 29 Wix capabilities)

**Abbreviations:**
- **Wix status:** WIC = working in code (a reachable caller exists); EXEC-OFF = written but blocked by the runtime execution gate (env `AI_GROWTH_PROVIDER_WRITES_ENABLED` + company `provider_execution_enabled`); UNREACH = no caller.
- **Docs:** see `evidence/SHOPIFY_DOCS_VERIFIED_2026-04.md`.
- **Scopes:** the app has 7 read-only scopes, frozen by the Founder 2026-10-29 rule "no write_*, no read_reports" (`scopes.ts:1-4`).

**Bucket key:**

| Code | Bucket |
|---|---|
| WRK | Shopify already working |
| R/S | REUSE / SMALL ADAPTER |
| MED | MEDIUM NEW DEVELOPMENT |
| LRG | LARGE / different semantics |
| UNS | NOT COMPARABLE / provider-specific, or blocked by Founder authority |
| NP | NOT PROVEN |

| W | GRW | Wix capability | Wix status | Shopify API (2026-04) | Current Shopify code | Reuse | Missing work | Permissions / external | Risk | Bucket | Pre-P3 | Acceptance test |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| W-01 | G-100 | Store Doctor (catalog health, low/out stock, missing price/image/SEO, duplicates) | WIC | `products`, `productVariants` (aggregate qty), `InventoryLevel` per location (`read_inventory`), `locations` | None reachable. Capability queries (`lib/providers/capabilities/shopify/queries.ts`) unreachable; `store.sync` never enqueued | Store Doctor UI + `wix-stock-state` thresholds (≤5) are generic logic; throttle code | Shopify catalog-health adapter (≈3–4 queries); a **location rule** (aggregate vs per-location); primary-aware route; truthful unknown vs 0 | Scopes already requested (`read_inventory`, `read_locations`). Granted on existing installs: NOT PROVEN (optional scopes) | Wrong multi-location totals; >25 variants; cost limits (1,000 pts/query) | **MED** | **Core** | Shopify-only → Store Doctor shows Shopify products, unknown ≠ 0, no Wix call |
| W-02 | G-101 | Order windows / diagnostics | WIC | `orders` (PCD for customer fields) | Canonical `provider_orders` exist (webhook path); legacy `syncShopifyOrders` | Canonical read layer `lib/data/canonical/read.ts` | Shopify diagnostics view over `provider_orders` (no new provider call) | PCD status NOT PROVEN | low | **R/S** | Core | Shopify primary → window lists Shopify orders, labelled Shopify |
| W-03 | G-102 | Wix orders import (staging → promotion) | WIC | — | Shopify ingestion exists (webhook + legacy sync) | — | None for parity (Shopify blank-order root cause R-1 is tracked separately) | — | — | **WRK** | — | — |
| W-04 | G-102 | Wix recovery / reconcile | WIC | — | Shopify reconnect / health via Connections | Connections health | Shopify reconnect CTA in the Growth setup card | — | low | **R/S** | Core | Revoked token → "reconnect Shopify" |
| W-05 | G-103 | Product workspace list | WIC | `products` (+ `productVariants`) | None | Workspace UI | Shopify product list adapter + pagination | `read_products` (required) | pagination cost | **R/S** | Core | 300-product fixture paginates fully |
| W-06 | G-104 | Product → Meta catalog mapping, bulk, suggestions | WIC | `products` (ids/handles/SKUs) | None | `ai_growth_product_mappings`; suggestion logic (provider neutrality NOT PROVEN) | Shopify id/variant keys, matcher on Meta `retailer_id`, schema check for a provider column | — | Wrong product→catalog link | **MED** | Core-optional (catalog campaigns) | Mapping saves Shopify ids; never Wix ids |
| W-07 | G-105/114 | Product-set draft / preview / selection summary | WIC | `products`, `collections` | None | Draft tables | Shopify selection resolver | — | — | **MED** | Optional | Preview lists Shopify products |
| W-08 | G-106 | Meta product set from selection (approval-gated) | EXEC-OFF | Meta API (provider-neutral) + Shopify resolver | None | Meta write path + approvals | `resolveShopifySelectionForCatalog` equivalent | Meta approvals unchanged | wrong targeting | **MED** | Optional | Approved request targets the correct Meta catalog with Shopify-mapped items |
| W-09 | G-107 | Product detail update | EXEC-OFF | `productUpdate` (`write_products`) | None | Approvals | Would need a write scope | **Blocked: frozen read-only scopes** | provider write | **UNS** | No (Founder) | — |
| W-10 | G-108 | Inventory update | EXEC-OFF | `inventorySetQuantities` (`write_inventory`) | None | — | — | **Forbidden: V10.2 FD-INV-05 (Shopify read-only)** | — | **UNS** | No | Shopify stock-write action is never offered |
| W-11 | G-109 | Coupon create / activate | EXEC-OFF | `discountCodeBasicCreate` (`write_discounts`); read `discountNodes` (`read_discounts`, requested) | None | — | Read-only listing possible | **Write blocked by scope rule** | — | **UNS** (write) | Q (see 07) | — |
| W-12 | G-112 | Blog draft / publish | EXEC-OFF | `articleCreate` (`write_content`) | None | Ask AI blog proposal UI | — | **Blocked: scope** | — | **UNS** | Q | — |
| W-13 | G-110 | Order cancel | EXEC-OFF | `orderCancel` (`write_orders`, irreversible) | None | — | — | **Blocked: scope**; canonical order-cancel rule (DR-15) | High | **UNS** | No | — |
| W-14 | G-111 | Refund | EXEC-OFF | `refundCreate` (`orders` scope per doc) | None | — | — | **Blocked**; finance safety | High | **UNS** | No | — |
| W-15 | G-19 | Analytics access check | WIC | `shopifyqlQuery` (`read_reports` + **Level-2 PCD**) | None | — | — | **Blocked: no read_reports (frozen)** | — | **UNS** | No | Shopify shows "store analytics not available", not a Wix CTA |
| W-16 | G-19 | Blog access check | WIC | — | — | — | — | follows W-12 | — | **UNS** | No | — |
| W-17 | G-84 | Planner stock / catalog signals | WIC | via W-01 data | Planner shows "Connect Wix Store" | Planner logic | Feed it the Shopify Store Doctor adapter | — | — | **R/S** (after W-01) | Core | Planner uses Shopify signals |
| W-18 | G-11/84 | Planner suggestions / playbooks ("Wix shows…"; only `wix_store` / `meta_ads` make cards) | WIC | — | Shopify numbers labelled "Wix" | Same logic | Provider-neutral wording; allow the Shopify provider in playbooks | — | Mislabel | **R/S** | Core | No "Wix" text for Shopify primary |
| W-19 | G-46 | Ask AI Wix analyst tools (`wix_query` semantic models incl. inventory, cost) | WIC | No semantic-model equivalent; ShopifyQL blocked | None | Tool framework, guard, quotas | New Shopify read tools over canonical `provider_orders` / products + GraphQL catalog / inventory | Data-access guard source "shopify" | Model truthfulness | **LRG** | Core (min set) | "What sold?" / "low stock?" answered from Shopify, sourced |
| W-20 | G-39 | Product picker / set selection / winning shortlist | WIC | `products` search; sales from `provider_orders` | None | Picker UI, shortlist logic | Shopify catalog + sales ranking adapter | — | — | **MED** | Core | Picker shows Shopify products for Shopify primary |
| W-21 | G-39 | "In stock" literal | Not user-visible (removal matching only, `product-selection.ts:188-202`) | — | — | — | None (prior defect claim **corrected**) | — | none | **R/S** (no work) | — | — |
| W-22 | G-31/42 | Ask AI Meta proposals "from Meta and Wix data"; starters | WIC | depends on W-19 / W-20 | Starters need Wix | Proposal engine | Provider-neutral context assembly | — | — | **MED** | Core | Shopify merchant gets proposals without Wix text |
| W-23 | G-113 | Connect / install / lifecycle / webhooks | WIC | OAuth app | **Shopify connect + webhooks exist** | — | — | Custom-distribution step (FD-EXT-03) | — | **WRK** | — | — |
| W-24 | G-130/20/13 | Status / reconnect / freshness | WIC | — | Shopify status card exists (G-130) | Status model | Primary-aware status + freshness for Shopify in Growth cards | — | — | **R/S** | Core | Disconnected Shopify → truthful state |
| W-25 | — | History capture (Wix reader only) | WIC (env-gated) | `orders` / `products` | None | History framework | Shopify history reader | env | — | **R/S** | Optional | — |
| W-26 | G-59 | Canonical webhook / sync into `provider_orders` | Webhook WIC; sync never enqueued | same pipeline | **Same pipeline for Shopify** (shared R-1 blank order, D-1 sync not enqueued, D-2 primary-only) | — | Shared defects, tracked once | flags `store_sync_*`, `webhooks_apply` | — | **WRK** (shared defects) | — | — |
| W-27 | — | P2-CAP capability router (`wix.*`) | UNREACH | — | `shopify.*` queries also exist, unreachable | **Reuse target** for W-01 / W-05 | Wire into Growth | — | — | **R/S** | Core enabler | — |
| W-28 | G-12x | Approvals Wix-op form, uncertain-write reconcile | WIC | — | — | Generic approvals | Hide Wix ops for Shopify; Shopify has no write ops | — | Wrong-provider op offered | **UNS** | — | Shopify primary → no Wix op in the select |
| W-29 | — | Legacy Wix order ops outside Growth | not traced | — | — | — | Outside parity scope | — | — | **NP** | — | — |

## Counts
| Bucket | Count | Rows |
|---|---|---|
| WRK | 3 | W-03, W-23, W-26 |
| R/S | 9 | W-02, 04, 05, 17, 18, 21, 24, 25, 27 |
| MED | 6 | W-01, 06, 07, 08, 20, 22 |
| LRG | 1 | W-19 |
| UNS | 9 | W-09, 10, 11, 12, 13, 14, 15, 16, 28 |
| NP | 1 | W-29 |
| **Total** | **29** | |