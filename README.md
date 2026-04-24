# B2B SaaS Marketing Skills for AI Agents

Operator-built marketing skills for B2B SaaS teams running enterprise and mid-market motions. Built for Claude Code, Claude Projects, Cursor, and any AI agent that reads SKILL.md files.

These aren't generic marketing prompts. They encode the workflows, terminology rules, and decision frameworks that B2B SaaS marketing teams actually use — pipeline attribution, ABM orchestration, compliance-safe messaging, BDR enablement, marketing ops governance, and competitive enablement.

**Built by** [Stallin Sanamandra](https://www.linkedin.com/in/stallinsanamandra) — growth marketing and demand generation leader at a B2B SaaS compliance automation platform, running multi-geo demand gen across NA-EU-ANZ and India-APAC.

## Why This Exists

The Claude skill ecosystem has 300+ marketing skills. Almost all of them are built for:

* Founder-led PLG companies
* Agency/freelancer workflows
* Consumer/DTC brands

If you run demand gen for a B2B SaaS company selling to enterprises — with 6-12 month sales cycles, multi-persona buying committees, HubSpot as your MAP, and pipeline (not leads) as your north star — the existing skills don't work out of the box.

This repo fills that gap.

## Skills

| Skill | What It Does | Status |
| --- | --- | --- |
| [GRC Messaging Guardrails](skills/grc-messaging-guardrails/SKILL.md) | Validates compliance/security terminology and enforces claim accuracy in marketing copy | ✅ Live |
| [Pipeline Attribution Narrator](skills/pipeline-attribution-narrator/SKILL.md) | Builds multi-touch attribution models and generates stakeholder-ready pipeline narratives | ✅ Live |
| [ABM Program Orchestrator](skills/abm-program-orchestrator/SKILL.md) | End-to-end ABM program design: account selection, tiering, channel orchestration, BDR coordination, measurement, and closed-loop optimization | ✅ Live |
| [BDR Enablement Generator](skills/bdr-enablement-generator/SKILL.md) | Account research briefs, personalized outreach sequences, persona-specific talk tracks, objection handling, and closed-loop performance review | ✅ Live |
| [Marketing Ops SOP Generator](skills/marketing-ops-sop-generator/SKILL.md) | Campaign naming conventions, UTM governance, lead routing, QA checklists, incident response, change management, and continuous drift detection | ✅ Live |
| [Competitive Battlecard Generator](skills/competitive-battlecard-generator/SKILL.md) | Competitor intelligence briefs, persona-specific battlecards, win/loss analysis, deployment playbooks, and decay prevention with 90-day refresh cycles | ✅ Live |

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

## Who This Is For

* **Demand gen leaders** at B2B SaaS companies ($5M-$100M ARR) running paid + ABM + content motions
* **Marketing ops managers** who need standardized processes for HubSpot, UTM governance, and campaign tracking
* **Growth marketers** who report on pipeline and revenue, not MQLs
* **BDR/SDR managers** who need scalable account research and outreach frameworks

## Design Principles

1. **Pipeline over leads.** Every skill measures success in pipeline dollars, not vanity metrics.
2. **Enterprise buyer reality.** Multi-persona buying committees, 6-12 month cycles, risk-averse decision-makers.
3. **Operator-built, not theory-derived.** These skills encode workflows tested with real budget and real quota.
4. **HubSpot-native where applicable.** Field names, workflow logic, and attribution models reference HubSpot conventions.
5. **Vertical-aware.** GRC/cybersecurity/compliance context is baked in where relevant, but the frameworks apply to any regulated B2B SaaS vertical.
6. **Motion-aware.** Different ABM and demand gen motions require different orchestration. These skills distinguish between 1:1 strategic ABM, 1:few segment-based ABM, 1:many account-targeted campaigns, competitive displacement plays, and expansion motions. Framework logic adapts to the motion, not the other way around.

## Context File (Recommended)

## Context File (Recommended)

For best results, create a `product-context.md` file alongside your skills with:

* Your ICP definition (company size, vertical, buyer personas)
* Your product's positioning statement
* Your approved messaging and terminology rules
* Your funnel stage definitions (MQL → SQL → SQO → Closed Won)
* Your channel mix and budget allocation

See [context/product-context-template.md](context/product-context-template.md) for a starter template.

## Contributing

Found a gap? Built a B2B SaaS marketing skill that should be here? PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

Requirements for contributed skills:

* Must be specific to B2B SaaS (not generic marketing)
* Must reference pipeline/revenue metrics (not lead volume)
* Must follow the SKILL.md format with YAML frontmatter
* Must include "When to Use" and "When NOT to Use" sections

## License

MIT — use it, fork it, adapt it. See [LICENSE](LICENSE).
