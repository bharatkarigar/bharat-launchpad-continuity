# Evidence and document map — V10.4
**Last reconciled:** 2026-11-08. **Documentation repo, NOT the SaaS code repo.**

## Canonical (latest Founder planning baseline)
- [Founder Decisions V10.4](canonical/FOUNDER_DECISIONS_V10_4.md): 210 distinct decision headers; authoritative product requirements.
- [Pre-P3 Scope V10.4](canonical/PRE_P3_SCOPE_V10_4.md): full functional/UI/UX, Admin, cleanup and acceptance scope.
- [Pre-P3 Implementation Master Plan V10.4](canonical/PRE_P3_MASTER_PLAN_V10_4.md): 23 WPs, stage dependencies, 11 merchant acceptance journeys.
- [Execution Roadmap](canonical/EXECUTION_ROADMAP_V10_4.md): suggested wave sequencing; not a proof of completed work.
- [CURRENT_STATE](CURRENT_STATE.md): **current checkpoint overrides earlier planning-only status**.

## Original/historical evidence stored here
- [WP07/WP06 initial implementation report](evidence/PRE_P3_WAVE_0A_INITIAL_REPORT_33286ffd.md), exact original uploaded report text; candidate subsequently Codex REJECTED.
- [Point 3 retired Product Sales notification audit](evidence/PRE_P3_POINT3_VENDOR_NOTIFICATION_AUDIT_5bc0e1b3.md): **reconstructed concise summary** of user-provided audit; original local full report not in this repo (Files attachment was access-unavailable).
- [Wix-to-Shopify Growth 29-capability matrix](evidence/WIX_SHOPIFY_GROWTH_PARITY_29_CAPABILITIES_5bc0e1b3.md), historical static evidence; product rule updated in V10.4.
- [Wave 0A Claude/Codex review mandates](review-mandates/): complete task instructions and review checklists for original candidate, first and second rejections and third review. **A mandate is NOT the resulting verdict.**
- [Original deep context (October 11)](archive/HISTORICAL_CONTEXT_2026_10_11.md) and [P2 planning audit continuity](archive/P2_PLANNING_AUDIT_CONTINUITY.md): long-form historical project reconstruction.
- [Sanitized P2 full-chat continuity (November 7)](archive/P2_CHAT_CONTINUITY_2026_11_07_SANITIZED.md): **historical**, possible key-like literal redacted on upload; not current authority.
- [REVIEW_HISTORY](REVIEW_HISTORY.md): accurate digest of Codex #1 and #2 rejection outcomes supplied in conversation, with current candidate #3 pending.

## Not stored here or unverified
- Full original Pre-P3 line-for-line ChatGPT transcript from every conversation; private thought transcripts are not transferable.
- Full latest locally saved Claude reports `PRE_P3_WAVE_0A_CODEX_FIX_FORWARD_REPORT_e85b8a34.md` and `PRE_P3_WAVE_0A_CODEX_2ND_FIX_FORWARD_REPORT_ab74f114.md`, unless user later uploads them. Their findings are transparently summarized in [REVIEW_HISTORY](REVIEW_HISTORY.md).
- Independent Codex actual result for candidate `ab74f114`: **NOT RECEIVED** at the last verified checkpoint.
- Live Mac development repo, unpushed local branches, production DB, provider permissions, real checkout/browser cookies and live WhatsApp delivery: **NOT PROVEN** by these documents.
- 506-capability source manifest, historical 172-screen/727-state wireframe image gallery and full 49MB interactive source ZIPs: large artifacts remain separate; their **existence is documented**, not individually reverified by this repo.
- Historical personal payment identifiers in old application Git commit history: not remediated/authorized; should not be imported here.

## Source conflict & update rules
Explicit Founder decision controls product requirements. Actual latest code can prove what *is implemented* without silently changing what *should be implemented*. New candidate SHAs, test ledgers and Codex verdicts must be recorded with attribution and checked against actual source when available. Use `CURRENT_STATE` as the front door to determine next authorized action. Historical audits may be wrong or superseded; preserve rather than quietly rewrite their provenance.


---

## NEW evidence continuity (Nov 8–16, 2026; reconciled Nov 16)
- [Full chronological delta and exact SHA/review/decision detail](evidence/2026_11_16_FULL_DELTA.md) — the authoritative **user-provided catch-up** since the earlier Wave 0A state. It is narrative reconstruction, **not** the private local source repo or all original reports.
- [Founder's Mac source packet / report location map](evidence/LOCAL_REVIEW_ARTIFACTS_2026_11_16.md) — pointer-only; local report contents **not stored in GitHub**.
- [CURRENT_STATE.md](CURRENT_STATE.md) — newest gate, frozen SHAs and next authorized action.
- [REVIEW_HISTORY.md](REVIEW_HISTORY.md) — all supplied Wave 5/Wave 6/SEC-8c/SEC-2 independent review outcomes and open status.
- [NEW_CHAT_BOOTSTRAP.md](NEW_CHAT_BOOTSTRAP.md) — updated prompt for clean new chat.
- Independent Codex Wave 5 R3 report on Founder's Mac: `~/Downloads/CODEX_WAVE5_R3_INDEPENDENT_REVIEW_ce811b2a_2026-11-16.md` — **ACCEPTED** as reported; tests 22/22 DB, 17/17 integrated claim E2E, 174/174 focused.
- Independent Codex Wave 6 R1 `~/Downloads/CODEX_WAVE6_INDEPENDENT_REVIEW_db1bed9f_2026-11-16.md` — **REJECTED** as reported. 110 rows, Codex found Staff `operate` supplemental vendor WhatsApp security problem.
- Independent Codex SEC-8c R1 local `/tmp/CODEX_SEC8C_474_INDEPENDENT_REVIEW_6dabf8aa_2026-11-16.md`, later reportedly saved under `~/Downloads/BHARAT_LAUNCHPAD_WAVE_6_QA/SEC8C_474/codex_r1/` — **REJECTED** two verified PostgreSQL races, despite 16/16 own tests.
- SEC-8c **R2 PENDING** packet `~/Downloads/BHARAT_LAUNCHPAD_WAVE_6_QA/SEC8C_474/SEC8C_474_CODEX_R2_PACKET.md`; candidate `036da7b2...`.
- SEC-2 held packet `~/Downloads/BHARAT_LAUNCHPAD_WAVE_6_QA/SEC2_CR6/SEC2_479_CODEX_PACKET.md`; candidate `748d292d`, needs merge with accepted SEC-8c base and new independent review.
- Local Wave 6 matrix and state at `~/Downloads/BHARAT_LAUNCHPAD_WAVE_6_QA/W6_MATRIX_CLASSIFIED.md`, `W6_BLOCKERS_STATUS.md`, `W6_FOUNDER_DECISIONS_2026-11-16.md`, `MORNING_STATUS.md`, master ledger. **Not uploaded to continuity repo.**
- Past statements above saying latest result for Wave 0A still pending refer to **2026-11-08 historical checkpoint**; current program has moved through Wave 5/6 and security candidates. Do not promote unknown intermediate Wave 0A/W0B–2 verdict details to fact.
- Current external proof remains absent, and GitHub continuity storage does **not** imply application source, Codex reports, test logs, production DB or secrets were ingested. If absolute completeness needed, source local ledger and report files separately, after sanitizing (repo is PUBLIC).


### 2026-11-16: SEC-8c R2 acceptance (newest independent review evidence)
- Exact candidate `036da7b2b8020e87ff41663d8aa18e42f6000b56` independently Codex **ACCEPTED** as reported by Founder; B1/B2 CLOSED, 23/23 tests, canonical migration chain 412/412 with matching schema fingerprint.
- Mac-local report `/tmp/CODEX_SEC8C_474_R2_INDEPENDENT_REVIEW_036da7b2_2026-11-16.md`; user-provided SHA-256 `b2613c441b4e1936905cd797acb26e9d16cb877275b845827347bcc561cf5ce0`. **Full bytes not in GitHub**. Preserve a copy outside /tmp.
- Historic R1 REJECTED remains valid for old SHA; SEC-2 `748d292d` is NOT Codex-accepted, needs accepted SEC-8c merge and fresh new SHA/review. Current status and next gate in [CURRENT_STATE](CURRENT_STATE.md).


---

## Cross-chat completeness audit and recovered intermediate programme history (16 Nov 2026)
- [Continuity completeness audit](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md) — evidence-by-evidence assessment of what's present, what's missing and what remains only locally or in other chats. **It does not claim exhaustive access to every chat or original report.**
- Recovered **reported** exact accepted milestones (Codex reports not stored here): Wave 0A `ab74f11459e1efdab62464fd4d7614b1132203eb` (original excerpt incomplete; independent 8 Nov audit noted ambiguity), consolidated Wave 0 `175327c520c1dbad1dbaeb5b5612c26cb32a961f`, Wave 1 `1848756e2a8de56cc761ad39376f43fd0806c066`, Wave 2 `4598b4220d61a264dfba728d64fffaddbc8de115`. The early Wave 0B `616c91bb23a77cc69be9f79ceab2bf8d17f465dd` review approved **implemented scope only**, not whole Wave 0B; WP08 local code `d46a50427078725225164c517f09e92d66bc60e7` reported independently approved. Distinguish accepted later SHA from earlier mandate or static audit.
- Local/uploaded audit and design pointers **not stored as full documents in this public repo**: `BHARAT_LAUNCHPAD_CONTINUITY_AUDIT_2026-11-08.md`; `BHARAT_LAUNCHPAD_WAVE_0_OVERNIGHT_THREE_GATE_CLOSEOUT_MANDATE_2026-11-09.md`; `BHARAT_LAUNCHPAD_OVERNIGHT_WAVE0_AND_ISOLATED_WAVE1_START_2026-11-09.md`; `BHARAT_LAUNCHPAD_WAVE1_FINAL_INDEPENDENT_CODEX_REVIEW_2026-11-09.md` (**review instruction, NOT verdict**); `BHARAT_LAUNCHPAD_WAVE2_INDEPENDENT_GAP_REVIEW_2026-11-13.md` (**static gap audit, NOT final verdict**); `BHARAT_LAUNCHPAD_COMBINED_WAVE_3_4_EXECUTION_PLAN_DRAFT_V1.md`; `BHARAT_LAUNCHPAD_W34_MASTER_V3_0.zip` (six files, contract/checklists/mandates, **not actual implementation PASS**).
- **Incomplete and still needed for A-to-Z reconstruction:** original final independent Codex reports (Wave 0A/0/1/2/3/4, W5 and W6 and security), all affected full test and Red-Team log bytes, the 506-capability source manifest, full 110-row Wave6 matrix/evidence, historical UX contracts/172 screen IDs/727 states, current local git SHA after SEC-2 integration. Private/local source files should be provided through authorized uploads, sanitized when copied into public repo.
- The repo's original archived P2 conversations are **sanitized historical context**, not a verbatim archive of all chats or live Pre-P3 source. Current live integrations, staging, production DB and evidence have not been fetched for this audit.


## 2026-11-16 extended deep-context archive — cross-chat audit remediation
The public documentation repo now contains additional curated, provenance-labelled source reconstructions rather than every raw chat line:
1. [Wave 0A/0B/0/1/2 detailed context](evidence/PRE_P3_WAVES_0_TO_2_DETAILED_CONTEXT_2026_11_16.md): all significant WP acceptance contracts, security invariants, 27 Wave 2 static issue IDs, verified-vs-reported Codex SHA lineage and unknown original verdict bytes.
2. [Wave 3/4/5 detailed context](evidence/PRE_P3_WAVES_3_TO_5_DETAILED_CONTEXT_2026_11_16.md): C1–C6.4 W3/W4 execution/gating, Wave 5 D0–D6 and B1/B2/B3 fix-forward rationale.
3. [P2→Pre-P3 runtime safety and agent workflow](evidence/P2_TO_PREP3_RUNTIME_SAFETY_AND_AGENT_WORKFLOW_2026_11_16.md): frozen production flags, release boundaries, one-writer Claude MAIN/Red-Team/Founder manual Codex discipline and OmniRoute architecture freeze.
4. [Exact SHA + independent-review candidate ledger](REVIEW_CANDIDATE_LEDGER.md): rejected/accepted/pending status across all waves with provenance and current next action.
5. [Completeness gap audit](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md): what still needs original locally held reports, full 110-row matrix, complete 506 manifest/UX source and actual live provider evidence.

**IMPORTANT:** These additions do NOT make the repository a line-for-line copy of all ChatGPT conversations. Original local Codex report bytes, some complete verification transcripts and unuploaded private project files remain absent. Because this repo is PUBLIC, do not blindly paste raw customer messages, personal payment details, private tokens, emails or full unredacted conversations. Source gaps must remain labeled NOT ARCHIVED / REPORTED / NOT PROVEN rather than hallucinated.


### Historical P2 bridge and mounted-source hash manifest — audit expansion
- [P2→Pre-P3 decisions and protected Product Onboarding Q17](evidence/P2_CONTINUITY_BRIDGE_TO_PREP3_V10_4_2026_11_16.md): dated P2 baseline, Q17 three existing AI helpers and 20/20 decisions, financial/commerce status, vendor/shipping/WhatsApp/provider constraints. Not a fresh live code audit.
- [Source coverage and SHA-256 inventory](evidence/SOURCE_FILE_COVERAGE_AND_HASH_MANIFEST_2026_11_16.md): exact hashes of five available historical source bundles plus the significant local audit/contract file index, original bytes unavailable in PUBLIC GitHub, next archival steps.
- Full precision matters: independently accepted Codex **Wave5** `ce811b2a3f19307e1f68f3e96e67d601cc92b3bb`, **SEC8c** `036da7b2b8020e87ff41663d8aa18e42f6000b56`; **Wave6 R1 REJECTED** `db1bed9f81f82275f7257adbab976b3b5e92f332`; SEC2 old base `748d292d` still not Codex-reviewed. Do not mistake attached review prompt for actual final report.


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
