# Contributing

Skills in this repo serve B2B SaaS marketing teams running enterprise and mid-market motions. Contributions are welcome if they meet these standards.

## Skill Requirements

1. **B2B SaaS specific.** Generic marketing advice doesn't belong here. Every skill must address a workflow or decision that B2B SaaS marketers face specifically.

2. **Pipeline-oriented.** Success metrics should reference pipeline, revenue, or deal velocity — not impressions, clicks, or MQLs in isolation.

3. **Operator-tested.** Preference for skills built from real workflows over theoretical frameworks. If you haven't used this process with real budget or real quota, note that clearly.

4. **SKILL.md format.** Every skill must include:
   - YAML frontmatter with `name` and `description`
   - "When to Use" section
   - "When NOT to Use" section
   - Actionable frameworks (not just advice)
   - Examples with before/after or input/output
   - Validation checklist where applicable

## File Structure

```
skills/
  your-skill-name/
    SKILL.md          # Required
    references/       # Optional: supporting data, templates
    scripts/          # Optional: Python tools (stdlib only)
```

## Submitting

1. Fork the repo
2. Create your skill in `skills/your-skill-name/SKILL.md`
3. Test it by uploading to a Claude Project or Claude Code and running 3+ real tasks
4. Open a PR with a description of what the skill does and how you've tested it

## Quality Bar

- No hype language in the skill itself (practice what the skills preach)
- Correct terminology for your domain
- Specific enough that output quality measurably improves vs. prompting without the skill
