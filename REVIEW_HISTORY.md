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


---

## 2026-11-16 continuity update — Waves 3–6 and security independent gates
**This dated addendum supersedes the older "Wave 0A active" headline above for CURRENT status, but preserves original R1/R2/Wave 0A history.** Exact Wave 0A third Codex outcome and W0B–2 review SHAs are not in currently provided records; acquire full local ledgers before asserting details. Full comprehensive ledger: [2026 Nov 8–16 delta](evidence/2026_11_16_FULL_DELTA.md).

### Wave 3 / Wave 4 intermediate reported acceptance
- Wave 3 Codex-accepted reported SHA `4cae4ada7731ebc302a6468aa153479a6e7c9d16` (WP05/WP17/WP18). Actual report not stored here.
- Wave 4 Codex R2-accepted reported SHA `1b2695e5fd6d44ac96f992ce4733a1792314709f` (WP22/WP23 Growth/Ask AI Shopify/Wix). Actual report not stored here.

### Wave 5 (WP15/16/19) independent Codex history
- **R1 REJECTED** SHA `a4c5374c6ee9937888d68e02586e9fed5ea774dd`: B1 privacy triage audit atomicity; B2 Shopify duplicate blog draft; B3 Staff Shipping Settings nav 404.
- **R2 REJECTED** SHA `c3b605d260d58f8b412e1436b2711a58315174a5`: B1/B3 CLOSED; B2-R2 ambiguous persisted Shopify create + 503 + temporarily empty read-back caused second create; B2-R2b uncertain claim could stick after later positive reconciliation.
- **R3 ACCEPTED** independently exact SHA `ce811b2a3f19307e1f68f3e96e67d601cc92b3bb`; all prior findings CLOSED. Codex reproduced/verified migration 478 22/22, integrated Shopify claim E2E 17/17, regressions 174/174; independent fresh build limited by isolated font dependency, exact-SHA supplied build evidence accepted; live Shopify unproven. Founder-provided Codex report local (see evidence index).

### Wave 6 (WP20) independent review
- **R1 REJECTED** exact SHA `db1bed9f81f82275f7257adbab976b3b5e92f332`. Codex reproduced cross-tenant provider/order link SEC-8c, newly confirmed Staff `operate` supplemental vendor WhatsApp manual initiation untested by RT-06, SEC-2 finance retained-data guard gap, nine FAIL matrix rows, no live J1–J11, verify-pins and migration-333 red. Independent 1,183 focused PASS assertions, 411 migration chain and more. Wave 6 R2 not prepared/accepted on a final integrated SHA.
- 83 local/simulated PASS, 9 FAIL, 1 deferred, 4 NOT PROVEN, 13 external; no live-provider launch-PASS. Decisive Founder defer: MS-10 abandoned-cart worker `PP3-BL-01`; WA-02 existing behavior unchanged, configure Delhivery later; Staff convenience changes not authorized, but **real security bypass cannot be waived**.

### SEC-8c migration 474
- Red-Team R1 initially rejected late-created/deleted-recreated links and dual-write races; R2 internal approved `6dabf8aadc1e509a1800bf00ebecb892391b18df`.
- **Independent Codex R1 REJECTED** that SHA; two CONFIRMED blockers: alternate REPEATABLE READ snapshot race and migration preflight/trigger-installation writer race, even with 16/16 PostgreSQL passing tests.
- Founder local-only narrow fix-forward approved: restrict protected writes to READ COMMITTED (reject RR/SERIALIZABLE, SQLSTATE 55000), lock both tables against writes before migration preflight, atomic 474/rollback transaction and tests 474q–474v.
- **R2 candidate `036da7b2b8020e87ff41663d8aa18e42f6000b56`: Claude tests 23/23 and Red-Team APPROVED; independent Codex R2 PENDING.** No claim of closure. Production preflight/release not approved.

### SEC-2 / CR-6 migration 479
- First local `b34b81d0` Red-Team R1 REJECTED F1 identity/company-change deletion bypass; F2 concurrent payment/RTD protection-mark omission; N1 unsafe silent no-op in migration 319 compatibility. Founder authorized focused local remediation.
- **Internal Red-Team R2 APPROVED** `748d292d`, claimed F1/F2/N1 fixed and native checks pass. **Codex NOT YET RUN and held** because candidate descends from independently rejected SEC8c `6dabf8aa`; after SEC8c R2 approval merge accepted base forward (no rebase), new SHA + tests/Red-Team, then Codex.
- No finance-risk waiver, no production migration authority.

### Future required gate
Separate SEC-8c R2 independent Codex → integrated SEC-2 Codex → targeted Staff security fix/integration Wave 6 R2 Codex → final integrated Pre-P3 Codex → external/staging/live proof, pins, release governance and separate Founder production permission. **No code push/deploy/prod action through this documentation update.**


---

## 2026-11-16 — SEC-8c Codex R2 independently ACCEPTED (latest outcome)
**Provenance:** Founder pasted independent Codex result in ChatGPT; Mac-local report itself was not fetched by this repository update.
- Exact accepted code SHA: `036da7b2b8020e87ff41663d8aa18e42f6000b56`; tag `sec8c-474-candidate-036da7b2`.
- Previous rejected SHA `6dabf8aadc1e509a1800bf00ebecb892391b18df` remains preserved. R1 B1 REPEATABLE READ concurrency bypass **CLOSED**; R1 B2 migration preflight/installation race **CLOSED**; fail-before tests reproduced on rejected candidate.
- Codex results: SEC-8c 23/23; dependent migration 475 8/8, 477 9/9, 478 22/22; canonical migration chain 412/412; matched fingerprint; no new candidate-level blockers.
- Codex report on user Mac `/tmp/CODEX_SEC8C_474_R2_INDEPENDENT_REVIEW_036da7b2_2026-11-16.md`, reported SHA-256 `b2613c441b4e1936905cd797acb26e9d16cb877275b845827347bcc561cf5ce0`; original file bytes not in continuity repo.
- Acceptance does NOT authorize production. 139 verify-pins refusals, read-only production existing-data preflight, controlled migration window and production apply remain pending.
- **New next gate:** Merge accepted SEC-8c forward into SEC-2 `pre-p3/sec-2-479` without rebasing/history loss, rerun 474/479 integrated tests/Red-Team, freeze NEW SHA and run separate SEC-2 Codex. Old SEC-2 `748d292d` only internally approved, NOT Codex-accepted. Wave 6 R1 remains REJECTED and the Staff supplemental WhatsApp privilege issue remains OPEN.


---

## 2026-11-16 cross-chat continuity audit — recovered Wave 0–2 checkpoints
**Evidence class:** Earlier-chat/user-reported independent Codex verdicts, cross-checked against locally available historical planning/audit files; original COMPLETE final Codex report bytes for these waves are **not archived** in this repository. Do not promote a review **mandate** into a reviewer verdict.

- **Wave 0A WP06/WP07**, final code `ab74f11459e1efdab62464fd4d7614b1132203eb` — earlier user turn reported **Codex APPROVED** for both WPs and Wave 0A. However the 2026-11-08 continuity audit examined an incomplete pasted report ending before full WP06 and overall conclusion; label **REPORTED APPROVED / full original source missing** until original report is archived. Preserve first two R1/R2 rejections above.
- **Wave 0B** early candidate `616c91bb23a77cc69be9f79ceab2bf8d17f465dd` — independent Codex reportedly **APPROVED FOR IMPLEMENTED SCOPE**; WP12/WP14 approved; WP08/WP16 partial; **NOT whole-wave complete at that early SHA**. Later WP08 code `d46a50427078725225164c517f09e92d66bc60e7` reported independently Codex-approved; separate migration-453 schema/artifact and release pins governance followed.
- **Wave 0 consolidated** reported independent Codex **APPROVED** final `175327c520c1dbad1dbaeb5b5612c26cb32a961f`; this exact SHA appears as "approved Wave 0 base" in Nov 9 Wave 1 Codex review **mandate**. Local engineering acceptance only; WP16 audit-only deferral and production gates remain separately tracked; original Codex verdict report missing here.
- **Wave 1** WP01/WP02/WP03/WP04/WP21 reported independent Codex **APPROVED** at `1848756e2a8de56cc761ad39376f43fd0806c066`. The Nov 13 Wave 2 independent gap audit explicitly identifies that exact SHA as frozen Wave 1 base. An earlier `b3594720df9a9dc226413def224d1954ede50839` appears in a review mandate, **not** proven final accepted candidate; original Wave 1 final verdict report not stored here.
- **Wave 2** WP09/WP10/WP11/WP13/WP19 reported independent Codex R2 **APPROVED** at `4598b4220d61a264dfba728d64fffaddbc8de115`, as explicitly named by Nov 14 Wave 3/4 execution-plan document. An independent Nov 13 *static gap audit* of a prior builder SHA had 27 shipping/WhatsApp issues; this was a preliminary audit, **NOT Wave 2 final verdict**. Actual Wave 2 R2 original report not stored.
- **Wave 3 and Wave 4** accepted exact SHAs are already recorded in Nov 16 addendum; their detailed V3.0 execution contracts and original Codex reports also not stored.
- The complete gap inventory and source provenance are at [CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md). These recovered history entries do **not** change latest Wave 5 ACCEPTED, Wave 6 REJECTED, SEC-8c R2 ACCEPTED, SEC-2 pending integration, or release HOLD.


## 2026-11-16 — SEC-2 accepted-base forward integration (Founder/Claude-reported; Codex PENDING)
- **New integrated exact code SHA:** `2298446b8f16246cd39daf1cbfccaa2dfde0692f`, tag `sec2-479-candidate-2298446b`. Founder relays that this is a **forward merge** of old SEC-2 `748d292d` and independently Codex-accepted SEC-8c `036da7b2b8020e87ff41663d8aa18e42f6000b56`, without rebase or history rewrite. Mac-local branch/code not fetched by this public continuity repository.
- **Reported migration provenance:** 474 and 479 migrations and their tests byte-identical to respective pre-merge candidates; only manifest and schema fingerprint had merge conflicts. This is a claim for independent Codex to verify against exact parents, not a fresh independent Git diff.
- **Reported local results:** SEC-2 27/27; SEC-8c 23/23 incl two-session races; security 8/8; 413 native forward migrations; 475/477/478 8/8, 9/9, 22/22; older 365/367, 319, bundle15/16 all pass; app 49/49; E2E 216/217, with the one expected-red D-MS10-2 explicitly deferred `PP3-BL-01`; manifest/type/lint/privacy/diff pass. Inherited `company_privacy_348` and release `verify-pins` remain red; do not treat as accepted or waive. First E2E attempt invalid because test DB stopped prematurely; valid rerun 216/217.
- **Internal Red-Team:** APPROVE reported, no blocking finding; notes same-order 474/479 locks, compatible transaction mode, either rollback order, rare conflicts cleanly error. **Manual combined rollback only**; permanent combined rollback regression test suggested but not implemented. Codex must decide gate impact from source and real DB proof, without inventing scope or softening tests.
- **Current review packet:** `~/Downloads/BHARAT_LAUNCHPAD_WAVE_6_QA/SEC2_CR6/SEC2_479_CODEX_PACKET_INTEGRATED.md`. Old packet for `748d292d` is superseded. No independent Codex verdict yet. No push, production DB, deployment, migration or provider execution reported.
- **NEXT:** Founder manually runs independent READ-ONLY Codex on exact `2298446b8f16246cd39daf1cbfccaa2dfde0692f` and new packet. Reviewer independently verifies merge parents/bytes, SEC-2 F1/F2/N1 and finance-history deletion/concurrency/rollback safeguards, 474/479 combined guarantees, test provenance and unchanged inherited reds. Return ACCEPTED/REJECTED and exact evidence. **STOP**; no Staff/Wave 6 expansion until separate authorized next gate. Wave 6 R1 remains REJECTED; Staff supplemental vendor WhatsApp authorization bug OPEN; production Pre-P3 HOLD.


## 2026-11-16 — SEC-2 integrated independent Codex ACCEPTED (Founder-provided result)
- **Exact accepted application SHA:** `2298446b8f16246cd39daf1cbfccaa2dfde0692f`; tag `sec2-479-candidate-2298446b`; forward merge from old SEC-2 `748d292d` and accepted SEC-8c `036da7b2`. Founder relays independent Codex verified merge parents/tag, clean repository, disposable PostgreSQL stopped.
- **Independent Codex verdict: `SEC-2 INTEGRATED: CODEX ACCEPTED`**, specifically this immutable SHA. Report on Founder Mac: `/tmp/CODEX_SEC2_479_INTEGRATED_REVIEW_2298446b_2026-11-16.md`; Founder-reported SHA-256 `ea3fb70fe859ec18a08ab4b6a51e967cd0062058a481fb619f3597a869eade39`. **Original bytes were not accessible to this documentation update.** Copy report from transient /tmp to preserved private evidence if needed.
- Reported Codex evidence: SEC-2 27/27; SEC-8c 23/23; exactly seven added F1/F2/N1 tests fail-before on rejected SHA; combined rollback both directions PASS with fingerprint restored; native canonical chain 413/413; app security 49/49. Deferred D-MS10-2 remains explicitly red, NOT PASS. `company_privacy_348` / privacy and release-pin failures remain open release-only gates, not waived.
- **Next authorized review stage:** scoped Staff supplemental vendor WhatsApp authorization security remediation (confirmed Wave 6 Codex R1 vulnerability), test-first, preserve existing Owner/Admin messaging and mature vendor workflows, no additional Staff feature redesign. Claude local fix + independent Red-Team → fresh immutable SHA → Founder manual independent Codex → Wave 6 R2 integrated candidate/full matrix. Do not assume this SEC-2 verdict approves Wave 6 or production.
- **No production permission:** no production DB access/migration, provider sends/writes, release pin, flag, signed release, deployment or go-live authorization from this verdict. Wave 6 R1 at `db1bed9f` remains REJECTED until new integrated R2 review.


## 2026-11-16 — Wave 6 R2 NON-STAFF independent Codex ACCEPTED (Founder-provided)
- **Immutable reviewed application SHA:** `7cf95386f44527fdf9835b0e6329805cdee8eca0`, branch `pre-p3/wave-6-r2`, tag `w6-r2-candidate-7cf95386`; base accepted integrated SEC-2 `2298446b8f16246cd39daf1cbfccaa2dfde0692f`. Founder relays independent review completed and clean repository; disposable PostgreSQL stopped. No production changes authorized or reported.
- **Verbatim reported verdict:** `WAVE 6 R2 NON-STAFF CANDIDATE: CODEX ACCEPTED`. Local report `/tmp/CODEX_WAVE6_R2_INDEPENDENT_REVIEW_7cf95386_2026-11-16.md`; reported SHA-256 `891eef01be7c0228427de4538103a7794e2e84c8c9355b6888128111130f6880`. Mac-local report bytes NOT accessible through public docs, so no independently claimed report-text/hash verification.
- Claude's prior R2 candidate report (not independently reproduced by this continuity update) stated 15,936 Vitest PASS / 0 FAIL, `test:pre-p3` PASS with expected-red OT-11, E2E 216/217 due deferred D-MS10-2, DB/migration/build/type/lint/privacy gates pass. Reported revised 110-row matrix: 88 local PASS, 4 FAIL (`RT-06` Staff authorization, `OT-11` Founder ruling, `RG-05` and `RG-06` release pins), 1 DEFERRED, 4 NOT PROVEN, 13 EXTERNALLY BLOCKED. This matrix remains subject to actual original Codex report scope and evidence limitations; no live J1–J11 launch-PASS.
- Founder explicitly directs **Staff existing roles/permissions/module UNTOUCHED for now**, while confirmed supplemental vendor WhatsApp initiation authorization vulnerability remains OPEN/NOT WAIVED. OT-11 and CR-7 Prepaid label final wording require actual evidence/Founder decision; do not invent either. Migration333 rollback/repin, SEC5 prod preflight, migrations454–479, SEC8c prod link count, SEC2 prod window, staging, live Shopify/Wix/Delhivery/WhatsApp proof, privacy/release pins and final integrated review remain open approval/release gates.
- **Status distinction:** independent Codex ACCEPTED *non-Staff scoped candidate at exact SHA*, NOT full Wave6 closure, NOT Pre-P3 release authorization, NOT Staff security acceptance. Preserve Wave6 R1 rejection and historical SHAs. No automatic next development assignment or production action.


## 2026-11-23 — Orzik Shopify independent release + Stage2 security review
- **Stage1** production controlled dark release (separate from Pre-P3): signed apply 480/481/483/484 at DB prefix 95/95, verified by second signed status; independent Claude post-migration audit PASS, 10 linked companies owner parity 0; production app SHA **e6e05f99e46872debfbab254ffb31d3fa6c73fa5** fast-forward to GitHub main, Vercel **dpl_2pmJ3bgTn1GXwnoXjqpoeT3yGFuU** READY with non-destructive smoke PASS. Founder **STAGE1 CLOSED — DARK**. Migration 482 remains deferred.
- **S2-A allow-list candidate** exact SHA **d48a2d8cc1092077f320d707de8a0d6a90a61620**, parent e6e05f99, clean local worktree. Founder-supplied **original independent Codex review** stated **CODEX_S2A_APPROVED**: 0 P0, 0 P1, 1 P2 (~10-minute stale company membership authorization in callback), 2 P3 (direct denied resolver side-effect test; shop label length validation). 16/16 security checks PASS; 16,095 tests passed, 10 skipped, zero failures; 53 unchanged preexisting tsc source errors. Codex did not rerun build. Original report private file 19a_CODEX_REPORT_S2A_original.txt, SHA256 7c24f80a4d96a4dc8ffcdb0ead6e06aa147a95257050579b859a4b1c2c815834. **Not a deployment approval**.
- **S2-A2** locally approved *scope only*: legacy install-flow flag change candidate + callback membership revalidation + P3 remediations. Builder running at latest report; NO exact SHA, NO completed Red-Team or Codex verdict. Shopify S2-2 deploy HOLD due IP allowlist and installation model; both security issues unproven resolved.
- **S2-1** CLI + Shopify account read-only app identity PASS at org 249330912/app 450606792705, store orzik-qa.myshopify.com browser-confirmed; no Shopify config or production mutations.
- Existing prior Wave6/SEC rejected candidates are **not** reclassified by Orzik release. For complete evidence attribution and all IDs see [Orzik A-to-Z](evidence/ORZIK_SHOPIFY_A_TO_Z_CONTINUITY_2026_11_23.md).
