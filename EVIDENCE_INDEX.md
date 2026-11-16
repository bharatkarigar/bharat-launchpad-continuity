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
