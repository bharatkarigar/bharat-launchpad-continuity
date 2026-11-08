# Bharat Launchpad — Pre-P3 Wave 0A | Codex Second Rejection: Fix-Forward Mandate

**Issued:** 2026-11-08  
**Status:** Wave 0A **OPEN**. Independently reported verdict: **WP07 PASS WITH NONBLOCKING FOLLOW-UPS / WP06 REJECT**.  
**Authority:** The existing Founder approval for **local Wave 0A fix-forward only**. This does not authorize production, pushes, merges, deployments, migrations, env/flags/cron changes, live WhatsApp sends, external provider calls, historical Git rewrite, Wave 0B, or unrelated feature/refactor work.

## 1. Exact repository identity and evidence hierarchy

- Local repository: `/Users/harshvidyarthi/Desktop/lp-final-int`
- Expected branch: `pre-p3/v10-4-wave-0a-safety`
- Pre-wave baseline: `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`
- First rejected code candidate: `33286ffd85b515aee6955bf54cbce201d35e997d`
- Second candidate, independently reviewed and rejected: `e85b8a3481cbd790325977001228f2fe138329fe`
- Expected current docs-only HEAD: `c5b38a9e09fef0bb3596d01f1d558d0431814e3c`; verify live, do not assume.
- Independently reported Red-Team rejection in preserved history: `8d7df3a4` (verify exact commit and context).
- Codex second verdict supplied by Founder: **B1 PASS with nonresponse evidence gap; B2 REJECT; B3 PASS; B4 REJECT; B5 PASS with follow-ups**. Four blocking findings below, the last being a quality gate defect.
- V10.4 registry source if present: `BHARAT_LAUNCHPAD_FOUNDER_DECISION_REGISTRY_CANONICAL_V10_4_2026-11-08.md`; core frozen requirements include RT-03 (wrong-payee fail-closed) and RT-16 (server-authoritative Mini-Store money). Read the repository report `docs/pre-p3-execution/WAVE_0A_CODEX_REJECTION_FIX_FORWARD_REPORT.md` and earlier Wave 0A mandate. If a document is unavailable, label it **SOURCE UNAVAILABLE** rather than inventing a decision.

**Evidence precedence:** actual code and adversarial tests on an identified SHA > exact Codex findings > earlier implementation claims. File line numbers below refer to `e85b8a34` and may move after edits; trace actual symbols/callers. Do not claim any test performed or fix verified unless actually reproduced.

### Preflight (no edits until complete)

1. Print `pwd`, `git branch --show-current`, `git rev-parse HEAD`, `git status --porcelain`, `git log -8 --oneline`. Record baseline and rejected candidate ancestry. **If nonclean/unknown HEAD or wrong branch: STOP, do not stash/reset/rebase.**
2. Identify local DB/provider/environment targets **without printing secrets, personal financial identifiers, session tokens, PII or env values**. Use isolated/mocked tests only. If uncertain of test isolation, stop the affected test.
3. Check installed dependencies and the previous `node_modules` symlink/worktree cleanup incident. Do not delete or recreate worktrees or dependency directories. No destructive cleanup.
4. Capture relevant current behavior and **failing-before tests** for each defect on `e85b8a34` (or the clean current docs-only HEAD with same code). Preserve red-team rejected commits, do not amend/rebase/squash or rewrite history.
5. Use builder and **independent red-team** roles sequentially. Avoid agents concurrently editing shared files. All changes are local, fix-forward commits only.

## 2. Mandatory four findings — minimal corrections and acceptance tests

### F1 — BLOCKER: Store A visitor gets mutated by Store B checkout; Store B cannot recover

**Codex evidence:** `app/store/[clientSlug]/check-availability/page.tsx:41` passes a host-wide visitor cookie into `createOrRefreshVisitor`; `app/actions/mini-store.ts:419` looks up that token without company scope, then updates the existing visitor at approximately `432–449` without confirming `existingVisitor.client_id === resolvedClient.id`. Later `saveEnquiry` rejects at `725–729`, but wrong-tenant PII has **already been mutated**. Existing O3 test enters at save and misses the capture side effect.

**Required behavior:**

- Resolve Store B from trusted **server** store route/domain, not browser-supplied tenant authority. A visitor token for Store A **must never update/read** Store A data while capturing an enquiry for Store B, and must never become Store B's tenant authority.
- On Store A cookie used at Store B: treat as **foreign-store session**, create distinct **Store B visitor and token**, update/replace relevant cookie without touching Store A; Store B visitor should be able to quote, submit, refresh and return. Do not silently fail with “reload” instructions that remain broken.
- Maintain valid **same-store refresh** and legitimate update behavior. Preserve storefront public access and authorization rules; an anonymous shopper may legitimately visit different merchants.
- Carefully inspect token lookup scope, cookie path/domain/SameSite/security settings, Set-Cookie in server-action/route context, stores sharing a host, redirects, stale browser tabs and race conditions. Do not create a solution that merely changes a UI error while retaining unsafe DB updates. For collisions, wrong-tenant lookup must not grant a read/update.
- Avoid touching WP08 publish-state redesign, auth systems or historical visitor migration unless a proven dependency genuinely requires it.

**Test first, prove after:**

- **Real page/action integration with mocked isolated DB**: Store A cookie → navigate Store B → submit visitor capture → assert **zero Store A update or PII mutation**; **new Store B visitor with Store B client_id**, new cookie/token; Store B quote + enquiry succeed; page reload/resume still succeeds.
- Same-store return updates only matching store; Store B cookie used on Store A vice versa; no cookie; malformed/expired cookie; nonexistent visitor token; concurrent tabs / return visits as feasible.
- Adversarial attempt forged `clientSlug`/`clientId` or token does not allow cross-company update. Ensure tests watch **earlier capture mutation**, not only `saveEnquiry` refusal.
- Failure must not leave partially mutated wrong-tenant data. Verify actual DB writer order and isolation conditions.

### F2 — BLOCKER: Incomplete cart gets a deceptive resolved ₹0/free or partial quote

**Codex evidence:** `app/actions/mini-store.ts:649,661–666` retrieves available listings, silently removes requested products that are missing/hidden/unlinked/foreign/unpurchasable, and still returns `status: "resolved"`. `components/client/mini-store/CheckAvailabilityPage.tsx:227` continues to count/use original local items. This lets stale-only carts show ₹0/free, or mixed baskets show a partial total with full local item count.

**Choose minimal safe policy:** **fail the quote CLOSED** when **any** normalized requested item cannot be priced/purchased under the current merchant. Do not automatically delete items from customer cart, silently substitute them, or represent incomplete basket as an approved quote. An alternative sanitized-basket acknowledgement requires more UX complexity; use only if demonstrably necessary to preserve mature flow and explicitly document choice.

- Compare **every normalized requested product** with authoritative tenant-scoped product/vendor/link/visibility/purchasability results. Consider duplicate product rows/IDs, requested quantities, zero-item basket, old carts, cross-store IDs, hidden products, ended supplier relationships and missing DB rows.
- Return a sanitized non-sensitive **basket-unavailable / items-changed** outcome; do not leak whether a foreign tenant's private item exists. Show an actionable checkout message, e.g. return to cart/remove unavailable products, and block submission until shopper explicitly fixes/reconfirms basket. Differentiate genuine lookup error (retry) from unavailable listing (review cart), and explicit free shipping from an empty/incomplete basket.
- Do not trust UI item count, names, prices, or subtotal as source of truth. Preserve current quote-revalidation and `quote_changed` affirmative reconfirmation. Confirm cart subtotal, shipping band, message, enquiry snapshot, and thank-you all refer to the **same fully represented basket**.
- Do not mutate Mini-Store vendor/order/stock logic or introduce auto inventory deductions.

**Test first, prove after:**

- **Rendered Checkout & Cart tests plus server action tests:** all products missing; valid+stale; hidden; removed/unlinked product; ended supplier; foreign-store product; duplicates; zero valid products; all valid; free shipping on a **valid positive-value** basket; legitimate zero-price edge under established policy.
- For rejected basket: `status` must not be `resolved`; no payable “₹0/free” success claim; submit disabled; **zero enquiry, enquiry-items, vendor-queries, outbox or order writes**; any customer-visible message cannot suggest all local items are included.
- After shopper removes stale item and gets fresh complete quote, normal save and confirmation work. If listings disappear/change between quote and save, return safe reconfirm/failure before writes.
- At relevant shipping bands below/at/above, totals still align with server value; out-of-order quote response must not override newer basket.

### F3 — BLOCKER: Two protected baseline tests regress due to new `clientSlug` requirement

**Codex evidence:** exact isolated base = **38/38 PASS**, candidate = **36 PASS / 2 FAIL**. Existing protections now fail *before exercising tenant-scoped assertions* because their test fixtures omit `clientSlug`:

- `qa/security/bundle8/f1-storefront-filters.action-test.ts:232`
- `qa/security/bundle9/bundle9.action-test.ts:155`

**Required action:** update only test fixtures/mock resolution or minimal compatibility wiring so these **original protected tenant isolation assertions actually run and PASS**. Supply the correct store slug and resolver mock, with **matching server-resolved company**. Never add a bypass for wrong slug, weaken `saveEnquiry` security, change production behavior solely to appease tests, delete/skip/rename assertions or reclassify newly failing tests as baseline failures.

**Evidence:** capture 36/38 failure on rejected candidate; fix; same isolated test command yields **38/38 PASS**, with original assertions demonstrably reached. Inspect for other protected tests that bypass only because of new required inputs. Re-run full related security suite.

### F4 — BLOCKER: Changed-file quality gate fails on EOF whitespace

**Codex evidence:** `app/actions/mini-store-save-enquiry-money.action-test.ts:312` added blank line at EOF. `pnpm lint` has zero ESLint errors but **fails `git diff --check`**.

**Required action:** remove trailing whitespace/extra EOF blank line without changing test behavior; rerun **the exact repo quality command**, `git diff --check` in the relevant diff context, and show clean exit code. Be precise: check against **original baseline and current candidate** (e.g., `git diff 5bc0e1b3..<new SHA> --check`; plain `git diff --check` on clean committed working tree alone checks nothing). Run lint, including its combined workflow.

## 3. Protections already passed — DO NOT REGRESS

Codex's second review accepted these safeguards on `e85b8a34`:

- **B1** typed shipping outcomes distinguish DB error, no-config, no-match, explicit-free and paid; DB errors and throws fail enquiry with zero writes. **Nonresponse/timeout remains NOT PROVEN**; at least inspect and report behavior. Do not silently convert unresolved IO to free shipping.
- **B3** old 120-quantity browser cart is normalized to **99** in rendered page, localStorage, quote, message and submitted payload. Keep rendered regression tests.
- **B5 / WP07** current code/test privacy scan finds zero personal payment identifiers; no real payee values in test names/logs; unsafe legacy template markers fail closed. Keep `pnpm quality:privacy`, server-only matching and company-specific saved template requirement. Historical Git literals and low-entropy fingerprint brute-force risk are follow-ups **not authorization to rewrite history or build new secrets/config**.
- **B2** server-authoritative quote, stale-response suppression, changed-price confirmation; strengthen basket completeness while keeping them.
- **B4** the original publicly callable arbitrary-company raw shipping-rule action is removed; do not reintroduce it. Focus now on visitor capture tenant isolation/recovery.
- **No-match/no-configuration = ₹0** remains the currently documented existing shipping rule; do not invent merchant fees or conflate with explicit free shipping or DB lookup failure.
- Payment statuses other than Payment Pending, Mini-Store vendor queries/responses, order conversion, fulfillment vendor notification, tenant isolation, no automatic numeric stock writes and retained historical data must remain functional and unchanged unless proven regression demands a narrowly scoped fix.

**Separately track, do not silently grow Wave 0A:** same enquiry double-submission currently possible; DB shipping never-responds/timeout; historical payee values in Git history; old hard-coded brand fallbacks elsewhere. If you discover a newly exploitable **material money/tenant issue** during these fixes, explicitly report it for independent assessment rather than concealing or automatically deferring it.

## 4. Required test and independent verification discipline

- Write **failing-before** adversarial tests for F1/F2; the existing F3/F4 failures serve as documented red tests. Record exact test names, commands, assertion details and result before editing; do not fabricate red evidence.
- Fix each root cause by minimal edits; keep old rejected commits as immutable history. Make **new named fix-forward commits**; no history changes. Re-run direct tests after each fix, then all Mini-Store/messaging relevant suites, protected security bundles, privacy scan, project lint/quality, `git diff <base>..<new-candidate> --check`, and `tsc --noEmit` using a clean isolated environment (exclude or separately report `.next` generated types). Report **baseline vs candidate error signatures** rather than counts alone.
- Full suite: Codex's last exact candidate showed **619 files passed / 5 failed; 12,524 tests passed / 13 failed**. Only 2 protected tests were independently proven new against baseline; compare the **same commands and isolation** to original SHA to distinguish all baseline failures and any remaining regressions. Target **no new failures**; never call suite GREEN while baseline failures remain. If complete suite expensive, run relevant first but full comparison must be attempted before claiming Wave 0A ready.
- **Independent Red-Team:** separate reviewer tests the new SHA with adversarial Store A→Store B capture, stale/partial cart, quote confirm, protected security assertions, and valid two-tenant checkout. Reviewer can REJECT; builder must fix forward and repeat. Keep reviewer findings in report, including rejected cycles.
- No real provider execution, production DB or WhatsApp, cron, migrations, activation flags, deployments, push/merge. Any live/isolated DB E2E needs separate verified environment and approval. Distinguish unit/mock/component/browser-real-DB levels of evidence; do not claim live proof.
- Preserve the prior `node_modules` symlink incident in provenance, but do not perform further dangerous worktree removal.

## 5. Completion, evidence ledger, and STOP gate

Produce `docs/pre-p3-execution/WAVE_0A_CODEX_SECOND_REJECTION_FIX_FORWARD_REPORT.md` **as a docs-only final commit** after code candidate is committed. Report should contain:

1. Repository identity: base, rejected SHA `e85b8a34`, fix-forward code candidate full SHA, docs-only HEAD full SHA, clean worktree, commits, no rewrite.
2. F1–F4 root cause and file:line, exactly what changed, negative/positive tests and red→green proof. Include full Store A capture → Store B checkout → reload chain, full-basket completeness and the two protected assertions.
3. B1–B5 preservation check with WP07/WP06 split; nonresponse gap explicitly identified; privacy scan **counts only**, no actual payee identifiers.
4. Test ledger: changed-file lint/diff-check; protected **38/38**; focus suites; full-suite baseline-vs-candidate failure **paths and fingerprints**; clean typecheck comparison; mock/isolation proof; no removed assertions.
5. Any new regressions, residual risks and E2E NOT PROVEN items, with classification and later owner. No false completion.
6. Codex packet: `git diff 5bc0e1b3..<new-code-SHA>` and `git diff e85b8a34..<new-code-SHA>`, independent reviewer focus, exact output commands, and the **docs-only** report commit distinguished from code SHA.

Final response to Founder must state exactly **`READY_FOR_CODEX_RE-REVIEW`** only if independent Red-Team has approved F1–F4 and no new blocker remains, otherwise **`WAVE 0A STILL OPEN — NOT READY`**. Even if ready, Wave 0A **is not closed** until a fresh independent Codex APPROVED verdict and Founder close-out. **STOP after report; do not start Wave 0B.**