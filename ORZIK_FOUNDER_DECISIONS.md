# Orzik Shopify — Founder decisions and constraints (through 23 Nov 2026)

This is a dated addendum for the **new Orzik Shopify Public App**, not a rewrite of canonical Bharat Launchpad V10.4 decisions. The evidence and latest state are in [the A-to-Z chronology](evidence/ORZIK_SHOPIFY_A_TO_Z_CONTINUITY_2026_11_23.md).

## Brand and application boundaries
1. Use **Orzik**, tagline **Your AI Cofounder**, main public brand **orzik.co**, app host **app.orzik.co**. Do not migrate live legacy merchants or force old app installs.
2. **Only new Orzik Shopify app**, org **249330912**, app **450606792705**. **Never touch** old org 243933135 / app 450405007361. Earlier test-0o3wx8jg.myshopify.com not an authorized Orzik dev-store target.
3. Authorized Shopify development store: **orzik-qa.myshopify.com** only; existing in org 249330912. QA SaaS company **ZZZQA-PRODSMOKE-001**, never the ten real merchant companies. Its full verified UUID must be copied from trusted source, not guessed from abbreviated reports.
4. Shopify requested read and write scopes; existing 10-scope list reviewed; offline expiring tokens and customer-redaction protections need actual QA validation. Orders retained up to customer redact where agreed, and redact scrubs PII per design. Do not assume Shopify data access or approval is granted for public merchants.

## Release and governance
5. **Stage 1 closed** after approved 480/481/483/484 production DB and e6e05f99 production code deployment; this is a **controlled DARK** release, not install/public readiness.
6. Migration **482 deferred by Founder**, accepted while onboarding dark; **separate signed/audited production release before unrestricted public onboarding and slug creation**, without reusing stale Stage1 backup or signatures.
7. Keep **SHOPIFY_ORZIK_ENABLED=false** until separately approved; self-serve onboarding OFF; no Shopify app installations, public onboarding, provider live writes, outbound WhatsApp, real customer edits, payments or public App Store submission under Stage1/Stage2 investigation permissions. Existing unrelated P2 provider execution Enabled expected and should stay ON.
8. Maintain explicit separate approval gates for local builder work, independent red-team/Codex, GitHub production push, Vercel, Shopify version/config deploy, IP allowlist configuration/enforcement, database migration, merchant installs, public access or costs.
9. No force pushing to main. Never equate tests/Codex approval with live release or permission to deploy. Exact SHA reviewed is mandatory.

## Stage2 security direction
10. **Option B: server-side default-deny allow-list**, not short public global switch test. Shop AND active company must be allow-listed; missing/invalid lists fail closed. Installed integration still globally dark until explicitly opened for QA.
11. S2-A local SHA **d48a2d8cc1092077f320d707de8a0d6a90a61620** independently Codex APPROVED; approval applies to local code only, not production.
12. Founder authorized **S2-A2 LOCAL ONLY**: evaluate **use_legacy_install_flow=true**, callback company-membership revalidation, resolver denial side-effect test, shop-domain length alignment and negative regressions; new candidate requires red-team + fresh Codex. This does **not** approve any Shopify configuration deployment or new version.
13. Codex P2 (10-minute stale membership after claim) must be resolved **before public merchant activation**. QA-only testing may be considered under separate permission; P3 tests/validation improvements follow up.
14. S2-1 allowed pinned Shopify CLI local installation + Founder browser sign-in + read-only app info; **completed**. Separate limited shopify app config pull to temporary copy was allowed; completed without remote changes. No app dev, deploy, config link, env show, or displaying secret credentials.
15. **S2-2 ON HOLD** after identified Shopify-managed install vs deny-before-install conflict and IP allowlist requirement; no release or installation without new Founder go.
16. External ChatGPT Work/browser permitted for **explicit read-only** Shopify org/app/dev-store/data-access/settings verification; do not modify settings, create/submit app, or install unless Founder separately approves. CLI terminal tasks handled on user's Mac with interactive login.

## Cost, compliance and separate issues
17. Founder explicitly **does not approve $100/month Vercel Static IPs, paid hosting upgrade or recurring egress expense**. Free/lowest-cost compliant options only for research until separate cost approval. Do not purchase or enable service.
18. Proposed ASN + US allowlist is only a **research candidate**; neither ASN nor egress reliability verified. No guessing ASN or production probe; observed Supabase source IPs not automatically all Shopify egress IPs.
19. Shopify Protected Customer Data saved development selections ≠ public approval. Public access request Draft 0/16, legal terms/privacy/support and public review questions open. App Store listing product decisions A–C (login before OAuth, non-embedded experience, off-platform billing) not finalized.
20. F-RUN runner silent evidence-write failure, F-TEST outdated test, and **EXC-BK010** pre-existing aradhyavastram.in / client_slug issue need separate scope/approval. Do not silently fix BK010 or relax security because it predates Orzik.
21. Founder wants frequent simple Hinglish explanations, exact copy/paste instructions when on Mac, one next manual action at a time, and every new chat able to pick up full context without repeated settled questions.

**Standing rule:** If later explicit Founder instructions conflict with this date-stamped register, record newer decision with provenance, do not silently overwrite or widen approvals.
