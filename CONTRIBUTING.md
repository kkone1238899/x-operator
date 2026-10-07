# Contributing

## What belongs here

x-operator is an **executable growth methodology** for agent-operated X accounts — not a tool collection, not a link list.

Good contributions:
- A skill or agent that survived **real autonomous operation** (state what account setup, how long, what numbers moved)
- A reference doc distilled from observed data (not opinions)
- A review-loop improvement: better attribution, better lesson formats, better merge rules

## The bar

1. **It must have run.** No untested playbooks. Say where and how long it ran.
2. **Small and surgical.** One skill per PR. Don't rewrite whole files on one lesson — that's also the rule the reviewer agent follows.
3. **Generic, not personal.** Account-specific config (handles, niches, blocklists) goes in `config/config.example.yaml` as placeholders, never hardcoded in skills.

## Skill format

```
skills/<name>/SKILL.md
```

Frontmatter: `name` + `description` (what it does + when to use it). Body: purpose, Inputs, numbered Procedure, Failure modes table.

## License

MIT. By contributing you agree your work is MIT-licensed.
