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
| SEC-2 integrated next | NOT YET REPORTED | PENDING | No live progress claim; prepare new packet, independent Codex |
| Staff supplemental WhatsApp authorization | Separate R2 fix NOT YET REPORTED | CONFIRMED Codex Wave6 R1 security finding | tests-first scoped permission correction required |
| Wave 6 R2 integrated | NOT YET REPORTED | PENDING | exact new SHA and full QA/test/Red-Team/Codex |
| Final integrated Pre-P3 | NOT YET REPORTED | PENDING | new exact SHA + complete external/live/pins/governance gates |

## Active next sequence
1. Accepted SEC-8c `036da7b2` → local SEC-2 branch **no-rebase forward merge**, integrated native DB+concurrency regression, independent Red-Team and freeze NEW SEC-2 candidate SHA.
2. Founder manually runs independent Codex SEC-2 review on new SHA; reject/accept only exact SHA, preserve previous history.
3. Targeted Staff supplemental vendor WhatsApp permission remediation: preserve Owner/Admin-only messaging, no unrelated redesign; tests-first, independent adversarial review.
4. Reconcile security fixes and Staff into NEW Wave6 R2 candidate; rerun 110-row matrix, J1–J11, production-equivalent staging and external safety evidence where approved. Then fresh independent Codex and final integrated independent review.
5. Founder-only later release approvals: SEC-8c existing-data count; SEC-5/migration367 RLS check; SEC-2 finance trigger; release pins + migration333; staging, provider permissions, production migrations454–479, live smoke and deployment.

## Files / source authority
See [CURRENT_STATE.md](CURRENT_STATE.md), [REVIEW_HISTORY.md](REVIEW_HISTORY.md), [EVIDENCE_INDEX.md](EVIDENCE_INDEX.md), [cross-chat completeness audit](evidence/CONTINUITY_COMPLETENESS_AUDIT_2026_11_16.md), [Wave 0–2 history](evidence/PRE_P3_WAVES_0_TO_2_DETAILED_CONTEXT_2026_11_16.md), [Wave 3–5 history](evidence/PRE_P3_WAVES_3_TO_5_DETAILED_CONTEXT_2026_11_16.md). Original independent report bytes not necessarily on GitHub. Always label provenance.
