> HISTORICAL / ARCHIVED CONTEXT. Superseded by canonical V10.4 for current Founder rules and by CURRENT_STATE for live wave status.

# BHARAT LAUNCHPAD — P2 PLANNING AUDIT MASTER CONTINUITY
## Full A-to-Z reconstruction for continuation in a new ChatGPT / Claude / Codex session

**Reconstruction date:** 2026-11-05  
**Project:** Bharat Launchpad  
**Founder:** Harsh Vidyarthi  
**Purpose:** Preserve the complete recoverable reasoning, scope evolution, Founder decisions, implementation/release state, regression findings, production facts, deferred work, and transition from P2 into Pre-P3.

---

# 0. IMPORTANT RECONSTRUCTION NOTE

This document is a **comprehensive reconstruction of the recoverable “P2 Planning Audit” conversation and its directly related Project evidence**.

It is intentionally not presented as a byte-for-byte/verbatim transcript of every chat turn, because the original long chat hit an `Unknown error` and was no longer reliably usable as a source surface. Instead, this file combines:

1. recoverable prior-conversation context;
2. the P2 scope audit;
3. P1/P0 continuity needed to understand P2;
4. release logs and production migration evidence;
5. later production regression context;
6. Pre-P3 audits and Founder decisions that were made as a direct continuation of P2;
7. preserved project memories and continuity state.

Where a past interpretation was later superseded, **both are preserved** and the current status is marked clearly.

Status labels used throughout:

- **HISTORICAL** — true description of what was believed/used at that time.
- **SUPERSEDED** — no longer authoritative.
- **AUTHORITATIVE** — current/frozen governing interpretation for that point in the project.
- **DEFERRED** — intentionally postponed, not forgotten.
- **PROTECTED LEGACY** — existing production capability that must not be casually broken while transforming the product.
- **UNKNOWN / GAP** — evidence could not be recovered strongly enough to claim certainty.

Do not use this file to reopen frozen decisions merely because earlier versions of the plan are also documented.

---

# 1. PRODUCT / COMPANY CONTEXT

## 1.1 Product

**Bharat Launchpad**

The product evolved from an existing multi-feature commerce operations platform into a broader SaaS / AI Cofounder operating layer for founder-led product businesses, initially Indian D2C / ecommerce merchants.

The long-term AI operating loop is:

> Understand → Analyze → Recommend / Decide → Explain → Founder Approval → Execute → Verify → Measure → Learn

The product principle is not “AI agrees with the Founder.” The AI should:

- reason from company evidence;
- challenge a decision when evidence warrants it;
- explain why;
- preserve Founder authority;
- execute only within explicit approval boundaries;
- measure whether actions actually worked;
- learn from outcomes over time.

Long-term architecture principle:

> **The systems can change. The Company Brain remains.**

Another important product constraint:

> Launchpad should become a unified business operating system where merchants can perform day-to-day work in one place instead of switching among 5–6 dashboards.

The goal is **not merely consolidated analytics** and not a giant static dashboard.

---

# 2. CORE PRODUCT GUARDRAILS THAT CARRY THROUGH P2

The pre-X-Ray/frozen product philosophy established:

- true multi-tenancy;
- companies/users/members/roles/permissions;
- strict tenant isolation;
- self-serve company creation;
- self-serve onboarding;
- self-serve connections;
- plans/subscriptions/entitlements;
- Launchpad Ready activation;
- persistent Company Brain;
- decision/recommendation layer;
- explicit approval for real-world actions;
- execution through connected systems;
- outcome measurement;
- learning loop;
- founder-focused UX;
- security/reliability/auditability.

The product should **not** become:

- a replacement for every SaaS/ERP/accounting/ad platform;
- a giant dashboard;
- an uncontrolled “add every AI feature” project;
- an autonomous company manager without Founder authority;
- a rewrite-everything project.

One-line guardrail:

> **Stay narrow strategically. Build broad internally.**

---

# 3. USER / FOUNDER WORKING PREFERENCES

The Founder repeatedly preferred:

- compact Hinglish / English explanations;
- exact copy-paste operational commands when commands are required;
- one operational step at a time;
- evidence-based status only;
- no fabricated progress;
- routine technical/security decisions delegated to Claude/Codex;
- Founder escalation only for true business, financial, irreversible, authority or scope decisions;
- production safety first;
- do not restart a frozen plan from scratch;
- preserve existing customer functionality while transforming architecture;
- pre-development test cases mandatory;
- sibling/adversarial testing;
- independent Codex approval before closure of high-risk work;
- no weakening of security/testing merely to move faster.

On 22 Oct the Founder explicitly required:

> P2 must use the same P1 development/testing/Red-Team/final Codex review process. No security/testing compromise.

---

# 4. PHASE 0 BASELINE RELEVANT TO P2

P2 was not starting from a blank application. It inherited a heavily hardened P0/P1 system.

## 4.1 Final Phase 0 authoritative state

**AUTHORITATIVE**

- Phase 0 = CLOSED.
- Production live.
- DB certification = PASS.
- DB write freeze = OFF.
- Maintenance = OFF.
- Smoke = 6/6 PASS.
- Controlled company recovery = PASS.
- Seven legacy recovery accounts = deferred.
- No manual session/token revoke.
- Migration `294` = NEVER REMOTE.
- Automatic RTD refund = OFF.
- Do not reopen P0 merely to chase waived residual local checks.

Recorded P0 closeout production commit:

`1fa7c70b277daa4089dffb61521d6f38a44a99f5`

## 4.2 Non-negotiable inherited security principles

- least privilege;
- tenant isolation;
- OAuth/token safety;
- provider policy readiness;
- privacy/data-flow controls;
- auditability;
- deletion/retention controls;
- webhook verification;
- rate limiting;
- abuse protection;
- continuous security testing;
- safe multi-tenant scaling;
- no “we will harden it later” designs.

## 4.3 Important inherited frozen decisions

Relevant examples:

- GST = platform-managed.
- Shared supplier cleanup = preserve vendor master/history and end only the second-company relationship.
- Historical RTD ₹18,163 = no action/refund/rewrite.
- ₹10 wallet drift = no adjustment.
- Automatic RTD refund = OFF.
- Old/paused client data is non-blocking unless it creates active financial loss, irreversible deletion, cross-tenant exposure, credential loss or outage.
- Delhivery credentials remain sealed.
- Do not casually rotate/delete active Delhivery encryption key `p1`.
- Do not reintroduce plaintext credentials.
- No destructive smoke tests.
- Evidence only.

These constraints remained part of the safety foundation inherited by P1/P2.

---

# 5. P1 STATE IMMEDIATELY BEFORE P2 PLANNING AUDIT

## 5.1 P1 production state

**AUTHORITATIVE at P2 planning kickoff**

Production code:

`7fc59290`

Vercel production deploy was Ready.

Production database:

- P1 migrations `322–338` applied.
- Verified at 18/18 steps.
- Release ledger marked applied.
- Phase-0 freeze controls existed but were not active.

P1 was signed off:

`P1_OPERATIONALLY_COMPLETE`

Messaging activation / Gate F was skipped and remained OFF.

Deferred P1 issues included:

- `ISS-143`
- `ISS-191`
- `ISS-192`
- `ISS-193` (where applicable in the issue series)
- `ISS-194`
- `ISS-195`
- `ISS-196`

The continuity record most consistently names `ISS-143` and `ISS-191–196`.

## 5.2 What P1 had materially introduced

P1 program had included work around:

- company membership;
- Owner/Admin/Staff roles;
- Team page;
- company invites foundation;
- entitlements;
- usage limits;
- connections/disconnect/setup foundations;
- order truth / transition service;
- stock/inventory protection;
- WhatsApp template work;
- delivery tracking restoration;
- AI Growth Hub foundations;
- regression/release runner hardening.

Important P1 decisions:

- Stock reduces only on confirmed order.
- Ignore old orders for stock.
- RTD refund remains internal.
- Delivered status can be manually editable under BK delivered.
- Staff cannot message customers.
- Owner/Admin may message customers.
- Role rollout was intentionally staged.
- Growth Hub role application was last.
- Messaging activation remained a separate go-live gate.

---

# 6. WHY P2 PLANNING BECAME CONFUSING

Several different “P2” definitions existed in project materials/conversations.

The P2 Planning Audit was necessary to answer:

> **What is the actual authoritative P2?**

The important discovery was that not every document using “P2” referred to the same company-delivery phase.

---

# 7. P2 SCOPE HISTORY — ALL MAJOR DEFINITIONS

## 7.1 Definition A — “Core Business Operations Transformation”

**HISTORICAL / UNSOURCED / SUPERSEDED AS P2**

A remembered/used definition described P2 as:

- Orders
- Products
- Vendors/Suppliers
- Delhivery/Fulfilment
- WhatsApp Operations
- Mini-Store
- Product Onboarding
- Influencers
- Finance V2

Finance V2 discussion included concepts such as:

- Product Master;
- COGS;
- order cost snapshots;
- exact product mapping;
- vendor settlement ledger;
- finance migration.

This interpretation was discussed seriously in the conversation and at one point treated as frozen.

Later audit result:

- no authoritative source document could be found for this as the official P2;
- its feature list closely resembled the frozen architecture’s **P3 operational area rebuild**;
- pulling it into P2 would invert the intended dependency sequence.

Therefore:

> **Do not treat “Core Business Operations Transformation” as the authoritative P2.**

It is useful historical context for what later operational transformation / P3 work was expected to contain.

---

## 7.2 Definition B — “P2 Decisions / Recommendations”

**HISTORICAL / CHAT-HANDOFF FRAMING / SUPERSEDED**

An earlier roadmap framing said:

> P0 Security/Foundation → P1 Company Brain + Read-Only Intelligence → P2 Decisions/Recommendations → P3 Controlled Execution → P4 Measure/Learn

Under that framing, P2 contained ideas such as:

- attention feed;
- detection;
- evidence/confidence;
- recommendations;
- expected impact;
- alternatives;
- approval workflow;
- decision records;
- prioritization;
- cross-system reasoning;
- action plans without execution.

This framing was coherent conceptually, but later evidence showed it was not the governing frozen implementation sequence.

The P1 X-Ray changed P1 itself from the handoff’s “Company Brain + read-only intelligence” framing into:

> **Product Stabilization & Foundation**

The frozen V2.1 phase plan placed Company Brain/decision-detail work later.

Therefore Definition B must be kept as historical strategy context, not the production P2 implementation authority.

---

## 7.3 Definition C — V2.1 “Self-Serve SaaS Foundation”

**AUTHORITATIVE P2**

Frozen Architecture V2.1 defined P2 as:

> **Self-serve SaaS foundation**

Key areas:

- self-serve onboarding;
- multiple companies per user;
- invitations/team activation;
- company/brand profile;
- connections / Delhivery;
- hosted address;
- plan-controlled custom domains;
- privacy records;
- plans/subscriptions/usage/entitlements.

The authoritative audit conclusion on 25 Oct:

> **P2 = V2.1 “Self-serve SaaS foundation”, minus what P1 already delivered.**

Why this won:

1. It was the only definition backed by the frozen architecture.
2. It had concrete work packages.
3. It had migration placeholders.
4. It was reaffirmed by ACR-004 dated 15 Oct.
5. P1 had already delivered portions of this scope, so the correct P2 was the **remaining delta**, not a duplicate rebuild.

---

## 7.4 Definition D — “P2 Competitive Advantage”

**NOT A COMPANY DELIVERY PHASE**

The pre-X-Ray priority rubric used labels:

- P0 Launch blockers
- P1 Core product
- P2 Competitive advantage
- P3 Scale / polish

This was a **priority classification framework**, not the same numbered implementation-phase sequence.

It should not be confused with the authoritative company roadmap.

---

# 8. GOVERNING ARCHITECTURE / FREEZE

Authoritative architecture:

**Architecture Freeze V2.1**, frozen 6 Oct 2026.

Amendments / decisions included:

- ACR-001 — WhatsApp provider decision.
- ACR-002 — Founder product decisions.
- ACR-003 — Founder product decisions / primary store requirement.
- ACR-004 — 15 Oct decision reaffirming self-serve onboarding/company/domain direction.

The Founder also established a one-time all-phase freeze:

> No scope additions or re-phasing without ACR + Founder approval.

Later authoritative broad phase sequence was recorded as:

> **P2 → P3 → P4 → P5 → P6 → P7 → P8**

P2 was to be completed/frozen before P3 was pulled forward.

On 24 Oct the Founder explicitly accepted:

> **P2 only. P3 completely deferred. No execution-layer build or real Meta/Wix/Shopify/WhatsApp writes until P2 formally freezes/closes.**

That rule is important because it prevented “while we are here” scope creep.

---

# 9. AUTHORITATIVE P2 SCOPE AT AUDIT FREEZE

The seven V2.1 packages plus the multi-company delta were reduced to the actual remaining work after P1.

## 9.1 P2-ONB — Self-Serve Onboarding

Goal:

A normal customer should be able to:

> Signup → Create Company → Configure → Connect → Activate

without routine manual database intervention.

Remaining work at audit time:

- idempotent `create_company_with_owner`;
- rate/abuse controls;
- onboarding wizard;
- company creation;
- onboarding progress;
- mandatory primary store;
- fail-closed onboarding state;
- safe defaults;
- tenant isolation.

P1 already had signup/pending foundations, but company creation was still admin/manual.

---

## 9.2 Multi-Company Switcher

P1 schema supported membership in multiple companies, but active-company selection was missing.

At audit time:

- user with several seats could be treated as ambiguous/denied;
- no clean active-company switcher existed.

Needed:

- active company state;
- secure switcher;
- resolver changes;
- no cross-company leakage;
- stale membership handling;
- all client entry points aware of active company.

This was classified **high blast radius** and should be done first/alone.

---

## 9.3 P2-TEAM — Invite Activation

P1 already had:

- `company_members`;
- Team page;
- `company_invites`;
- invite route.

Remaining activation dependency:

- invite email transport (`ISS-143`);
- activation flag/config.

Important role rule:

- Staff cannot message customers.
- Owner/Admin only for customer messaging.

---

## 9.4 P2-COMPANY — Company / Brand Profile

Goal:

Move safe brand/company fields from Founder/admin-controlled configuration to self-service.

At audit time:

- brand profile foundation existed;
- minimal settings existed;
- population/use was incomplete.

P2 needed:

- company profile;
- brand profile;
- protected vs editable fields;
- slug/routing relationship;
- business context useful to downstream AI;
- tenant-scoped edits.

---

## 9.5 P2-CONN — Connections / Delhivery

P1 already had:

- connection status;
- disconnect/setup foundations;
- client connections page;
- sealed Delhivery credentials.

But Delhivery setup remained admin-assisted.

P2 needed:

- self-serve save/test/remove;
- health/status lane;
- no credential leakage;
- preserve tracking and shipment behavior for existing clients.

---

## 9.6 P2-DOMAIN — Hosted + Custom Domain

Key Founder/product rule:

> **Domain ownership must never block onboarding.**

Every company should receive a Launchpad-hosted address first.

Custom domains are:

- optional;
- plan-controlled;
- self-serve when entitlement allows;
- ownership/DNS verified;
- safe failure-state controlled;
- existing live custom domains protected/grandfathered.

Before P2, custom domains existed but were admin-attached for roughly 4–5 stores.

---

## 9.7 P2-PRIV — Privacy Records

Before P2:

- static privacy/data-deletion pages existed;
- full privacy records/workflow layer did not.

P2 intended:

- privacy notice versions;
- consent records;
- data-rights requests;
- offboarding records;
- tenant-aware privacy state.

Legal wording itself was considered an external input and should not unnecessarily block safe schema/workflow foundations.

---

## 9.8 P2-ENT — Plans / Subscriptions / Entitlements / Usage

P1 already had:

- `company_entitlements`;
- module/limit enforcement;
- `ai_units_*`;
- `members_max`;
- usage-limits foundation.

P2 needed:

- plans;
- plan entitlements;
- company subscriptions;
- overrides;
- usage counters;
- backward-compatible `legacy_full_access` behavior/backfill.

Key audit rule:

> **No payment collection in P2.**

Payment collection required additional pricing/provider/legal decisions and was intentionally separate.

---

# 10. IMPORTANT P2 OUT-OF-SCOPE ITEMS

At authoritative P2 freeze, the following were not to be pulled into P2 merely because they were desirable:

- P3 operational area rebuild:
  - Orders UI/guard transformation
  - Products
  - Suppliers/Vendors
  - WhatsApp area rebuild
  - Influencers
  - Mini-Store area rebuild
  - Finance UI
  - broader settings shell
- new full Company Brain shell;
- decision-detail rebuild;
- Action Policy work;
- notifications/founder WhatsApp lane (later phase);
- proactive AI/provider writes;
- provider order write-back;
- outcome measurement/learning;
- 10k load testing;
- pentest/pre-GA legal gate;
- open public sign-up;
- legacy cleanup/ebook retirement;
- autonomous execution;
- full Meta automation;
- full Creative Studio;
- broad AI-worker system;
- payment collection;
- Shopify expansion that was not part of required P2 foundation;
- vendor self-onboarding;
- influencer marketplace;
- queue workers beyond bounded foundation needs;
- messaging activation/Gate F unless separately approved.

---

# 11. P2 FOUNDER DECISIONS REQUIRED AT AUDIT TIME

The P2 scope audit identified six decisions.

## F1 — Which P2 definition is authoritative?

Options considered:

- C = frozen self-serve SaaS foundation;
- A = operations transformation;
- C now, A as P3.

Recommended and later authoritative outcome:

> **C now; operations transformation belongs later/P3.**

---

## F2 — Billing in P2

Options:

- plans/subscription schema + admin assignment, no payment collection;
- include payment collection.

Authoritative direction:

> **No payment collection in P2.**

---

## F3 — Signup exposure at P2 release

Options:

- internal/invited cohort behind flag;
- open public signup.

Audit recommendation:

> Internal/invited cohort first.

Open/public launch gates belonged later unless Founder explicitly changed the phase.

---

## F4 — Messaging activation

Options:

- keep skipped Gate F out of P2;
- include BK001 pilot.

Recommended:

> Keep messaging activation out of P2.

Do not let unfinished activation machinery become a P2 blocker unless explicitly re-approved.

---

## F5 — Custom domain policy

Options:

- self-serve for selected plans, grandfather existing domains;
- remain admin-assisted.

Recommended/frozen direction:

> Self-serve, plan-controlled custom domain; existing domains protected.

---

## F6 — External activation inputs

Needed externally:

- privacy notice text;
- invite email sender/DNS if required.

Options:

- build safe placeholders/state and activate later;
- block all P2 work on external inputs.

Recommended:

> Do not block the entire P2 build on external wording/DNS inputs.

---

# 12. P1 LESSONS THAT CHANGED HOW P2 WAS TO BE EXECUTED

P1 had taken roughly 10–12 elapsed days and the Founder wanted P2 materially faster **without weakening quality**.

Recovered P1 execution pain:

- final review happened on a very large candidate;
- seven Codex rounds;
- six rejections before approval;
- late release-path threat-model hardening;
- launcher/trust-root/TOCTOU/single-use-ledger/digest/shell/ACL issues;
- messaging activation machinery built late but not used;
- large Red-Team issue count;
- repeated tests with low new information;
- mid-stream Founder decisions;
- complex migrations;
- long gate runs;
- usage-limit interruptions;
- concurrent edit contamination.

P2 improvement policy:

1. Freeze threat models and acceptance contracts before coding high-risk packages.
2. Reuse approved release tooling where possible.
3. Avoid building activation machinery that will remain OFF.
4. Do Codex-style hostile review per package before final Codex.
5. Positive controls required for security tests.
6. One builder per file family.
7. No edits during gate runs.
8. Founder decisions before implementation.
9. Smaller non-overlapping workstreams.
10. Preserve critical/security tests even when optimizing speed.

Important Founder instruction:

> Do **not** change P1 process mid-P1 just to optimize P2. Apply process improvements at P2 kickoff.

---

# 13. PRE-DEVELOPMENT TEST PLAN FOR P2

The audit required coverage before implementation.

## Mandatory categories

### Core happy paths

Prove end-to-end:

- create company;
- switch company;
- invite;
- profile;
- Delhivery;
- domain;
- consent;
- plan.

### Regression

Preserve:

- entire P1 gate suite;
- Mini-Store enquiry → supplier → order path;
- live custom-domain stores;
- order/inventory truth;
- role behavior;
- AI Growth Hub existing functionality;
- broadcast/tracking jobs.

### Tenant isolation

Test:

- switcher leakage;
- wrong-company invite;
- domain hijack;
- active-company confusion;
- stale membership.

### Authorization / RLS

Test:

- SECURITY DEFINER create-company function;
- Owner/Admin/Staff matrix;
- entitlement enforcement;
- direct PostgREST access.

### Financial / inventory invariants

P1 order truth must remain intact.

### Idempotency / concurrency

Test:

- duplicate company creation;
- concurrent invite accept;
- domain verification races.

### Provider failure

Test:

- Vercel failure/timeout;
- Delhivery failure;
- email transport failure.

### Stale state

Test:

- company switch mid-request;
- revoked membership;
- stale session.

### Migration / backward compatibility

Require:

- expand-only where possible;
- `legacy_full_access` parity;
- mutation testing per migration;
- old clients unaffected.

### Mobile UX

Widths:

- 320
- 390
- tablet

Dark mode and headless browser tests were expected.

### Privacy / security

- consent versioning;
- masking;
- abuse/rate limits.

### Log / secret safety

- no credentials;
- no DNS verification secrets;
- sealed fields preserved.

### Rollback / fix-forward

- pinned rollback/fix-forward;
- release rehearsal.

### Adversarial / sibling

- positive controls mandatory.

---

# 14. BLAST RADIUS / EXECUTION ORDER LOGIC

High-risk sequence:

## 14.1 Multi-company first

Touched:

- every tenant entry point;
- session resolver;
- membership;
- Ask AI owner resolution;
- Growth Hub owner resolution;
- legacy owner checks.

Therefore:

> **Do first and alone.**

## 14.2 Onboarding after switcher

Create-company flow depended on:

- membership;
- entitlement defaults;
- active company;
- profile state.

## 14.3 Domains isolated from storefront regressions

Domains touched:

- Vercel domain actions;
- host routing;
- Mini-Store domain resolution;
- live stores.

Therefore:

> no concurrent storefront refactor.

## 14.4 Delhivery isolated from fulfilment regressions

Existing tracking and shipment behavior must continue.

---

# 15. RELEVANT CRONS / BACKGROUND JOBS THAT MUST NOT BREAK

The P2 audit explicitly remembered ongoing operational workers such as:

- tracking;
- broadcast worker;
- broadcast producer;
- broadcast scheduler;
- journey worker (OFF where intentionally disabled);
- AI history-related jobs.

Existing operational crons were not to be casually rewritten as part of P2 self-service work.

---

# 16. P2 IMPLEMENTATION / RELEASE EVOLUTION

P2 eventually moved beyond the original seven-package schema and the final production candidate contained a larger hardened migration set.

Final production baseline:

`7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`

Short SHA:

`7f3cf5f1`

Commit description visible in release evidence:

`fix(release): pin only the first four audit partitions (F1 Red-Team B1/O1)`

The release candidate was handled through a guarded release process, not an ordinary direct migration push.

---

# 17. FINAL P2 PRODUCTION MIGRATION CHAIN

Production apply-all evidence recorded **23/23 steps fully applied and verified**.

Final migration list:

1. `339_jobs_queue.sql`
2. `340_rate_limits_budgets.sql`
3. `341_company_feature_flags.sql`
4. `342_audit_events.sql`
5. `343_provider_webhook_events.sql`
6. `344_active_company.sql`
7. `345_plans_subscriptions.sql`
8. `346_company_profile_fields.sql`
9. `347_company_brain_entries.sql`
10. `348_privacy_records.sql`
11. `354_routing_slugs.sql`
12. `355_custom_domain_requests.sql`
13. `350_store_connections.sql`
14. `352_company_pickup_locations.sql`
15. `351_canonical_commerce.sql`
16. `353_ai_data_access_settings.sql`
17. `358_shopify_installation_lifecycle.sql`
18. `359_team_invites_activation.sql`
19. `356_vendor_client_delhivery_channels.sql`
20. `357_protect_order_shipment_columns.sql`
21. `360_delete_client_orders_checked.sql`
22. `361_self_serve_onboarding.sql`
23. `362_revoke_inventory_trigger_function_grants.sql`

Final recorded release state:

> state: prefix 23 of 23 steps  
> fully applied migrations: 23 of 23  
> verified against expected state

And:

> **OWNER PARITY PASSED — 0 violations, 10 linked companies**

This is a key production fact.

---

# 18. WHAT THE FINAL MIGRATION SET TELLS US ABOUT P2

The final migration set shows P2 became more robust than the initial placeholder migration list.

It covered foundations for:

- queue/job safety;
- rate limits and budgets;
- feature flags;
- audit events;
- provider webhook events;
- active company;
- plans/subscriptions;
- company profile;
- Company Brain storage foundation;
- privacy records;
- routing slugs;
- custom-domain requests;
- store connections;
- pickup locations;
- canonical commerce structures;
- AI data-access settings;
- Shopify installation lifecycle;
- team invite activation;
- vendor/client Delhivery channels;
- order/shipment column protections;
- guarded client-order deletion;
- self-serve onboarding;
- inventory trigger grant revocation.

Important interpretation:

These are **foundational capability/data/security surfaces**. Their existence does **not** automatically mean every later operational UX or autonomous/provider write behavior became part of P2.

---

# 19. RELEASE TOOLING / AUTHORITY MODEL

P2 reused a highly controlled release model inherited from P1.

Important properties:

- exact candidate SHA;
- signed Founder approval;
- separate execution artifact;
- independent Codex attestation;
- pinned migration hashes;
- trust anchor;
- installed launcher digest verification;
- release ledger;
- explicit command-class authorization;
- operator separation expectations.

A particularly important safety property was proven:

> An approval for one command class did not authorize another command.

Example:

A Founder approval signed for `apply` was used with `production status`.

The launcher correctly refused:

> `AUTHORITY REFUSED: the Founder release approval is signed for another command class`

And:

> nothing was executed, nothing was done

This should be preserved as a security invariant.

---

# 20. FOUNDER RELEASE KEY ROTATION

During P2 release work, the Founder signing key was rotated.

Old fingerprint:

`SHA256:/1xSI+cEcBmPbYkgfenixfTACsQXKGDbLHfl1B4Cxg0`

New fingerprint:

`SHA256:eda/D5AhvxSsOE6vQVMVeOL+6VZeVSKeP2syF08a7c0`

The old trust anchor/archive was intentionally retained to verify historical P1 evidence.

Important later finding:

A rotation verification attempt failed because the release operator was also in the admin group, violating the intended distinct/non-admin operator separation.

Interpretation:

- key rotation itself occurred;
- operator-separation verification exposed a real governance issue;
- historical evidence must remain verifiable;
- do not weaken role separation just to satisfy tooling.

Do not include or expose private signing key material or passphrases in future continuity docs.

---

# 21. P2 PRODUCTION RELEASE RESULT

Recovered authoritative production outcome:

- candidate: `7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`
- 23/23 migrations applied and verified;
- release ledger marked applied;
- owner parity 0 violations across 10 linked companies;
- production state used as later Pre-P3 audit baseline.

The user/project later treated P2 as:

> **P2 CLOSED**

and:

> **100% / 12 of 12 packages**

Where package labels were used operationally in status reporting, future sessions should preserve the closure status even if package-level subdocuments are unavailable.

Do **not** reopen P2 simply because a later phase finds legacy cleanup or P3 design work.

Only reopen P2 for:

- genuine blocking regression;
- security problem directly caused by P2;
- cross-tenant isolation issue introduced by P2;
- critical page/API broken by P2;
- unexpected activation caused by P2.

---

# 22. PROVIDER EXECUTION — IMPORTANT CORRECTION

During production regression, a mistaken assumption appeared:

> Provider execution being Enabled might be a blocker.

Founder correction:

> **Provider execution being Enabled is intentional and Founder-approved. Do NOT treat that as a blocker.**

Expected behavior:

- Growth Hub may show `Provider execution — Enabled`.
- UI should load.
- State should be internally consistent.
- Do not trigger unsafe provider writes merely to test it.
- Enabled state alone = **PASS**, not failure.

For regression:

- read-only verification is safe;
- no provider write/execution action unless clearly read-only or explicitly safe/approved.

This is a frozen interpretation for the P2 regression state.

---

# 23. P2 PRODUCTION REGRESSION — REMAINING AREAS THAT WERE EXPLICITLY TESTED/REQUESTED

After correcting the provider-execution misunderstanding, the remaining production regression areas were:

1. Company Profile
2. Plans / Entitlements
3. Trusted Commerce Data
4. Hosted / Custom Domains controls
5. Self-Serve Onboarding dark-state
6. Shopify / Wix regression
7. Analytics
8. Payments
9. Wallet

Regression rule:

P2 remains closed unless a **real blocking regression** exists.

Valid blockers:

- security issue;
- data isolation problem;
- broken existing flow;
- unexpected activation;
- failed critical page/API.

Not blockers:

- Provider execution intentionally ON;
- intentionally dark/inert future functionality;
- planned later-phase work;
- old business logic scheduled for later replacement, unless actively unsafe.

---

# 24. SELF-SERVE ONBOARDING DARK-STATE PRINCIPLE

The product may contain schema/UI foundations for self-serve onboarding while public activation remains controlled.

Do not equate:

> “foundation exists”

with:

> “public acquisition is fully enabled.”

The expected P2 safety posture allowed:

- implemented flows;
- guarded cohort;
- feature flags;
- dark/inert state;
- internal/invited activation.

Public exposure remained governed separately.

---

# 25. COMPANY PROFILE / PLAN / DOMAIN PRE-P3 MODEL

By the Pre-P3 continuation, Flow 2 was described as:

> Company Profile → Plan / Entitlements → Hosted Store Address → optional Custom Domain

Key product rule:

> **A merchant should never be blocked from onboarding because they do not own a domain.**

End-state expectations:

- system knows company identity;
- merchant sees only entitled modules;
- default hosted storefront resolves;
- custom domain can be configured when entitlement allows.

Old Founder/admin setup was to become merchant-facing self-service while protected platform fields remained protected.

---

# 26. MCP VS DIRECT API STRATEGY

Frozen integration strategy:

> **Hybrid — MCP first where official/capable; direct API where MCP is incomplete, unavailable or insufficient for deeper control.**

Goals:

- avoid duplicating integration effort;
- preserve capability depth;
- reduce custom maintenance where provider MCP is reliable;
- keep ONE-CONNECT UX;
- do not force the merchant through unnecessary double authorization.

Providers considered included:

- Wix
- Meta
- Shopify

Important:

This was an architecture/integration strategy, not permission to bypass provider security or platform review requirements.

---

# 27. CURRENT PRODUCT TRUTH AROUND SHOPIFY / WIX

Later Founder decision on 4 Nov:

> **Shopify/Wix are source of truth.**

Additional decisions:

- no manual products/orders where provider is canonical;
- normalized synced copy is allowed inside Launchpad;
- vendor assignment remains at order level;
- provider COGS only where relevant;
- inventory is read/sync-oriented;
- current Vendor Wallet/Payment concept should be removed and future vendor payments designed fresh.

This is a major forward-looking constraint for P3/legacy cleanup.

---

# 28. SIX FOUNDER DECISIONS APPLIED IN PRE-P3 CONTINUATION

The Pre-P3 foundation/orders audit explicitly states that it applied six Founder answers from 4 Nov.

Recovered decisions:

1. **Realized revenue basis**  
   Revenue recognition should follow realized/completed business truth, not merely provisional/shipped/Meta-attributed values.

2. **P2 provider tables only**  
   Preserve the provider foundation delivered in P2; do not inflate the cleanup into a new provider-execution architecture.

3. **Separate `mini_store` AI control**  
   Mini-Store data/AI control should be separately addressable rather than hidden inside a broad catch-all provider permission.

4. **Influencer ledger removal**  
   Old influencer-ledger logic should not be preserved merely because it exists.

5. **Mini-Store + catalog included in export**  
   Data export/privacy behavior must account for Mini-Store/catalog data.

6. **Shopify/Wix commercial facts read-only**  
   Commercial facts originating from Shopify/Wix should not be manually mutated as if Launchpad were the source of truth.

These decisions should be carried into P3 planning and cleanup.

---

# 29. PRE-P3 FOUNDATION / ORDERS AUDIT — VERIFIED PRODUCTION FACTS

Audit baseline:

`7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`

Mode:

- planning/read-only;
- no code;
- no migration;
- no cron/webhook/flag/ACR/data changes.

## 29.1 Broad conclusion

Across 58 assessed capabilities:

- 29 keep as-is;
- 19 adapt;
- 5 supersede/remove;
- 4 need retesting;
- 1 needs verification.

The key point:

> P0/P1/P2 foundations largely survive. What changes is legacy business logic, not the safety foundation.

Keep:

- tenant isolation;
- RBAC;
- memberships;
- entitlements;
- connections;
- provider layer;
- domains;
- onboarding;
- privacy;
- transition service.

---

# 30. ORDER TRUTH FINDINGS BEFORE P3

## 30.1 P1 order dimensions exist but are not active as live data truth

On 707 orders:

- `commerce_status` = NULL on 707/707;
- `after_sale_status` = NULL on 707/707;
- `delivery_status` had only 3 values (`lost`).

Operational truth was still primarily carried by:

`bk_status`

Problem:

`bk_status` mixed:

- business states;
- shipping states;
- custom labels.

The audit identified a canonical-status decision before P3.

Recommended cleanup default:

> Keep `bk_status` as operational truth for the cleanup and defer a full status-dimension redesign to P3.

Reason:

Activating/backfilling new canonical dimensions would touch every status screen and test and would expand cleanup into redesign.

---

# 31. `client_price` FINDING

On all 707 production orders:

`client_price` was NULL.

The value was computed at runtime from legacy `products.bk_price`.

Implication:

Deleting the unused column would remove no populated order data, but any change still needs downstream dependency review.

---

# 32. `protect_order_columns` AS A REAL SECURITY BOUNDARY

Production audit found:

- `authenticated` had broad table grants on `orders`;
- RLS policies allowed direct PostgREST mutations for allowed actors;
- therefore app-only validation was insufficient.

Important rule:

> **Shopify/Wix commercial facts read-only must be enforced at DB boundary (`protect_order_columns` or equivalent), not merely in UI/server route code.**

This is critical for P3 architecture.

---

# 33. LATENT CROSS-TENANT READ ISSUE

Policy:

`users_view_own_orders`

Behavior:

Allows SELECT where order `customer_email` equals caller profile email.

Current observed matches:

- 73 orders;
- all currently matched either the admin or correct owners;
- no actual cross-company exposure was observed in the sample.

But conceptually:

> this is a live latent cross-tenant read path.

It was known as item S12 and originally deferred to P8.

Audit recommendation was to consider removing it earlier because the Founder wanted the foundation solid before P3.

Important distinction:

- it is **not evidence that P2 introduced a cross-tenant leak**;
- it is legacy security debt discovered during Pre-P3 review.

---

# 34. MINI-STORE MANUAL DISPATCH / REALIZED REVENUE

Observed:

- 18 in-transit Mini-Store orders;
- all were manually dispatched;
- `current_status = 'Manual Dispatch Created'`;
- none had delivered date.

Under the accepted realized-revenue rule:

> Mini-Store realized revenue is approximately ₹0 until merchant delivery confirmation occurs.

The confirmation path existed:

- client can set delivered;
- `client_manual` stamp.

But audit found it had not been used for those orders.

This must be considered when building company analytics/revenue truth.

---

# 35. LEGACY `orders.source` DEFAULT

Audit finding:

`orders.source` defaulted to:

`google_sheet`

This is a legacy marker.

It conflicts with a future invariant like:

> no writer can create a legacy-source order unless it is genuinely from that source.

P3/cleanup must fix source truth rather than silently relying on a historical default.

---

# 36. SHOPIFY/WIX ADDRESS CORRECTION CONFLICT

Existing route:

`/api/orders/update-customer`

could mutate customer/address details.

Potential conflict:

If Shopify/Wix provider facts are canonical/read-only, an internal address correction may modify provider-owned facts in Launchpad.

P3 must define:

- which customer fields are provider-owned;
- which are Launchpad-operational overlays;
- whether corrections are local overlays or provider writes;
- whether provider write-back is ever allowed and under what approval.

Do not leave this ambiguous.

---

# 37. TIMESTAMP CONSISTENCY ISSUE

Order status timestamp family such as:

- `confirmed_at`
- other status-time fields

used `timestamp without time zone`.

Other fields such as:

- `created_at`;
- delivery stamps

used `timestamptz`.

Risk:

- UTC vs IST bucketing may disagree;
- analytics/revenue by date can drift.

This was a Pre-P3 cleanup/design concern, not a reason to rewrite P2 history.

---

# 38. TRUSTED COMMERCE DATA PRINCIPLE

The later regression/audit language “Trusted Commerce Data” should be interpreted as:

- provider truth clearly separated from Launchpad operational overlays;
- canonical source known;
- protected commercial facts;
- tenant scoped;
- no accidental manual mutation;
- normalized copies allowed;
- data provenance available to AI;
- analytics do not mix provisional and realized truth silently.

This is especially important for:

- orders;
- revenue;
- COGS;
- fulfillment;
- inventory;
- provider attribution.

---

# 39. ANALYTICS PRINCIPLE

Analytics must distinguish:

- Meta-claimed purchases;
- actual store orders;
- paid orders;
- COD/unpaid orders;
- paid cash revenue;
- provisional COD revenue;
- cash ROAS;
- Meta ROAS;
- freshness/sync state.

This principle existed in Growth Hub design and continues into later trusted-company-data work.

Never let a marketing platform’s claimed conversions silently become company financial truth.

---

# 40. PAYMENTS / WALLET DIRECTION

Historical platform had wallet/payment/refund concepts.

Later Founder decision:

> Remove current Vendor Wallet/Payment and build future vendor payments fresh.

Carry forward:

- do not preserve wrong legacy finance business logic merely because tables exist;
- preserve audit/history where legally/operationally necessary;
- redesign future vendor payment/settlement around actual product requirements;
- Launchpad should not casually become a money-transfer intermediary unless explicitly intended.

P0 frozen RTD/history decisions remain respected.

---

# 41. ROLE / PERMISSION MODEL

Known role model:

- Owner
- Admin
- Staff

Important frozen operational rule:

- Staff cannot message customers.
- Owner/Admin can message customers.

Entitlements should be server-enforced.

Environment flags remain global kill switches.

Legacy screens may remain more restricted until migrated.

No client should gain access merely because a UI element is hidden/shown incorrectly.

---

# 42. EXISTING CLIENT BACKWARD COMPATIBILITY

P2 transformation principle:

> Existing clients must not lose working production capabilities during SaaS conversion.

Examples:

- `legacy_full_access` / entitlement parity;
- existing live custom domains grandfathered;
- Mini-Store path preserved;
- Delhivery tracking preserved;
- existing order truth preserved;
- no blind schema rewrite;
- expand-first, migrate safely;
- protect old customers while introducing self-service.

---

# 43. TESTING GOVERNANCE

The Founder required:

- pre-development test cases;
- Claude adds sibling/adversarial cases;
- continuous security tests;
- provider compliance tests;
- third-party policy readiness;
- independent Codex review;
- no task “closed” before review;
- evidence over claims.

Future legal/governance pages planned in broader program included:

- Privacy;
- Terms;
- Cookie;
- DPA;
- Subprocessors;
- Security & Trust;
- AUP;
- Billing/Refunds;
- Deletion/DSR.

Not all legal-page drafting was a P2 implementation blocker.

---

# 44. CLAUDE VS CODEX RESPONSIBILITY MODEL

During P1/P2 program the practical governance evolved into:

## Claude

- primary implementation/orchestration;
- code changes;
- task execution;
- test creation;
- sibling/adversarial test expansion;
- status updates;
- documentation.

## Codex

- independent review;
- security review;
- hostile/adversarial validation;
- release candidate review;
- final approval/REJECT gate;
- regression where independently valuable.

Founder did not want free coding models used as the main coding authority.

---

# 45. P2 RELEASE / PRODUCTION SAFETY RULES

Do not weaken:

- exact SHA verification;
- clean worktree/candidate;
- signed authority;
- independent review;
- pinned migration hashes;
- command-purpose binding;
- owner/tenant parity;
- release ledger;
- backup/rollback/fix-forward evidence;
- no destructive smoke;
- no unrelated production writes during verification.

---

# 46. WHAT LOOKED LIKE A BLOCKER BUT WAS NOT

## 46.1 Provider execution = Enabled

Not a blocker. Founder-approved.

## 46.2 Intentional dark-state functionality

Not a blocker by itself if:

- safe;
- internally consistent;
- activation intentionally deferred.

## 46.3 Later-phase feature missing

Not a P2 blocker if explicitly P3+.

## 46.4 Legacy cleanup debt

Not necessarily P2 blocker unless it creates:

- security exposure;
- data loss;
- isolation failure;
- broken existing flow;
- unexpected active behavior.

---

# 47. WHAT WOULD HAVE KEPT P2 OPEN

P2 should only remain open for a genuine blocker such as:

- production security regression;
- cross-tenant isolation failure;
- critical existing flow broken;
- unexpected feature activation;
- critical page/API failing;
- release evidence not matching actual deployed state;
- migration inconsistency;
- P2-introduced data corruption.

---

# 48. FINAL P2 AUTHORITATIVE STATE

**AUTHORITATIVE**

P2 should be treated as:

> **CLOSED**

Production baseline:

`7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`

Production migrations:

> **23/23 applied + verified**

Owner parity:

> **0 violations across 10 linked companies**

Provider execution:

> **Enabled intentionally; PASS condition by itself**

Scope that P2 established:

- self-serve SaaS foundation;
- active-company foundation;
- plans/subscriptions/entitlements;
- profile foundation;
- privacy;
- routes/slugs;
- domains;
- store/provider connections;
- canonical commerce foundation;
- AI data-access settings;
- Shopify installation lifecycle foundation;
- team invites activation;
- Delhivery channel foundations;
- order/shipment protections;
- safe deletion path;
- self-serve onboarding foundation;
- inventory trigger permission tightening;
- queue/rate-limit/feature-flag/audit/webhook foundations.

P2 should **not** be reopened merely to reclassify later P3 work as unfinished P2.

---

# 49. P3 AND LATER — WHAT WAS INTENTIONALLY LEFT FORWARD

The exact later-phase labels evolved, but the following were not meant to be silently dragged back into P2:

## P3-style operational transformation

- Orders redesign/operational truth cleanup;
- Products;
- Suppliers/Vendors;
- WhatsApp operational area;
- Mini-Store operational area;
- Finance rebuild;
- settings/business operations shell;
- canonical business/shipping status model;
- provider-truth overlays;
- deeper operational workflows.

## Later phases

- notifications/founder alerts;
- proactive AI;
- broad provider write execution;
- outcome measurement;
- learning;
- public GA scale;
- load/pentest gate;
- deep legacy cleanup;
- autonomous expansion.

---

# 50. VERY IMPORTANT: PRE-P3 IS NOT “REOPEN P2”

After P2 close, the project began audits to answer:

> What must be cleaned/reconciled before P3 builds on top of the foundation?

That work may identify old problems.

Examples:

- `users_view_own_orders`;
- legacy `orders.source`;
- mixed timestamp types;
- unused order columns;
- old wallet/payment logic;
- manual-dispatch realized-revenue ambiguity.

These findings belong to:

- Pre-P3 cleanup;
- P3 design;
- security debt remediation;

unless evidence proves P2 itself caused them.

---

# 51. CURRENT PRE-P3 DECISION DIRECTION

The immediate Pre-P3 foundation/orders audit recommended:

- preserve P0/P1/P2 safety foundations;
- remove/supersede wrong finance business logic rather than rewrite foundation;
- use `bk_status` temporarily instead of redesigning all status dimensions during cleanup;
- protect provider-owned commercial facts at DB level;
- close latent cross-tenant read paths earlier if approved;
- define realized Mini-Store revenue correctly;
- fix source provenance;
- establish timestamp/date consistency before analytics depends on it.

---

# 52. DO NOT DO

Future sessions must **not**:

1. restart P2 planning from scratch;
2. call “Core Business Operations Transformation” the authoritative P2;
3. call the old “P2 Decisions/Recommendations” framing the authoritative delivery phase;
4. reopen P0 waived residuals;
5. rerun P0 migrations;
6. apply migration 294 remotely;
7. rotate secrets casually;
8. expose signing/private keys/passphrases;
9. reintroduce plaintext provider credentials;
10. treat Provider Execution = Enabled as a failure;
11. perform provider writes merely to prove the flag is enabled;
12. duplicate capabilities P1/P2 already delivered;
13. break existing clients while building future architecture;
14. assume Shopify/Wix synced data may be manually edited as Launchpad truth;
15. preserve old Vendor Wallet/Payment simply because it exists;
16. treat a later-phase missing feature as a P2 closure failure;
17. loosen tenant/RLS/security boundaries for speed;
18. call a task complete without required review/evidence;
19. silently merge conflicting roadmap definitions;
20. build P3 execution while pretending it is P2 foundation work.

---

# 53. FROZEN / HIGH-CONFIDENCE FOUNDER DECISIONS TO CARRY FORWARD

1. P2 authoritative scope = frozen V2.1 self-serve SaaS foundation, minus P1 delivery.
2. P3 was deferred until P2 close.
3. P2 must keep P1 security/testing quality.
4. Existing clients must be protected.
5. Every client should have a Launchpad-hosted address; domain ownership cannot block onboarding.
6. Custom domains are plan-controlled/self-serve capability.
7. Hybrid MCP + API strategy.
8. One-connect UX preferred.
9. Provider execution Enabled is intentional.
10. Shopify/Wix are source of truth for their commercial data.
11. Normalized synced copies are allowed.
12. No manual provider products/orders as canonical truth.
13. Vendor assignment remains order-level.
14. Current vendor wallet/payment logic is not the future design.
15. Realized revenue must follow actual business truth.
16. Mini-Store AI access should be separately controllable.
17. Influencer ledger can be removed rather than preserved blindly.
18. Mini-Store/catalog must be included in data export/privacy coverage.
19. Shopify/Wix commercial facts must remain read-only unless a separately authorized provider-write workflow exists.
20. Staff cannot message customers; Owner/Admin only.
21. No autonomous execution without approval architecture.

---

# 54. SOURCE / PROVENANCE INDEX USED FOR THIS RECONSTRUCTION

Major recoverable sources included:

## P0 continuity

- `BHARAT_LAUNCHPAD_DEEP_CONTEXT_FULL_CHAT_2026-10-11.md`

## P2 scope authority

- `BHARAT_LAUNCHPAD_P2_SCOPE_AUDIT_2026-10-25.md`

## Release / production evidence

- `Pasted markdown.md`
- `Pasted markdown(4).md`
- `Pasted markdown(5).md`
- `Pasted text(20261104-085502).txt`

## Pre-P3 continuation

- `Bharat_Launchpad_PreP3_Foundation_and_Orders_Audit_2026-11-05.md`
- `Bharat_Launchpad_Flow_2_Company_Plans_Domain_PreP3.pdf`

## Product baseline / strategy

- `Bharat_Launchpad_Pre_XRay_Detailed_Report.pdf`
- `Bharat_Launchpad_Gemini_Deep_Research_Master_Prompt.md`
- `Bharat_Launchpad_Product_Philosophy.pdf`

## Recoverable prior-conversation context

Included:

- 22 Oct instruction that P2 must preserve P1 testing/security process;
- historical “Core Business Operations Transformation” interpretation;
- 24 Oct “P2 only, P3 deferred” instruction;
- 25 Oct scope audit/freeze;
- 4 Nov production closure/regression state;
- 4 Nov Founder commercial/provider decisions;
- 5 Nov Pre-P3 continuation.

---

# 55. KNOWN CONTINUITY GAPS

The original `P2 Planning Audit` chat itself became error-prone and could not be exported as a literal turn-by-turn transcript.

Therefore this file intentionally avoids claiming:

- exact wording of every single user/assistant turn;
- every temporary task percentage update;
- every intermediate Claude message;
- every transient commit that did not become part of retained project evidence;
- every status-site text revision.

Where exact source evidence was recoverable, exact IDs/numbers were preserved.

This document should be treated as:

> **the best available authoritative continuity reconstruction, not a forensic verbatim transcript.**

If a future source file contains stronger evidence that conflicts with this file, do not silently overwrite history. Record:

1. old claim;
2. new evidence;
3. authoritative resolution;
4. whether an ACR/Founder decision is required.

---

# 56. CURRENT AUTHORITATIVE P2 STATE — QUICK SNAPSHOT

## Phase status

**P2 = CLOSED**

## Production baseline

`7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`

## Database

- 23/23 P2/closure migrations fully applied and verified.
- Owner parity 0 violations / 10 linked companies.

## Provider execution

**Enabled intentionally. Not a blocker.**

## P2 core outcome

Self-serve SaaS/data/security foundation is in place sufficiently for the program to move to Pre-P3/P3 work.

## Not a reason to reopen P2

- legacy cleanup;
- P3 operational redesign;
- future finance/payment rebuild;
- later provider writes;
- public GA;
- learning loop.

---

# 57. INTENTIONALLY DEFERRED / P3+

Keep separate from P2 closure:

- operational Orders redesign;
- provider-truth operational overlay model;
- full products/suppliers/operations transformation;
- full finance rebuild;
- new vendor payments design;
- proactive AI;
- provider write-back;
- learning/outcomes;
- public-scale launch gates;
- 10k load/pentest;
- deep legacy cleanup;
- autonomous execution.

---

# 58. NEXT VALID ACTION

The next valid program action is **not to re-plan P2**.

It is:

> Continue the Pre-P3/P3 foundation audit and convert the verified findings + Founder decisions into the frozen P3 implementation plan.

The P3 plan should:

1. start from production `7f3cf5f1...`;
2. preserve P0/P1/P2 foundations;
3. resolve canonical order/commercial truth;
4. separate provider truth from Launchpad overlays;
5. clean legacy security/business-logic debt before building new execution;
6. keep tenant isolation and DB-level write protection;
7. preserve exact Founder decisions on Shopify/Wix, Mini-Store, revenue, vendor payment and data access;
8. write tests before implementation;
9. use independent Codex review;
10. avoid reopening completed phases without new evidence.

---

# 59. NEW CHAT BOOTSTRAP INSTRUCTION

Copy the following into any new ChatGPT / Claude / Codex session together with this file:

```text
This file is the master continuity reconstruction for the Bharat Launchpad
“P2 Planning Audit” conversation and its direct continuation into Pre-P3.

Read it fully before proposing any work.

Treat the document’s AUTHORITATIVE sections as the current project state.
Treat HISTORICAL and SUPERSEDED sections as context only.

Do not:
- restart P2 planning,
- reinterpret old P2 definitions as current,
- reopen Phase 0,
- rerun old migrations,
- treat Provider Execution = Enabled as a blocker,
- pull P3 work backward into P2,
- weaken testing/security,
- break existing clients.

P2 is closed at production baseline:
7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b

Production evidence:
- 23/23 migrations applied + verified
- owner parity 0 violations / 10 linked companies
- provider execution Enabled intentionally

Before continuing, tell me only:
1. what P2 ultimately became,
2. what P2 completed,
3. what is intentionally P3+,
4. what Pre-P3 risks are currently known,
5. what the next valid action is.

Then continue from the Pre-P3/P3 state rather than planning P2 again.
```

---

# 60. FAST REFERENCE

## Project

Bharat Launchpad

## Founder

Harsh Vidyarthi

## Core product

AI Cofounder / unified business operating layer for founder-led product businesses.

## Production application

`https://dashboard.bharatkarigar.com`

## Supabase production project

`qmlbqcgisufsijmtswqk`

## Staging project

`tluwnketpufetxxngkzd`

## Repository

`bharatkarigar/v0-dropshipping-admin-dashboard`

## P0

CLOSED

## P1

`P1_OPERATIONALLY_COMPLETE`

P1 production baseline before P2:

`7fc59290`

## P2 authoritative meaning

**Self-serve SaaS foundation minus P1-delivered work**

## P2 final production baseline

`7f3cf5f1a45bc0d4fa8de50b7e05b5be9730509b`

## P2 DB result

23/23 applied + verified

## Owner parity

0 violations / 10 linked companies

## Provider execution

Enabled intentionally

## Current program position

**P2 CLOSED → Pre-P3/P3 audit/planning**

---

# END OF MASTER CONTINUITY