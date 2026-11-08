# Bharat Launchpad — Founder execution roadmap from V10.4 review

**Status:** Founder has approved moving toward development through current conversation, but this is NOT production release approval. The visual HTML was a functional UI simulator, not a committed product implementation.

## What happens now, in practical order

| Wave | Key WPs | Objective | Founder-visible acceptance | Execution state |
|---|---|---|---|---|
| **0A — First** | WP07, WP06 | Wrong-payee messages and Mini-Store server-trusted money | Two-company payment test; tampered shipping/total refused; valid order still works | **HANDOFF PREPARED; NOT YET EXECUTED** |
| **0B** | WP08, WP12, WP14, WP16 | Paused storefront, retired stock=5 Product Sales APIs, logout/Admin gates, old writers | Paused store blocked, 410 has no side effect, live vendor messages still work, sign-out truly signs out | NOT STARTED |
| **1** | WP01, WP02, WP03, WP04, WP21 | Full Shopify/Wix source→operational order, one external store; retain mature import | A real test order has customer, items, amount, COD/prepaid, shipping and correct source; no duplicates | NOT STARTED |
| **2** | WP09, WP10, WP11, WP13, WP19 | Confirm→vendor→Delhivery/Own Courier→tracking→live WhatsApp, no stock mutation | Full end-to-end merchant/customer path plus held/failure/suppression recovery | NOT STARTED |
| **3** | WP05, WP17, WP18 | Cost truth, product editing/Price Rules, privacy | Correct frozen COGS and tenant-scoped product data; privacy export/erase | NOT STARTED |
| **4** | WP22, WP23, WP02, WP04, WP21 | Shopify/Wix Growth + Ask AI functional READ/approved WRITE parity | Each provider has appropriate Store Doctor/planners/catalog/actions with approval/scope/audit | NOT STARTED |
| **5** | WP15, WP16, WP19 | Admin, Plans, Settings, protected features & UX, final cleanup | Five Admin pages and preserved client modules work; intentionally retired features absent | NOT STARTED |
| **6** | WP20 | End-to-end QA, P0–P2 regression, Red-Team, fresh Codex, release | 11 J1–J11 journeys PASS on new SHA with negative tests; separate Founder go-live decision | NOT STARTED |

**Readiness rule:** A UI mockup, static code check or unit PASS cannot substitute for the complete merchant journey. No automatic inventory deductions, no unapproved provider writes. Each wave closes only with evidence; failed wave stays open.

**Founder review points:** (1) Wave 0A risk/test report; (2) integrated order journey; (3) live WhatsApp and shipping acceptance; (4) Growth parity; (5) final release decision. Avoid repetitive questions about already locked product rules.