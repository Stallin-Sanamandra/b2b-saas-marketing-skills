---
name: ceo-monthly-revenue-report-generator
description: >
  Generates the monthly revenue-accountable marketing report that B2B SaaS
  marketing leaders deliver to CEOs, CFOs, executive teams, and boards. Use when
  preparing the monthly CEO report, drafting the marketing section of a board
  deck, defending budget decisions, diagnosing pipeline gaps, or transitioning
  marketing from MQL/SQO reporting to revenue, CAC payback, and forward pipeline
  coverage. Designed for B2B SaaS demand generation leaders who own pipeline
  targets across segments, geos, and motions, and need to explain marketing's
  revenue contribution in executive language.
---

# CEO Monthly Revenue Report Generator

> A repeatable monthly artifact that translates marketing activity into revenue
> contribution, CAC payback, and forward pipeline coverage in the language a
> CEO, CFO, and board will use. Replaces the activity-volume marketing reports
> that get marketing classified as a cost center.

## Why This Skill Exists

Most marketing reports to CEOs fail in the same way. They lead with activity
metrics (MQLs generated, campaigns launched, content published), follow with
funnel conversion rates, and end with a budget ask. The CEO walks out of the
meeting unable to answer: "did marketing make money this month, and are we
investing the right amount?"

This skill fixes three failure modes:

1. **The wrong leading metric.** MQLs and SQOs measure work done, not value
   created. Pipeline value, closed-won revenue contribution, and CAC payback
   period measure value. The CEO report leads with the latter.

2. **No segment view.** Aggregated marketing performance hides everything that
   matters. SMB might be subsidizing a failing mid-market program, or ABM might
   be driving most new ACV from a small share of pipeline volume. Without
   segmentation, every reallocation decision is a guess.

3. **Backward-looking only.** A report that only shows what happened last month
   forces the CEO to ask "what's next?" The report should answer that
   pre-emptively with forward pipeline coverage, leading indicators, and a
   stated bet for the next 30-90 days.

This skill produces a report that closes those three gaps in a format the CEO,
CFO, and board can read in 5 minutes and reference in their own decision
making.

## When to Use This Skill

- Preparing the monthly marketing review for the CEO or executive team
- Drafting the marketing section of a board deck (compressed to 1-2 slides — see Phase 2)
- Building a recurring revenue dashboard that replaces ad-hoc updates
- Transitioning marketing reporting from MQL/SQO volume to revenue and CAC payback
- Defending a budget ask with revenue evidence (not activity evidence)
- Onboarding a new CEO or CFO who wants to understand marketing's economics
- Diagnosing a quarter-over-quarter pipeline decline with stakeholder-ready narrative

## When NOT to Use This Skill

- Weekly campaign performance reviews (use a campaign-level dashboard)
- Operational team standups (this is an executive artifact, not a working doc)
- Budget planning from scratch (this reports against existing budget, not allocates new)
- Attribution model design (use `pipeline-attribution-narrator` first to get the model right)
- Quarterly business reviews (use `quarterly-business-review-builder` for the deeper QBR cut, when added)

## How This Skill Fits Into the Skill Stack

```
pipeline-attribution-narrator       →  Defines the attribution model + monthly narrative
   ↓
ceo-monthly-revenue-report-generator → Packages it for the CEO/CFO/board audience  ← YOU ARE HERE
   ↓
[quarterly-business-review-builder]  →  Aggregates 3 monthly reports into the QBR (future companion skill)
```

This skill assumes attribution infrastructure is already in place. If pipeline
attribution is still ambiguous, run `pipeline-attribution-narrator` first.

**Future companion skill:** `quarterly-business-review-builder` if added later
for aggregating three monthly reports into a quarterly cut.

---

## Phase 0: Required Inputs

Before generating the report, gather the following. If three or more required
inputs are missing or stale, the report will be misleading — fix the data
infrastructure first, don't paper over it with narrative.

| Input | Why It Matters | Source |
|---|---|---|
| Closed-won revenue for the month, by segment | The revenue contribution headline | CRM (closed-won deals) |
| Qualified pipeline created in the month, by segment | Forward-looking indicator | CRM (SQO+ stages) |
| Marketing spend for the month, by channel and segment | CAC denominator | Ad platforms + finance |
| Allocated sales spend, by segment | CAC denominator (full picture, optional — see CAC fallback rule) | Finance + RevOps |
| Average ACV by segment, for new customers | CAC payback numerator | CRM closed-won |
| Gross margin by segment | CAC payback adjustment | Finance |
| Stage-to-stage conversion rates, current vs historical baseline | Coverage ratio integrity | CRM funnel report |
| Stage velocity, current vs historical baseline | Coverage ratio integrity | CRM funnel report |
| Sales capacity status (rep headcount, ramp state, follow-up SLA adherence) | Coverage ratio is meaningless without capacity to work pipeline | RevOps + sales leadership |
| Last month's "bet" status (resolved / in-progress / abandoned) | Continuity across reports | Last month's report |

**Anti-pattern.** Do not generate the report with placeholder figures. A report
with `[X]` in production fields that should have real numbers signals to the
CEO that the data infrastructure isn't there — at which point the report's
existence raises more questions than it answers.

### Attribution Definitions Required

Before comparing month-over-month performance, define these terms explicitly.
Quiet redefinitions corrupt month-over-month trends — every redefinition
should be called out in the methodology notes when it happens.

- **Sourced revenue:** Revenue where marketing created the first known meaningful touch or acquisition source.
- **Influenced revenue:** Revenue where marketing touched the account or opportunity within the agreed lookback window.
- **Lookback window:** Default 90 days unless the business has a different agreed standard.
- **Qualified pipeline:** Pipeline that has reached the agreed sales-qualified opportunity stage or equivalent.

If any of these definitions changed during the reporting month, flag it
explicitly in the methodology notes and exclude that change from
month-over-month comparisons until two clean months under the new definition
exist.

---

## Phase 1: The Six-Block Report Structure

Every monthly CEO report has the same six blocks. Consistency matters more than
comprehensiveness. The CEO learns to scan for specific information; varying the
structure forces a re-read every month and reduces the report's utility.

### Block 1: Executive Summary (One Page)

This is the only block most CEOs will read carefully. It must stand alone.

**Required elements:**

- **Headline.** One sentence: did marketing hit, miss, or exceed the revenue contribution target this month?
- **Four numbers.** Closed-won revenue influenced by marketing, new qualified pipeline created, CAC payback period (or marketing CAC proxy — see Block 3), forward pipeline coverage ratio for next quarter.
- **Data confidence.** High / Medium / Low, with one-sentence reason.
- **What worked.** Two bullets, each one sentence. Specific channels, segments, or motions.
- **What didn't.** Two bullets, each one sentence. Honest, with the diagnosis.
- **The bet.** One sentence on the reallocation or focus decision being made for the next 30 days as a result.

**Critical rule on the four numbers.** Closed-won revenue and qualified
pipeline are different value pools — closed-won is realized revenue, qualified
pipeline is forward-looking. Never sum them into a single "pipeline
contribution" number. Mashing them together creates the appearance of a single
metric while hiding the time-lag relationship between pipeline and revenue.

**Length.** 8-10 lines. If the executive summary doesn't fit on a phone screen,
it's too long.

### Block 2: Revenue Contribution

This block is where marketing's impact lives or dies. It must show:

- **Closed-won revenue with marketing as a touchpoint** (any touch in the agreed lookback window)
- **Closed-won revenue with marketing as primary source** (first-touch attribution per the sourced definition)
- **Pipeline created in the month** (qualified pipeline value, not just count)
- **Pipeline-to-revenue conversion lag** (how long does $1 of pipeline created today take to become revenue?)

Show segment cuts:

| Segment | Closed-Won (Influenced) | Closed-Won (Sourced) | New Pipeline | Conversion Lag |
|---|---|---|---|---|
| SMB | $X | $X | $X | X days |
| Mid-market | $X | $X | $X | X days |
| ABM cohort | $X | $X | $X | X days |
| **Total** | **$X** | **$X** | **$X** | **X days** |

**Critical rule.** Show influenced *and* sourced revenue side-by-side. Influenced
inflates marketing's contribution; sourced understates it. The CEO needs both to
calibrate.

**Segment naming.** Use whatever segment names your organization actually uses
internally (SMB, Mid-market, Enterprise, or company-specific designations).
Consistency with how the CEO and CFO already describe segments matters more
than naming convention purity.

### Block 3: CAC Payback by Segment

This is the block that earns marketing the right to ask for budget. Every
segment must have its own CAC payback calculation.

**Required calculation per segment:**

```
CAC = (Marketing spend allocated to segment + Sales spend allocated to segment) / New customers acquired
ACV = Average annual contract value for new customers in segment
Gross margin = % gross margin for segment (typically 75-85% for B2B SaaS)
CAC Payback = CAC / (ACV × Gross margin / 12)  [in months]
```

#### CAC Data Fallback Rule

Full CAC requires both marketing spend and allocated sales spend. Allocated
sales spend is often unavailable on a monthly cadence, especially in companies
where finance allocates quarterly. If allocated sales spend is not available,
do not block the report — use the fallback.

```markdown
CAC status: [Full CAC / Marketing CAC proxy / Data unavailable]
```

- **Full CAC:** Both marketing and allocated sales spend included. Default state.
- **Marketing CAC proxy:** Only marketing spend in the denominator. Label every
  CAC payback figure as "marketing CAC proxy" — never as full CAC. The
  executive summary must call out that full CAC payback is pending finance or
  RevOps allocation.
- **Data unavailable:** Skip the CAC payback block. State the gap in the
  appendix and flag it as a data infrastructure issue in the bet section if
  recurring.

The proxy is useful even though it's incomplete — it tracks marketing
efficiency trend within marketing's own decisions. It is not useful for
go/no-go business decisions on segment-level investment without finance sign-off.

#### Display

| Segment | CAC | ACV | Gross Margin | CAC Payback (months) | Trend vs. Last Month |
|---|---|---|---|---|---|
| SMB | $X | $X | X% | X | ↑/↓/→ |
| Mid-market | $X | $X | X% | X | ↑/↓/→ |
| ABM cohort | $X | $X | X% | X | ↑/↓/→ |
| **Blended** | **$X** | **$X** | **X%** | **X** | ↑/↓/→ |

#### Industry Reference Ranges (Directional Only)

| Segment | Commonly Cited Industry Range |
|---|---|
| SMB / PLG | 3-6 months |
| Mid-market | 9-15 months |
| Enterprise | 12-24 months |
| Blended (B2B SaaS) | ~12 months commonly cited, ~18 months tolerable |

These are directional industry ranges only. They should never override the
company's own historical baseline, gross margin profile, sales cycle, ACV,
retention, or finance-approved operating model.

**Finance alignment rule.** Do not present a CAC payback target as "healthy"
in a CEO or board report unless finance has agreed that it is the right
operating target for the business. The marketing leader's job is to report
performance against the finance-approved target, not to define what the
target should be.

**Rule.** If a segment's CAC payback exceeds the finance-aligned target for
two consecutive months, the report must explicitly address it in Block 6
(The Bet). No silent failures.

### Block 4: Channel and Motion Performance

Where revenue actually came from. This block answers: "If I gave you another
$100K next month, where would it go and why?"

| Channel / Motion | Spend | Pipeline Created | Closed-Won | $ Pipeline per $ Spend | CAC Payback |
|---|---|---|---|---|---|
| Inbound (organic + content) | $X | $X | $X | $X | X mo |
| Paid search | $X | $X | $X | $X | X mo |
| Paid social (LinkedIn) | $X | $X | $X | $X | X mo |
| BDR outbound | $X | $X | $X | $X | X mo |
| ABM cohort | $X | $X | $X | $X | X mo |
| Events / conferences | $X | $X | $X | $X | X mo |
| Partnerships | $X | $X | $X | $X | X mo |

Sort the table by **$ Pipeline per $ Spend** descending. The CEO sees the
ranking immediately.

**Annotation rule.** Any channel with a 30%+ shift month-over-month gets a
one-line annotation explaining why (audience saturation, creative refresh,
competitive pressure, seasonality).

### Block 5: Forward Pipeline Coverage

The CEO's most pressing question is always: "are we going to hit next quarter?"
This block answers that with data, not optimism.

**Required metrics:**

- **Coverage ratio.** Total qualified pipeline / next quarter's revenue target. Healthy = 3.0-4.0x for typical B2B SaaS, but validate against your historical conversion rates.
- **Coverage ratio by segment.** Same calculation, broken out per segment.
- **Velocity check.** Are deals moving stage-to-stage at historical rates, or is the funnel slowing?
- **Conversion check.** Are stage-to-stage conversion rates holding, or has something cracked?
- **Gap to target.** If coverage is below your healthy threshold, what's the gap in dollar terms and what's the plan to close it?

**Sales capacity check.** Coverage ratio only matters if sales has enough
capacity to work the pipeline. If pipeline coverage is healthy but rep
capacity, ramp state, follow-up SLA, or stage velocity is constrained, call
that out separately. A 4x coverage ratio with 60% rep capacity is functionally
the same as a 2.4x coverage ratio with full capacity — and the CEO needs to
know which problem is actually live.

**Honest rule.** If coverage is below your established healthy threshold for
the next quarter, this block leads the report — not the executive summary.
The CEO needs to know about coverage gaps as early as possible, not buried
in Block 5.

### Block 6: The Bet (Forward 30 Days)

The single most important block. Every monthly report ends with one specific
bet — a focused reallocation or doubling-down decision for the next 30 days,
with a stated success metric.

**Required structure:**

- **The bet:** What specifically is changing? (e.g., "Shifting a portion of paid social budget to ABM creative production for the mid-market cohort.")
- **The hypothesis:** Why? (e.g., "Mid-market paid social CAC payback is materially longer than ABM. Creative quality, not budget, is the constraint on the ABM motion.")
- **The success metric:** What will tell us the bet worked or failed? (e.g., "ABM cohort SQOs up 30% in 30 days. If flat or down, revert.")
- **The kill criteria:** When do we cut losses? (e.g., "If ABM SQOs not up 15% in 30 days, return to current allocation.")

**Anti-pattern.** "We're going to do better next month" is not a bet. "We're
launching three new initiatives" is not a bet — that's spreading thin. A bet
is one specific, measurable, time-bound reallocation.

**Carry-forward rule.** Every report references the previous month's bet and
states resolved / in-progress / abandoned status. No silent disappearances.

---

## Phase 2: The Report Template (Full Monthly) and Board Deck Compression

### Full Monthly Report Template

```markdown
# Marketing Revenue Report — [Month Year]

**Prepared by:** [Name, Title]
**For:** [CEO Name], [Other recipients]
**Date:** [YYYY-MM-DD]
**Data confidence:** [High / Medium / Low]
**Reason:** [One sentence on data completeness, attribution quality, or known gaps]

---

## Executive Summary

**Headline:** [One sentence. Hit, miss, or exceed?]

**Four numbers:**
- Closed-won revenue influenced by marketing: $[X]
- New qualified pipeline created: $[X]
- Blended CAC payback: [X] months ([Full CAC / Marketing CAC proxy])
- Q[N] coverage ratio: [X.X]x

**What worked:**
- [One sentence]
- [One sentence]

**What didn't:**
- [One sentence]
- [One sentence]

**The bet:** [One sentence on the 30-day reallocation decision.]

**Status of last month's bet:** [Resolved / In-progress / Abandoned, with one-sentence note]

---

## 1. Revenue Contribution

[Table: Closed-won influenced vs sourced, new pipeline, conversion lag — by segment]

[2-3 sentences of narrative interpretation. What does the data show that the table doesn't?]

---

## 2. CAC Payback by Segment

**CAC status:** [Full CAC / Marketing CAC proxy / Data unavailable]

[Table: CAC, ACV, gross margin, CAC payback, trend — by segment]

[2-3 sentences. Which segment is most efficient? Where is payback degrading? If proxy: what's pending from finance.]

---

## 3. Channel and Motion Performance

[Table: Spend, pipeline created, closed-won, $ pipeline per $ spend, CAC payback — by channel]

[Annotations on any 30%+ month-over-month shifts.]

---

## 4. Forward Pipeline Coverage

- **Q[N] coverage ratio:** [X.X]x ([healthy / below target / critical])
- **By segment:** SMB [X.X]x | Mid-market [X.X]x | ABM [X.X]x
- **Velocity check:** [Stage-to-stage timing vs historical]
- **Conversion check:** [Stage conversion rates vs historical]
- **Sales capacity check:** [Rep capacity, ramp state, SLA adherence]
- **Gap to target:** $[X] gap, plan: [one sentence]

---

## 5. The Bet (Next 30 Days)

- **The bet:** [What is changing?]
- **The hypothesis:** [Why?]
- **The success metric:** [What will tell us it worked?]
- **The kill criteria:** [When do we cut losses?]

---

## Appendix: Methodology Notes

- Attribution model: [First-touch / multi-touch / influenced — name the model]
- Lookback window: [90 days standard, or other agreed window]
- Sourced/influenced definitions: [Restate or link to standard]
- Segment definitions: [Link to segment definitions doc]
- Finance-aligned CAC payback target: [State the target by segment, with date of last finance alignment]
- Data sources: [HubSpot, Salesforce, ad platforms — list them]
- Known data gaps: [Be honest about what isn't being measured]
- Attribution definition changes this month: [List any, or "None"]
```

### Board Deck Compression (1-2 Slides)

The full monthly report is too dense for a board deck. For board use,
compress into 1-2 slides. The full report stays in the appendix or is
provided on request as the backup artifact.

**Slide 1: The numbers.**
- Revenue contribution (influenced + sourced)
- New qualified pipeline created
- CAC payback by segment (with CAC status flag)
- Forward coverage ratio with sales capacity context
- Data confidence flag

**Slide 2: The narrative.**
- What changed (one bullet)
- What didn't work (one bullet)
- The next 30-day bet (one bullet)
- Asks of the board (if any)

Anti-pattern: do not paste the full monthly report into the board deck. Board
members read the slide; the report is the receipt.

---

## Phase 3: Quality Bar

Before this report goes to a CEO, CFO, or board, it should pass this checklist.

### Numbers Integrity
- [ ] All figures cross-checked against source systems (HubSpot, Salesforce, ad platforms)
- [ ] Segment definitions consistent with prior months (no quiet redefinition — flag if changed)
- [ ] CAC calculation includes both marketing and sales spend, OR is clearly labeled as marketing CAC proxy
- [ ] Pipeline figures are qualified pipeline (SQO+), not raw lead value
- [ ] Currency consistent throughout (no mixing USD/INR/EUR)
- [ ] Sourced/influenced/lookback definitions explicitly stated in appendix

### Honesty
- [ ] Data confidence marked High / Medium / Low with reason
- [ ] "What didn't work" section is real (every report has at least one honest miss)
- [ ] CAC payback issues flagged explicitly, not buried
- [ ] CAC status (Full / Proxy / Unavailable) called out in executive summary
- [ ] Coverage gaps stated in dollar terms, not just ratios
- [ ] Sales capacity context accompanies coverage ratio
- [ ] The Bet section names a specific kill criteria (not just success criteria)
- [ ] Last month's bet status carried forward (resolved / in-progress / abandoned)

### Executive Readability
- [ ] Executive summary fits on a phone screen
- [ ] No marketing jargon (MQL, SQL, MAL — use revenue terms)
- [ ] Tables sortable by the metric that matters most ($ pipeline per $ spend)
- [ ] Every chart has a one-sentence takeaway annotation
- [ ] Closed-won revenue and qualified pipeline shown separately, never summed

### Forward-Looking
- [ ] The Bet is specific and measurable
- [ ] Forward pipeline coverage stated clearly
- [ ] Sales capacity status referenced explicitly
- [ ] Leading indicators present, not just lagging metrics

### Finance Alignment
- [ ] CAC payback "healthy" framing references the finance-aligned target, not generic industry benchmarks
- [ ] Date of last finance alignment on CAC target stated in appendix

---

## Phase 4: Measurement and Learning Loop

A monthly report is a recurring artifact. Its value compounds (or decays)
based on whether the CEO, CFO, and board actually use it for decisions.
Track three levels.

### Track Three Levels

| Level | Signal | What It Tells You |
|---|---|---|
| **Report quality** | Numbers match source systems, structure stays consistent month over month, attribution definitions stable | The report is technically defensible |
| **Stakeholder usage** | CEO references the report in board prep, CFO uses it in budget discussions, sales leadership reads "What didn't" section before pushback meetings, board references the compressed slides | The report is being used for decisions |
| **Decision velocity** | Reallocation decisions happen faster, budget arguments are shorter, monthly cadence replaces ad-hoc data requests, finance and marketing converge on shared CAC targets | The report is closing the strategic loop |

### Per-Report Feedback Capture

After each monthly report ships, record (one-line each):

```markdown
## Report Feedback

- **Month:** [Month Year]
- **Did the CEO ask for additional data after reading?** [Yes / No — what?]
- **Did the bet from last month resolve cleanly, or get re-litigated?** [Note]
- **Did any segment or attribution definition change during the month?** [Note any quiet redefinitions]
- **Did the report help close any decision that had been open?** [Note]
- **What field in the report did no one reference?** [Candidate for removal]
- **CAC status this month:** [Full / Proxy / Unavailable]
- **Data confidence trend:** [Improving / stable / declining]
```

### Quarterly Review Cadence

Every 3 reports, review the pattern:

- Which blocks consistently drive questions or decisions? Keep and deepen.
- Which blocks no one references? Trim or remove.
- Did the bets resolve cleanly, or are they bleeding into the next month?
  Bleeding bets signal vague success criteria.
- Has the CEO's question pattern shifted? The report should evolve with what
  leadership is actually trying to decide.
- Has CAC status moved from proxy to full? If still proxy after two quarters,
  escalate the data infrastructure gap.

---

## Common Failure Modes

### Failure 1: Activity Theater
Symptom: Report leads with "we generated 2,400 MQLs this month, up 18%."

Fix: Lead with revenue contribution and CAC payback. Activity metrics belong in
working dashboards, not CEO reports.

### Failure 2: The Aggregation Trap
Symptom: Blended CAC payback looks fine; segment-level CAC payback shows ABM is
broken and SMB is subsidizing it.

Fix: Always show segment-level cuts. The blended number is a check, not the
headline.

### Failure 3: Optimistic Forward Forecasting
Symptom: Coverage ratio quoted as 3.5x but assumes historical conversion rates
that haven't held in two months.

Fix: Velocity check and conversion check must accompany every coverage ratio.
If conversion has degraded, the coverage ratio is overstated.

### Failure 4: The Vague Bet
Symptom: "We're going to focus more on ABM next month."

Fix: A bet has a directional commitment, a source of funds, a destination,
a hypothesis, a success metric, and a kill criteria. Anything less is wishful
thinking.

### Failure 5: Silent Misses
Symptom: Last month's "What didn't work" included a paid social CAC issue.
This month it's not mentioned. The CEO doesn't know if it was fixed or
forgotten.

Fix: Carry forward unresolved issues. Every report references the previous
month's bets and states resolved/in-progress/abandoned status.

### Failure 6: Placeholder Generation
Symptom: Report goes out with `[X]` in production fields, or with figures
that don't reconcile to the underlying systems.

Fix: Phase 0 inputs are required, not optional. If the data isn't there, fix
the data — don't ship a report that papers over it.

### Failure 7: Industry Benchmark Substitution
Symptom: Report uses "12 months blended CAC payback target" because that's
the published industry benchmark, not because finance has agreed it's the
right operating target for the business.

Fix: Industry benchmarks are starting points for calibration, not targets
you import. Apply the finance alignment rule — never present a CAC target
as "healthy" without finance sign-off.

### Failure 8: Conflated Value Pools
Symptom: Executive summary shows "pipeline contribution: $X" combining
closed-won revenue and qualified pipeline as a single number.

Fix: These are different value pools — closed-won is realized revenue,
qualified pipeline is forward-looking. Show them separately in the four-
number summary. Never sum them.

### Failure 9: Coverage Without Capacity
Symptom: Report celebrates 4x pipeline coverage. Sales capacity is at 60%.
Pipeline that can't be worked is not coverage — it's a queue that ages out.

Fix: Sales capacity check must accompany every coverage ratio. Coverage
ratio is meaningful only when capacity to work the pipeline is also healthy.

### Failure 10: Definition Drift
Symptom: "Influenced revenue" was 90-day lookback in March, became 180-day
lookback in April, became "any touch ever" in May. Month-over-month trends
look great but reflect definition expansion, not real growth.

Fix: Lock attribution definitions. Any change gets called out in the
methodology notes and excluded from month-over-month comparisons until two
clean months under the new definition exist.

---

## Integration With Other Skills

- **Inputs from:** `pipeline-attribution-narrator` (attribution model and underlying numbers)
- **Cross-references:** `marketing-ops-sop-generator` (data hygiene SOPs that ensure numbers integrity)
- **Future companion skill:** `quarterly-business-review-builder` if added later, for aggregating three monthly reports into a QBR

---

## Changelog

- **v1.0b** (April 2026): Pre-merge revision after second editorial review pass. Expanded YAML description and intro to explicitly cover CEO/CFO/board audiences. Added attribution definitions section in Phase 0 (sourced, influenced, lookback, qualified pipeline) with definition drift rule. Added sales capacity status as a required Phase 0 input. Added CAC data fallback rule with three states (Full / Marketing CAC proxy / Data unavailable). Added finance alignment rule on CAC payback targets — no "healthy" framing without finance sign-off. Separated closed-won revenue and qualified pipeline in executive summary (now four numbers, not three) with explicit rule against summing different value pools. Added data confidence flag (High/Medium/Low) to executive summary. Added sales capacity check to Block 5 forward coverage. Added board deck compression guidance (1-2 slides) to Phase 2. Added Failure Modes 8 (conflated value pools), 9 (coverage without capacity), 10 (definition drift). Added Finance Alignment quality checklist section. Strengthened directional framing on industry CAC payback ranges.
- **v1.0a** (April 2026): First editorial revision. Removed employer-identifiable segment terminology (C1/C2) in favor of generic industry terms (SMB / Mid-market). Replaced specific dollar figure example in The Bet section with directional language. Replaced specific CAC payback numbers in hypothesis example with directional comparison. Added Phase 0 (Required Inputs) for input quality gating. Added Phase 4 measurement and learning loop. Added carry-forward rule on previous month's bet status. Softened CAC payback "healthy ranges" framing. Added Failure Modes 6 (placeholder generation) and 7 (industry benchmark substitution). Removed hard dependency on `quarterly-business-review-builder`.
- **v1.0** (April 2026): Initial release. Six-block report structure, template, quality checklist, common failure modes.
