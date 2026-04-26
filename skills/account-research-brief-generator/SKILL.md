---
name: account-research-brief-generator
description: >
  Generates sourced, BDR-ready account research briefs for named target accounts
  in B2B SaaS ABM and outbound motions. Use after a target account list is built
  and before outreach sequences are written. Best for Tier 1, Tier 2, and
  intent-qualified accounts where BDRs need a clear "why this account, why now,
  why this persona" hypothesis. Designed for B2B SaaS teams selling compliance,
  security, GRC, risk, or other technical platforms into mid-market and
  enterprise buyers. Not intended for broad list building or mass enrichment.
---

# Account Research Brief Generator

> A repeatable framework for turning a company name into a BDR-ready research brief
> in 10-60 minutes depending on tier. Reduces inconsistent manual research by
> giving BDRs a tier-calibrated workflow that produces a standardized brief
> across researchers, accounts, and outreach waves.

## Why This Skill Exists

Most account research is wasted work. BDRs spend an hour on a single account, find
three usable insights, and the rest of the data dies in a Notion doc no one reads.
By the time outreach starts, half the intel is stale and none of it ties to a
specific message angle.

This skill fixes three failure modes:

1. **Inconsistent depth across accounts.** Tier-1 accounts get 90 minutes of
   research; tier-2 accounts get 10. The brief format here scales depth to tier
   without losing structure.

2. **Research that doesn't drive outreach.** Generic "they raised a Series B"
   notes don't tell a BDR what to say. Every section in this brief ends with a
   "so what" — the implication for messaging.

3. **No reusable artifact.** Each researcher works from scratch. This skill
   produces a standardized brief that can be reviewed, refined, and reused
   across multiple outreach waves.

## When to Use This Skill

- Preparing outreach for a specific named account (single brief)
- Building research packets for a tier-1 ABM cohort (batch briefs)
- Onboarding a new BDR with their first account list
- Refreshing intel on accounts re-entering active outreach after 60+ days
- Pre-call research for sales discovery on a recycled pipeline account
- Building "account snapshots" for executive sponsor outreach
- Validating that an account on the target list actually fits the ICP after research

## When NOT to Use This Skill

- Building the target account list itself (use `abm-program-orchestrator` for list construction)
- Writing the outreach sequences (use `bdr-enablement-generator` after research is done)
- Mass-research on 1000+ accounts (this is a depth tool, not a breadth tool — use intent data platforms for breadth)
- Customer research for expansion (different motion; expansion needs usage data, not external signals)
- Competitive battlecards (use `competitive-battlecard-generator`)

## Boundary With `bdr-enablement-generator`

These two skills are deliberately separated:

- **`account-research-brief-generator`** = the account intelligence layer. Produces sourced research output ending in an outreach hypothesis. Stops before any sequences are written.
- **`bdr-enablement-generator`** = the outreach execution layer. Takes a finished brief as input and produces sequences, talk tracks, and objection handlers.

If you find yourself writing email copy in this skill, stop. That's the next skill in the stack.

## How This Skill Fits Into the Skill Stack

```
abm-program-orchestrator         →  Gives you the prioritized account list
   ↓
account-research-brief-generator →  Produces the BDR-ready intelligence brief  ← YOU ARE HERE
   ↓
bdr-enablement-generator         →  Turns the brief into outreach sequences
   ↓
grc-messaging-guardrails         →  Validates compliance terminology in the output
```

Run this skill after the target account list is set and before sequences are written.

---

## Phase 1: Inputs and Tier Calibration

The brief's depth scales with account tier. Don't research a tier-3 account at
tier-1 depth — that's how teams burn 40 hours/week on research and ship nothing.

### Required Inputs

Before generating a brief, gather:

| Input | Why It Matters | Source |
|---|---|---|
| Company legal name + domain | Disambiguates between similar-named companies | Account list |
| Tier (1, 2, or 3) | Determines research depth | ABM program design |
| ACV target ($) | Calibrates effort against deal value | ICP / opportunity sizing |
| Primary persona to engage | Focuses the "so what" against one buyer | ICP / persona doc |
| Compliance frameworks relevant (SOC 2, ISO 27001, HIPAA, PCI DSS, GDPR) | Anchors the GRC angle | Discovery from public signals |
| Trigger event (if any) | The reason this account is being prioritized now | Intent data, news, sales input |

### First-Party and Second-Party Signal Inputs (Required When Available)

Public signals alone produce generic briefs. The "why now" hypothesis gets
sharper when first-party and second-party signals feed Section 3 (Trigger
Events).

| Signal Source | Type | What It Tells You |
|---|---|---|
| HubSpot engagement (page views, form fills, email opens) | First-party | Active research happening on your site |
| Factors.ai or similar reverse-IP visitor data | First-party | De-anonymized account-level web visits |
| G2 buyer intent (category page visits, comparison searches) | Second-party | The account is in active evaluation |
| Paid ad engagement (LinkedIn, Google) | First-party | Topic and creative resonance |
| BDR/AE prior conversations (recycled pipeline) | First-party | Past pain points, blockers, objections |
| Intent platforms (Bombora, 6sense) | Third-party | Topic interest at the account level |

If first-party signals exist for an account, they take precedence over public
triggers in Section 3. A real page visit on your pricing page beats a
six-month-old funding announcement.

### Tier Calibration

| Tier | Research Time | Brief Length | Depth |
|---|---|---|---|
| **Tier 1** (1:1 motion) | 45-60 min | 800-1200 words | All 6 sections, deep on each |
| **Tier 2** (1:few) | 20-30 min | 400-600 words | All 6 sections, summary on each |
| **Tier 3** (1:many) | 10-15 min | 200-300 words | Sections 1-3 + Section 6, deeper sections marked "Skipped by tier" |

Note: Tier 3 briefs use the same schema as Tier 1 and Tier 2. Sections that
aren't researched at this tier are explicitly marked "Skipped by tier" rather
than removed. This preserves the consistent scan-pattern that makes the brief
format usable across tiers.

---

## Phase 2: The Six-Section Brief Structure

Every brief uses the same six-section schema. Lower tiers may mark selected
sections as "Skipped by tier" but the structure stays constant. This consistency
matters more than comprehensiveness — BDRs and AEs learn to scan for specific
sections, and varying the structure forces them to re-read every brief.

### Section 1: Company Snapshot

**What goes here.** Basic firmographics and current state.

- Company name, HQ, founding year
- Employee count (LinkedIn — useful for directional headcount; verify with secondary sources for high-stakes accounts since LinkedIn data can be stale or inflated)
- Funding stage and total raised (Crunchbase — flag last raise date and amount)
- Revenue (if public; for internal sizing only, can estimate from headcount × $200K-$400K per employee for B2B SaaS — **do not use estimated revenue in outreach unless publicly sourced**)
- Industry vertical and sub-vertical
- Customer segment (B2B / B2C / both)

**So what.** One sentence on what this company does and who it sells to. Not
their marketing tagline. The actual business model.

> Example: "Series B FinTech B2B SaaS, ~220 employees per LinkedIn, raised $45M
> in Sept 2025. Sells fraud detection APIs to mid-market banks and lenders.
> Last 18 months: aggressive expansion into EU."

### Section 2: GRC and Compliance Surface Area

**What goes here.** The compliance and security angle. This is where Scrut wins
or loses the deal — get this section right.

- Compliance frameworks already publicly committed to (check website footer, trust center, security page)
- Compliance frameworks they likely *need* but haven't publicly attested to
- Recent compliance-relevant events (audit findings, breach disclosures, regulatory actions)
- Stated security/compliance team size and seniority (LinkedIn search: "Compliance," "GRC," "Security" at the company)
- Use of competing GRC platforms (search G2, LinkedIn job posts mentioning "Vanta," "Drata," "Secureframe," "Tugboat Logic")
- Third-party risk exposure (do they sell into regulated industries? do their customers demand attestations?)

**So what.** One paragraph. The compliance pressure they're under, the gap
between what they have and what they need, and which framework is the strongest
hook.

**Critical rule on competitor claims.** If the account is using a known
competitor, do not improvise messaging in this brief. Reference the approved
competitor battlecard notes from `competitive-battlecard-generator` and tag
the relevant battlecard in the brief. Unsourced competitor swipes in research
briefs become unsourced competitor swipes in outreach — and that creates legal
and credibility exposure.

> Example: "Has a public SOC 2 Type II attestation but no ISO 27001. EU
> expansion means GDPR exposure and EU enterprise buyers will likely require
> ISO 27001 within 12 months. Currently using Drata (job post mention from Aug
> 2025) — see Drata battlecard for approved positioning. Compliance team is 2
> people per LinkedIn — likely overloaded. Hook: ISO 27001 as the EU expansion
> blocker."

**Critical terminology check.** Run any compliance language in this section
through `grc-messaging-guardrails` before finalizing. Common errors: calling SOC
2 a "certification" (it's an attestation), conflating GDPR with general data
privacy, treating ISO 27001 as a one-time event.

### Section 3: Trigger Events

**What goes here.** The reason this account is researchable *now*. Triggers are
what make outreach feel relevant instead of generic.

**First-party and second-party triggers (highest priority when available):**
- Active page visits on your site (pricing, product, comparison pages)
- G2 category or comparison page visits
- Paid ad engagement (specific creative, topic resonance)
- Past conversations with BDR/AE (recycled pipeline)

**Public triggers:**
- Funding rounds (last 12 months)
- Executive hires or departures (especially CISO, CTO, VP Engineering, Head of Compliance)
- Product launches (especially anything that expands their data surface area)
- Geographic expansion (especially into regulated regions: EU, healthcare, finance)
- Public security incidents or breach disclosures
- Customer logos announced (especially regulated-industry customers)
- M&A activity
- Job posts that signal compliance need (e.g., hiring "Compliance Manager," "Security Analyst")
- Public statements on compliance roadmap (earnings calls, blog posts, conference talks)

**So what.** Rank triggers by recency and outreach value. The freshest, most
relevant trigger anchors the opening message. First-party signals beat public
signals when both exist.

> Example: "Highest-value trigger: New security leader hired in Oct 2025
> (ex-Plaid). Security leaders often reassess tooling early in tenure —
> validate with their recent LinkedIn posts and public priorities. Outreach
> window is now."

### Section 4: Buying Committee

*Tier 1: deep. Tier 2: summary. Tier 3: Skipped by tier.*

**What goes here.** The 3-7 people who will influence or decide a Scrut purchase.
For tier-1 accounts, name them. For tier-2, identify by role. For tier-3,
explicitly mark this section "Skipped by tier — segment-level personas apply."

For each person:

- Name + title + tenure (LinkedIn)
- Reporting line (who they report to, who reports to them)
- Background (previous companies — flag if they've used GRC tools before)
- Public content (LinkedIn posts, conference talks, podcast appearances on compliance/security)
- Likely role in a Scrut deal (Decision Maker / Champion / Influencer / Blocker / End User)

**So what.** One sentence per person on how to engage them and what they care
about most. Don't write generic personas — write *this person* given their
background.

> Example: "Sarah Chen, Head of Compliance, joined from a Series D FinTech where
> she rolled out Vanta. She'll have strong opinions on what 'good' looks like and
> will benchmark Scrut against her last experience. Champion candidate. Reference
> Drata battlecard for approved competitor positioning — do not improvise
> Vanta-specific claims."

### Section 5: Tech Stack Signals

*Tier 1: deep. Tier 2: summary. Tier 3: Skipped by tier.*

**What goes here.** What they use that tells you about their compliance maturity
and integration needs.

- Cloud infrastructure (AWS, GCP, Azure — visible from job posts, BuiltWith, security pages)
- Productivity stack (Google Workspace vs M365 — affects integration priorities)
- Identity provider (Okta, Azure AD, Google — critical for evidence collection)
- Existing GRC/security tools (visible from LinkedIn job posts, G2 reviews, RFP responses)
- HR system (Rippling, Workday, BambooHR — affects employee evidence collection)
- Code repositories (GitHub, GitLab — affects developer evidence collection)
- Ticketing (Jira, Linear, ServiceNow — affects audit evidence workflows)

**So what.** Two sentences. The integration story Scrut needs to tell to make
adoption frictionless. Flag any blockers (e.g., proprietary in-house systems
that won't have native connectors).

> Example: "AWS + Okta + GitHub + Jira — fully covered by Scrut connectors.
> Rippling for HR (native connector). Migration friction is low. Lead with
> 'evidence collection works on day one with your existing stack.'"

### Section 6: Outreach Hypothesis

**What goes here.** The synthesis. Given everything above, what should the BDR
say first?

- The single highest-priority trigger event
- The single most pressing compliance gap
- The persona to lead with and why
- The opening message angle (one sentence — not a full email)
- The proof point or asset to lead with (case study, framework guide, calculator)
- The disqualification criteria (what would make this account not worth pursuing)

**So what.** This section is the brief. Sections 1-5 are evidence; Section 6 is
the recommendation. If a BDR only reads Section 6, they should still know what
to do.

> Example:
> - **Trigger:** New security leader hired Oct 2025 (early-tenure tooling reassessment window)
> - **Gap:** ISO 27001 likely needed for EU expansion within 12 months
> - **Persona:** Sarah Chen, Head of Compliance (champion candidate)
> - **Angle:** "Security leaders we work with often benchmark GRC tooling early in tenure. Worth a 15-min comparison?"
> - **Lead asset:** ISO 27001 scoping guide for FinTech
> - **Disqualify if:** They've signed a Drata renewal in the last 90 days (check via job posts mentioning Drata after Sept 2025)

---

## Phase 3: Source Hierarchy and Verification

Not all sources are equal. Use this hierarchy to weigh signals.

| Source Tier | Examples | Trust Level | Use For |
|---|---|---|---|
| **Tier A: Primary** | SEC filings, official trust centers, earnings call transcripts, regulatory filings | High | Compliance frameworks, financial state, public commitments |
| **Tier B: Verified secondary** | Crunchbase, LinkedIn (company), G2 verified reviews, official press releases | Medium-high | Funding, headcount (directional), product launches, customer logos |
| **Tier C: Inferred** | Job posts, LinkedIn employee profiles, BuiltWith, Wappalyzer | Medium | Tech stack, team size, hiring signals |
| **Tier D: Sentiment** | Reddit, Glassdoor, Twitter/X, Slack communities | Low | Cultural signals, internal pain points (treat as hypothesis, not fact) |

**Verification rule.** Any claim in Sections 1-3 should have a Tier A or Tier B
source. Sections 4-5 can rely on Tier C. Tier D goes in Section 6 only as
hypothesis ("BDR should validate on first call: rumors of friction with current
GRC vendor").

**Anti-hallucination rule.** If the brief generator can't find a source for a
claim, the claim doesn't go in the brief. "Likely" and "probably" are flags to
either find a source or remove the claim — *or* mark the claim as hypothesis
explicitly. Brief credibility dies on the first fabricated detail a BDR
mentions in outreach.

**Signal freshness.** Every claim should carry an implicit freshness rating.
Funding rounds older than 12 months are stale. Executive hires older than 6
months are stale. Tech stack signals older than 12 months may be outdated. When
using a stale signal because nothing fresher exists, mark it explicitly: "Last
public signal: Aug 2025 (~9 months old, validate)."

---

## Phase 4: The Brief Template

```markdown
# Account Research Brief: [Company Name]

**Tier:** [1 / 2 / 3]
**Researcher:** [Name]
**Date:** [YYYY-MM-DD]
**Refresh due:** [YYYY-MM-DD — 60 days from creation]
**First-party signals available:** [Yes / No — list source]

---

## 1. Company Snapshot
[2-4 sentences. End with the "so what" sentence on business model.]

## 2. GRC and Compliance Surface Area
[3-5 sentences. End with the hook framework + persona angle.]
[If competitor named: reference approved battlecard.]

## 3. Trigger Events
[Bulleted list, ranked by outreach value. First-party signals first, then public.]
[Top trigger highlighted. Each trigger tagged with date.]

## 4. Buying Committee
[Tier 1: 3-7 named people with one-sentence engagement angle each.]
[Tier 2: 3-5 roles with one-sentence engagement angle each.]
[Tier 3: "Skipped by tier — segment-level personas apply."]

## 5. Tech Stack Signals
[Tier 1-2: 3-5 sentences on stack + integration story.]
[Tier 3: "Skipped by tier — segment-level integration story applies."]

## 6. Outreach Hypothesis
- **Trigger:** [Single highest-priority trigger, with date]
- **Gap:** [Single most pressing compliance gap]
- **Persona:** [Persona to lead with + why]
- **Angle:** [One-sentence opening hypothesis]
- **Lead asset:** [Specific asset name]
- **Disqualify if:** [Concrete disqualification criteria]

---

## Sources
[List all sources with URLs and dates. Required for any claim in Sections 1-3.]
```

---

## Phase 5: Quality Bar

Before a brief goes to a BDR, it should pass this checklist.

### Content Quality
- [ ] Every claim in Sections 1-3 has a source URL with a date
- [ ] No fabricated details (employee counts, revenue figures, executive names)
- [ ] Estimated revenue (if used internally) is not repeated in outreach
- [ ] Compliance terminology validated against `grc-messaging-guardrails`
- [ ] Trigger events are within the last 12 months OR explicitly marked stale
- [ ] Buying committee names are spelled correctly (cross-check LinkedIn)
- [ ] First-party signals (if available) are reflected in Section 3

### Specificity
- [ ] Section 6 ("Outreach Hypothesis") names a specific persona, not a generic title
- [ ] The "Angle" sentence is something a BDR could actually send (not a topic — a hook)
- [ ] The "Lead asset" is a specific named asset, not a generic category
- [ ] Disqualification criteria are concrete and observable, not vibes

### Honest Calibration
- [ ] If the account doesn't fit the ICP after research, the brief says so explicitly
- [ ] Confidence levels are stated where signals are weak ("likely," "estimated," "rumored")
- [ ] No claims sourced from Tier D alone are presented as fact
- [ ] If a competitor is named, only approved battlecard claims are referenced

### Schema Consistency
- [ ] All six sections present in the document (skipped sections marked "Skipped by tier")
- [ ] Section order unchanged from template

---

## Phase 6: Brief Lifecycle and Refresh

Briefs decay. A brief written today is roughly 60% accurate in 60 days, 30%
accurate in 180 days. Build a refresh cadence into the system.

| Brief Age | Action |
|---|---|
| 0-30 days | Use as-is |
| 31-60 days | Validate trigger events still relevant before outreach |
| 61-120 days | Re-run Sections 2 and 3 (compliance state + triggers) |
| 120+ days | Full re-research before outreach |

**Refresh trigger events.** Re-run a brief immediately if:
- The account had a funding round
- An executive in Section 4 left or was hired
- A breach or compliance incident was disclosed
- The account's primary geography changed (M&A, expansion announcement)
- New first-party signals appear (active page visits, form fills, ad engagement)

---

## Phase 7: Measurement and Feedback Loop (v1)

The brief is only useful if it improves outreach quality and pipeline conversion.
This v1 measurement layer captures the minimum required to validate the format
and surface improvements. Full attribution measurement is deferred to v2 once
v1 has 4-6 weeks of production usage.

### Three v1 Measurement Principles

1. **Track usage before outcomes.** Before measuring whether briefs improve
   reply rates, measure whether BDRs actually use them. If brief completion
   rate is below 80% or BDRs are skipping Section 6, the format needs
   simplifying before any outcome metric is meaningful.

2. **Capture per-account feedback after every outreach cycle.** A brief without
   a feedback loop is one-way intelligence. Every brief gets updated with
   outreach outcome before it's archived.

3. **Kill fields that don't drive decisions.** If a research field never changes
   the BDR's outreach approach across 20+ accounts, remove it from the template.
   The brief should get shorter over time, not longer.

### Per-Account Feedback Capture

After every outreach cycle, append a feedback block to the brief:

```markdown
## Outreach Feedback (appended after first outreach cycle)

- **Date of first touch:** [YYYY-MM-DD]
- **Persona engaged first:** [Name]
- **Persona who responded (if any):** [Name or "no response"]
- **Trigger that anchored the message:** [Which trigger from Section 3]
- **Reply rate on sequence:** [Replied / No reply]
- **Meeting booked:** [Yes / No]
- **If meeting booked, accepted by AE:** [Yes / No]
- **Hypothesis match (Section 6):** [Hypothesis was right / partially right / wrong]
- **What to change in the next account in this segment:** [One sentence]
```

This minimum feedback set is what feeds the v2 measurement framework once
enough briefs have run.

---

## Common Failure Modes

### Failure 1: Generic Briefs
Symptom: The brief could apply to any company in the same vertical. Outreach
based on it gets ignored.

Fix: Force every section to include at least one detail unique to *this* company.
If you can't find one, the account isn't researchable yet — flag it for delay.

### Failure 2: Insight Without Action
Symptom: 1200 words of research, no outreach hypothesis. The BDR still doesn't
know what to say.

Fix: Section 6 is mandatory regardless of tier. Without an outreach hypothesis,
the brief is journalism, not enablement.

### Failure 3: Stale Triggers
Symptom: BDR opens with "I saw you raised your Series B" — six months after the round.

Fix: Triggers older than 90 days lose impact. Use the freshest credible trigger.
If the freshest is old, mark it stale and lead with a compliance gap angle
instead.

### Failure 4: Persona Inflation
Symptom: Brief lists 12 people in Section 4. BDR doesn't know who to start with.

Fix: Cap Section 4 at 7 people max. The right number is "decision maker + champion
+ 1-2 influencers + 1-2 end users." Anyone else is noise at the brief stage.

### Failure 5: Compliance Mistakes
Symptom: Brief calls SOC 2 a "certification." BDR repeats it in outreach. Buyer
flags Scrut as "doesn't know what they're talking about."

Fix: Mandatory `grc-messaging-guardrails` validation pass before any brief
leaves the system.

### Failure 6: Unsourced Competitor Swipes
Symptom: Brief includes a claim like "Vanta is weak at scale" with no source.
BDR repeats it in outreach. Prospect has a Vanta contact and screenshots the
message to them.

Fix: Competitor claims come only from approved battlecards. If the battlecard
doesn't say it, the brief doesn't say it.

---

## Integration With Other Skills

- **Inputs from:** `abm-program-orchestrator` (target account list, tier assignments)
- **Outputs to:** `bdr-enablement-generator` (research brief feeds sequence personalization)
- **Validated by:** `grc-messaging-guardrails` (compliance terminology check)
- **Cross-references:** `competitive-battlecard-generator` (when account uses a known competitor, pull the relevant battlecard for approved positioning)

---

## Changelog

- **v1.0a** (April 2026): Pre-merge revision after editorial review. Tightened YAML description to clarify positioning vs. `bdr-enablement-generator`. Reconciled time-promise inconsistency (10-60 minutes depending on tier). Softened LinkedIn headcount claim to "directional, verify if high-stakes." Added internal-only guardrail on estimated revenue. Replaced unsourced competitor example with approved-battlecard requirement. Reconciled Tier 3 schema (sections marked "Skipped by tier" rather than removed). Added first-party and second-party signal inputs as required where available. Added signal freshness tagging to source hierarchy. Added Phase 7 v1 measurement layer (usage-first principles + per-account feedback capture). Softened CISO-tenure claim from definitive to pattern-based. Added explicit Boundary section vs. `bdr-enablement-generator`.
- **v1.0** (April 2026): Initial release. Six-section brief structure, tier-calibrated depth, source hierarchy with verification rules, refresh lifecycle, integration with ABM orchestrator and BDR enablement skills.
