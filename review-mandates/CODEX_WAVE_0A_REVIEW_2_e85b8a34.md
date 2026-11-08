# CODEX INDEPENDENT RE-REVIEW — BHARAT LAUNCHPAD PRE-P3 WAVE 0A

**Target:** WP07 Wrong Payee + WP06 Server-Authoritative Mini-Store Amounts — second Codex pass after five confirmed blockers.  
**Date:** 2026-11-08  
**Role:** Independent adversarial *reviewer*, not builder.  
**Authority:** READ-ONLY verification of local code candidate. Do not approve on the basis of Claude/Red-Team assertions; independently inspect and falsify them.

## 0. Mandatory permissions / stop rules

- **READ-ONLY.** Do not change code, test assertions, fixtures, docs, git history, commits, branch, tracked/untracked files, DB, migrations, env, plans, feature flags, provider scopes, cron or live data. Do not stash, reset, rebase, squash, clean, push, merge or deploy. Do not begin Wave 0B or later work.
- Do not send WhatsApp, trigger live checkout/payment/provider execution, access production databases, invoke authenticated third-party APIs, or perform external mutations. If a purportedly safe test requires real services, **do not run it**; mark `NOT PROVEN`.
- Do not reproduce personal payment credentials, token values, PII or legacy payee identifiers in console, report, screenshots, fixture output or excerpts. For privacy checks show only pass/fail, paths and counts.
- Only run tests when proven isolated/mocked; identify and avoid commands that would modify repo outputs or hit real resources. If a read-only review tool itself produces ephemeral generated files, disclose them and preserve/restore clean state without destructive operations (prefer static inspection).
- If repository identity is wrong, relevant SHA is missing, or worktree is unexpectedly dirty, **STOP and report**; do not silently switch refs.

## 1. Exact identity and input evidence

User's handoff claims:

- Repo: `/Users/harshvidyarthi/Desktop/lp-final-int`
- Branch: `pre-p3/v10-4-wave-0a-safety` (LOCAL ONLY)
- Base SHA: `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`
- First Codex REJECTED code candidate: `33286ffd85b515aee6955bf54cbce201d35e997d`
- NEW CODE candidate to review: **`e85b8a3481cbd790325977001228f2fe138329fe`**
- Report-only branch HEAD: `c5b38a9e` (verify complete SHA; no assumption that HEAD diff equals the code diff)
- Internal Red-Team REJECTED intermediary: `8d7df3a4` (retained in history; identify exact commit and grounds from report)
- Candidate worktree reportedly clean. No push/merge/deploy, DB/flag/env/cron/provider mutations or real WhatsApp sends.

Independently record `pwd`, `git branch --show-current`, `git rev-parse HEAD`, `git status --porcelain=v1`, `git log --oneline --decorate -12`, `git show --stat --oneline e85b8a34`, and concise diff stats. Confirm refs resolve and rejected history remains reachable. **Do not modify the branch.**

Review **both diffs**:

1. Full Wave 0A: `git diff 5bc0e1b302be55a22046e6d3335ddc60b558f4bd..e85b8a3481cbd790325977001228f2fe138329fe`
2. Fix-forward since Codex rejection: `git diff 33286ffd85b515aee6955bf54cbce201d35e997d..e85b8a3481cbd790325977001228f2fe138329fe`

The docs-only report commit must not be mistaken for implementation. Inspect `docs/pre-p3-execution/WAVE_0A_CODEX_REJECTION_FIX_FORWARD_REPORT.md`, the first Wave 0A report and available V10.4 Founder registry / initial mandate. If a requested file is absent, mark `SOURCE UNAVAILABLE` and use the actual code and supplied review findings rather than inventing its content. User's current handoff is *claims*, not independent evidence.

## 2. Re-review exact five previously confirmed blockers

Make a five-row verdict matrix: `BLOCKER`, `original exploit`, `new code location`, `failing-before test`, `passing-after test`, `Codex verdict`, `residual risk`.

### B1 / N3 — Shipping lookup failure must not become ₹0 shipping

Original issue: `app/actions/shipping-rules.ts` collapsed DB failure and no-match into 0; `saveEnquiry` persisted 0 on errors.

Independently prove:

- DB `error`, thrown exception, timeout/nonresponse, malformed rule and no valid rule are correctly distinguished; exceptions fail **closed** and produce a useful retryable failure.
- Error paths write **zero** enquiries, line items, messages/outbox rows and order data, not merely display an error after a partially persisted record.
- “No rule matches” still yields ₹0 **under the existing documented business rule**. Do not reinterpret no-match as an explicitly configured free-shipping rule or silently change the Founder policy. Test a genuine free-shipping rule separately, and paid shipping.
- Server-priced totals, selected merchant, rule priority/band evaluation, rounding and the snapshot seen by create-order are internally consistent.
- Check how the shipping-rule lookup is called by the public quote and final save; a happy-path test mock must not mask DB failures.

### B2 / N4 — One authoritative quote, explicit re-confirmation

Original issue: browser preview and saved subtotal/shipping could differ; shipping lookup was async with swallowed/stale responses.

Independently prove with rendered tests and traced handlers:

- Before quote load, after quote failure, on stale/out-of-order results, on network retry, and on rapid quantity edits, **no misleading payable** is shown as confirmed and submission is gated properly.
- Browser cannot forge price/subtotal/shipping/total, quote ID, tenant ID or a “confirmed” flag to save a lower amount. Server re-derives from authoritative DB and correct merchant context at save.
- When DB price or shipping rule changes between preview and save, user is shown the actual updated price and must **affirmatively confirm before any enquiry mutation**. Probe repeated and concurrent changes (TOCTOU), double-click, stale confirmation and session mismatch; do not assume returning a new quote automatically means approval.
- Displayed cart subtotal, checkout total, customer message, persisted snapshot, and thank-you page use the **same final server-authoritative result**. Returned result must include authoritative values rather than only enquiry ID.
- Check band boundaries just below/at/above each relevant shipping tier, integer/decimal rounding, zero-price item handling and missing data. Unit tests of pure helpers alone are insufficient proof of user-facing consistency.
- Verify valid older order conversion and vendor-related flows are preserved, while recognizing live E2E is untested.

### B3 — Old saved carts 120 vs cap 99

- Inject legacy `localStorage` cart with quantity 120 and verify **rendered** Cart + Check Availability, stored cart, message, server payload and persisted quantity are all 99.
- Verify hydration immediately normalizes and safely persists, not just calculation-time clamps. Test direct navigation to checkout, page refresh, inconsistent tabs, quantity edits, invalid/negative/decimal quantities, and one normal 1–99 quantity.
- Detect if unsanitized values flash in UI or remain in local storage while being charged differently. Confirm no existing inventory policy changed.

### B4 / N7 — Public shipping quote must not expose other tenants' rules

- Prove the original browser-invocable `calculateShippingCharge(clientId)` service-role action cannot be invoked to fetch raw shipping-rule rows with arbitrary tenant IDs after the fix. Check current exports, Next server action manifest/import surface and any alternate action/API proxy, including indirect aliases.
- Public checkout must still work without shopper login, with server-resolved storefront identity, correct company and public availability/publish gates. Test Store A slug / Store B UUID mismatch; Store A session on Store B route; unknown store; paused store; direct crafted action payload. No arbitrary company UUID may become tenant authority.
- Only necessary public price/quote fields may be returned; no private labels, priorities, raw bands, private company config, secrets or other merchant's internal data. Distinguish legitimate access to Store B's **public price** by visiting Store B from unauthorized cross-tenant internal rule inspection.
- **User-reported UX regression to evaluate:** a browser with a Store A session visiting Store B on the same domain gets refused and reload does not recover. Determine if this is an accidental cross-store boundary/normal shopper journey regression and whether safe recovery exists. Classify blocker only if grounded in the actual allowed storefront UX or causes legitimate checkout failures; otherwise record a clearly scoped follow-up.
- No general tenant/auth rewrite or WP08 build is in scope.

### B5 — Remove private payee identifiers while preserving unsafe-template detection

- Confirm active source/test/fixtures/snapshots/test names/current logs cannot emit actual personal payment number, UPI handle, bank details or other retired identifiers. Run/report only **safe counts/PASS-FAIL**; do not print matched values, and inspect scan scope and false negatives.
- `pnpm quality:privacy` must cover relevant tracked active source and test outputs; inspect implementation to make sure it cannot be bypassed by trivial string splitting or by omitted file types. No secret values in test titles, logs, snapshots or report.
- Validate one-way legacy markers/fingerprints detect all five original unsafe identifiers in a realistic saved template; normalization/casing/spacing/format variants; valid merchant template passes; invalid/placeholder/stale template blocks before enqueue/status mutation; manual send, outbox, retry and re-render flows remain tenant-safe.
- **Security nuance:** unsalted SHA-style fingerprints of short numeric identifiers are **brute-forceable** and do *not* protect a high-secrecy credential. Assess actual confidentiality risk and whether hash constants in public client bundles/logs leak the numbers; verify fingerprints are kept server-only where appropriate. Do not demand a history rewrite or new production secret/migration as a surprise scope expansion.
- Old committed history still contains literals, per user report. Treat **Git history rewrite** as separate explicit Founder approval. Evaluate whether history exposes a live financial secret or only historical personal identifiers and report urgency without printing data or performing rewrites.
- Check default brand fallback and old saved merchant templates so tenant A cannot silently send tenant B's payee. No actual WhatsApp send.

## 3. Cross-cutting regression, evidence and known risks

Review the **whole Wave 0A diff**, not only the five fixes. Specifically inspect:

- No broad API/public storefront change breaking legitimate enquiry submission, vendor query, `createOrderFromEnquiry`, payment statuses or other Mini-Store states; no accidental inventory mutation.
- No bad arithmetic, negative/NaN, stale product prices, integer overflow, duplicate cart rows, empty basket misuse, wrong company/product, service-role escape or cross-tenant disclosure introduced.
- Double-submitted identical enquiry still creates two: determine user harm and whether new quote/confirm logic makes duplicate writes worse; classify with evidence. Do **not** invent a new global dedupe architecture as Wave 0A requirement absent a clear money/tenant blocker.
- Supplier/onboarding/canonical-sync suite failures: user reports **8 at candidate vs 11 at original baseline in the same untouched files**. Independently verify tests and root causes using same environment/commands/fixtures. If not rerun, label `CLAIMED / NOT INDEPENDENTLY VERIFIED`; don't describe the whole suite as passing. Check no new regression even if absolute totals improved.
- Typecheck: reported clean-isolated **53 errors base = 53 candidate**; earlier 87 included generated `.next` types. Verify matching error *signatures*, not counts alone; report generated-types caveat.
- Lint: 0 errors asserted; inspect any warnings. Focused suites: **1,126/1,126 asserted PASS**; verify direct independent rerun when safe, not just the report.
- Worktree incident: temporary worktree removal followed `node_modules` symlink, dependencies were restored via lockfile. Check `git status`, lockfile integrity and test reproducibility. Do not take destructive cleanup actions or infer git source was changed absent evidence.
- Evidence ledger distinguishes static inspection, mock tests, component browser tests, isolated DB tests, live integration and production. Last categories **NOT PROVEN** unless independently executed with proper explicit authority (not authorized here).

## 4. Decision criteria and deliverables

**Use precise severity and no false closure**:
- A `BLOCKER` means reproducible unsafe payment communication, shopper/merchant total mismatch, monetary undercharge on lookup errors, cross-tenant private rule leak, regression preventing normal intended checkout, or a clear new customer/data safety violation.
- A legitimate recorded pre-existing issue can still block Wave 0A if it violates the Wave 0A explicit money/tenant-safety goal; do not defer automatically.
- A deferred risk can be `NONBLOCKING FOLLOW-UP` only with reproducible bounds, owner and rationale. **Do not silently expand scope** into unrelated Wave 0B tasks.

### Output format in chat (read-only; no repo report file)

A. Repo verification: branch, `HEAD`, candidate SHA, worktree clean/dirty, two diffs reviewed, history confirmed. No source edits.

B. Five-blocker closure matrix: **B1/B2/B3/B4/B5** each `PASS`/`REJECT`/`NOT PROVEN` with precise file:line and the tests that matter; state if historical Red-Team rejection is genuinely corrected.

C. **Separate** verdicts: `WP07: PASS | PASS WITH NONBLOCKING FOLLOW-UPS | REJECT`; `WP06: PASS | PASS WITH NONBLOCKING FOLLOW-UPS | REJECT`.

D. Findings ordered by severity with `CONFIRMED`/`RISK`/`NOT PROVEN`, trigger, exact file:line, affected user, minimal fix/test or rationally scoped follow-up. Address the Store A/Store B session refusal, privacy fingerprint strength, duplicate-submit and nonmatch free shipping explicitly.

E. Safe test ledger: commands, passed/failed counts and failing paths; distinguish baseline failures from candidate regressions and clarify `53` versus `.next` errors.

F. Remaining evidence gaps: realistic browser checkout, isolated real DB shipping lookup and actual WhatsApp (not authorized); ensure local candidate acceptance does not masquerade as production readiness.

G. Exactly one of:

- **`CODEX APPROVED — WAVE 0A READY FOR FOUNDER CLOSE`** (both WP07 and WP06 acceptable locally, no blocking issues); or
- **`CODEX REJECTED — WAVE 0A REMAINS OPEN`** (at least one verified material blocker; provide minimal test-first builder fix-forward handoff).

**STOP after the independent review.** Do not implement, commit, start Wave 0B, release or request production access. Founder separately controls Wave 0A closure and all future waves / deployment.