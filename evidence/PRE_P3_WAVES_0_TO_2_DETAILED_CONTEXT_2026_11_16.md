# Bharat Launchpad — Detailed Wave 0A/0B/0/1/2 Continuity
**Compiled 2026-11-16, based on available earlier user/Claude/Codex conversation excerpts and uploaded local planning/audit documents.** Not a verbatim transcript or independent current source verification. Do not conflate a code-review *mandate*, static gap audit, Red-Team pass or user-reported independent verdict.

## Common V10.4 programme invariants
Bharat Launchpad is an integrated multi-tenant merchant operating system, not standalone dashboards: storefront onboarding, one external Shopify **OR** Wix source per company with optional native Mini-Store, operational orders, vendor fulfilment, shipping, transactional WhatsApp, payments/order truth, Growth and Ask AI, and Platform Admin. 23 work packages / J1–J11 / 506 capability index; no presumption of 506 runtime proven. Preserve matured P2 shipping/vendor/WhatsApp/Meta/Wix functionality; code safety and user experience first, never blindly rebuild.
- Inventory is provider-owned; **no automatic numeric stock decrement or restore on Launchpad Confirm/Cancel**. Existing merchant-approved inventory writes via gated provider Growth actions are separate.
- Realtime messages must be company-scoped, opted-in, LIVE only, no unexpected replay; sending tests must not cause live sends.
- Existing historical orders/finance/customer records are retained; old legacy flows can be 410-retired only after proof of caller scope and no side-effects.
- Code acceptance via tests-first, independent deterministic gates + Red-Team + Founder-manual Codex. Application Git SHA ≠ docs-only commit SHA ≠ production deployment.

## Wave 0A — WP07 wrong-payee communication / WP06 Mini-Store trusted pricing
- Original clean base `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`, local branch `pre-p3/v10-4-wave-0a-safety`.
- Initial candidate `33286ffd85b515aee6955bf54cbce201d35e997d`: independent Codex REJECTED: shipping DB error treated as free shipping, customer/cart/quote vs saved total mismatch, old 120-item cart vs 99 persisted, exported tenant-unsafe shipping action, personal payment identifiers in source/test outputs.
- Fix-forward `e85b8a3481cbd790325977001228f2fe138329fe`: independent Codex WP07 PASS with follow-ups but WP06 REJECTED; cross-store cookie could mutate other company's visitor, quote silently dropped missing/hidden/foreign items and gave partial/₹0, protected tenant tests 36/38 due fixture, bad diff whitespace. Earlier 1,126 focused PASS did not equal acceptance.
- Final `ab74f11459e1efdab62464fd4d7614b1132203eb`: earlier direct user-provided Codex excerpt independently CLOSED F1–F4 (cookie store-scope/recovery, all-item fail-closed quote, original protected tests 38/38, clean diff) and PRESERVED WP07 protections. Local focused 1,265/1,265, privacy scan reported 4,537 text files with no old payee identifiers, type baseline 53→53, lint 0. Earlier chat reported Codex Wave0A APPROVED (WP07 and WP06) and Founder responded 'ok'. **Nuance:** separately uploaded 8 Nov continuity audit had only a truncated pasted review before final WP06 verdict, so **the complete original Codex R3 report is still missing**. Status: reported Codex acceptance, not original-report-byte verified in this repo.
- Money safety: shipping lookup failure must block with retry, while legitimate no matching shipping rule can be ₹0; quote and save both require every line available, use real server pricing, never silent downgrade; unavailable entries prompt shopper removal. Live WhatsApp and real-cookie browser proof not shown by mocked tests; existing customer-facing payment_pending must use company-approved saved template (legacy payee strings invalid).
- R3 report and local worktree pointers in earlier chronology; no production writes/merges.

## Wave 0B — WP08 storefront state / WP12 legacy Product Sales / WP14 real logout+Admin / WP16 deprecated writer audit
- Local `pre-p3/v10-4-wave-0b-safety`, first candidate `616c91bb23a77cc69be9f79ceab2bf8d17f465dd`, report-only `0deffb9c`. Internal Red-Team initially rejected ungated 'load more' on closed catalog; corrected.
- Independent Codex approved **implemented scope only**, not full WP08/WP16. WP08 existed with only company deactivation/Mini-Store entitlement, not durable Draft/first Publish/Live/Paused state (required separate migration). Existing stores with no settings preserved; public listing, cart, share, quote/enquiry, metadata and loadMore gated. Existing enquiry address-completion exception deliberately remains.
- WP12 independently approved old Product Sales six endpoint retirement to deterministic 410 with no DB/WhatsApp effects; Product Sales tab removed. Preserve historical tables and legitimate Vendor Step 4, Mini-Store vendor messages, vendor responses, Admin Products.
- WP14 real logout of session and server-side protected /er-diagram and database-export (not cosmetic link); preserve other Admin guards.
- WP16 classified old writers/crons, **do not delete still-used Google Sheet → products sync** until production dependency proof; dead crons in vercel.json require separate Founder release/config authorization. Friendly closed-store "Temporarily unavailable" response acceptable; caching and HTTP behaviour require tests.
- Follow-up WP08 review candidates include `3841dd62` (independent rejection/fix-forward earlier) and later `d46a50427078725225164c517f09e92d66bc60e7` independently **reported approved**. Migration **453**/schema snapshot/rollback identity/manifest and pins were subject to separate native/independent review. Exact full original final WP08 report bytes not archived here. Do not infer live production schema changed.

## Consolidated Wave 0
- Independent Codex **APPROVED as reported** final app SHA `175327c520c1dbad1dbaeb5b5612c26cb32a961f`; explicitly used as Wave 1 approved base in later independent review mandate.
- The consolidated acceptance does not retroactively make unbuilt historic WP16 legacy cleanup or live migration/go-live approved. Preserve 453 schema verification, stock=5 retired APIs, full Mini-Store payment safety, logout/Admin protections and release-pin governance. Separate old code and report commit SHAs; do not rewrite failed history.

## Wave 1 — WP01/02/03/04/21, Shopify/Wix source and operational order truth
- Independent Codex **APPROVED as reported** final app SHA `1848756e2a8de56cc761ad39376f43fd0806c066`; source named as frozen Wave1 base in 13 Nov Wave2 static gap review. Earlier `b3594720df9a9dc226413def224d1954ede50839` was a review mandate candidate; not a substitute for accepted SHA.
- One active external commerce store **Shopify OR Wix** per merchant, optional Mini-Store; connect/UI/server/webhook/manual+background sync/reconciliation/AI context must all enforce this, not merely UI hide. Staff read-only for connection management. Legacy double-connected history must be preserved and marked Needs Resolution if no provable owner-approved primary.
- Unified authoritative company+provider+verified shop+provider-order-id operational upsert. No duplicate operational orders, source fallback, inferred identity, fake ₹0/Manual/COD/sparse-shell shipped-ready orders. Missing protected PII = explicit NEEDS ACCESS/INCOMPLETE, no fabricated recipient or invented pincode. Customer shipping phone/address, all variants/lines with pagination, accurate discounts/taxes/subtotal/shipping/paid-vs-COD/refunds/currency, truthful event ordering and source provenance required.
- Webhook, scheduled/manual sync and replay converge; old/new importers must not race; Growth page refresh must not secretly create operational orders. No auto-shipping, vendor confirm, WhatsApp history replay or inventory mutation from imports.
- WP03 narrow sanitized Shopify/Wix provider event/order snapshot allowed, **not** generic raw provider-data lake. Enforce explicit minimal fields and privacy export/erase/offboarding, tenant-scoped access and retention; no raw PII logs/auth tokens.
- Preserve mature downstream vendor, Delhivery/Own Courier, WhatsApp outbox, Mini-Store, P2 order statuses. Source-created order = placed state; assignment ≠ confirmed; operational commerce_status distinct from internal bk_status. COGS unknown ≠ zero; full cost WP05 Wave3.
- Tests-first isolated local, independent Codex accepted, but real live provider grants and staging verification still NOT PROVEN.

## Wave 2 — WP09/10/11/13/19, fulfilment/shipping and WhatsApp activation safety
- Wave1 base `1848756e...`; Nov13 independent static audit reviewed 75-file ZIP (74 checksums), builder intermediate `4e4778a6...` and 27 issue IDs, **NOT final verdict**.
- Wave2 final independent Codex **R2 APPROVED as reported** exact `4598b4220d61a264dfba728d64fffaddbc8de115`; named frozen accepted baseline in 14 Nov combined W3+W4 V3.0 programme. No live WhatsApp/Delhivery approved simply from acceptance.
- Audited issue families: 6 fulfilment defects D1–D6, 5 smaller M1–M5, 16 WhatsApp W1–W16. IDs are *static audit claims* not necessarily 27 distinct proven runtime bugs.
  - D1 cancel shipment before vendor reassignment only on terminal verified state; preserve past AWB/audit.
  - D2 vendor active flag truth/status alignment, guard open orders.
  - D3 platform vendor ownership cannot infer tenant rights from company link count.
  - D4 prohibit Staff/invalid COD/unconfirmed AWB or tracking edits bypassing guards.
  - D5 ambiguity of 'manual' payment: never classify as COD automatically; retire new-order Razorpay/manual options without rewriting old payment history.
  - D6 delivered transition needs truth, role, reason, confirm and audit, while legitimate Own Courier support intact.
  - M1 shipping-label provider errors and public document URLs potential PII exposure; verify actual URL access before claiming exploit.
  - M2 COD manual dispatch error 500/artifact naming; M3 vendor portal broad select(*) privacy; M4 stale stock wording; M5 date regex source trace before changes.
  - W1 held-on-disconnect **never auto-replay on reconnect**.
  - W2 tenant-scoped Do-not-WhatsApp suppression checked at send boundary.
  - W3 sender must be exact company account/template; no fallback to arbitrary operations/default account, preserving legitimate Broadcast.
  - W4 master switch/merchant guided activation; existing companies remain OFF until approved, no new invited company unconditional send.
  - W5 template OFF cancels unsent intent, ON must not replay history.
  - W6 WhatsApp Message Activity company-code vs UUID mismatch and pagination.
  - W7 existing manual retry RPC safely wired with Owner/Admin confirmation.
  - W8 alerts visible actionable.
  - W9 durable dedupe for same event *without* blocking explicit audited distinct manual resend.
  - W10 re-check recipient, consent, tenant, account and provider at send time.
  - W11 avoid false Delhivery label in Own Courier templates.
  - W12 per-account configured send limits enforced atomically at final authorization.
  - W13 no direct tracking send path bypassing common outbox/allowlist/guards; determine environment effect before changing.
  - W14 Staff-reachable Mini-Store sends through operate permission: must restrict server-side Owner/Admin per approved policy; later Wave6 Codex separately confirmed **supplemental vendor manual send** flaw, which remains open until fixed.
  - W15 reconciler must never turn old/backfill/failed/held into unintended sends.
  - W16 manual vendor message needs account preview/confirmation/audit/no duplicate; preserve valid manual vendor operations.
- WP13 inventory side: existing no-stock-movement and approved Wix explicit inventory edit tested as preserved semantics; no new Shopify write here.
- Wave2 checkpoint B/C/D/E test gates: isolated local DB with real SQL concurrency where needed, negative/two-tenant send safety, fail-before/green-after, original Feature/Broadcast/Orders preservation, final Red-Team then independent Codex. Historical 27-gap audit may not represent final accepted code; original full final report absent from GitHub.

## Evidence and missing bytes
- Local source files inspected in ChatGPT workspace but **not copied wholesale to PUBLIC repository**:
  `BHARAT_LAUNCHPAD_PRE_P3_WAVE1_FULL_EXECUTION_CONTRACT_REVIEWED_V1_1_2026-11-09.md`,
  `BHARAT_LAUNCHPAD_WAVE2_INDEPENDENT_GAP_REVIEW_2026-11-13.md`,
  `BHARAT_LAUNCHPAD_CONTINUITY_AUDIT_2026-11-08.md`,
  `BHARAT_LAUNCHPAD_WAVE_0_OVERNIGHT_THREE_GATE_CLOSEOUT_MANDATE_2026-11-09.md`,
  `PRE_P3_WAVE2_CHECKPOINT_C_PLAN.md`, `PRE_P3_WAVE2_CHECKPOINT_D_UI_PLAN.md`,
  plus earlier ChatGPT snippets and local reports.
- Reports/logs/real app branches remain unavailable; no full-fidelity proof of these reported Codex acceptances from their original report bytes in this documentation-only repository.
- [Audit ledger](CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md) and [current state](../CURRENT_STATE.md) take precedence for newest handoff.
