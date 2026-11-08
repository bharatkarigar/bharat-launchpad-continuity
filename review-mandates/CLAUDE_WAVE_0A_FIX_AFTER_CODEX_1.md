# Bharat Launchpad Pre-P3 — Wave 0A Codex REJECTED: Controlled Fix-Forward Mandate

**Issued:** 2026-11-08  
**Authorization:** Extend the previously Founder-approved **local Wave 0A** development **only to correct the five confirmed Codex blockers** below. This does **not** authorize Wave 0B, production, push/merge/deploy, live sends, production DB work, migrations, flags, external provider actions, or unrelated refactoring.

## 0. Authority and starting position

- Repo as independently reported: `/Users/harshvidyarthi/Desktop/lp-final-int`
- Local branch: `pre-p3/v10-4-wave-0a-safety`
- Clean HEAD before changes: `9e8002e63dc5412fa8d18a83d706e76248ae9b08` (report-only tip; verify rather than assume)
- Original baseline: `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`
- Rejected code candidate: `33286ffd85b515aee6955bf54cbce201d35e997d`
- Independently reported result: **WP07 REJECT / WP06 REJECT — Wave 0A OPEN**.
- The Codex verdict supplied in chat is the **blocker list**. Claude must validate file/line references against the actual checkout and tests and **must not treat this prompt as a replacement for evidence**. Read existing `docs/pre-p3-execution/WAVE_0A_WP07_WP06_REPORT.md`, V10.4 Founder Registry (if available), Wave 0A original mandate, and Codex review transcript/report if present. If V10.4 is unavailable, declare `SOURCE UNAVAILABLE`; do not invent rules.

### Preflight: required before any edit

1. Record `pwd`, branch, `git rev-parse HEAD`, `git status --porcelain`, `git log -6 --oneline`. Confirm the original baseline, rejected candidate and report commit exist locally. Confirm the worktree is clean. **If not clean or surprising HEAD, STOP** without stashing/resetting/rebasing.
2. Examine relevant code and tests, including all active callers and customer-visible readers. Check available test/build commands. Prove that test execution is **mocked or isolated** before running. Never print env values, phone/bank/UPI credentials, tokens, customer data or secrets; inspect env **variable names and target identities only** if necessary.
3. Preserve rejected commits and complete provenance. Make **new fix-forward commits** on the same local branch; no amend/rebase/squash or history rewriting. Keep an independent test ledger. No parallel editing agents on shared paths.
4. Set pre-change assertions for each blocker **before** modifying implementation. Record a failing-before result or explicitly explain why it cannot be safely captured; do not claim red/green without proof.

## 1. Five BLOCKERS to close — all mandatory

### B1 — N3: DB shipping lookup error silently becomes free shipping

**Reported leads:** `app/actions/shipping-rules.ts:57,69`, `app/actions/mini-store.ts:769,792`, `app/actions/mini-store-save-enquiry-money.action-test.ts:16`.

- Trace the actual rule query, existing shipping policy, public quote, save and downstream create-order. Never interpret a database failure/timeout/throw as `₹0` or as a successful free shipping rule.
- Introduce a **discriminated outcome** or equivalent exhaustive typed result: `matched_rule`, `explicit_free_shipping`, `no_configuration` / `no_match` (distinctly classified), and `lookup_error` / `unavailable` (retryable). Exact names may differ with repository conventions.
- Fail **closed with zero enquiry, item, vendor-query and outbox writes** for read failure/exception. Ensure downstream consumers cannot mistake failure for zero.
- Preserve legitimate explicit free-shipping policies. Determine from existing rules whether **no matching rule** historically means no fee, a validation error, or a merchant-specific fallback. Document observed behavior; do **not** invent a new fee or silently treat unconfigured / no match / explicit free as the same condition. If required policy is not provable, stop just that unresolved behavior, clearly flag `NEEDS FOUNDER DECISION`, and keep money unsafe states blocked; do not proceed with an invented rule.
- Test-first: query returns error; query throws; successful no configured rule; configured rules with no matching band; explicit free rule; normal paid shipping; zero subtotal if supported; zero writes on failures and retryable customer-facing error.

### B2 — N4: Customer quote, saved amount, message and thank-you disagree

**Reported leads:** `components/client/mini-store/CheckAvailabilityPage.tsx:168,231,239,367,383`, `app/actions/mini-store.ts:760`, `app/store/[clientSlug]/check-availability/page.tsx:123`.

- Map the **entire** customer-visible money path: cart prices → quote loading → shipping lookup → displayed subtotal/shipping/payable → submit → persisted enquiry → rendered WhatsApp text/confirmation → thank-you page/order conversion.
- Ensure **one authoritative amount**: derive from current server DB products and rule snapshot (never browser money). A server quote/commit protocol or an equivalent transactional response can be used; no hardcoded browser amount can override the persisted truth.
- Guard asynchronous races with a request identity/version or cancellation check; disregard stale responses when cart/quantities/products/company change. Clearly represent `loading`, `resolved`, `failed`, and `stale` states. Disallow final submit when quote unresolved/error or stale, subject to verified current business policy.
- A final server-side save **recalculates** and returns trusted `subtotal`, `shipping`, `grand_total`, and any necessary authoritative normalized line items / chosen rule provenance. Customer message and thank-you must use **the persisted server result**, not stale cart totals. If price changed since the prior displayed quote, clearly show corrected amount / require confirmation as appropriate; **do not silently charge a different amount** or imply approval of a different total. Do not persist a misleading customer-facing amount.
- Avoid a sprawling rewrite: reuse existing Mini-Store pricing/availability logic and response types; keep current enquiry/order/vendor flows functional.
- Test-first: price band boundaries immediately below, exactly at, and immediately above; cached ₹999 vs current DB ₹1,000; deliberate delayed/error/out-of-order responses; cart mutation while quote pending; submit before quote; race between quote and save; returned DB snapshot used in persisted customer text and thank-you; valid legacy path.

### B3 — Previously rejected 120 → 99 issue remains in hydrated cart

**Reported leads:** `components/client/mini-store/CartPage.tsx:61,167,273,346`, `lib/mini-store-limits.logic-test.ts:9`.

- Normalize quantities **at localStorage hydration**, using shared cap (99) and established min/integer rules; persist sanitized cart back to storage where safe; ensure add/edit/submission use the same helper. No indefinite display of 120 while billing/saving 99.
- Test the actual **rendered component**, not helper alone: inject historic cart with quantity 120; verify displayed quantity 99, subtotal at 99, persisted cart 99, customer message 99, submitted quantity 99 and resulting saved snapshot 99. Test invalid/negative/decimal quantities as applicable and normal carts unaffected.
- Do not affect order-driven inventory behavior. Keep no automatic numeric stock writes.

### B4 — N7: Arbitrary-tenant public shipping-rule reads

**Reported leads:** `app/actions/shipping-rules.ts:44,55`, public server-action registration, arbitrary clientId accepted.

- **Remove any browser-invocable exported service-role action** that returns raw shipping rules for a caller-supplied tenant UUID. Relocate privileged rule lookup to server-only internal logic with explicit tenant context. Inspect other imports/call sites before changing exports.
- A public storefront still needs to quote legitimate shipping without login. Resolve tenant from **trusted server-established storefront routing/context** (e.g. route slug/domain resolved to approved store/company) rather than accepting a raw arbitrary `clientId` as authority. A user may visit another **public storefront**, but must not extract internal raw rule rows, priorities, other tenant private data, or target an arbitrary UUID. Return only the minimal public price/quote projection required for that current storefront; apply public/publish gating as applicable under the current rules without implementing the future WP08 redesign.
- Test-first: direct invocation of old action by foreign tenant UUID fails / is no longer publicly reachable; quote for public Store A only contains minimal Store A total; malicious mixed Store A slug + Store B UUID cannot obtain B's rule rows; internal calculation retains isolation; no anonymous service-role table dump. Verify generated server-action exports/manifest where tests/build allow.
- Security boundary is mandatory even if the weakness predates Wave 0A. Avoid general multi-tenant architecture rewrites beyond closing this exposure.

### B5 — WP07: Private payee identifiers remain in production source/test output

**Reported leads:** `lib/mini-store-status-messages.ts:46`, `lib/messaging/outbox-enquiry-payment.action-test.ts:30,97`.

- Remove actual personal payee numbers, UPI handles, banking identifiers and corresponding human-readable tokens from **current application source, tests, fixture files, test titles, snapshots and logs**. Do not echo the values to console, assistant output, reports or commit messages.
- Preserve protection against **already saved legacy unsafe templates**; detection must remain tenant-safe and deterministic. Options include non-plaintext normalized matching metadata / fingerprints or a safer design, but analyze and document leakage risks of simple hashes of low-entropy phone numbers. **Do not introduce a new production env secret/migration, silently delete merchant templates, or weaken legacy blocking** just to satisfy a grep test.
- Replace fixture identifiers with synthetic non-personal markers; add tests showing legacy unsafe data is still blocked, properly configured merchant text passes, and log/JUnit/test-title output cannot contain personal identifiers.
- Add a **privacy-safe repository scan gate** that reports **only PASS/FAIL and paths or counts**—not literal matched secret values. Scan tracked current application source/test/fixtures and generated test outputs as appropriate. Historical Git commits containing previously committed literals are not fixed by a working-tree edit; do not rewrite Git history without separate authority. Log any history remediation advice outside this wave.
- Preserve `payment_pending` fail-closed, company-branded defaults for other safe statuses, merchant setup error, correct outbox retry handling, and no status/enqueue on blocked send.

## 2. Mandatory test contract and red-team gates

Before implementation, independently author targeted regression + adversarial assertions for **all five blockers**. Each must record `FAIL-before` → `PASS-after` where safely reproducible. Test the integrations with **mocked DB/outbox/provider** only, not production. Tests must assert side-effects (no DB writes when lookup fails, no outbox mutation when payment configuration fails) rather than only checking returned text. Verify real React hydration/rendering via component tests where feasible.

Minimum outcome matrix:

| ID | Required proof | Pass condition |
|---|---|---|
| N3-a | shipping query error / throw | retryable error, zero enquiry/items/outbox writes |
| N3-b | no config / no matching band vs explicitly free | distinct result and documented policy, no accidental free outcome |
| N3-c | valid paid rule | correct calculated server shipping |
| N4-a | initial/pending/stale/error quote | cannot submit misleading total |
| N4-b | ≤ / = / ≥ every price-band edge | visible/returned/persisted total agree |
| N4-c | price changes between preview and save | truthful re-quote/confirmation, no silent mismatch |
| N4-d | customer WhatsApp text and thank-you | only authoritative stored quote/total |
| QTY | old local cart 120 | rendered, submitted, persisted 99; storage normalized |
| N7-a | arbitrary foreign company UUID | cannot fetch raw foreign rules via public action |
| N7-b | valid Store A public quote | scoped minimal projection, no raw config leak |
| WP07-a | current source and emitted test output | no real personal identifier disclosure |
| WP07-b | saved unsafe template | blocked before enqueue/status change, even after source literals removed |
| WP07-c | valid company template, manual/outbox | correctly scoped and unaffected |

Also rerun the originally reported **43 files / 958 tests** or their current equivalent, relevant typecheck and changed-file lint. Typecheck comparison: Codex independently reported **53 baseline vs 53 candidate** in a clean isolated comparison; previous builder's `87` included generated `.next` types. Do not use 87 as the canonical baseline without specifying environment. Attribute only **new** errors to the current fix. Report warnings separately.

Independent Red-Team (read-only review after edits) must attempt:
1. Third-party company-shipping-rule extraction through public actions/routes.
2. Shipping DB exception under checkout with potential undercharge.
3. Out-of-order response and price-band edge that shows a mismatched payable.
4. Old cart hydration with 120 shown and 99 saved.
5. Legacy unsafe payment template bypass, logger/test stdout leakage, and retry resend.
6. Valid customer enquiry, order conversion and active vendor notifications regression (static evidence and mocked tests; label unrun live E2E as `NOT PROVEN`).

If Red-Team rejects, **fix-forward** only and rerun relevant tests. Never turn a rejected test green by weakening acceptance assertions or silently changing policy. Produce new CODE candidate SHA and **stop before independent Codex**; Codex itself remains a separate reviewer.

## 3. Scope boundaries and immutable Founder decisions

- Only Wave 0A monetary and tenant-safety corrections described above; do **not** begin WP08/WP12/WP14/WP16 or any later wave even though the service-action fix overlaps future security work. This overlap is explicitly necessary to close N7.
- No migrations, manual DB updates, production reads/writes, row deletions, env changes, provider OAuth/scopes, cron, activation flags, live WhatsApp, pushes, merges, deploys or destructive Git operations.
- Preserve existing Mini-Store enquiry, vendor query, create-order and customer journey pathways, merchant-custom templates, current shipping business configuration and saved historical data.
- Preserve live Fulfilment Step 4 vendor send (`/api/whatsapp/notifications/send-to-vendor`), Mini-Store vendor notifications, and vendor responses. The retired Product Sales APIs are **Wave 0B**, not this task.
- Do not add automatic inventory decrement/restore, do not touch Shopify/Wix provider stock execution, don't create an unrelated payment-integration/checkout architecture.
- Founder product policy ambiguity that cannot be grounded from code/registry must be surfaced as `NEEDS FOUNDER DECISION`; do not invent a default that affects customer money. No unrelated product questions.

## 4. Required outputs and stop condition

1. Commit or report the **new candidate SHA** after fix-forward, branch and status, plus original rejected SHA; preserve history.
2. `docs/pre-p3-execution/WAVE_0A_CODEX_REJECTION_FIX_FORWARD_REPORT.md` with: five findings → root causes → changed files → before/after test proof → exact test commands/counts → baseline vs introduced typecheck → red-team verdict → valid-flow checks → `NOT PROVEN` gaps → any remaining risks. Include any decisions required, but do not conflate already settled rules.
3. A new Codex review packet: exact diff `5bc0e1b3..<NEW_CODE_SHA>` **and** incremental fix diff `33286ffd..<NEW_CODE_SHA>`; do not review only the final report commit or only incremental diff.
4. Explicitly state one outcome: `READY_FOR_CODEX_RE-REVIEW` or `BLOCKED — NOT READY`; do **not** self-declare Wave 0A closed.
5. **STOP**. No Wave 0B, no production action. Await independent Codex approval and Founder close-out.

**One-line execution instruction:** Fix exactly the five Codex-confirmed Wave 0A blockers test-first, preserve customer/vendor flows, independently red-team the new local candidate, report the new SHA, and stop for Codex re-review.