# Non-negotiable operating rules — Bharat Launchpad
## Founder governance
- Approved Founder Registry V10.4 controls product behavior. Never reinterpret decisions from an audit's suggestion. New Founder decisions require explicit user intent and an auditable addendum.
- No repeatedly asking answered questions; search registry/evidence first.
- Preserve existing mature Shopify/Wix, Mini-Store, fulfilment, vendor, WhatsApp and Growth functions; fix broken connections and unsafe paths, not arbitrary rewrites. **Product Onboarding Q17 correction:** existing in-module AI description/color/price helpers are already working and MUST be preserved; product decision round 20/20 resolved. Do not remove/move those helpers as 'new optional AI' merely to consolidate into Growth/Ask AI. See dated P2→Pre-P3 bridge.
- Inventory: no automatic numerical stock decrement/restore from Launchpad order Confirm/Cancel; provider-owned stock; manual explicitly Owner-approved, audited provider inventory edits through Growth allowed.
- Only Shopify OR Wix as external primary store per company, optional Mini-Store. Reject second external store explicitly.
- **Historical rule (Nov 8):** WP07/WP06 Wave 0A was the only active scope then. **Superseded for active status** by later Founder-authorized Wave 3–6 execution, limited Wave 6 provisional QA sequencing exception and narrowly approved SEC-8c/SEC-2 local remediation (see CURRENT_STATE and dated full delta). Independent review and Founder go-live gates are NOT waived.
- No unauthorised production DB, migrations, flags, provider write, webhook replay, WhatsApp send, customer email, deploy, merge or release actions.

## Evidence and review
Use explicit labels: **FOUNDER LOCKED**, **TOOL/REPO VERIFIED**, **CODEX REPORTED**, **CLAUDE REPORTED**, **USER REPORTED**, **STATIC CODE-OBSERVED**, **NOT PROVEN**, **SUPERSEDED**.
- Never claim live end-to-end PASS because mocks pass, or treat historical wireframes as actual current UI.
- Codex REJECT means the wave is OPEN until new exact candidate independently passes. Keep rejected SHAs / rejections in review history.
- Maintain review/acceptance gates: failing-before adversarial tests, minimum safe fixes, full relevant regression, independent Red-Team, Codex, Founder sign-off.
- Preserve exact candidate SHA and separately identify docs-only report HEAD, merge/release SHA, baseline SHA.
- A new chat should verify present GitHub repo status via connected tool. Development worktree on user Mac cannot be inspected from this repo unless newly pushed/uploaded.
- Site/API financial or tenant-isolation risks cannot be waved away merely because they predate this wave. Record severity and gate impact.

## Security and information minimization
- Never commit secrets, API keys, credentials, personal bank/UPI identifiers, raw customer messages, production PII or sensitive raw logs.
- Public visibility of this repo was observed at setup; it may change. Treat it as **public-readable unless verified private**. Historical Git commits remain recoverable.
- Sanitized audit summaries are fine. Source code security findings can be documented without reproducing credentials.
- GitHub direct writes are permitted **to this continuity documentation repository** for maintaining project memory, but not to the application repository unless explicitly separately authorized.
- Before mutating GitHub docs: read current latest content and avoid overwriting concurrent changes, retain provenance and meaningful commit messages; don't erase history.
- This is a user-triggered/in-chat update discipline, **not an autonomous daemon**.
