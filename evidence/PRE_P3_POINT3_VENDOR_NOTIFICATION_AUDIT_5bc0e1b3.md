# Point 3 — Retired Product Sales vendor notification forensic audit
**Source type:** Faithful summary of the user's Claude report in the 2026-11-08 conversation. **Not the original full downloaded report**; original local file: `~/Downloads/PRE_P3_POINT3_VENDOR_NOTIFICATION_RETIREMENT_AUDIT_5bc0e1b3.md`.
**Candidate static audit SHA:** `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`.
**Audit scope:** Read-only; no source changes, production checks, DB writes or real WhatsApp. Exact production effects NOT PROVEN.

## Findings
1. `app/api/inventory/notify-vendor-product-sales/route.ts`: single in-app caller `components/admin/product-sales-tab.tsx`, still reachable from Admin Product Sales. Legacy `product_sales.current_stock = 5` through service role; vendor/product-name filter without company; errors ignored. Sends through platform WhatsApp account; copy says quantity 4, code sets stock 5.
2. `app/api/inventory/notify-vendor/route.ts`: no discovered UI, library or cron caller; reachable via direct HTTP with Platform Admin authorization. Writes old `product_inventory.current_stock = 5` unconditionally before messaging.
3. Both tables are old pre-SaaS/noncanonical stock and aren't read for active stock. Do not claim current canonical inventory changed.
4. **Active live vendor notifications independent**:
   - Order Fulfilment Step 4: `/api/whatsapp/notifications/send-to-vendor` — Owner/Admin only; Staff denied.
   - Mini-Store availability enquiry: `lib/mini-store-whatsapp.ts` through company-specific WhatsApp instance.
   - Vendor response: `vendor-product-queries.ts`.
5. One retired sibling clear API can delete historical rows. All relevant sibling APIs require authorization and reachability check before safe retirement.

## Existing Founder decision and minimum safe implementation scope
- Admin Product Sales is retired, not part of canonical ecommerce product operations.
- Safely disable both obsolete notification endpoints as 410 with **zero DB and WhatsApp side effects**, remove Product Sales sidebar item/tab, audit and retire other four old-only Product Sales APIs, including destructive clear.
- Preserve historical tables/data, preserve useful Admin Products and live vendor / Mini-Store notifications.
- Update obsolete behavior-pinning tests; add direct HTTP 410/zero-writes tests and regression coverage for current vendor flows.
- No implementation approved by this **audit** itself; work belongs to authorized Pre-P3 cleanup wave, not Wave 0A.

## Disposition (as of audit)
`POINT 3: RETIRED-ONLY`
`STOCK=5 CURRENT CODE PATH: CONFIRMED`
`ACTIVE VENDOR NOTIFICATION SAFE TO PRESERVE: YES`
`FOUNDER DECISIONS NEEDED: 0`
`READ-ONLY VERIFICATION COMPLETE — NO CODE OR PRODUCTION CHANGES`

**Evidence limitation:** Original file not included because an available Files attachment reference resolved to an access-unavailable message. This reconstructed report is not a verbatim replacement. Reconcile against original downloaded audit if disputes arise.
