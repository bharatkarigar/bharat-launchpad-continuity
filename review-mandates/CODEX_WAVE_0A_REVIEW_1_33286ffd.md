# CODEX — INDEPENDENT FINAL REVIEW | Bharat Launchpad Pre-P3 Wave 0A

## Nature of task / permissions
You are the **independent, adversarial Codex reviewer**, not the builder. Review the actual git code and tests locally. **READ-ONLY:** do not edit code, tests, migration, docs, env, credentials, DB, branch, Git history, feature flags or deployment; do not commit, stash, reset, rebase, push, merge, deploy, trigger live WhatsApp, call real provider APIs or production endpoints. Do not launch WP08, WP12 or any later work. Safe mocked/static tests only after checking no production side effects and environment isolation; otherwise perform static review and explain tests NOT RUN. Do not expose or print secrets or personal payment credentials. If asked to fix issues later, wait for a separate Founder-approved execution mandate. Avoid unrelated findings unless a provable new cross-tenant, monetary or regression risk is exposed.

## Repo identity and review range
- Expected local repo: `/Users/harshvidyarthi/Desktop/lp-final-int`
- Expected branch: `pre-p3/v10-4-wave-0a-safety`
- Base SHA: `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`
- **CODE candidate SHA: `33286ffd85b515aee6955bf54cbce201d35e997d`**
- Branch HEAD after report commit: `9e8002e63dc5412fa8d18a83d706e76248ae9b08` (docs-only; VERIFY, don't presume)
- Compare **`git diff 5bc0e1b302be55a22046e6d3335ddc60b558f4bd..33286ffd85b515aee6955bf54cbce201d35e997d`**, not only HEAD diff; use report commit as documentation only.
- First record `pwd`, `git branch --show-current`, `git rev-parse HEAD`, `git status --porcelain`, `git show --stat --oneline 33286ffd`, `git diff --stat 5bc0e1b3..33286ffd` and verify SHA identity. If repo, base or diff not found, **STOP and report** rather than guessing or substituting a different tree.
- Read `docs/pre-p3-execution/WAVE_0A_WP07_WP06_REPORT.md` and available V10.4 Founder registry, scope, execution mandate. If registry isn't present, say `SOURCE UNAVAILABLE`, and review against the supplied report + actual code without inventing authority.

## Background (builder's report is an assertion, not proof)
WP07 removed platform-owner payment credentials and platform-brand default text from Mini-Store Payment Pending fallback; requires merchant's own saved payment template, with fail-closed no enqueue/status change. WP06 replaced browser subtotal/shipping/rule ID with DB-product-price and server-side shipping calculation, added a shared 99-item limit, tenant and sellability checks, and maximum 100 rows. Builder reports 43 test files / 958 tests PASS with mocked DB/provider, 87 baseline TypeScript errors, 0 ESLint errors/30 warnings, and one Red-Team rejection on WP06 followed by a fix-forward APPROVE. No end-to-end browser/real isolated DB test was proven. No production action authorized.

## Review the two work packages deeply
### WP07 — WRONG PAYEE / TENANT ISOLATION
1. Trace **all actual active producer, renderer, preview, send, outbox, retry and manual resend paths** for `payment_pending`, other manual statuses, and default templates. Verify no hardcoded platform payee/brand can reach another merchant's customer. Ensure platform-owner bank/UPI/phone is never emitted in logs, tests, fallback, or customer notification. Avoid printing private values in report.
2. For missing, placeholder, stale legacy, malformed, lookup-error or cross-company payment template: confirm **fail-closed** before enqueue, status change or side effects; retry behavior must be bounded and not silently send unsafe text. Verify role/tenant safeguards and valid merchant template behavior.
3. Check legacy saved templates, existing queued outbox messages, retry reuse of stale payloads, non-payment status fallback branding, preview-versus-send UX, and whether the merchant's own saved template may still contain legacy payee. Distinguish new regression from prior existing data risk and flag any real cross-company harm.
4. Verify Bharat Karigar itself now requires setup and merchant-facing error is correct; no silent loss of legitimate Follow Up / Final Invoice / Close Query / Payment Received workflows.

### WP06 — SERVER-TRUSTED ENQUIRY MONEY
1. Trace browser cart and all public save entry points through `saveEnquiry`, DB product lookup, delivery pricing, persisted enquiry fields, and downstream **create-order** readers. Demonstrate tampered subtotal/shipping/rule/discount/final amount is ignored at the server trust boundary.
2. Product ID/variant, visibility/sellability, correct company, current DB price, null/zero/negative/huge/NaN values, decimal rounding, 99-item cap (including old persisted carts), 100-row cap, selected items vs stored cart, duplicate product rows, invalid/empty basket, and order creation amount consistency. Verify no duplicate/omitted line items or free orders created accidentally.
3. Shipping rules must use the intended merchant's currently valid rule and appropriate price band. Compare browser preview with server saved amount; check rules include boundary conditions, zero/empty shipping configuration, data access failures and currency calculations. Verify no new trust boundary or tenant leak via client-supplied identifiers.
4. **Do not treat the following as harmless because they predate this wave. Determine if they are a release-blocking violation of Wave 0A's money-safety contract:**
   - **N3:** DB shipping-rule lookup failure silently persists ₹0 shipping (potential undercharge). Should this fail closed / return retryable error? Provide precise source evidence and a concrete adversarial test case.
   - **N4:** Preview and persisted price-band shipping may differ. Show exact boundary inputs and effect on customer-visible payable.
   - **N7:** unauthenticated exported `calculateShippingCharge(clientId)` potentially reads any tenant's rules. Is data sensitive? Does the new code worsen or preserve this? Assign justified severity.
   - Double submission saves duplicate enquiries, old cart display >99, empty enquiry when invalid items: classify concrete data integrity/UX risk and ownership; be alert to cross-wave dependencies.
5. Validate valid historic Mini-Store enquiries/orders, vendor-query notifications, customer status flow preserved (trace unchanged call paths; don't overclaim runtime PASS). No order-driven inventory mutation introduced.

## Evidence and gates
- Inspect test implementations for realistic adversarial assertions vs mocks that simply assume correctness; check tests independently of authors' claims. Run focused safe local tests if guaranteed mocked, cite exact commands and pass/fail counts. Avoid real integration/provider actions.
- Compare original rejected commit `0b0d6534` with fix-forward `33286ffd` for the 120-vs-99 bug: customer-visible quantity, DB-saved quantity, invoice/message/submission must align. Include old cart case.
- Assess observed 87 `tsc` errors only if trustworthy before/after evidence exists, otherwise `UNVERIFIED` baseline; prevent any new compiler issue from this diff.
- For each significant finding, provide `severity (BLOCKER/HIGH/MEDIUM/LOW)`, `status (CONFIRMED/RISK/NOT PROVEN)`, exact repo `file:line`, exploit/trigger and specific minimal fix or test. Do not invent or inflate a finding without code evidence.
- Maintain a clear **Wave 0A close gate** distinct from **production-ready gate**. Local unit/red-team PASS does not prove browser E2E, real shipping DB rules, provider WhatsApp, or production readiness.

## Required report (output within chat, no file write unless Founder separately authorizes)
A. Repo identity verified, exact diff, clean-worktree check, no modifications.
B. WP07 verdict + WP06 verdict separately: `PASS`, `PASS WITH NONBLOCKING FOLLOW-UPS`, or `REJECT`; cite evidence.
C. Findings table (severity, confirmed/possible, exact location, fix recommendation); specifically decide N3 and N4 instead of blindly deferring.
D. Test evidence ledger: static vs mocked vs real integration, and gaps marked `NOT PROVEN`.
E. Live vendor/mini-store and tenant-isolation impact check; avoid fake PASS on unrun E2E.
F. Explicit final decision **exactly one**:
   - `CODEX APPROVED — WAVE 0A READY FOR FOUNDER CLOSE` (only if no material money/cross-tenant/regression blockers), or
   - `CODEX REJECTED — WAVE 0A REMAINS OPEN` (if a real blocker, with precise minimal follow-up scope).
G. If rejected, include a short **builder fix-forward handoff** with test-first requirements; do NOT implement.

**STOP after independent review.** Do not begin Wave 0B or push/merge/deploy.