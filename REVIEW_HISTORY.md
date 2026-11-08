# Decision and Review History — audit trail
Last reconciled 2026-11-08. Each entry describes **reported review results**, not a newly performed independent code audit by ChatGPT.

## Pre-P3 planning before code execution
- Reconciled product scope from multiple Founder sessions/audits through V10.4.
- Founder decisions emphasize one unified operating system, retained mature customer paths, no hidden stock mutations, Wix↔Shopify Growth/Ask AI READ and approval-gated WRITE parity, per-merchant messaging, Admin and privacy/security controls, UI/UX and safe cleanup.
- 23 work packages, 11 end-to-end merchant journeys, 210 unique Founder decisions, 506 capability index entries and a historical wireframe gallery (172 screen IDs; 727 states). **Counts describe documentation, not completed feature PASS.**
- Inventory Point 3: retired Admin Product Sales `notify-vendor` and `notify-vendor-product-sales` APIs hard-set `current_stock=5` on legacy tables. Current vendor notification uses separate flows. Founder discussion **CLOSED**, implementation later in safe cleanup. Preserve historical tables.
- Approved controlled **local** development beginning Wave 0A, but no push/merge/deploy/production approval.

## Wave 0A — WP07 / WP06
### Initial candidate `33286ffd85b515aee6955bf54cbce201d35e997d` — Codex REJECTED
- Local branch `pre-p3/v10-4-wave-0a-safety`; base `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`. Internal Red-Team approved after WP06 corrected a 120-vs-99 quantity mismatch.
- Independent Codex confirmed **5 blocking issues**: shipping-rule DB failures accepted as ₹0 shipping; preview/customer message disagreed with persisted total; old cart display 120 vs persisted 99; arbitrary tenant shipping-rule read via exported server action; legacy personal payment identifiers remained in source/test output.
- WP07 REJECT / WP06 REJECT. Original internal result 958/958 did not prove blocker closure.

### Fix-forward candidate `e85b8a3481cbd790325977001228f2fe138329fe` — Codex REJECTED again
- Claude reported all previous blockers fixed; internal Red-Team approved; targeted 1,126/1,126.
- Codex: B1 shipping errors PASS with nonresponse evidence gap; B3 120→99 PASS; B5 private payee removal PASS with nonblocking follow-ups; B2 authoritative quote REJECT; B4 tenant boundary REJECT.
- **Four confirmed blockers**:
  1. Store A session cookie used on Store B could update Store A visitor PII before the later guard rejects Store B enquiry.
  2. Quote silently filtered removed/hidden/foreign/unlinked basket items and displayed partial or ₹0 totals.
  3. Two protected existing tenant-isolation tests regressed from 38/38 baseline to 36/38 because tests lacked new required `clientSlug` setup.
  4. `git diff --check` failed on extra blank EOF line despite 0 ESLint errors.
- WP07 PASS WITH NONBLOCKING FOLLOW-UPS, WP06 REJECT, Wave 0A OPEN. Full suite showed 13 failures (including 2 actual protected-test regressions).

### Latest candidate `ab74f11459e1efdab62464fd4d7614b1132203eb` — internal Red-Team APPROVED, Codex #3 PENDING
- Claude reports fixes: store-scoped visitor lookup and recovery on cross-store cookies; fail-closed all-item quote/save with unavailable-item removal UI; protected original security tests 38/38; whitespace gate clean; shipping nonresponse timeout 8 sec.
- Reported 1,265/1,265 focused PASS, full-suite baseline-equivalent 11 failures, 53/53 type diagnostics, privacy scan PASS.
- Report commit `a9c8db14`, docs-only; local branch only, worktree clean.
- **Do not mark WP06 or Wave 0A PASS until independent Codex evidence arrives.**

## Deferred/not silently resolved
- Double-submit idempotency, historical payee strings in Git history, low-entropy fingerprints, two unused unscoped visitor helpers, actual E2E DB/cookies/provider confirmation.
- WP07 also changes Bharat Karigar's own payment_pending messaging until its company saves a template: accepted safety trade-off.
- No approved rewrite/cleanup of Git history or live tenant migrations.
