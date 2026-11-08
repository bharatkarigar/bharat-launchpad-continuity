# Pre-P3 Wave 0A — WP07 + WP06 Implementation Report

**Status:** READY_FOR_CODEX_FINAL_REVIEW. This is a local candidate only. Nothing has been pushed, merged or deployed, and there were no production, DB, env, flag, cron, provider or WhatsApp actions.

## Identity
| Item | Value |
|---|---|
| Worktree | `/Users/harshvidyarthi/Desktop/lp-final-int` |
| Branch | `pre-p3/v10-4-wave-0a-safety` (local; created from clean base) |
| Base SHA | `5bc0e1b302be55a22046e6d3335ddc60b558f4bd` (pre-p3/final-integration, clean, porcelain 0) |
| Code candidate SHA | `33286ffd85b515aee6955bf54cbce201d35e997d` |
| Commits | `8af111e6` WP07 · `7e98a455` WP07 fix-forward · `0b0d6534` WP06 (internal red-team REJECTED) · `33286ffd` WP06 fix-forward (cycle 1) · plus this docs-only report commit |
| History | Fix-forward only. No amend, rebase or squash. The rejected candidate is preserved. |
| Models | Builder: `launchpad-builder` (Sonnet/medium per agent definition). Red-Team: `launchpad-red-team` (Opus/high per agent definition). Both are as configured; neither was overridden per invocation. |

## WP07: tenant-specific payment communication
**Root cause:**
- `lib/mini-store-status-messages.ts` hard-coded the platform owner's personal GPay, PhonePe and Paytm number, UPI ID and bank account/IFSC in the built-in `payment_pending` text, and signed every built-in message "Bharat Karigar".
- The outbox resolver used this text as the fallback for any tenant without its own template.
- `lib/mini-store-templates.ts` editor defaults contained the same payee details.
- No per-company payee configuration exists in code.

**Fix:**
- **Built-in text:** it now contains no payee details and no platform brand, and it signs with the sending company's own brand.
- **`payment_pending`:**
  - It now requires the company's OWN saved template.
  - A template is treated as not configured if it is missing, if it still contains the placeholder, or if it contains any legacy payee marker (case-insensitive).
  - When not configured, the send-time resolver returns `payment_details_not_configured` and the outbox skips the message. It never falls back to other text.
  - When not configured, the manual send refuses BEFORE any Staff claim, enqueue or status change, with an honest "set up your Payment Pending message" error.
  - A lookup error returns the retryable `lookup_failed`, with bounded retries.
- **Editor defaults:** they are now neutral, and the payment default is a placeholder.

## WP06: Mini-Store server-authoritative money
**Root cause:** `saveEnquiry` (`app/actions/mini-store.ts`) persisted the browser-supplied subtotal, shipping charge, rule id and rule snapshot without bounds. It is the only writer of enquiry money, and order creation later reads `shipping_charge`.

**Fix:**
- **Browser money ignored:** the browser money fields are accepted as `unknown` and never persisted.
- **Server amounts:** the server computes:
  - subtotal = Σ DB `selling_price` (null or ≤0 counts as 0) × quantity, rounded to 2 dp;
  - shipping = the existing `calculateShippingCharge` for the visitor's own company, only when subtotal > 0 (this mirrors the existing browser rule; no new fees);
  - grand_total = round2(subtotal + shipping).
- **Quantity cap:** one shared quantity cap (99) is used by Cart, the add-to-cart path, Checkout totals, the message and submission, and the server schema. What the customer sees is exactly what is persisted.
- **Missing selected items:** they are now looked up even when the DB cart is non-empty, with tenant, visible and purchasable filters.
- **Row limit:** more than 100 rows is refused cleanly.

## Changed files (15 code/test + this report)
- **WP07:**
  - `lib/mini-store-status-messages.ts`
  - `lib/mini-store-templates.ts`
  - `lib/messaging/outbox-enquiry.ts`
  - `app/actions/client-mini-store.ts` (`sendMiniStoreManualStatusMessage` pre-check only)
- **WP06:**
  - `app/actions/mini-store.ts`
  - `lib/mini-store-limits.ts` (new)
  - `components/client/mini-store/CartPage.tsx`
  - `components/client/mini-store/CheckAvailabilityPage.tsx`
  - `components/client/mini-store/MiniStoreStack.tsx`
  - `app/store/[clientSlug]/check-availability/page.tsx` (type only)
- **Tests:**
  - `lib/messaging/outbox-enquiry-payment.action-test.ts` (new)
  - `app/actions/mini-store-enquiry-outbox.action-test.ts`
  - `lib/mini-store-templates.logic-test.ts`
  - `app/actions/mini-store-save-enquiry-money.action-test.ts` (new)
  - `lib/mini-store-limits.logic-test.ts` (new)
- **Not touched:** migrations, `scripts/`, `supabase/`, env, `vercel.json`, middleware, cron, provider or auth config.

## Test ledger (Node 22, vitest, all provider/DB mocked; orchestrator re-ran these)
| Case | Result |
|---|---|
| Base baseline: outbox-enquiry + enquiry-outbox + templates tests | PASS 46/46 (pre-change) |
| WP07 new tests failing before the fix (builder ran them with the source stashed) | 15 FAIL of 37 → after the fix 37/37 PASS |
| WP07 fix-forward: per-marker checks; lookup error → `lookup_failed` | PASS. A separate failing-before run was not captured. |
| WP06 new tests before the fix | 8/8 FAIL → after the fix PASS |
| WP06 cycle-1 (missing selected items, bad money values, row limit) before the fix | 3 FAIL → after the fix PASS. The cap-agreement logic test has no failing-before run because it was written together with the new lib. |
| `npx vitest run lib/messaging app/actions/mini-store lib/mini-store components/client/mini-store` at 33286ffd | **PASS 43 files / 958 tests** |
| `npx tsc --noEmit` | 87 errors at both base and candidate. All are pre-existing and none are in new code. |
| eslint on changed files | 0 errors, 30 warnings |
| React component rendering of the cap wiring | NOT PROVEN (proven via the shared helper plus diff review) |
| Real DB shipping-rule query / real E2E checkout / real WhatsApp send | NOT RUN (no isolated DB proven; production intentionally untouched) |

## Preserved-flow proof
- **Statuses other than Payment Pending:** Follow Up, Final Invoice, Close Query and Payment Received still resolve and send. They use the merchant template, or the neutral company-branded built-in text. (Tested.)
- **Tenant A:** with its own payment template, it still sends its own text, correctly scoped. (Tested.)
- **Enquiry flow:** creation, vendor-query rows, cart-abandon flag, and the downstream order creation and modal readers are unchanged. Order creation code was not modified.
- **Not exercised end to end:** vendor notifications (Step 4 and Mini-Store vendor query) and historical data were not changed. Their end-to-end behaviour is NOT PROVEN beyond the regression suite.

## Internal Red-Team
| Candidate | Result |
|---|---|
| WP07 8af111e6 | **APPROVE** (low observations: two of them were fixed in 7e98a455) |
| WP06 0b0d6534 | **REJECT** (B1: a quantity above 99 was clamped server-side while the customer saw the unclamped payable) |
| WP06 33286ffd | **APPROVE** |

## Known residual risks / follow-up (not in Wave 0A)
1. **Saved "Bharat Karigar" sign-off:** existing saved `manual_status_*` templates (other than payment) may still contain this sign-off as stored merchant data. A read-only production count is recommended.
2. **Brand-name fallbacks:** "Bharat Karigar" is still a brand-name fallback (no payee details) in `lib/messaging/outbox-template-resolver.ts:107`, `lib/whatsapp/default-templates.ts:235` and the `send-to-customer` route:79.
3. **Payment Pending preview:** it shows the placeholder, not the merchant's saved template. The block is only discovered when the merchant clicks Send (UX).
4. **Shipping lookup error:** a DB error during the shipping-rule lookup stores ₹0 shipping (N3). The price-band edge can also differ between the preview and the stored amount (N4).
5. **`calculateShippingCharge` (pre-existing, N7):** it is an exported server action with no auth and accepts any client id, so another company's shipping rules can be read. This is WP14/WP17-class follow-up work.
6. **No double-submit protection:** `saveEnquiry` has no idempotency guard (pre-existing). A double submit gives two enquiries with identical server amounts.
7. **Old carts:** a browser cart with a stored quantity above 99 displays the raw number until edited. The totals and submission are clamped.
8. **Empty enquiry:** an enquiry with zero products is possible when every selected item is invalid but the DB cart has a row (pre-existing, narrower now).
9. **Behaviour change visible to Bharat Karigar's own company:** the Payment Pending message is now blocked until the company saves its own payment template. This is the intended safety rule (registry RT-03).

## Codex review packet
- **Task:** Pre-P3 Wave 0A, WP07 (tenant payment messages) + WP06 (server-authoritative Mini-Store money).
- **Repo and SHAs:** repo `/Users/harshvidyarthi/Desktop/lp-final-int`, branch `pre-p3/v10-4-wave-0a-safety`, base `5bc0e1b302be55a22046e6d3335ddc60b558f4bd`, code candidate `33286ffd85b515aee6955bf54cbce201d35e997d`. The report commit is docs-only; its SHA is given in the handoff message.
- **Review command:** `git diff 5bc0e1b3..33286ffd`
- **Previously accepted areas:** do not reopen them without new evidence.
- **Out of scope:** WP08, WP12, WP14, WP16, WP01–05, inventory policy and vendor notification paths are for later waves.