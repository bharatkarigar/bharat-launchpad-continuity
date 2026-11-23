# NEW CHAT — Orzik Shopify resume prompt (23 November 2026)

Paste this at the start of a new ChatGPT conversation within Bharat Launchpad Project:

> Continue the **Orzik Shopify Public App Stage 2 controlled rollout** from the public versioned continuity repository https://github.com/bharatkarigar/bharat-launchpad-continuity. You MUST read via GitHub connector, in this order, without assuming old Nov 16 checkpoint is latest:
>
> 1. START_HERE.md and OPERATING_RULES.md;
> 2. **ORZIK_CURRENT_GATE_2026_11_23.md** (latest Orzik status);
> 3. **evidence/ORZIK_SHOPIFY_A_TO_Z_CONTINUITY_2026_11_23.md**, FULL, including exact SHAs, chronological Stage 1/2 results, evidence attribution and unresolved blockers;
> 4. **ORZIK_FOUNDER_DECISIONS.md**;
> 5. CURRENT_STATE.md, REVIEW_HISTORY.md, EVIDENCE_INDEX.md and REVIEW_CANDIDATE_LEDGER.md for the SEPARATE historic Bharat Launchpad/Pre-P3 stream; when related read older canonical V10.4 files and historical evidence. Do not conflate them with Orzik Shopify Stage2.
>
> Verified/reported most recent state: Stage 1 **CLOSED CONTROLLED DARK** with DB migrations 480,481,483,484, prefix 95/95, migration 482 NOT applied, production GitHub/Vercel exact SHA **e6e05f99e46872debfbab254ffb31d3fa6c73fa5**, Vercel deployment **dpl_2pmJ3bgTn1GXwnoXjqpoeT3yGFuU** READY. Production Orzik and onboarding still OFF.
>
> S2-A local exact code SHA **d48a2d8cc1092077f320d707de8a0d6a90a61620** has independent **CODEX_S2A_APPROVED** (0 P0/1, 1 P2, 2 P3), not deployed. S2-1 read-only Shopify CLI identity and Dashboard preflight PASS. Shopify org 249330912, app 450606792705, dev store **orzik-qa.myshopify.com**, QA SaaS company **ZZZQA-PRODSMOKE-001**. Old org 243933135/app 450405007361 untouched. **S2-A2** local security/config remediation reportedly in builder, NO SHA or Codex verdict yet; **S2-2 HOLD** because managed vs legacy install and mandatory IP allowlist not resolved.
>
> Founder rejects $100/month static IP upgrade / any unapproved spending. Read-only Supabase gateway log measurement provided **114 distinct IPs / 49,291 requests**, US Amazon-related organization metadata, **not verified ASNs**, 24h window 22–23 Nov. IP-only private file orzik_egress_ips_2026-11-23.txt, SHA256 **7544b56d3bb27064718fa181331baeb913350bd506e81ce10aced03ea4c2c2ab**. It was available as private ChatGPT artifact; Claude MAIN needs the actual 114 IPs privately to map Team Cymru and RIPEstat. Do not copy them into this **public** repo.
>
> **NEXT PERMITTED TASK:** help founder privately transfer the 114-IP file to Claude MAIN; obtain verified ASN mapping and attribution, continue S2-A2 local builder/red-team/Codex after exact new SHA. Do not deploy app config/Shopify install, enable flags, migrate 482, change Vercel, push app main or pay anything without separate Founder approval.
>
> Keep old Founder decision history; label CLAUDE REPORTED, TOOL-VERIFIED, CODEX original, NOT PROVEN. Treat current status as of 23 Nov only and reconcile any new chat updates via GitHub connector. Explain in Hinglish, one next operator action at a time. If private local evidence not available, do not claim it was independently re-read. No background auto-sync.

**Important:** Continuity GitHub is public documentation, not SaaS code, signed production logs or a verbatim chat transcript. This bootstrap preserves actionable project state, but complete private source transcripts remain outside GitHub.
