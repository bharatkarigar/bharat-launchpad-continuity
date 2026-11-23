# Orzik Shopify — CURRENT GATE (23 Nov 2026)

**Latest known checkpoint:** Founder supplied Claude MAIN's IP-list request after a successful read-only Supabase logs measurement. The 114 IPs were extracted to a private conversation file, **not yet delivered to Claude on the Mac**. S2-A2 builder was still working when last reported. This is a documentary checkpoint, not automatic permission to proceed.

## At-a-glance
| Area | State | Source |
|---|---|---|
| Stage 1 | **CLOSED — Controlled Dark Production Release** | Founder closure + signed output + Claude independent audit |
| GitHub SaaS production main | **e6e05f99e46872debfbab254ffb31d3fa6c73fa5** | Founder-supplied release report |
| Vercel production | READY, **dpl_2pmJ3bgTn1GXwnoXjqpoeT3yGFuU** | Claude smoke report |
| Production DB | **95/95**, migrations **480, 481, 483, 484** applied; **482 deferred** | signed runner output + Claude audit |
| Shopify Orzik install + onboarding | **OFF**; no public / dev-store install authorized or reported | dark-state audit |
| S2-A local shop/company allow-list | **CODEX_S2A_APPROVED** at exact **d48a2d8cc1092077f320d707de8a0d6a90a61620**; not pushed/deployed | original Codex review |
| S2-1 CLI identity | PASS, Shopify CLI 5.0.2, config identity verified; read-only | Claude / browser report |
| S2-A2 | **LOCAL BUILD IN PROGRESS**, no candidate SHA/review yet | latest Claude message |
| S2-2 Shopify config deploy | **HOLD / NOT AUTHORIZED** | Founder |
| Shopify IP allowlist | DISABLED, no proven ASN, public-app requirement open | browser preflight |
| Stage 3 / Stage 4 | NOT STARTED / NOT AUTHORIZED | Founder |
| Extra Vercel static-IP plan / $100-month cost | **NOT APPROVED** | Founder |

## App identities — never mix
- New Orzik Shopify org: **249330912**; app **450606792705**, active Shopify version **orzik-1**.
- Approved QA dev store: **orzik-qa.myshopify.com** (Shopify store ID 77710295134).
- QA SaaS company: **ZZZQA-PRODSMOKE-001**, test-only, 1 pre-existing test order, zero existing store connections. Full UUID to be retrieved independently from secure local source before any env write; do not guess.
- Old org **243933135** and old app **450405007361** are strictly protected. Earlier test-0o3wx8jg.myshopify.com NOT on Orzik allow-list.
- Orzik app host **app.orzik.co**; legacy dashboard + Mini-Stores preserved.

## Latest IP evidence — partial progress, NOT a solved allowlist
- Supabase read-only API gateway log query, project qmlbqcgisufsijmtswqk, filtered server-role Node/Supabase clients, 2026-11-22T10:29:40Z to 2026-11-23T10:29:40Z:
  **49,291 requests / 114 distinct IPs, US**.
- Classified network organizations (not verified ASNs): Amazon Data Services Northern Virginia **75**, Amazon Technologies Inc. **23**, Amazon.com Inc. **16**.
- Private IP-only list: orzik_egress_ips_2026-11-23.txt, **114 valid IPv4**, SHA-256 **7544b56d3bb27064718fa181331baeb913350bd506e81ce10aced03ea4c2c2ab**. Not committed to public GitHub.
- Bare IPs should be provided privately to Claude for Team Cymru / RIPEstat cross-check. Attribution to Vercel, BGP ASNs, country consistency for Shopify API traffic, and future stability **not proven**.
- No IP allowlist enforcement, paid networking or diagnostic production route authorized.

## Immediate permitted next moves
1. **Evidence-only:** share private 114-IP list with Claude MAIN; Claude checks IP→origin ASN through 2 independent sources, source attribution and weak shared-cloud controls; no settings edits.
2. **Local-only:** Claude MAIN finishes S2-A2 scope: proposed use_legacy_install_flow=true, callback membership recheck (S2A-P2-1), explicit zero-side-effect token resolver tests (P3-1), domain-length validation matching DB migration 480 (P3-2), install/token/webhook/legacy regression. Builder → internal review → Red-Team → Founder-run Codex on **new exact SHA**.
3. **No deployment yet:** Shopify S2-2, new version, IP settings, Vercel env/flag, GitHub main push, migration482, QA app install, public data request and real merchant activation all need distinct Founder approvals.
4. **Security questions:** whether Shopify-managed install bypasses Orzik allow-list when use_legacy_install_flow=false; whether true actually routes authorization before install; whether ASN/US allowlist is compliant/usable and safe; exact Shopify allowlist enrollment/enforcement order.
5. Later separate: signed F-482, F-RUN runner evidence-write bug, F-TEST old test, BK010 missing slug domain exception; Shopify Protected Customer Data public review Draft 0/16 and App Store decisions A–C.

## Source hierarchy
- Full details, timelines, SHAs, constraints, evidence-file names: [A-to-Z Orzik continuity](evidence/ORZIK_SHOPIFY_A_TO_Z_CONTINUITY_2026_11_23.md).
- Binding new Orzik Founder restrictions: [ORZIK_FOUNDER_DECISIONS.md](ORZIK_FOUNDER_DECISIONS.md).
- Older Pre-P3 Wave history remains in [CURRENT_STATE.md](CURRENT_STATE.md) and canonical V10.4 documents, with separate status.
- Documentation repo is **PUBLIC**, application repo and Mac-local packets are separate. Information can advance after this date; check newest messages and source before acting.

## Update — 23 Nov 2026, 16:32 IST: S2-A2 frozen, independent Codex PENDING

**Founder forwarded Claude MAIN report (REPORTED, not source-inspected by continuity maintainer):** local branch `feat/orzik-s2a-allowlist`, worktree `~/Desktop/launchpad-orzik-s2a`, exact candidate commit **`9a8dd26fc5d68188c4564c2b91440b2e64da6b78`**; one new commit on accepted S2-A `d48a2d8c`, 13 files touched, clean worktree, **not pushed/deployed**. Includes Orzik-only `use_legacy_install_flow=true`, signed OAuth state user ID and active Owner/Admin membership re-check before token exchange, denied token resolver zero-side-effect tests, shop-label 61/62 boundary alignment with migration 480, unauthorized/unlisted/forged/missing-signature/revoked-membership tests, token/webhook/legacy regression. No reported legacy app, SQL, webhook route or global flag edits.

**Claude builder report:** 16,103 tests PASS / 0 FAIL; lint + build PASS; 53 pre-existing TypeScript errors (typecheck is NOT green); internal red-team APPROVE with two low-risk observations: (1) callback membership re-check does not check orders module; (2) signed-state original user identity is checked, but current OAuth browser operator identity not proven. Independent **Codex has NOT run / verdict PENDING**. Local review packet `~/Downloads/ORZIK_SHOPIFY_RELEASE_EVIDENCE_2026-11-21/23_CODEX_REVIEW_PACKET_S2A2_9a8dd26f.md`, partial SHA-256 `f1fe00fa…20feb` only; actual full hash must be verified locally. Diff/logs `gate_logs/s2a2_9a8dd26f/`. Save original independent Codex output privately as `23a_CODEX_REPORT_S2A2_original.txt`, preserve missing original S2-A `19a_CODEX_REPORT_S2A_original.txt`.

**Next gate:** Founder manually runs independent read-only Codex on exact `9a8dd26f...` and packet 23; no Shopify config deploy, install, IP allowlist, Vercel/app main, production DB 482, spending or activation. Shopify **actual** legacy install behavior remains untested, even if local Codex approves. ASN mapping subsequently reported 114/114 **AS14618 Amazon US**, Team Cymru and RIPEstat both agree; no direct Shopify egress proof; AS14618+US a **QA proposal only**, not an approved config. Existing earlier status below remains as of its original snapshot until this update.


## LATEST — 23 Nov 2026: Independent S2-A2 Codex REJECTED (supersedes earlier pending state)
Founder provided FULL independent review text for **exact frozen local SHA `9a8dd26fc5d68188c4564c2b91440b2e64da6b78`**. Worktree clean, parent `d48a2d8cc1092077f320d707de8a0d6a90a61620`, ancestor `e6e05f99e46872debfbab254ffb31d3fa6c73fa5`. Review packet SHA-256 verified in report **`f1fe00fa6cc7db42588d3a2b6f853f5f64229d2b6c9c6abb037028eb18720feb`**. **VERDICT `CODEX_S2A2_REJECTED`**.

- **P1 BLOCKER:** `use_legacy_install_flow=true` plus app-specific `[[webhooks.subscriptions]]` is likely unsupported by Shopify CLI; may prevent config deploy and break app/uninstalled / ordinary order topic subscription registration. Local configuration-text tests not sufficient. Shopify/cli issue #6171 and #4417 identify limitation; Shopify staff response in #4417 explicitly describes incompatibility. Actual validation using **pinned Shopify CLI 5.0.2**, final version creation and installation NOT run. Report does **not** prove definitive failure on exact environment.
- **P2:** callback checks active Owner/Admin membership but not current **orders-module entitlement**; permissions may be withdrawn within signed-state 10-minute window. No cross-company bypass shown; remediate before new approval.
- **P3:** callback trusts HMAC-bound original user and state cookie, not independently current browser login. Short-lived signed user lease; report calls non-exploitable informational with present checks. Document, do not invent exploitable escalation.
- Independently executed 6 test files / **77 PASS, 0 FAIL**. Builder suite **16,103 PASS, 0 FAIL** (not independently rerun). Lint/build builder PASS; **53 pre-existing TypeScript errors**, not green. Prior P3 resolver side-effect and shop validation boundary are **resolved**. No P0.
- **Mandatory next gate:** local-only fix-forward candidate **S2-A3** or equivalent; verify exact pinned CLI config compatibility safely before any remote deployment. Preserve compliance webhooks separately and ensure ordinary/uninstall delivery by supported shop-specific registration after OAuth if needed; check registration, duplicate/idempotency, install/uninstall cleanup, token/sync behavior. Never create an extra Shopify app or execute `shopify app dev/deploy --no-release` without separate explicit Founder permission; even `--no-release` can mutate Shopify remote version. Seek permission if remote proof is truly necessary.
- **All external operations remain HOLD:** S2-2 Shopify version deploy, IP allowlist AS14618+US configuration/enforcement, dev install, Vercel/app main, migration482, public activation, paid networking. Do not label S2-A2 approved based on red-team/Builder checks.
