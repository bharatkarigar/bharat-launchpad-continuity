> HISTORICAL / ARCHIVED CONTEXT. Superseded by canonical V10.4 for current Founder rules and by CURRENT_STATE for live wave status.

# Bharat Launchpad — Deep Context Reconstruction
## Phase-0 Security / Production Release / Recovery / Closeout
### Reconstructed from the long conversation through 11 Oct 2026

> **Purpose**
>
> This is not a short handoff. It is a detailed continuity document intended to preserve the reasoning context, production state, failures, reviews, fixes, Founder decisions, file/commit references, commands, rollout sequence, deferred work, and the transition into Phase 1.
>
> It is designed so a new ChatGPT/Claude/Codex session can understand **why** each decision was made, not only what the latest state is.

---

# 1. Product / company context behind this work

**Product:** Bharat Launchpad

**Founder:** Harsh Vidyarthi

**Positioning:** AI Cofounder / company decision layer for founder-led product businesses, initially Indian D2C / ecommerce.

**Core operating loop:**

> Understand → Analyze → Recommend / Decide → Explain → Founder Approval → Execute → Verify → Measure → Learn

The AI is not intended to merely agree with the founder. It should challenge decisions when evidence warrants it, explain its rationale, report when a recommendation fails, and operate within explicit approval boundaries.

Long-term principle:

> **The systems can change. The Company Brain remains.**

Phase 0 existed because security, tenancy, auth, credential handling, financial safety, provider policy readiness, auditability, and release safety were treated as **architecture requirements**, not later hardening.

The architecture target discussed was multi-tenant scale toward roughly **10,000 clients**, with strict tenant isolation and no unsafe shared-state assumptions.

---

# 2. User working style / operating preferences that shaped execution

The user consistently wanted:

- compact Hinglish / English,
- exact copy-paste commands,
- one operational step at a time,
- minimal branching choices,
- evidence-based status only,
- Claude / Codex to make routine technical/security decisions,
- Founder escalation only for genuinely business, financial, irreversible, or authority-bound choices.

The user repeatedly rejected “planning from scratch” once a phase had been frozen.

Important execution preference:

- new feature work should normally be isolated,
- production safety first,
- no fabricated progress,
- no destructive smoke tests,
- no casual secret rotation,
- no touching financial/payment/refund/shipment state during verification unless specifically approved.

---

# 3. Core repository / environment

**Repository**

`bharatkarigar/v0-dropshipping-admin-dashboard`

**Main Phase-0 worktree**

`/Users/harshvidyarthi/Desktop/launchpad-security-w1`

**Stack**

- Next.js 16.x
- React 19.x
- Supabase
- Vercel

**Production Supabase project ref**

`qmlbqcgisufsijmtswqk`

**Staging Supabase project ref**

`tluwnketpufetxxngkzd`

**Production application**

`https://dashboard.bharatkarigar.com`

**Vercel project**

`harsh-4038s-projects/v0-dropshipping-admin-dashboard`

---

# 4. Phase-0 architecture freeze and why Phase 0 became large

Before production rollout, a Phase-0 security map was built and reviewed.

Recovered context says:

- architecture V2.1 was frozen,
- Phase 1 was not allowed to begin before Phase 0,
- the security map reached roughly 19 docs,
- 14 known issues were tracked,
- 10 additional live findings were discovered,
- the map initially contained no production code/migration/deploy changes,
- staging verification then exposed more unsafe behavior.

Major security findings included areas such as:

- wallet manipulation risk,
- anonymous table access,
- credential/secret exposure,
- shared-supplier banking/privacy leakage,
- storage overwrite/delete paths,
- order payment tampering,
- vendor/PostgREST bypass risk,
- private payment evidence exposure,
- unsafe cascade behavior,
- preview/staging using production-like secrets,
- maintenance-mode limitations,
- direct Supabase writes that could bypass app-only maintenance,
- manual-dispatch / Delhivery race risk.

A staging gate at one point confirmed **19 unsafe behaviors** and was deliberately paused rather than pretending release readiness.

---

# 5. Non-negotiable architecture principles

Security/compliance/scalability were frozen as core requirements:

- least privilege,
- strict tenant isolation,
- secure OAuth/token handling,
- provider policy / app-review readiness,
- privacy/data-flow controls,
- auditability,
- deletion/retention controls,
- webhook verification,
- rate limiting,
- abuse protection,
- continuous security testing,
- safe multi-tenant scale.

No design should rely on “we will harden it later.”

---

# 6. Frozen Founder decisions — do not reopen casually

These were explicitly frozen during Phase 0:

1. **GST** = platform-managed.
2. **Shared supplier cleanup** = Path B:
   - end only the second-company relationship,
   - hide/deactivate that company’s listings,
   - preserve vendor master,
   - preserve original relationship,
   - preserve enquiries/orders/history/evidence.
3. **Legacy passwords** are treated as possibly real:
   - linked Auth users must be reset before legacy plaintext copies are cleared.
4. **Historical RTD ₹18,163**:
   - no action,
   - no refund,
   - no rewrite.
5. **₹10 wallet drift**:
   - no adjustment.
6. **Automatic RTD refund**:
   - OFF.
7. **Old/paused client data**:
   - non-blocking unless it creates active financial loss, irreversible deletion, cross-tenant exposure, credential loss, or outage.
8. **Missing real Delhivery sandbox booking**:
   - accepted as a later/P3 residual.

Later explicit Founder constraints:

- do not rotate the exposed production DB password right now,
- do not revoke recovery/session tokens merely because one token appeared in a screenshot,
- do not send the other seven recovery emails without fresh approval.

---

# 7. Hard release rules

These rules were repeated throughout the thread:

- **Migration 294 must NEVER be applied remotely.**
- No destructive smoke tests.
- Evidence only; no fabricated status.
- Do not casually re-freeze production after certification.
- Do not casually rotate/delete active Delhivery encryption key `p1`.
- Do not reintroduce plaintext credentials.
- Do not rerun Phase-0 migrations during closeout.
- Do not modify payment/refund/shipment state during closeout.
- Do not send the seven deferred recovery emails without fresh Founder approval.
- Do not reuse the first exposed recovery link/token.
- Do not manually revoke sessions/tokens unless the Founder later changes that decision.

---

# 8. Important commit history

| Purpose | Commit |
|---|---|
| Approved application tree | `107d2587b6a7b2a2e830a4bfa85db2ce2f0e30c4` |
| Earlier production main | `7f98631c611bd76993cfe89fe48205234a4c4fb2` |
| Fingerprint pin-list fix | `6a3fbf7b3a83d12240543eb2c4d517ddeb9ff202` |
| Codex approval / fix-forward record | `e7a7cb59ef23a4179a31745da1ea2e90b42e556e` |
| First password-recovery implementation — rejected | `386ae5215eb1766300dc288796cf2728ae0c4096` |
| Hardened password-recovery implementation — approved | `907cacca5f30614eb38d538f33d08440e4e20295` |
| Later exact-credential recovery candidate | `d1bdef40d382cea20c218f270749ad919aeb9503` |
| Later email-transport follow-up | `fc361fc34d644398be3bbe77a531d86163c18aef` |
| Final later production closeout state recorded in project context | `1fa7c70b277daa4089dffb61521d6f38a44a99f5` |

Important distinction:

- `107d...` was the approved application tree during the main Phase-0 release.
- `e7a7cb5...` became the certified production/fix-forward release identity before the recovery fix.
- `907cacc...` was the independently approved password-recovery hardening release.
- The later same-workstream continuation eventually recorded production at `1fa7c70...` before the Founder formally closed Phase 0 with some residual verification work waived.

---

# 9. Bundle / staging progression before production

The Phase-0 work progressed in bundles rather than one giant blind migration.

Recovered milestones:

- Bundle 8 covered items around `266a`, `266e`, `271`, `269b` and was staging-only at that point.
- Bundle 9 covered coexistence work around `266e`, `271`, `271a`, `272`; referenced commits included `3979ec8`, `e18ebbf`, `88cfd77`, `710c28f`, `e0f25a9`; test count was ~4,057.
- Bundle 18 became the final major candidate and included migrations around `305–309`, `290`, canonical builds, final staging/production gates, with a tested SHA around `6739b07` and ~4,479 tests.
- Staging later passed key chains including `306/305/307/308/309/271/290/266a/310`.
- Item `267` was independently approved and staging-approved; a later staging run showed 23/23 JWT-related checks passing.
- Item `268` credential/domain uniqueness was classified non-blocking / P2-type residual.

The central release philosophy was: **prove each dependency chain on staging first, then production under a controlled write freeze.**

---

# 10. Main migration / closure chain used in production

The production sequence eventually included:

## Integrity / relationship chain

- `266d`
- `271a`
- `304`
- `269b` with Founder-approved Path B
- `272`
- `291`
- `292`
- `293`

## Finance chain

- `295`
- `296`
- `297`
- `298`
- `299`
- `300`
- `301`
- `302`
- `303`
- `305`
- `307`
- `308`
- `309`

## Closure / hardening chain

- `311`
- `266c`
- `315`
- `318`
- `316`
- `317`
- `267`
- `312`
- `313`
- `266b`

## Access lockdown

- `266e`
- `271`
- `290`
- `266a`
- `310`
- `268`

## Legacy password cleanup

- `314_clear_legacy_login_passwords.sql`

## Release-freeze controls

- `319` installed/managed the release-freeze control surface.

Important:

- `294` was baseline-only / never remote.
- `306` had historical/staging/production handling and was not to be blindly rerun later.

---

# 11. Production release plan and state model

The release used two protection layers:

1. **Application maintenance mode**
2. **Database write freeze**

The important idea was that app maintenance alone was insufficient because direct Supabase/Data API writes could bypass the app. Therefore Phase 0 added a DB-level freeze.

The planned sequence was roughly:

1. deploy approved app under maintenance,
2. install/check freeze controls,
3. preflight,
4. turn DB write freeze ON,
5. reset legacy-linked Auth passwords,
6. wait JWT/access-token lifetime,
7. run migration/cleanup chains,
8. clear legacy password copies only after timing/session gates passed,
9. seal Delhivery credentials,
10. certify the exact release state,
11. end DB freeze only if certified and unchanged,
12. smoke test while app maintenance still ON via bypass,
13. turn application maintenance OFF only after smoke.

This was intentionally fail-closed.

---

# 12. Backup / attestation / production identity

A production backup was taken and verified before the irreversible release sequence.

A release attestation file was used to tie production checks to the exact release identity.

During fix-forward, a fresh attestation was generated for the `e7a7cb59...` release identity.

The release process repeatedly verified:

- exact commit identity,
- environment = production,
- maintenance state,
- Supabase project identity,
- no pending financial/shipment conditions,
- database quietness,
- no unsafe old deploy route,
- auth token lifetime,
- Delhivery keyring state.

---

# 13. Legacy password security action

A high-risk issue existed because legacy client rows could contain plaintext login-password copies.

Founder decision: treat them as real passwords until safely neutralized.

The reviewed process was:

1. identify every company row with a legacy password copy,
2. identify linked Auth accounts,
3. during DB freeze, set each linked Auth account to a **random unknown password**,
4. mark reset time in service-only metadata,
5. revoke/handle old sessions,
6. wait configured access-token lifetime + safety margin,
7. only then clear legacy plaintext copies with migration `314`.

Production counts later diagnosed:

- Companies: 10
- Linked company sign-in accounts: 9
- Missing linked Auth accounts: 0
- Reset markers present: 8
- Non-reset linked company accounts: 1
- Legacy password copies remaining: 0

One ninth legacy password copy had no linked Auth account, so it was cleared but no Auth reset was possible/needed.

This design directly explains why old company passwords stopped working after Phase 0.

---

# 14. Delhivery credential sealing

Courier credentials were moved out of plaintext storage into an encrypted/sealed model.

Important state:

- active encryption key id: `p1`
- `DELHIVERY_CREDENTIALS_SEALED_ONLY=true`
- release evidence had previously verified zero plaintext values and successful open/verify behavior.

A fresh valid keyring was generated, stored securely, and used to seal production credentials.

At one point production counts showed 14 credential values total across company/platform fields, all sealed on active key `p1`.

Rule:

- do not casually rotate/delete `p1`,
- do not print key material,
- do not expose credential values in chat/logs.

---

# 15. Fingerprint certification failure and fix-forward

The first production certification attempt failed on a schema fingerprint mismatch for:

`increment_correction_usage(row_id uuid)`

Observed fingerprint included:

- function definition hash `9c2bf0...`
- definer false
- expected ACL state

Independent diagnosis showed this was not a DB security regression. The certified staging state had the same function definition. The production “may remain” pin list had omitted the exact expected production state after access hardening.

Fix-forward:

- file adjusted: `docs/phase-0-security-map/bundle18-runbooks/production_only_may_remain_after_release.txt`
- runner SHA table regenerated
- review package added: `PHASE_0_FIX_FORWARD_REVIEW_FINGERPRINT_PIN.md`
- fix commit: `6a3fbf7b3a83d12240543eb2c4d517ddeb9ff202`
- independent Codex review: APPROVE
- approval record commit: `e7a7cb59ef23a4179a31745da1ea2e90b42e556e`

The application tree itself remained unchanged from the approved application SHA.

This was a release-control metadata/pin-list correction, not a production schema rewrite.

---

# 16. Production certification and freeze end

After the fix-forward:

- `main` was fast-forwarded to `e7a7cb59...`
- Vercel production deployment became Ready
- release attestation was rebound to the new certified identity
- preflight passed
- database freeze status showed required conditions PASS
- certification succeeded
- DB freeze ended successfully within the allowed certification window

After freeze end:

- DB write freeze = OFF
- database writes = open under final RLS/grants/security posture
- certification = YES
- application maintenance was still ON until smoke

At this point the system had transitioned from temporary release protection to permanent RLS/grants/access controls.

---

# 17. Protected smoke after certification

Required smoke set:

1. Admin sign-in
2. Dashboard
3. Orders
4. One Delhivery tracking lookup using sealed credentials
5. Existing-order harmless save + restore
6. Company sign-in

The first five passed.

Company sign-in initially returned:

`401 Invalid login credentials`

A network screenshot proved:

- request reached `/api/auth/login`,
- maintenance bypass cookie was present,
- response was genuinely auth 401,
- maintenance was not the cause.

Read-only diagnosis confirmed this was **expected** for the eight reset accounts because their old passwords had deliberately been invalidated during Phase 0.

---

# 18. Maintenance bypass and related operational detail

During protected smoke, maintenance bypass was set via cookie/header rather than disabling maintenance prematurely.

The app supported:

- header `x-maintenance-bypass`
- cookie `maintenance_bypass`

The user later turned maintenance OFF and redeployed while diagnosing company login; the same 401 remained, further proving maintenance was not the issue.

A screenshot contained the maintenance-bypass token. The rule afterward was not to repeat or expose secret values.

---

# 19. First controlled recovery email and discovery of a real auth-recovery defect

The user explicitly requested that recovery email be sent to **only one** account:

`bharatkarigar7@gmail.com`

The first email arrived from Supabase Auth.

Clicking “Reset Password” redirected to:

`http://localhost:3000/#access_token=...`

The browser showed `ERR_CONNECTION_REFUSED` because localhost was not serving the app.

This revealed a real production recovery defect:

1. recovery request did not provide an explicit production return URL,
2. Supabase Site URL was still effectively pointing to localhost at that time,
3. the application had no dedicated reset-password landing page.

The first recovery link/token appeared in a screenshot.

Founder instruction after discussion:

- **do not revoke anything right now**,
- treat that first recovery link as obsolete,
- never reuse it.

---

# 20. First password-recovery fix — rejected

First implementation commit:

`386ae5215eb1766300dc288796cf2728ae0c4096`

Files/change areas included:

- `app/auth/reset-password/page.tsx`
- `app/auth/reset-password/reset-password-form.tsx`
- `lib/auth/password-recovery.ts`
- `lib/auth/password-recovery-client.ts`
- `lib/supabase/public-routes.ts`
- `scripts/remediation/legacy-password-reset.mjs`
- `scripts/remediation/password-recovery-redirect.mjs`
- related tests

Intent:

- add a real recovery page,
- make reset route public,
- use explicit redirect address,
- keep recovery client memory-only,
- add single-account targeting.

Independent Codex review **REJECTED** it for four reasons:

1. redirect validator accepted arbitrary public HTTPS domains / lookalikes,
2. recovery authorization was not cryptographically distinguished strongly enough from ordinary valid sessions,
3. global sign-out failures could be hidden while UI claimed success,
4. adversarial tests were incomplete.

This rejection prevented deployment.

---

# 21. Hardened recovery fix — approved

Hardening commit:

`907cacca5f30614eb38d538f33d08440e4e20295`

Parent:

`386ae5215eb1766300dc288796cf2728ae0c4096`

## Redirect hardening

The production recovery tool accepts only the literal URL:

`https://dashboard.bharatkarigar.com/auth/reset-password`

Rejected before network activity:

- arbitrary domains,
- lookalike subdomains,
- localhost,
- IP loopback,
- HTTP,
- wrong path,
- query/fragment variations,
- credentials in URL,
- whitespace/case/trailing-slash variants,
- other unexpected forms.

## Recovery authorization hardening

Installed Supabase JS/Auth version around this work: `2.78.0`.

Recovery flow:

- parse fragment credentials client-side,
- remove fragment from browser location,
- use isolated memory-only Supabase client,
- call verified claims path (`getClaims()`),
- require verified AMR containing `method: "recovery"`,
- URL `type=recovery` has zero authority,
- check authorization before form display,
- recheck immediately before password mutation,
- ordinary password / magic-link / OAuth / OTP sessions fail,
- missing AMR fails closed,
- forged, expired, malformed, wrong-key tokens fail closed.

## Session invalidation behavior

After password update:

- global logout/revocation is requested,
- 401/403/404/429/5xx/network errors are not silently accepted,
- if revocation cannot be confirmed, UI reports partial completion rather than false full success,
- access JWT limitation is explicitly acknowledged: already-issued access tokens may remain valid until normal expiry (3600 seconds in this release),
- JWT lifetime was not changed as part of the fix.

## Single-account recovery targeting

The recovery tool gained:

`--only-company <company_id>`

and

`--resend`

Rules:

- company must exist in reviewed manifest,
- must map to linked Auth user,
- exactly one recovery request,
- cannot widen scope to other users,
- email not printed,
- `--resend` only valid together with `--only-company`,
- fresh send is verified as newer.

---

# 22. Independent Codex second review

Second review verdict:

**APPROVE**

Codex confirmed:

- redirect finding CLOSED,
- recovery authorization finding CLOSED,
- session invalidation finding CLOSED,
- test coverage finding CLOSED,
- recovery token verification PASS,
- single-account targeting PASS,
- secret handling PASS,
- no migration,
- no unrelated login/change-password/middleware changes.

Remaining uncertainty was classified only as:

**CONTROLLED-SMOKE-ONLY**

Reason:

- Supabase docs indicated recovery AMR behavior,
- but a real production recovery JWT had not yet been observed after the new deployment.

Fail-closed outcome if AMR was absent:

- no reset form,
- no `updateUser()`,
- no weak fallback,
- other seven users untouched.

---

# 23. Recovery test/build results

Independent results around `907cacc`:

- targeted security/auth tests passed,
- full suite: **318 files**, **4,775 passed**, **4 skipped**,
- production build via `next build --webpack`: PASS,
- `git diff --check`: PASS,
- runner hash-table check: PASS,
- typecheck comparison:
  - base diagnostics = 61,
  - candidate diagnostics = 61,
  - new changed-file diagnostics = 0,
  - apparent “107” discrepancy was output-line count, not diagnostic count.

---

# 24. Supabase Auth URL configuration rollout

Rollout was deliberately staged:

1. add exact reset redirect,
2. deploy approved reset page,
3. verify `/auth/reset-password` fail-closed with no credentials,
4. set production Site URL,
5. then send one fresh recovery email.

Production values:

**Site URL**

`https://dashboard.bharatkarigar.com`

**Exact recovery redirect**

`https://dashboard.bharatkarigar.com/auth/reset-password`

Existing broader redirects such as:

`https://dashboard.bharatkarigar.com/**`

and some v0/Vercel redirects were intentionally **not removed during the smoke** because their dependencies were not fully audited.

Final cleanup of broad redirects was separated from the high-risk release.

---

# 25. Production deployment of the approved recovery commit

The user pushed the approved candidate.

A first guarded push attempt terminated iTerm because a guard used `exit 1` and the terminal profile closed on shell exit.

Diagnostic state showed:

- local HEAD = `907cacca...`
- untracked evidence folder: `docs/phase-0-security-map/production-phase0-closure-execution/`
- `origin/main` still = `e7a7cb59...`

The untracked evidence folder was preserved and not deleted.

A safer subshell push block then succeeded:

`e7a7cb5..907cacc  907cacca5f30614eb38d538f33d08440e4e20295 -> main`

The deployed route:

`https://dashboard.bharatkarigar.com/auth/reset-password`

was manually verified in browser.

Without credentials, it correctly displayed:

- “Reset password”
- “This link cannot be used.”
- “This password reset link is invalid or has expired. Ask for a new one.”

That was the expected fail-closed state.

---

# 26. Controlled smoke account

Only one account was approved for recovery testing:

**Email**

`bharatkarigar7@gmail.com`

**Reviewed company ID**

`ee53e131-a995-42d5-a925-c24787d06d1d`

This ID matched the canonical reviewed manifest.

Canonical manifest:

`docs/phase-0-security-map/legacy-password-reset/manifest.tsv`

The exact production send design required:

- approved commit,
- canonical manifest,
- `--only-company`,
- `--resend`,
- explicit production reset redirect,
- fresh timestamp immediately before sending,
- other seven users untouched,
- no revoke.

The reviewed command pattern was:

```bash
cd /Users/harshvidyarthi/Desktop/launchpad-security-w1 && \
[ "$(git rev-parse HEAD)" = 907cacca5f30614eb38d538f33d08440e4e20295 ] && \
[ -z "$(git status --porcelain -- scripts docs/phase-0-security-map/legacy-password-reset)" ] && \
T="$(date -u +%Y-%m-%dT%H:%M:%SZ)" && \
SUPABASE_URL=https://qmlbqcgisufsijmtswqk.supabase.co \
SUPABASE_ANON_KEY="$PRODUCTION_ANON_KEY" \
PASSWORD_RECOVERY_REDIRECT_URL=https://dashboard.bharatkarigar.com/auth/reset-password \
node scripts/remediation/legacy-password-reset.mjs \
  --expect-ref qmlbqcgisufsijmtswqk \
  --manifest docs/phase-0-security-map/legacy-password-reset/manifest.tsv \
  --send-recovery --reset-started-at "$T" \
  --only-company ee53e131-a995-42d5-a925-c24787d06d1d --resend
```

Important: service-role credential must already exist in terminal environment and must never be pasted into chat.

---

# 27. Final recovery smoke result

Later continuity records show the fresh controlled recovery succeeded and company sign-in passed.

Final smoke became:

1. Admin sign-in — PASS
2. Dashboard — PASS
3. Orders — PASS
4. Delhivery tracking — PASS
5. Existing order save + restore — PASS
6. Company sign-in after fresh recovery — PASS

**Final smoke: 6/6 PASS**

The remaining seven reset-client recovery emails were explicitly deferred.

No manual session/token revoke was to be performed.

---

# 28. Later exact-credential recovery continuation

After `907cacc`, the same workstream continued into a stricter recovery credential flow.

Recovered later context:

- candidate: `d1bdef40d382cea20c218f270749ad919aeb9503`
- local branch: `fix/recovery-exact-credential`
- production `main` still initially `907cacc...`
- migration `320` introduced exact-credential recovery support / supporting DB objects
- staging migration 320 verified:
  - 2 tables,
  - 8 functions,
  - forced RLS / no client policies,
  - anon/authenticated/PUBLIC denied,
  - service_role access,
  - reviewed definitions matched.
- staging gate eventually passed 15/15
- browser smoke passed 17/17
- tests showed exact-credential reset behavior, single-use consumption, old-password rejection, new-password login, cleanup.

A final staging bundle was produced:

`/tmp/password-recovery-d1bdef4-final.tar.gz`

The production rollout was deliberately gated and initially stopped before real email transport.

---

# 29. Email transport continuation

A follow-up transport commit was recorded:

`fc361fc34d644398be3bbe77a531d86163c18aef`

Sender selection included:

`connect@bharatkarigar.com`

At that point:

- no real production email had yet been sent by that candidate,
- Google Workspace delivery eligibility remained a concern,
- a transport review found an issue where unexpected post-send replies needed classification as `unknown` rather than assumed success.

This was handled as a separate transport correctness layer rather than weakening auth security.

---

# 30. Final later production closeout state

Subsequent project context records the Phase-0 production state moving to:

`1fa7c70b277daa4089dffb61521d6f38a44a99f5`

with final smoke still **6/6 PASS** and seven recovery accounts still deferred.

A final read-only closeout attempt encountered local-environment verification problems:

- release-info parsing returned null/none fields in one attempt,
- one curl command had a zsh parsing issue,
- Delhivery verify could not run because local `DELHIVERY_TOKEN_ENCRYPTION_KEYRING` / active key material was missing or invalid in that shell,
- output included `keyring is invalid` / verify exit 2 in that local context.

Then the Founder explicitly decided:

> “jitna kaam hua h ab rahne do p0 me isko ab complete close karo . rest of the things ignore karo”

Meaning:

- Phase 0 was formally closed,
- remaining closeout verification residuals were accepted/waived,
- the work was not to be reopened merely to make every final local check cosmetically perfect.

Final closeout state recorded in project context:

- production commit: `1fa7c70b277daa4089dffb61521d6f38a44a99f5`
- DB certification: PASS
- DB write freeze: OFF
- maintenance: OFF
- smoke: 6/6 PASS
- controlled recovery account: PASS
- seven recovery accounts: deferred
- session/token revoke: not performed
- `/api/release-info` local final read and Delhivery local verify: accepted as residual/waived by Founder decision.

This is the point at which Phase 0 should be considered **closed and not reopened** unless there is genuinely new production evidence of a real problem.

---

# 31. Important secret-handling history

Sensitive values appeared during the long release process. Rules after exposure:

- never repeat DB password,
- never repeat service-role key,
- never repeat maintenance bypass token,
- never print Delhivery encryption key,
- never print access/refresh/recovery tokens,
- never print user passwords.

The Founder explicitly declined DB-password rotation at that time.

The first recovery token was visible in a screenshot, but the Founder explicitly said not to revoke anything immediately.

Therefore continuity rule remains:

- do not reuse exposed link,
- do not manually revoke unless Founder changes instruction,
- do not casually rotate unrelated secrets.

---

# 32. Files explicitly referenced / created / changed in this workstream

This section lists files directly referenced or materially discussed in the conversation context. It is not a complete inventory of every file in the repository.

## Core Phase-0 map / planning docs

- `docs/phase-0-security-map/00_PHASE0_SECURITY_MAP_MASTER.md`
- `docs/phase-0-security-map/01_EVIDENCE_BASELINE_AND_METHOD.md`
- `docs/phase-0-security-map/02_TENANT_ISOLATION_CROSS_CUTTING_GUARDS.md`
- `docs/phase-0-security-map/03_STAGING_SAFETY.md`
- `docs/phase-0-security-map/98_DECISIONS_AND_APPROVALS_REQUIRED.md`
- `docs/phase-0-security-map/99_RECOMMENDED_IMPLEMENTATION_ORDER.md`
- `docs/phase-0-security-map/10H_EXECUTION_BASELINE.md`
- `docs/phase-0-security-map/10H_EXECUTION_RECORD.md`
- `docs/phase-0-security-map/266a_READINESS_AUDIT_2026-10-08.md`
- `docs/phase-0-security-map/266a_TABLE_CONTRACT_2026-10-08.md`

## Major release / review docs

- `docs/phase-0-security-map/PHASE_0_SUPERVISED_EXECUTION_PACKAGE.md`
- `docs/phase-0-security-map/PHASE_0_PRODUCTION_RELEASE_PLAN.md`
- `docs/phase-0-security-map/PHASE_0_ROLLBACK_AND_FIX_FORWARD.md`
- `docs/phase-0-security-map/PHASE_0_FINAL_REVIEW_PACKAGE.md`
- `docs/phase-0-security-map/PHASE_0_STAGING_FINAL_CERTIFICATION.md`
- `docs/phase-0-security-map/PHASE_0_FIX_FORWARD_REVIEW_FINGERPRINT_PIN.md`
- `docs/phase-0-security-map/PHASE_0_CLOSEOUT_REPORT.md`
- `docs/phase-0-security-map/RELEASE_WRITE_FREEZE.md`
- `docs/phase-0-security-map/SERVICE_ROLE_TRUST_AUDIT.md`
- `docs/phase-0-security-map/STAGING_GATE_PAUSE_HANDOFF.md`

## Bundle/runbook material

- `docs/phase-0-security-map/bundle18-runbooks/`
- `docs/phase-0-security-map/bundle18-runbooks/wave1_chain_step_core.sh`
- `docs/phase-0-security-map/bundle18-runbooks/production_only_may_remain_after_release.txt`
- release runner SHA/hash table files inside Bundle 18 runbooks

## Password-reset / recovery evidence and tooling

- `docs/phase-0-security-map/legacy-password-reset/manifest.tsv`
- `scripts/remediation/legacy-password-reset.mjs`
- `scripts/ops/legacy_password_revoke_sessions.sql`
- `scripts/remediation/password-recovery-redirect.mjs`
- `qa/security/staging-gate/legacy-password-reset.staging.mjs`
- `qa/security/staging-gate/write-freeze.staging.mjs`

## Recovery application files

- `app/auth/reset-password/page.tsx`
- `app/auth/reset-password/reset-password-form.tsx`
- `lib/auth/password-recovery.ts`
- `lib/auth/password-recovery-client.ts`
- `lib/supabase/public-routes.ts`

## Recovery tests explicitly discussed

- `lib/auth/password-recovery.logic-test.ts`
- `lib/auth/password-recovery-client.logic-test.ts`
- `app/auth/reset-password/reset-password-form.component-test.tsx`
- `scripts/remediation/password-recovery-redirect.logic-test.ts`
- `scripts/remediation/legacy-password-reset-only-company.logic-test.ts`
- `app/api/auth/auth-routes.regression.action-test.ts`
- public-route regression tests
- middleware / maintenance regression tests
- login/change-password regression tests
- log-safety tests

## Existing auth/login/change-password files inspected

- `app/api/auth/login/route.ts`
- `app/auth/login/login-form.tsx`
- `components/client/client-change-password.tsx`
- `components/admin/settings-tab.tsx`
- `components/admin/settings-form.tsx`

## Delhivery / credential hardening references

- credential-seal remediation script(s)
- production keyring/sealed-only release checks
- Delhivery setup/OAuth credential paths referenced in service-role audit

## Evidence folders / artifacts

- `docs/phase-0-security-map/production-phase0-closure-execution/`
- `docs/phase-0-security-map/phase0-final-evidence/`
- `docs/phase-0-security-map/phase0-final-staging/`
- `docs/phase-0-security-map/10h-final-evidence/`
- production backup state under `~/phase0-prod-backups/`
- release attestation files under user home, including fix-forward attestation for `e7a7cb59...`

## Master continuity files created later

- `BHARAT_LAUNCHPAD_MASTER_HANDOFF.md`
- `BHARAT_LAUNCHPAD_MASTER_HANDOFF_POLISHED(1).md`
- `BHARAT_LAUNCHPAD_MASTER_HANDOFF (1).md`
- `Pasted text(20261010-173408).txt` (a detailed Phase-0 production-release handoff snapshot)

---

# 33. Key production commands / operational patterns used

The exact secret values are intentionally omitted.

## Maintenance bypass cookie

Used to access production while maintenance mode was ON:

```js
document.cookie = "maintenance_bypass=" + "<LOCAL_TOKEN>" + "; path=/; secure; samesite=lax"
```

## Git state verification before push

Pattern:

```bash
git fetch origin main
git rev-parse HEAD
git rev-parse origin/main
git status --porcelain
```

## Safe push of approved recovery commit

Used guarded exact SHA checks and pushed only the approved HEAD to `main`.

## Single-company recovery

Used:

- `PASSWORD_RECOVERY_REDIRECT_URL=https://dashboard.bharatkarigar.com/auth/reset-password`
- `--only-company ee53e131-a995-42d5-a925-c24787d06d1d`
- `--resend`
- fresh `--reset-started-at`
- canonical manifest.

---

# 34. Known operational mistakes / pitfalls discovered

## 34.1 iTerm closed unexpectedly

Cause:

- a guard block used `exit 1` in the main shell,
- iTerm/profile closed when shell exited.

Fix:

- use a subshell `( ... )` and `exit 0` inside guards during diagnostic/push blocks so the terminal stays open.

## 34.2 Untracked evidence directory blocked clean-worktree guard

`docs/phase-0-security-map/production-phase0-closure-execution/`

was intentionally preserved.

The push guard was adjusted to distinguish tracked code changes from untracked evidence.

## 34.3 App-only maintenance was insufficient

Direct Data API writes were a release-safety problem, which is why DB write freeze controls were added.

## 34.4 Recovery link silently fell back to localhost

Root cause was not just the missing page; it was the combination of:

- no explicit `redirect_to`,
- stale Site URL behavior,
- no landing page.

## 34.5 Generic redirect validation was unsafe

“Any public HTTPS URL” was rejected as a security design. Production reset tooling now exact-matches the intended domain/path.

---

# 35. Final Phase-0 state that should be treated as authoritative now

The Founder has already chosen to close Phase 0 and ignore remaining residual closeout items.

Current authoritative outcome:

- Phase 0 = **CLOSED**
- production release = live
- DB certification = PASS
- DB write freeze = OFF
- maintenance = OFF
- final smoke = 6/6 PASS
- controlled company recovery = PASS
- seven recovery accounts = deferred
- no manual session/token revoke
- no reopening Phase 0 for waived local verification residuals unless genuinely new evidence shows a real production issue
- migration 294 remains NEVER REMOTE
- automatic RTD refund remains OFF

Final production commit recorded in the later closeout context:

`1fa7c70b277daa4089dffb61521d6f38a44a99f5`

---

# 36. Phase 1 — what comes next

After Phase 0 was formally closed, the user asked what Phase 1 contains and said the **Startup Goals Summary** is the authoritative planning source.

Phase 1 was summarized as:

> **Company Brain + Read-Only Intelligence Foundation**

Core Phase-1 areas:

1. **Company profile/context**
   - founder-managed business context,
   - company goals, constraints, operating assumptions.
2. **Connected normalized data layer**
   - unify data from Meta, Wix/Shopify, GA4, payments, inventory, WhatsApp, etc.
3. **Company Brain / cross-system reasoning**
   - one coherent context layer above operational systems.
4. **Ask AI read-only intelligence**
   - answer questions like “why did sales fall?” using cross-system evidence.
5. **Founder attention feed**
   - surface “3 things require your attention” rather than dashboards only.
6. **Recommendation foundation**
   - AI should recommend/challenge with evidence.
7. **Approval architecture foundation**
   - prepare the later Recommend → Approve → Execute model without autonomous writes yet.
8. **Outcome tracking foundation**
   - prepare measurement/learning loop, but do not prematurely build full autonomous learning.

Explicitly **not** Phase 1:

- autonomous execution,
- full Creative Studio,
- dozens of AI workers,
- complete Meta automation,
- a huge 200-capability UI,
- broad Data Pool implementation,
- unrestricted write actions.

Broad roadmap framing after P0:

P0 Security/Foundation → P1 Company Brain + Read-Only Intelligence → P2 Decisions/Recommendations → P3 Controlled Execution → P4 Measure/Learn → later proactive/OS expansion.

---

# 37. UI/product design constraint that should carry into Phase 1

The user explicitly does not want a messy interface for 200 capabilities.

Preferred response UX:

- normal text / Markdown / tables where sufficient,
- dynamic special UI only when interaction/approval truly requires it,
- AI can ask what the user wants next rather than rendering dozens of bespoke widgets,
- keep mobile-first UX simple and fast.

This should influence Company Brain / Ask AI architecture.

---

# 38. How a new session should use this context

A new ChatGPT / Claude / Codex session should treat this document as continuity, not as a request to reopen Phase 0.

Recommended opening instruction:

```text
This is the deep continuity context for Bharat Launchpad.
Read it fully before answering.
Do not restart Phase-0 planning, rerun Phase-0 migrations, reopen frozen Founder decisions, rotate secrets, revoke sessions, or send the seven deferred recovery emails unless I explicitly ask.
Phase 0 is closed by Founder decision.
Use the Startup Goals Summary as the authoritative source for Phase 1 planning.
First tell me:
1. current exact state,
2. what is already complete,
3. what residuals are intentionally deferred,
4. what Phase 1 should begin with.
```

---

# 39. Fast reference

## Product

Bharat Launchpad = AI Cofounder / decision layer for founder-led product businesses.

## Production

- App: `https://dashboard.bharatkarigar.com`
- Supabase: `qmlbqcgisufsijmtswqk`
- Staging: `tluwnketpufetxxngkzd`
- Repo: `bharatkarigar/v0-dropshipping-admin-dashboard`
- Worktree: `/Users/harshvidyarthi/Desktop/launchpad-security-w1`

## Recovery

- Reset route: `https://dashboard.bharatkarigar.com/auth/reset-password`
- Smoke email: `bharatkarigar7@gmail.com`
- Smoke company ID: `ee53e131-a995-42d5-a925-c24787d06d1d`
- Canonical manifest: `docs/phase-0-security-map/legacy-password-reset/manifest.tsv`

## Security rules

- Migration 294: NEVER REMOTE
- Do not revoke sessions/tokens unless Founder changes decision
- Do not send remaining seven recovery emails without fresh Founder approval
- Do not casually rotate Delhivery key `p1`
- Do not reopen Phase 0 only to chase waived residual verification

## Final Phase-0 outcome

- CLOSED
- DB certified
- freeze OFF
- maintenance OFF
- smoke 6/6 PASS
- recovery smoke PASS
- seven accounts deferred
- residual closeout checks waived by Founder

## Next product phase

**Phase 1: Company Brain + Read-Only Intelligence Foundation**
