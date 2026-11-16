# Bharat Launchpad — Review candidate and exact-SHA ledger
**Snapshot:** 2026-11-16 after SEC-8c R2 acceptance. **Do not treat this as live GitHub application repo proof.** SHAs, test claims, verdict summaries are from earlier user-provided independent review results, Claude reports and available audited planning sources. Source report files are mostly *on Founder's Mac*, not in this public docs repository. **Candidate acceptance ≠ production release.**

| Milestone / review | Exact code candidate SHA | Verdict | Remaining caveat |
|---|---|---|---|
| Wave 0A initial | `33286ffd85b515aee6955bf54cbce201d35e997d` | CODEX REJECTED | WP06/WP07 five findings |
| Wave 0A fix 1 | `e85b8a3481cbd790325977001228f2fe138329fe` | CODEX REJECTED WP06 | WP07 nonblocking pass; cookie/quote/protected tests |
| Wave 0A final | `ab74f11459e1efdab62464fd4d7614b1132203eb` | CODEX APPROVED **reported** | complete original R3 verdict bytes not archived |
| Wave 0B partial | `616c91bb23a77cc69be9f79ceab2bf8d17f465dd` | CODEX APPROVED IMPLEMENTED SCOPE | WP08/WP16 then PARTIAL |
| WP08 subsequent | `d46a50427078725225164c517f09e92d66bc60e7` | CODEX APPROVED **reported** | source/453 schema release gates separate |
| Consolidated Wave 0 | `175327c520c1dbad1dbaeb5b5612c26cb32a961f` | CODEX APPROVED **reported** | actual original report not here |
| Wave 1 earlier review | `b3594720df9a9dc226413def224d1954ede50839` | Mandate/fix-forward history, not final acceptance | Do not imply accepted |
| Wave 1 final | `1848756e2a8de56cc761ad39376f43fd0806c066` | CODEX APPROVED **reported** | actual report not here; no live provider proof |
| Wave 2 static gap audit | `4e4778a66af8b5b04d938b18348f5270ec714fea` | AUDIT / not Codex final | 27 static issues, no live proof |
| Wave 2 final | `4598b4220d61a264dfba728d64fffaddbc8de115` | CODEX R2 APPROVED **reported** | exact original report missing |
| Wave 3 final | `4cae4ada7731ebc302a6468aa153479a6e7c9d16` | CODEX ACCEPTED **reported** | no live provider proof |
| Wave 4 final | `1b2695e5fd6d44ac96f992ce4733a1792314709f` | CODEX R2 ACCEPTED **reported** | live provider/grants separate |
| Wave 5 R1 | `a4c5374c6ee9937888d68e02586e9fed5ea774dd` | CODEX REJECTED | privacy audit, blog duplicate, staff nav |
| Wave 5 R2 | `c3b605d260d58f8b412e1436b2711a58315174a5` | CODEX REJECTED | B1/B3 closed, B2-R2 + B2-R2b open |
| Wave 5 R3 | `ce811b2a3f19307e1f68f3e96e67d601cc92b3bb` | **CODEX ACCEPTED** | 22/22 DB, 17/17 E2E, 174/174 regression; live Shopify not proven |
| Wave 6 R1 | `db1bed9f81f82275f7257adbab976b3b5e92f332` | **CODEX REJECTED** | SEC8c/SEC2/Staff auth, 9 FAIL, external and pins |
| SEC-8c initial internal R2 | `6dabf8aadc1e509a1800bf00ebecb892391b18df` | **CODEX R1 REJECTED** | RR snapshot bypass, 474 installation race |
| SEC-8c fix R2 | `036da7b2b8020e87ff41663d8aa18e42f6000b56` | **CODEX R2 ACCEPTED** | B1/B2 closed, 23/23; chain 412/412. Production not authorized |
| SEC-2 first | `b34b81d0` | RED-TEAM R1 REJECTED | order identity, concurrency, migration319 silent no-op |
| SEC-2 current (old base) | `748d292d` | RED-TEAM R2 APPROVED; CODEX NOT RUN | **Needs accepted SEC8c merge**, new SHA and new gates |
| SEC-2 integrated candidate | `2298446b8f16246cd39daf1cbfccaa2dfde0692f` | **INDEPENDENT CODEX ACCEPTED (Founder-reported)** | 27/27 SEC-2, 23/23 SEC8c, 7 fail-before, 413/413 native, 49/49 app security, both rollback directions PASS; original report bytes Mac-local; no prod authorization |nd accepted `036da7b2`; 27/27+23/23+413 chain reported; review actual integrated packet; no production authorization |
| Staff supplemental WhatsApp authorization | Separate R2 fix NOT YET REPORTED | CONFIRMED Codex Wave6 R1 security finding | tests-first scoped permission correction required |
| Wave 6 R2 integrated | NOT YET REPORTED | PENDING | exact new SHA and full QA/test/Red-Team/Codex |
| Final integrated Pre-P3 | NOT YET REPORTED | PENDING | new exact SHA + complete external/live/pins/governance gates |

## Active next sequence
1. Founder reports SEC-8c `036da7b2` successfully merged forward into SEC-2 branch on new SHA `2298446b`; integrated tests and Red-Team APPROVE reported, Codex NOT YET RUN.
2. **SEC-2 independent Codex ACCEPTED** exact `2298446b`; proceed only to scoped Staff WhatsApp authorization fix, not Wave 6 acceptance or production.
3. Targeted Staff supplemental vendor WhatsApp permission remediation: preserve Owner/Admin-only messaging, no unrelated redesign; tests-first, independent adversarial review.
4. Reconcile security fixes and Staff into NEW Wave6 R2 candidate; rerun 110-row matrix, J1–J11, production-equivalent staging and external safety evidence where approved. Then fresh independent Codex and final integrated independent review.
5. Founder-only later release approvals: SEC-8c existing-data count; SEC-5/migration367 RLS check; SEC-2 finance trigger; release pins + migration333; staging, provider permissions, production migrations454–479, live smoke and deployment.

## Files / source authority
See [CURRENT_STATE.md](CURRENT_STATE.md), [REVIEW_HISTORY.md](REVIEW_HISTORY.md), [EVIDENCE_INDEX.md](EVIDENCE_INDEX.md), [cross-chat completeness audit](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md), [Wave 0–2 history](evidence/PRE_P3_WAVES_0_TO_2_DETAILED_CONTEXT_2026_11_16.md), [Wave 3–5 history](evidence/PRE_P3_WAVES_3_TO_5_DETAILED_CONTEXT_2026_11_16.md). Original independent report bytes not necessarily on GitHub. Always label provenance.


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
