---
name: linkedin-post-generator-operator-pov
description: >
  Generates publish-ready LinkedIn posts for B2B SaaS marketing leaders writing
  from an operator point of view: real decisions, real trade-offs, real
  constraints, and defensible lessons. Use when turning an internal observation,
  framework, campaign decision, miss, or shipped artifact into a public LinkedIn
  post. Best for demand generation, ABM, marketing ops, product marketing, and
  SaaS GTM leaders building credibility through practical operating insight.
  Not intended for generic brand posts, company announcements, sales outreach,
  or long-form content.
---

# LinkedIn Post Generator (Operator POV)

> A repeatable framework for turning real operator insights into LinkedIn posts
> that read like they came from someone running the work — not a content
> marketer pretending to. Replaces the "this could apply to anyone" voice with
> specificity that signals depth, while keeping employer-identifiable details
> off the public record.

## Why This Skill Exists

Most marketing leaders' LinkedIn output reads identical to every other
marketing leader's LinkedIn output: vague aphorisms, framework worship, and
posts that could have been written by anyone in any company. The signal of
"I've actually done this" is missing.

This skill fixes three failure modes:

1. **Generic frame, generic content.** Posts about "the importance of
   alignment" or "data-driven decision making" are wallpaper. They don't
   distinguish the writer from any other marketing voice.

2. **Abstract claims, no proof.** "ABM works." "Pipeline marketing is dead."
   Without operator-level specificity (decisions, trade-offs, directional
   numbers), claims read as opinions, not evidence.

3. **Polish without payoff.** A well-formatted post with no actual insight is
   worse than a rough post with one real lesson. Most generators optimize for
   readability and skip the substance.

This skill produces posts that lead with a real operator situation (decision,
trade-off, miss, win), expose the reasoning, and end with a learnable takeaway
or open question — not a forced CTA or generic conclusion.

## When to Use This Skill

- Drafting a LinkedIn post about a marketing decision, framework, or lesson
- Turning an internal artifact (skill, doc, dashboard) into a public-facing post
- Announcing a new repo, framework, or open-source contribution
- Converting a longer piece of writing (newsletter, blog) into a LinkedIn-native version
- Building a 4-post queue to fill out a weekly publishing cadence
- Responding to a competitor or industry event with an operator point of view
- Documenting a miss or change in approach (these often outperform "win" posts)

## When NOT to Use This Skill

- Long-form blog posts (different length, different structure — use a blog skill)
- Newsletter writing (use a newsletter-specific skill)
- Sales outreach or BDR sequences (use `bdr-enablement-generator`)
- Internal Slack messages or memos (different audience, different voice)
- Posts about real public figures (avoid attributing fictional quotes; this skill is for first-person operator content)

## How This Skill Fits Into the Skill Stack

```
Internal artifact (skill, doc, framework, decision)
   ↓
linkedin-post-generator-operator-pov  →  Drafts the LinkedIn post  ← YOU ARE HERE
   ↓
[Humanization pass — see Phase 5]      →  Removes AI tells, tightens voice
   ↓
grc-messaging-guardrails               →  Validates compliance terminology if relevant
   ↓
Publish
```

**Future companion skill:** `content-calendar-orchestrator` if added later for
batching posts into a publishing cadence.

The humanization pass is mandatory. AI-generated text has tells that operator
audiences detect immediately. If a separate `humanizer` skill is available in
your environment, use it. Otherwise, apply the embedded humanization checklist
in Phase 5.

---

## Phase 0: Required Inputs

Before drafting, gather enough operator context to avoid generic content. If
the input does not include a real decision, constraint, directional number,
trade-off, or lesson, ask for more context or produce a weaker "draft for
refinement," not a final post.

| Input | Why It Matters |
|---|---|
| Topic or source artifact | Defines what the post is about |
| Intended audience | Determines whether the post speaks to marketers, founders, sales leaders, BDRs, or operators |
| Post archetype | Controls structure and tone (see Phase 1) |
| Real situation | Anchors the post in operating reality |
| Decision or trade-off | Creates operator credibility |
| Safe-to-share details | Prevents leaking employer-specific information (apply the redaction ladder in Phase 4) |
| Desired outcome | Clarifies whether the post should drive discussion, repo visits, credibility, hiring, or pipeline influence |

**Rule.** If three or more inputs are missing or weak, the skill produces a
"draft for refinement" — a starter shape that asks for more operator detail,
not a publish-ready post. Pretending to have specificity that isn't there
creates exactly the generic wallpaper this skill exists to prevent.

---

## Phase 1: The Five Post Archetypes

Most operator-POV posts fall into one of five archetypes. Pick the archetype
first; the structure follows.

### Archetype 1: The Decision Post

**When to use.** You made a non-obvious call and want to walk through the
reasoning.

**Structure.**
- Hook: The decision in one sentence (often counterintuitive)
- Context: Two sentences on the real situation (segment, constraint, directional figure)
- The reasoning: 3-5 lines on why you decided this way
- The trade-off: What you gave up to make this call
- The takeaway: One line on what this generalizes to (or a question)

**Example shape (numbers anonymized via redaction ladder).**
> Shifted a six-figure quarterly budget from paid social into an ABM cohort.
>
> The math: the existing channel had a long CAC payback. The ABM cohort
> projected a shorter payback, with higher ACV potential but slower initial
> volume.
>
> The trade-off: paid social was generating volume — a meaningful share of
> monthly SQOs. Pulling that budget meant accepting an SQO drop in Q1 in
> exchange for ACV in Q2.
>
> The reasoning: SQOs aren't the metric. CAC payback is. A lower-volume,
> higher-ACV motion compounds. A higher-volume, longer-payback motion drains.
>
> Hardest part wasn't the math. Was sitting with the SQO drop while the new
> motion ramped.

### Archetype 2: The Framework Post

**When to use.** You have a repeatable framework that's working in your
operating reality — not a borrowed one.

**Structure.**
- Hook: The framework in one sentence
- The problem it solves: Two sentences on the operator pain
- The framework: 3-7 named components (numbered list works here, but only here)
- The proof: One sentence on where this came from (your decisions, your outcomes)
- The takeaway: One line on when *not* to use it

**Anti-pattern.** Don't post a framework you read in a book. Don't post a
framework from a vendor blog. The signal of an operator framework is that it
was *forced* by a real constraint and refined by real outcomes.

### Archetype 3: The Miss Post

**When to use.** You ran a play, it didn't work, and you can articulate why.
These posts often outperform wins because they're rare and signal honesty.

**Structure.**
- Hook: The miss, stated plainly (no "lessons learned" framing)
- What you tried: Two sentences on the actual play
- What happened: The result, in directional terms
- The diagnosis: 2-3 lines on what was wrong with the assumption
- The takeaway: What you'd do differently

**Critical rule.** A miss post is not self-flagellation. It's diagnosis. If
the post reads as performative humility, scrap it. The signal is "I learned
something" not "I'm humble."

### Archetype 4: The Counter Post

**When to use.** You disagree with a widely-accepted take, and you have
operating evidence to back it.

**Structure.**
- Hook: The take you're countering, in one sentence
- The standard reasoning: Two sentences on why people believe it
- Your counter: 3-4 lines on why it's wrong (or incomplete) in your operating reality
- The evidence: One sentence on the proof (your decisions, your outcomes)
- The qualifier: When the standard take *is* right (always include this)

**Why the qualifier matters.** Counter posts without nuance read as
contrarianism. The qualifier signals that you've thought through both sides
and chosen yours deliberately.

### Archetype 5: The Build Post

**When to use.** You shipped something — a skill, a doc, a framework, a tool —
and want to share it.

**Structure.**
- Hook: What you built and why (in one sentence each)
- The problem it solves: Two sentences on the operator pain
- How it works: 2-3 lines on the mechanism (no implementation details)
- Where to find it: Direct link or pointer
- The ask: One line on feedback or use cases (optional)

**Link placement.** If usage is the goal (you want people to use the artifact),
put the link clearly in the post. If reach is the goal (you want broad
distribution and the artifact is a credibility signal), test link placement —
but never hide the artifact so deeply that interested readers cannot find it.

---

## Phase 2: The Operator Voice — What Distinguishes It

The voice is the differentiator. Five rules separate operator posts from
content-marketer posts.

### Rule 1: Specificity Beats Generality

Bad: "We saw great results from our ABM program."

Good: "Our ABM cohort generated meaningful pipeline influence across the
target segment in 60 days. Cost per SQO was higher than other channels. ACV
was directionally stronger. CAC payback came in shorter than the channel it
replaced."

Use directional language ("roughly," "in the ballpark of," "directionally,"
"meaningfully") when specifics would identify your employer. Never default to
generic claims when defensible specificity is available.

### Rule 2: Show the Decision, Not Just the Outcome

Bad: "ABM works for mid-market."

Good: "We had two choices: scale the existing channel to hit volume targets,
or shift budget to ABM and accept a Q1 SQO drop. We chose ABM because CAC
payback matters more than volume."

Outcomes are claims. Decisions are evidence.

### Rule 3: Name the Trade-Off

Every real operating decision has a trade-off. Posts that hide the trade-off
read as marketing, not operator content.

Bad: "We launched an ABM cohort and it worked."

Good: "Launching an ABM cohort meant pulling budget from a working channel
and accepting a 30-day SQO dip while the motion ramped. The trade-off was
real."

### Rule 4: No Forced CTAs

Operator posts don't end with "DM me to learn more" or "what do you think?"
forced engagement bait. They end with either:

- A real takeaway (one line, generalizable)
- A real question (something you genuinely don't know the answer to)
- Nothing (sometimes the post stands on its own)

### Rule 5: Short Sentences. No Em-Dashes. Minimal Adjectives.

LinkedIn rewards readability. Operator posts use:
- Short sentences (8-15 words average)
- One idea per line
- Concrete nouns
- Active verbs
- No em-dashes (replace with periods or commas)
- Adjectives only when they carry information ("shorter payback period" not "extremely long payback")

---

## Phase 3: The Post Template

```markdown
[Hook line — one sentence. The most counterintuitive or specific claim in the post.]

[Context line 1 — sets the situation in concrete terms.]
[Context line 2 — adds a directional figure or constraint that makes the situation real.]

[Body — 4-8 short lines. Each carries one idea. Use whitespace generously.]

[Trade-off or qualifier line — names what was given up or when this doesn't apply.]

[Takeaway or question — one line. Generalizable or genuinely open.]

[Optional: Link to the artifact, doc, or repo. Placement based on goal — see Build archetype.]
```

**Default length target.** 100-180 words for mobile readability. Longer posts
can work when the story has real tension, but do not add length without
adding insight. Posts under 80 words feel insubstantial.

**Formatting.** One blank line between every 1-2 lines of text. No bold, no
italics, no emoji walls. Operator voice is unadorned.

---

## Phase 4: Public Content Constraints

Operator posts use real specificity when possible. But there are limits.

### What Should Not Appear in Public Posts

- Specific budget figures from your employer
- Specific revenue or ARR figures from your employer
- Specific named customer logos unless already public
- Specific named competitor deals or win/loss details
- Internal stakeholder names (CEO, CFO, VP Sales by name)
- Specific named employees or reports
- Industry benchmarks presented as fact without a source

### What Can Appear in Public Posts

- Directional figures ("a six-figure quarterly budget," "low-eight-figure ARR range")
- Industry-standard ranges only when sourced or anonymized from internal experience
- Anonymized situations ("a B2B SaaS company in compliance automation")
- Frameworks and methodologies (these aren't proprietary)
- Personal observations and decisions
- Sourced public benchmarks (cite the source)

### Redaction Ladder

Use the most specific version that is safe. Specificity should create
credibility without making the post identifiable as an internal company memo.

| Private Detail | Safer Public Version |
|---|---|
| Exact budget | Directional range: "six-figure quarterly budget" |
| Exact pipeline number | Directional outcome: "meaningful pipeline influence" |
| Named customer | Segment: "mid-market FinTech customer" |
| Named competitor deal | Category: "incumbent GRC vendor" |
| Internal stakeholder name | Role: "finance leader," "sales leader," "CEO" |
| Exact CAC payback | Relative comparison: "shorter payback," "longer payback" |
| Specific industry benchmark | Sourced citation OR personal experience qualifier ("In the deals I've run...") |

**Rule.** When in doubt, climb one rung up the ladder. The post should be
defensible if a colleague reads it. Specificity that crosses into
employer-identifiable detail is a career risk, not a thought leadership move.

---

## Phase 5: Quality Bar (Including Embedded Humanization Pass)

Before a post is published, run this checklist.

### Voice and Specificity
- [ ] Hook line is specific, not generic (decisions, directional numbers, or counterintuitive claim)
- [ ] At least one concrete decision, constraint, or directional figure in the body
- [ ] No phrases that could appear in any other marketer's post ("data-driven," "alignment," "synergy")
- [ ] Trade-off is named explicitly somewhere in the post
- [ ] No forced CTA at the end

### Public Content Safety
- [ ] No employer-specific budget figures
- [ ] No employer-specific revenue or ARR
- [ ] No internal stakeholder names
- [ ] Redaction ladder applied where specificity would be inappropriate
- [ ] Any industry benchmarks cited or qualified with personal experience

### Compliance Terminology (if applicable)
- [ ] Any GRC/compliance terms validated against `grc-messaging-guardrails`
- [ ] SOC 2 referred to as attestation, not certification
- [ ] Framework names spelled correctly (ISO 27001, not ISO27001 or ISO 27,001)

### Format
- [ ] Length 100-180 words (default), longer only if tension justifies it
- [ ] No em-dashes
- [ ] No emoji walls
- [ ] Whitespace between every 1-2 lines

### Embedded Humanization Pass

Run this checklist before publishing. If a separate `humanizer` skill is
available in your environment, use it instead — these checks duplicate its
core logic.

- [ ] No phrases like "in today's fast-paced world," "in the world of B2B SaaS," "navigate the complexities of"
- [ ] No "leverage" as a verb, no "strategic" as filler, no "robust" as praise
- [ ] No three-item lists where two would do (rule of three is an AI tell)
- [ ] No symmetrical sentence pairs ("It's not X, it's Y") unless the contrast is real
- [ ] No vague attributions ("studies show," "experts say") without a source
- [ ] No conjunctive phrases used as transitions ("That said," "With that being said," "Furthermore")
- [ ] No em-dashes anywhere
- [ ] Read aloud — does it sound like you actually said it? If a colleague read it, would they recognize your voice?

### Final Pass
- [ ] If it could be posted by any marketer at any company, scrap it

---

## Phase 6: Measurement and Learning Loop

LinkedIn thought leadership is not measured only by likes. For B2B SaaS
operators, the goal is credibility, useful conversations, and eventual
pipeline influence. Track three levels and review the pattern every 4-6
weeks.

### Track Three Levels

| Level | Signal | What It Tells You |
|---|---|---|
| **Content quality** | Saves, comments from ICP, reposts with substance | The idea was useful |
| **Relationship creation** | Profile views from ICP, connection requests, DMs, event/podcast invites | The post built market credibility |
| **Business influence** | Self-reported source mentions, CRM notes, influenced opportunities, sales conversations referencing the post | The content may be contributing to pipeline |

**Anti-pattern.** Optimizing for Level 1 (likes, broad engagement) at the
expense of Level 2 and Level 3. A post with 50 likes from ICP buyers is
worth more than a post with 500 likes from generic marketing audiences.

### Per-Post Feedback Capture

After publishing, record:

```markdown
## Post Feedback

- **Post archetype:** Decision / Framework / Miss / Counter / Build
- **Topic:** [Post topic]
- **Audience reached:** [ICP / peers / generic audience]
- **Strongest signal:** [Save / comment / DM / profile view / meeting / opportunity mention]
- **What worked:** [1 sentence]
- **What to change next time:** [1 sentence]
```

### Review Cadence

Every 4-6 weeks, review the pattern across recent posts:

- Which archetypes are creating ICP conversations? Double down.
- Which archetypes are creating broad engagement but no ICP signal? Reduce.
- Which topics are showing up in CRM notes or sales conversations? These
  posts are contributing to pipeline — produce more of them.
- Which posts felt like wins but produced no Level 2 or Level 3 signal?
  These are vanity posts. Stop writing them.

The compound goal: every quarter, the share of posts producing ICP
conversations and pipeline-relevant signals should grow. If the ratio is
flat after two quarters, the archetype mix or topic selection is wrong.

---

## Common Failure Modes

### Failure 1: The Wallpaper Post
Symptom: Post about "the importance of alignment between marketing and sales."
Could be written by anyone, signals nothing.

Fix: Anchor every post in a specific operator situation. If you can't, don't
post.

### Failure 2: The Borrowed Framework
Symptom: Post about "the 4 Ps of marketing in B2B SaaS." Reads as
recycled MBA content.

Fix: Only post frameworks that emerged from your operating reality. Borrowed
frameworks read as borrowed.

### Failure 3: The Performative Miss
Symptom: "Mistakes I made in ABM and what I learned" post that's actually
humble-bragging.

Fix: Real miss posts are uncomfortable to write. If the post feels
comfortable, it's not a real miss — it's marketing.

### Failure 4: The Forced CTA
Symptom: Post ends with "What's your take? DM me!" or "Drop a 🔥 if you
agree."

Fix: Either have a real question or end on the takeaway. Engagement bait
signals low confidence.

### Failure 5: The Compliance Slip
Symptom: Post calls SOC 2 a "certification." Compliance buyers in audience
silently downgrade your credibility.

Fix: Mandatory `grc-messaging-guardrails` pass on any post mentioning
compliance frameworks.

### Failure 6: The AI Voice
Symptom: Post uses phrases like "in today's fast-paced world,"
"navigate the complexities of," or "leverage strategic insights."

Fix: Mandatory humanization pass before publishing (Phase 5 embedded
checklist or `humanizer` skill if available). AI tells kill operator
credibility instantly.

### Failure 7: The Employer Leak
Symptom: Post includes specific budget figures, named internal stakeholders,
or details that make it identifiable as an internal company memo.

Fix: Apply the Phase 4 redaction ladder. Specificity should create
credibility, not legal exposure.

### Failure 8: The Vanity Post
Symptom: Post got 200 likes but produced zero Level 2 or Level 3 signal
(no ICP DMs, no profile views from buyers, no CRM mentions).

Fix: Track the three levels in Phase 6. Stop writing posts that produce
likes but no business-relevant signal.

---

## Integration With Other Skills

- **Inputs from:** Any internal artifact (skill, doc, framework, decision log)
- **Validated by:** `grc-messaging-guardrails` (compliance terminology)
- **Humanization:** Phase 5 embedded checklist OR `humanizer` skill if available in environment
- **Future companion skill:** `content-calendar-orchestrator` if added later for batching posts into a publishing cadence

---

## Changelog

- **v1.0a** (April 2026): Pre-merge revision after editorial review. Removed all employer-specific budget figures from examples and replaced with directional language per redaction ladder. Tightened YAML description. Added Phase 0 (Required Inputs) for input quality gating. Removed hard dependency on `humanizer` skill (not in public repo) — embedded humanization pass into Phase 5 checklist with optional reference to `humanizer` if available. Removed hard dependency on `content-calendar-orchestrator` (does not exist) — marked as future companion skill. Added Phase 4 redaction ladder for safe public translation of internal details. Added Phase 6 measurement and learning loop (three-level tracking: content quality, relationship creation, business influence) with per-post feedback capture and 4-6 week review cadence. Softened "LinkedIn rewards this range" length claim to "default readability target." Reframed Build-archetype link guidance from absolute "above the fold" to reach-vs-usage trade-off. Added sourcing requirement for industry benchmarks. Added Failure Modes 7 (employer leak) and 8 (vanity post).
- **v1.0** (April 2026): Initial release. Five post archetypes (decision, framework, miss, counter, build), operator voice rules, public content constraints, quality checklist, common failure modes.
