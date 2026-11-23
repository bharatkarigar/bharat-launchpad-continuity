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


## 23 Nov 2026 — S2-A3 proposal received (NO Founder approval yet / NO implementation)
**Provenance:** Founder forwarded Claude MAIN diagnosis and proposal, report pointer `24_S2A3_DIAGNOSIS_AND_PROPOSAL.md` (full local report not ingested). Claude checked pinned Shopify CLI 5.0.2, Node22, isolated config from frozen S2-A2 9a8dd26f: `shopify app config validate --config orzik --path <isolated-copy> --no-input --no-color` returned **exit 0 / valid / no warnings** and no file change. This is *local syntax validation only*, not remote version-creation/deployment compatibility proof. S2-A2 independent Codex **REJECTED** remains in force.

**Proposed S2-A3, NOT BUILT:** retain `use_legacy_install_flow=true` and remove ordinary app-specific subscriptions for `app/uninstalled`, `orders/create`, `orders/updated`, `orders/cancelled` from TOML; use Orzik-only GraphQL Admin API shop-specific `webhookSubscriptionCreate` after successful OAuth with list/verify/idempotent retry; keep mandatory three compliance topics in TOML only if compatible (otherwise separate Founder-approved Dev Dashboard configuration); on failure mark connection as webhooks-pending, retry via sync/health plus daily check. Callback rechecks current orders entitlement before token exchange; P3 signed initiating-user semantics preserved/documented; protect legacy source byte identity. No DB schema change proposed. No Shopify change, install, push, migration, IP allowlist or production action done.

**Advisory constraints for local-only Founder decision:** verify existing persistent status supports `webhooks_pending` without DB schema changes; fail-closed UI/connection/sync behavior and recovery after partial registration; retry subscription deletion after webhook delivery failure, concurrency/idempotency; exact topic enum, URI and API version, response `userErrors`, pagination, GraphQL limits; ensure compliance registration remains app-level independent of shop token; test first-install/uninstall race / credentials revoked, signed uninstall and token-refresh failure fallback; ensure historical order cutoff/backfill gap repair; no new app or production remote trial. Shopify docs support shop-specific GraphQL subscriptions including APP_UNINSTALLED, and warn failing shop-specific subscriptions may be deleted: https://shopify.dev/docs/apps/build/webhooks/subscribe. Shopify CLI #6171 reports legacy app-specific incompatibility; local config validate PASS does not prove remote config accepted.

**Approvals A-E are separate.** No new independent Codex candidate SHA. The handoff can recommend **A local-only after constrained scope** but only Founder explicit approval authorizes building. B compliance Dev Dashboard, C remote `app deploy --no-release`/deploy, D IP allowlist AS14618+US, E QA install/Vercel/GitHub/env remain HOLD.


## LATEST — 23 Nov 2026: Founder-approved unattended LOCAL S2-A3 run started
**Provenance:** Claude MAIN progress message forwarded by Founder; operational claims are **CLAUDE REPORTED**, not independently inspected in the application worktree through this documentation change.
- Founder authorized unattended **local-only S2-A3** implementation, scoped Builder → checks → Red-Team → local remediation → freeze exact new SHA → independent Codex packet. No manual Founder Codex run delegated. No app push, Shopify install/config, production, Supabase migration, paid changes authorized.
- Claude verified local `~/Desktop/launchpad-orzik-s2a` on branch `feat/orzik-s2a-allowlist`, HEAD **`9a8dd26fc5d68188c4564c2b91440b2e64da6b78`**. Modified/untracked files were reportedly only interrupted S2-A3 changes, no unrelated Founder edits.
- All partial S2-A3 edits, **including untracked new webhook subscriptions module**, preserved in reversible Git stash titled **`S2-A3 interrupted partial builder edits 2026-11-23 (preserved, not reviewed)`**. Worktree then clean at starting SHA; no reset, deletion, rewrite or commit reported. **Do not drop stash** without explicit later approval and verification.
- A single Builder was started on complete approved S2-A3. **Step 0 remains IN PROGRESS/UNPROVEN**: existing durable DB field for `webhooks_pending` must be checked; if none exists, **STOP** and propose smallest separately-approved schema change. Compliance webhooks compatibility with legacy flag examined against pinned Shopify CLI 5.0.2 source; if local proof inconclusive, record remote proof R1, **not PASS**.
- Upcoming **not yet completed**: tests, type-check baseline comparison, lint, build, independent Red-Team, within-scope fix/retest/review, new candidate SHA freeze, diffs/logs, new Codex packet. No result, new SHA or pass verdict available yet.
- Claude will stop only on unapproved schema, irreversible operation, remote Shopify step, or unresolved P0/P1. **S2-A2 `9a8dd26f` remains CODEX REJECTED**; S2-A prior approved local SHA remains historical; S2-A3 has NO independent Codex verdict.
- Existing S2-2 Shopify config deployment, AS14618+US allowlist, QA install, Vercel production, GitHub app main push, migration482, merchant activation and paid networking **HOLD**. No authorization inferred from an unattended local run.


## 23 Nov 2026 — S2-A3 Step0 STOP: migration 485 local-only proposal
**Provenance:** Founder forwarded Claude MAIN's Step 0 diagnostic; private report pointer `~/Downloads/ORZIK_SHOPIFY_RELEASE_EVIDENCE_2026-11-21/25_S2A3_STEP0_STOP_MIGRATION_485_REQUEST.md` (not itself accessed from this public documentation repo). **Reported state:** S2-A3 Builder STOPPED before further implementation; clean local HEAD `9a8dd26fc5d68188c4564c2b91440b2e64da6b78`; interrupted draft remains in reversible stash, untouched. No commits, pushes, production, Shopify or paid writes.

**Step 0A finding (CLAUDE REPORTED):** existing `store_connections.health` overwritten to healthy by shared scheduled sync (`lib/data/canonical/sync.ts:124,211`) and health job regardless of webhooks; `status` and `last_sync_status` share other meanings/overwrite; token/lease columns reserved for token refresh. No safely persistent independent webhook pending state and no dedicated ensure lease. Reusing shared fields risks legacy Shopify/Wix behavior and false green status.

**Step 0B:** local Shopify CLI 5.0.2 validation passes, but actual Shopify remote legacy install + compliance_topics compatibility **NOT PROVEN**; retain exact remote proof R1, fallback compliance URLs in Partner Dashboard subject to separate Founder approval. No Shopify deploy was attempted.

**Claude's proposal, not yet executed/approved by this GitHub update:** Option A local-only migration **485** with three additive `shopify_stores` fields (`webhooks_state` pending/verified, `webhooks_verified_at` timestamp, `webhooks_ensure_lease_until` timestamp) and a service-role-only `orzik_record_webhooks_state` compare-and-set lease function, plus matching rollback/manifest/native Postgres forward→rollback→forward tests, S2-A3 local code and independent Red-Team/Founder Codex packet. Existing one legacy store row would default pending per proposal; need analyze whether default NULL + explicit Orzik pending would better isolate legacy records. Explicitly protect store and app identity in RPC and all worker calls; verify genuine lease ownership, expiry/retry/idempotence and no false healthy status, privilege/search_path safety and constrained function EXECUTE grants. Ensure migration 485 number does not conflict with any concurrent local canonical migration; migration482 still deferred. Signed runner prefix step 96 is an expectation pending validation, **not** approval to adjust pins or apply anything. Option B shared sync/health rewrites NOT recommended; Option C pause.

**Approval boundaries:** Recommended **A for local-only SQL/code/test/red-team/packet**, with separate explicit Founder approval; **no Supabase production migration485/482, DB writes, Vercel, Shopify app config/installation/IP allowlist, provider API, GitHub app push or paid service.** Local Postgres test migrations are permitted in approved disposable test DB only. If local test cannot demonstrate safe legacy isolation or service-role-only permissions, STOP for new design approval. Candidate S2-A2 9a8dd26f remains Codex REJECTED until independent S2-A3 code review.

**Pending actual founder action:** Respond A/B/C to Claude MAIN; continue local work only if Founder authorizes. The narrative here does not itself grant that permission.


## 23 Nov 2026 — Approved local S2-A3 + migration485 builder implementation underway
**Provenance: Founder-forwarded Claude MAIN progress update.** Explicit Option A local-only approval granted in the chat prior to this report. No claim of actual source inspection, completed code, SQL test success or independent verification by this public continuity updater.

- Starting worktree reportedly verified clean at `feat/orzik-s2a-allowlist`, HEAD `9a8dd26fc5d68188c4564c2b91440b2e64da6b78`; earlier partial builder stash intact. Migration number **485 unused** on inspected branches; migration **482 deferred** in manifest.
- **Local builder underway**, migration **485 first**. Design choice: **nullable** `shopify_stores.webhooks_state` (NULL for legacy; only Orzik stores pending/verified), `webhooks_verified_at`, lease expiry and **lease owner token** for compare-and-set. Reported planned service-role-only functions with `search_path=''`, scoped to exact shop AND company AND existing Orzik token; cannot modify legacy or other-company rows by design. **These safeguards are not yet tested or accepted.**
- Required local disposable Postgres verification plan: forward→rollback→forward, existing legacy row isolation, other-company isolation, anon/authenticated denial, concurrency single lease winner, expiry, stale owner tokens, invalid transitions, 480/483/484 regression. Add 485 to manifest. Runner release pins **step 96 NOT changed** and any production application requires separate signed approval. Stop if legacy safety needs shared Wix/legacy edits or second migration.
- After local SQL: Orzik-only TOML legacy flag with ordinary app-specific webhook topics removed, compliance remains **remote proof R1**; GraphQL per-shop subscription list/create/verify/repair for uninstall and three order topics, truthful pending UI, callback current orders entitlement recheck, missed-order reconciliation/uninstall handling, documentation and legacy byte-identity tests.
- Next **not yet complete**: Claude's full local tests, TypeScript (53 inherited errors as previously reported), lint, build, local Postgres suites; independent red-team, in-scope fix/retest, exact NEW frozen SHA and single combined independent Codex packet. Founder runs Codex separately.
- **No production writes** reported. S2-2 Shopify config/app install, IP ASN AS14618+US allowlist, Vercel, GitHub application push, DB production migration485/482, release runner pins and costs remain **HOLD**. S2-A2 SHA 9a8dd26f remains independently Codex REJECTED; S2-A3 no verdict yet.


## 23 Nov 2026 — S2-A3 read-only parallel review finished (Builder still running)
**CLAUDE REPORTED (Founder-forwarded):** Parallel read-only research/security/test-planning reviewer finished and relayed findings to sole local Builder; Builder still working. Scratchpad on Mac `/private/tmp/claude-501/-Users-harshvidyarthi-Desktop-v0-dropshipping-admin-dashboard/8373f38c-950e-4478-9920-468fb3c99f39/scratchpad/s2a3_parallel_review.md` (private, ephemeral; full original not read by documentation maintainer). No completed integrated candidate SHA, full tests, Red-Team or Codex verdict yet.
- **F1 medium, fix requested:** `verified` webhook state can outlive an unobserved uninstall/reinstall when connection token changes but shop row stays active. Proposed trigger reset to `pending` on token replacement; callback records pending first; local disposable Postgres reproduction required.
- **IMPORTANT REVIEW CONDITION:** distinguish *new OAuth install/re-authorization token replacement* from ordinary expiring offline-token access/refresh token rotation. Trigger resetting verified on every refresh would cause repeated false pending and potential repair storms; test ordinary refresh keeps verified intact while real reinstall/rebind transitions pending. Need clarify exact DB columns / token identity before approving F1 trigger.
- **F2–F4 low:** new Orzik row with NULL state must show not-fully-connected until callback sets pending; legacy/Wix unchanged; reason about preservation or invalidation of last verified timestamp; lease expiry mid-run cannot finalize verified or show success.
- **CLAUDE REPORTED Shopify documentation:** mandatory compliance topics not registrable using Shopify Admin API; keep app-level config (remote R1 still needed). Failing per-shop subscriptions deleted after eight retries within four hours; reverify/repair and missed order reconciliation necessary. Webhook handler target response within five seconds. Other claims (uninstall lifecycle, duplicates, pagination, throttling) not yet independently proven and remain Shopify remote proofs R1–R5.
- Test planner delivered 28 cases / 25 mandatory, builder checklist. After Builder local implementation: MAIN runs own tests/type/lint/build/local Postgres → independent Red-Team → in-scope fix/retest if necessary → freeze new local SHA / Codex packet. **No external writes; production/Shopify/GitHub-app/Supabase migration485/482 and AS14618 allowlist remain HOLD.**
