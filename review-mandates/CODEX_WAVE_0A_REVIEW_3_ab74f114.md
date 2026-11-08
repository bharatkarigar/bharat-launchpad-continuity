# Bharat Launchpad Pre-P3 Wave 0A — INDEPENDENT CODEX RE-REVIEW (Third Candidate)

**Date:** 2026-11-08  
**Task:** Verify WP07 + WP06 full-wave correctness and close the FOUR blockers from the second Codex rejection, without modifying code.  
**Role:** Independent adversarial reviewer. Treat Claude's claims and internal Red-Team approval as **unverified until independently tested**.

## 0. Absolutely non-negotiable boundaries

- This is a **STRICTLY READ-ONLY** code, test and security review. Do **not** edit source, tests, fixtures, docs, branch, history, commits, database, environment, flags, cron, provider integrations, deploy settings or production. No push, merge, rebase, reset, stash, clean, or worktree deletion. Do not start Wave 0B.
- Do not trigger real checkout, customer communications, WhatsApp, payment, providers, or production/non-isolated DB reads or writes. Before running any test, confirm it is mocked/offline. If unsafe or unverifiable, mark **NOT PROVEN**; never substitute a live test.
- **Never output, reproduce, grep-print or quote actual legacy personal UPI, phone, bank, or payee identifiers.** Use privacy-check PASS/FAIL and counts only, with sanitized file paths. Don't reproduce PII or secrets.
- Avoid scripts that mutate the repo or generated files. Snapshot `git status --porcelain=v1` before/after. Do not silently clean artifacts. If repo is dirty, or identity differs unexpectedly, stop and report.
- Do not accept an issue as a blocker solely because it is a hypothetical enhancement; substantiate with a concrete reachable path and relevant Pre-P3 contract. Conversely, do not defer active tenant-isolation, customer-money or protected-test regressions merely because they predate this wave.

## 1. Verify exact repository identity and reviewed objects

Reported by Claude (verify all):

| Item | Reported value |
|---|---|
| Repo | `/Users/harshvidyarthi/Desktop/lp-final-int` |
| Local branch | `pre-p3/v10-4-wave-0a-safety` |
| Original clean base | `5bc0e1b302be55a22046e6d3335ddc60b558f4bd` |
| First Codex-rejected candidate | `33286ffd85b515aee6955bf54cbce201d35e997d` |
| Second Codex-rejected candidate | `e85b8a3481cbd790325977001228f2fe138329fe` |
| **Current CODE candidate** | **`ab74f11459e1efdab62464fd4d7614b1132203eb`** |
| Docs-only HEAD | `a9c8db14` prefix; verify full SHA and that diff from code candidate is *only* the report |
| Worktree | Clean; branch/commits local only |

Run safe identity commands: `pwd`, `git branch --show-current`, `git rev-parse HEAD`, `git status --porcelain=v1`, `git log --oneline --decorate -16`, `git diff --name-status ab74f114..HEAD`, `git cat-file -t ab74f114`, and confirm no intervening source mutations. Do not review the docs commit as new code.

Review these exact immutable diffs:

```bash
git diff 5bc0e1b302be55a22046e6d3335ddc60b558f4bd..ab74f11459e1efdab62464fd4d7614b1132203eb
git diff e85b8a3481cbd790325977001228f2fe138329fe..ab74f11459e1efdab62464fd4d7614b1132203eb
git diff 5bc0e1b302be55a22046e6d3335ddc60b558f4bd..ab74f11459e1efdab62464fd4d7614b1132203eb --check
```

Read `docs/pre-p3-execution/WAVE_0A_CODEX_SECOND_REJECTION_FIX_FORWARD_REPORT.md` if present and prior reports, along with the V10.4 Founder registry **only if available locally**. Mark unavailable sources `SOURCE UNAVAILABLE`; do not invent content. Base and candidate tests must use **equivalent isolated commands/environments**.

## 2. Resolve precisely the four Codex rejection findings (F1–F4)

Produce a four-row matrix of **original exploit → code path → failing-before test → passing-after test → verdict → remaining risk**. Link exact **file:line** in this candidate, not outdated line numbers.

### F1 — Cross-store visitor mutation AND recovery (former B4)

Earlier confirmed: Store A's domain-wide visitor cookie was presented at Store B. `createOrRefreshVisitor` looked up a token without tenant scope, updated Store A visitor PII, then Store B enquiry was rejected. New code reportedly scopes lookup and creates a separate Store B visitor and cookie.

Verify independently:

1. Cross-store token is never used to **read, update, log, associate enquiries with, or reveal** Store A's visitor record while on Store B, including initial capture action preceding `saveEnquiry`. Check lookup UPDATE selectors, tenant resolution, SSR page, cookie-write code, middleware, and every caller.
2. Store A cookie → Store B page → visitor capture → server quote → enquiry submission → cookie replacement → Store B reload completes without impacting Store A's visitor, message/outbox, or enquiry. Verify the browser receives the **new** token, not just an in-memory token; cookie path/domain/SameSite and next server render must use Store B correctly.
3. Correctly preserve Store A's historical data and support returning to Store A (new Store A session if host-wide cookie now belongs to B). Normal repeat visit to same store must not create duplicate visitors unnecessarily.
4. Test mismatch/forged token, nonexistent/deleted token, valid same-store token, invalid store slug, rapid/concurrent visits, and attempts to pass arbitrary company IDs. There must be no cross-tenant writes or data leakage. Identify whether unused session helpers are truly server-only and unreachable from external callers; if reachable, don't defer a boundary flaw.
5. Demand **full rendered/integration chain** tests with DB/cookie mocks that inspect the visitor write target. Unit test on `saveEnquiry` alone is **not** sufficient. Real browser+DB remains **NOT PROVEN** and should not be claimed.

### F2 — Incomplete basket must never yield a resolved partial/₹0 quote (former B2)

Earlier confirmed: quote silently filtered missing/hidden/unlinked/foreign/supplier-ended products, returned `resolved`, and checkout counted unsanitized local items. New quote + save allegedly fail closed; Cart/Checkout show removable unavailable items.

Verify independently:

1. Every **normalized requested** product and quantity must be represented by same-tenant current available/purchasable DB rows **before** a quote becomes `resolved` or any enquiry writes occur. No silent subset, no empty basket falsely shown as free shipping, no leaking foreign private product existence.
2. Cases: all missing; valid+stale; hidden; unlinked; ended vendor/supplier; foreign company; duplicates, malformed IDs, quantities/99 cap, zero rows; normal multi-item basket; explicitly free shipping for a legitimate valid basket; no-config/no-match rule at ₹0 under existing business policy. Distinguish **unavailable** from transient DB **error** and allow correct retry/review actions.
3. Rendered Cart and Check Availability: mark unavailable items; one-click Remove unavailable items removes only the right items and updates browser localStorage, selected counts, message, fresh quote and visible totals. Submit stays blocked until a complete server quote and, after any price change, affirmative confirmation. No stale/out-of-order quote can re-enable submission, no mismatched UI item count.
4. At **save time**, revalidate the same complete basket to stop TOCTOU. On stale/missing items, zero enquiry/line-item/vendor-query/outbox/order writes; no mismatched thank-you or WhatsApp text. Test between quote and save, price-band boundary and repeated click conditions, and preserve vendor/order flow without inventory stock writes.
5. Make sure no source of authority is client subtotal/shipping/merchant ID. A properly scoped honest shopper can still complete checkout, and `quote_changed` confirmation remains functional.

### F3 — Protected security tests must genuinely PASS (not just bypassed)

Codex's last direct base isolation run **38/38 PASS**, rejected candidate **36/38**. Failures were at:
- `qa/security/bundle8/f1-storefront-filters.action-test.ts` (former line ~232)
- `qa/security/bundle9/bundle9.action-test.ts` (former line ~155)

New report says **38/38 PASS**, test setup now passes correct server-resolved slug without changing original assertions.

Check diffs and runtime assertions: only legitimate fixture setup changed; exact original tenant-scoping assertions are still executed; no `skip`, `todo`, test-name tricks, false mocks, deleted coverage, weaker predicates or expanded mocked permissions. Run the **same protected suite command** at candidate and, where safe, independently compare original base or inspect prior verified base evidence. Scan all relevant protected suites for new required `clientSlug` callers and ensure no similarly concealed early failures.

### F4 — Full quality command must be truly GREEN

Last rejection: `pnpm lint` had zero ESLint errors but `git diff --check` failed because of an extra EOF blank line in `app/actions/mini-store-save-enquiry-money.action-test.ts`.

- Run `git diff 5bc0e1b3..ab74f114 --check` and `git diff e85b8a34..ab74f114 --check` **with explicit candidate refs**. Do not use plain `git diff --check` on a clean committed worktree as proof.
- Confirm the repo's **actual lint/quality gate command** exits 0 (verify package script behavior); report warnings separately. Verify privacy scan passes and outputs no identifiers. Do not make edits to fix lint during review.

## 3. Preserve ALL previously accepted five-blocker protections (B1–B5)

Check all five again **against the complete base→candidate diff**, not only the latest patch:

- **B1 Shipping safety:** Typed outcomes distinguish DB `error`, throws, malformed rule, timeout/nonresponse, no configuration, no matching rule, explicit free shipping and paid shipping. Errors must return retryable failure with **zero writes**, not ₹0 disguised as free. New 8-second timeout must actually abort/bound failure or safely ignore late fulfillment and never persist after timeout; simulated timers are not a real DB timeout proof. No-match/no-config remain ₹0 *only* under approved existing behavior.
- **B2 Authoritative amounts:** Browser totals ignored; confirmed server pricing controls persisted subtotal/shipping/total and returned thank-you/message; stale quote suppression, required positive confirmation when price/rule changes, tier boundaries, payment fairness, and full basket completeness. No approved amount silently changes after consent.
- **B3 Quantities:** Legacy 120 normalizes to 99 in rendered UI, localStorage, server quote, message and saved enquiry. Test normal and invalid quantities and no 120 flash.
- **B4 Tenant-safe public pricing:** No exported arbitrary-company service-role shipping action; storefront context resolved by server; no private shipping rule detail leaked; cross-store visitor capture fix is essential to final approval.
- **B5 WP07 payments:** Payment Pending **fails closed** unless current merchant has a valid company-scoped saved template; no wrong payee, no status mutation or outbox enqueue on blocked send. All other existing status/vendor messages remain usable. `pnpm quality:privacy` scan + detector self-tests must pass; report only safe counts. Low-entropy fingerprint reversibility and Git history with legacy identifiers are documented follow-ups; **do not rewrite history** without Founder approval.

Also trace Mini-Store product/vendor query and downstream order conversion to catch any new API contract mismatch; no speculative feature building.

## 4. Independent test ledger — zero new regressions

Prior evidence (claims requiring confirmation):

- Candidate relevant suites: **1,265/1,265 PASS** (Mini-Store, messaging, protected security).
- Original base and candidate full-suite common failure categories: canonical sync and supplier onboarding. Candidate reportedly **11 baseline failures and no new failures**. Do not substitute the failed 13-test ledger from the previous candidate.
- Typecheck: **53 baseline, 53 candidate**, no new error signatures excluding incidental generated `.next` diagnostics.
- Project lint: 0 ESLint errors and full gate now exits successfully.
- Privacy scan: PASS. Worktree remains clean.
- No actual live E2E/browser-cookie+real-DB, provider/WhatsApp tests conducted.

Independently re-run safe test commands where feasible. For full suite, compare actual failed **test identifiers and assertion reasons** base vs candidate under same execution; “11 vs 11” without identities is inadequate. Verify no protected/new security test is skipped. Separate *MOCKED TEST PASS* from *REAL E2E NOT PROVEN*. If tests need repo-altering build/generated files or live resources, mark blocked and cite reason; do not pretend execution.

Check the earlier `node_modules` symlink deletion incident did not lead to source drift; inspect lockfile status and installed dependency/test environment if pertinent. **Do not delete worktrees, node_modules, or reinstall packages during read-only review.**

## 5. Verdict and stop gate

Produce sections in this exact order:

1. `REPOSITORY IDENTITY` — branch, immutable SHAs, clean worktree, docs-only HEAD verified.
2. `F1–F4 CLOSURE MATRIX` — each row PASS/REJECT/NOT PROVEN; code file:line, red→green evidence and new regressions.
3. `B1–B5 PRESERVATION MATRIX` — including separate **WP07** and **WP06** verdicts.
4. `TEST AND QUALITY LEDGER` — exact commands, counts, baseline comparisons, protected 38/38, lint/diff-check, privacy, typecheck, mock boundaries.
5. `BLOCKING FINDINGS` — only confirmed material risks or unacceptable missing mandatory evidence, each with minimal concrete fix and regression-test criteria. Distinguish *pre-existing nonblocking follow-ups* and *unproven external E2E*.
6. `RESIDUAL RISKS` — idempotency/double submit, historical Git credentials, low-entropy fingerprints, unused helpers, browser+real DB E2E; explicitly qualify them.
7. `FINAL VERDICT` — `WP07: APPROVED | REJECTED`; `WP06: APPROVED | REJECTED`; `WAVE 0A: CODEX APPROVED | CODEX REJECTED`.

**Approval rule:** approve ONLY if F1–F4 closed, B1–B5 preserved, no new money/tenant/security/functional regressions, and all mandatory safe tests/quality gates pass. Do not label the wave released or deployed. If one confirmed blocker survives, reject with evidence. Do **not** demand real provider/production actions to approve a local code gate; mark real E2E unproven and reserve separate controlled validation for later.

**STOP. No implementation, no Wave 0B, no push/merge/deployment, no production changes.**