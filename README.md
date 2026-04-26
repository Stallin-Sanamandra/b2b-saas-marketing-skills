# B2B SaaS Marketing Skills for AI Agents

Operator-built marketing skills for B2B SaaS teams running enterprise and mid-market motions. Built for Claude Code, Claude Projects, Cursor, and any AI agent that reads SKILL.md files.

These aren't generic marketing prompts. They encode the workflows, terminology rules, and decision frameworks that B2B SaaS marketing teams actually use — pipeline attribution, ABM orchestration, compliance-safe messaging, BDR enablement, marketing ops governance, competitive enablement, account research, executive revenue reporting, and operator thought leadership.

**Built by** [Stallin Sanamandra](https://www.linkedin.com/in/stallinsanamandra) — growth marketing and demand generation leader at a B2B SaaS compliance automation platform, running multi-geo demand gen across NA-EU-ANZ and India-APAC.

## Why This Exists

There are many generic marketing skills and prompt libraries in the AI ecosystem, but most are built for:

* Founder-led PLG companies
* Agency and freelancer workflows
* Consumer and DTC brands
* Broad content creation

If you run demand gen for a B2B SaaS company selling to enterprises — with 6-12 month sales cycles, multi-persona buying committees, HubSpot as your MAP, and pipeline (not leads) as your north star — those existing skills don't work out of the box.

This repo fills that gap.

## Skill Library

Nine live skills, grouped by workflow category. Each skill is independently usable. They also chain into workflows (see Common Workflows below).

### Revenue, Attribution, and Executive Reporting

| Skill | What It Does | Status |
| --- | --- | --- |
| [Pipeline Attribution Narrator](skills/pipeline-attribution-narrator/SKILL.md) | Builds multi-touch attribution models and generates stakeholder-ready pipeline narratives | ✅ Live |
| [CEO Monthly Revenue Report Generator](skills/ceo-monthly-revenue-report-generator/SKILL.md) | Monthly revenue-accountable marketing report for CEOs, CFOs, and boards: revenue contribution, CAC payback by segment with finance alignment, channel performance, forward pipeline coverage with sales capacity check, and a 30-day bet | ✅ Live |

### ABM, Outbound, and BDR Enablement

| Skill | What It Does | Status |
| --- | --- | --- |
| [ABM Program Orchestrator](skills/abm-program-orchestrator/SKILL.md) | End-to-end ABM program design: account selection, tiering, channel orchestration, BDR coordination, measurement, and closed-loop optimization | ✅ Live |
| [Account Research Brief Generator](skills/account-research-brief-generator/SKILL.md) | Tier-calibrated, sourced research briefs for named target accounts: company snapshot, GRC surface area, trigger events, buying committee, tech stack signals, outreach hypothesis, and per-account feedback loop | ✅ Live |
| [BDR Enablement Generator](skills/bdr-enablement-generator/SKILL.md) | Account research briefs, personalized outreach sequences, persona-specific talk tracks, objection handling, and closed-loop performance review | ✅ Live |

### Messaging, Positioning, and Competitive

| Skill | What It Does | Status |
| --- | --- | --- |
| [GRC Messaging Guardrails](skills/grc-messaging-guardrails/SKILL.md) | Validates compliance/security terminology and enforces claim accuracy in marketing copy | ✅ Live |
| [Competitive Battlecard Generator](skills/competitive-battlecard-generator/SKILL.md) | Competitor intelligence briefs, persona-specific battlecards, win/loss analysis, deployment playbooks, and decay prevention with 90-day refresh cycles | ✅ Live |

### Marketing Operations

| Skill | What It Does | Status |
| --- | --- | --- |
| [Marketing Ops SOP Generator](skills/marketing-ops-sop-generator/SKILL.md) | Campaign naming conventions, UTM governance, lead routing, QA checklists, incident response, change management, and continuous drift detection | ✅ Live |

### Thought Leadership

| Skill | What It Does | Status |
| --- | --- | --- |
| [LinkedIn Post Generator (Operator POV)](skills/linkedin-post-generator-operator-pov/SKILL.md) | Five archetypes (decision, framework, miss, counter, build) for converting real B2B SaaS marketing decisions into credible LinkedIn posts, with redaction ladder, embedded humanization checklist, and three-level measurement loop | ✅ Live |

## How to Choose the Right Skill

| If you need to... | Use this skill |
| --- | --- |
| Explain marketing-sourced or influenced pipeline | Pipeline Attribution Narrator |
| Build a CEO/CFO monthly revenue report | CEO Monthly Revenue Report Generator |
| Design an ABM program from account list to measurement | ABM Program Orchestrator |
| Research a named target account before outreach | Account Research Brief Generator |
| Turn account research into BDR sequences and talk tracks | BDR Enablement Generator |
| Validate compliance/security terminology and claims | GRC Messaging Guardrails |
| Build a competitor battlecard with win/loss intelligence | Competitive Battlecard Generator |
| Standardize campaign operations, UTMs, lead routing, and QA | Marketing Ops SOP Generator |
| Turn operator decisions and lessons into LinkedIn posts | LinkedIn Post Generator (Operator POV) |

## Common Workflows

The skills are more valuable as a system than as isolated files. Four common workflows that chain multiple skills together:

### 1. Build and activate an ABM motion

```
ABM Program Orchestrator
   ↓ (target account list, tiering)
Account Research Brief Generator
   ↓ (per-account research briefs)
BDR Enablement Generator
   ↓ (outreach sequences, talk tracks, objection handlers)
GRC Messaging Guardrails
   ↓ (compliance terminology validation)
Pipeline Attribution Narrator
   ↓ (measure ABM contribution to pipeline)
```

### 2. Prepare a monthly executive marketing review

```
Pipeline Attribution Narrator
   ↓ (attribution model + monthly numbers)
CEO Monthly Revenue Report Generator
   ↓ (executive-ready monthly report with CAC payback and forward coverage)
Marketing Ops SOP Generator
   ↓ (if data integrity gaps surfaced during reporting)
```

### 3. Launch a competitor displacement campaign

```
Competitive Battlecard Generator
   ↓ (positioning, win/loss intelligence, persona angles)
GRC Messaging Guardrails
   ↓ (validate any compliance claims in displacement messaging)
BDR Enablement Generator
   ↓ (displacement-specific outreach sequences)
Pipeline Attribution Narrator
   ↓ (measure competitive displacement pipeline contribution)
```

### 4. Turn internal operating lessons into public thought leadership

```
Internal artifact, decision, or campaign result
   ↓
LinkedIn Post Generator (Operator POV)
   ↓ (operator-voice draft with redaction ladder applied)
GRC Messaging Guardrails
   ↓ (if the post references compliance frameworks)
```

## Installation

### Claude Projects (claude.ai)

Upload any `SKILL.md` file as a Project Knowledge document. Strip the YAML frontmatter if Claude doesn't process it correctly in your setup.

### Claude Code

```
git clone https://github.com/Stallin-Sanamandra/b2b-saas-marketing-skills.git
cp -r b2b-saas-marketing-skills/skills/* ~/.claude/skills/
```

### Cursor / Windsurf / Other Agents

Copy skill folders into your project's `.cursor/skills/` or equivalent directory. Skills auto-activate based on task context.

### Manual (Any LLM)

Open the SKILL.md file, copy its contents, and paste it as your system prompt or first message. Works with Claude, ChatGPT, Gemini, or any LLM.

## Example Usage

Once installed, activate a skill by referencing it in a prompt with the relevant context:

```
Use the ABM Program Orchestrator skill to design a 1:many ABM motion
for 500 mid-market SaaS accounts in North America. Goal: generate
$500K qualified pipeline in 90 days. ICP: 200-1000 employees,
SOC 2 or ISO 27001 in scope, current GRC tooling either none or
non-Vanta/non-Drata.
```

```
Use the Account Research Brief Generator to create a Tier 2 brief for
[Company]. Primary persona: VP Engineering. Relevant frameworks: SOC 2
and ISO 27001. First-party signal: 3 visits to our pricing page in the
last 30 days.
```

```
Use the CEO Monthly Revenue Report Generator to draft this month's
executive marketing report using the attached pipeline data, spend
breakdown by channel, and segment-level closed-won numbers. CAC
status this month: marketing CAC proxy (sales spend allocation
pending from finance).
```

```
Use the LinkedIn Post Generator (Operator POV) to turn this internal
ABM cohort lesson into a public post. Archetype: Decision. Apply the
redaction ladder — no specific dollar figures, no internal stakeholder
names. Run the embedded humanization checklist before final output.
```

## Who This Is For

* **Demand gen leaders** at B2B SaaS companies (Series A through D, $5M-$200M ARR) running paid + ABM + content motions
* **Marketing ops managers** who need standardized processes for HubSpot, UTM governance, and campaign tracking
* **Growth marketers** who report on pipeline and revenue, not MQLs
* **BDR/SDR managers** who need scalable account research and outreach frameworks
* **Marketing consultants** advising B2B SaaS clients on demand gen and ABM motions

## Design Principles

1. **Pipeline over leads.** Every skill measures success in pipeline dollars, not vanity metrics.
2. **Enterprise buyer reality.** Multi-persona buying committees, 6-12 month cycles, risk-averse decision-makers.
3. **Operator-built, not theory-derived.** These skills encode workflows tested with real budget and real quota.
4. **HubSpot-native where applicable.** Field names, workflow logic, and attribution models reference HubSpot conventions.
5. **Vertical-aware.** GRC/cybersecurity/compliance context is baked in where relevant, but the frameworks apply to any regulated B2B SaaS vertical.
6. **Motion-aware.** Different ABM and demand gen motions require different orchestration. These skills distinguish between 1:1 strategic ABM, 1:few segment-based ABM, 1:many account-targeted campaigns, competitive displacement plays, and expansion motions. Framework logic adapts to the motion, not the other way around.

## Recommended Context File

For best results, create a `product-context.md` file alongside your skills with:

* Your ICP definition (company size, vertical, buyer personas)
* Your product's positioning statement
* Your approved messaging and terminology rules
* Your funnel stage definitions (MQL → SQL → SQO → Closed Won)
* Your channel mix and budget allocation

See [context/product-context-template.md](context/product-context-template.md) for a starter template.

## Data Privacy and Usage Notes

These skills are designed to encode workflows, not private company data. The skill files in this repo are intentionally generic and reusable across any B2B SaaS company.

When you populate a context file or apply these skills to your own operating data, **keep that data private**. Do not commit context files containing:

* Customer names or specific deal details
* Non-public revenue, pipeline, budget, or CAC figures
* Internal stakeholder names (CEO, CFO, VP Sales by name)
* Proprietary strategy documents
* Private competitive intelligence
* Access tokens, API keys, or CRM exports

Keep company-specific context in a private local file, private Claude Project, private Cursor workspace, or secure internal knowledge base. The public version of these skills should remain reusable frameworks, not records of confidential operating data.

This matters because the skills increasingly reference revenue, CAC, ABM accounts, pipeline, and executive reporting. The skills themselves are safe to share publicly. Your numbers are not.

## Status Definitions

| Status | Meaning |
| --- | --- |
| ✅ Live | Reviewed, ready for use, structurally complete |
| 🧪 Beta | Functional but needs more real-world testing before broad recommendation |
| 📝 Draft | In progress, not recommended for production use |
| 🔁 Needs Refresh | Useful but requires updates due to stale assumptions or framework drift |

All current skills are Live. Status will be updated as skills evolve based on production usage.

## Contributing

Found a gap? Built a B2B SaaS marketing skill that should be here? PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

Requirements for contributed skills:

* Must be specific to B2B SaaS (not generic marketing)
* Must reference pipeline/revenue metrics (not lead volume)
* Must follow the SKILL.md format with YAML frontmatter
* Must include "When to Use" and "When NOT to Use" sections
* Must include a measurement or feedback loop (consistent with the repo's pipeline-orientation rule)

## License

MIT — use it, fork it, adapt it. See [LICENSE](LICENSE).
