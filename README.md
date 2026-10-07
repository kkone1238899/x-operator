# x-operator

A Claude plugin for **agent-operated X growth** — the operating system an AI agent uses to run a Twitter/X account with zero humans in the loop.

中文说明：[README_CN.md](./README_CN.md)

## The story

This plugin is extracted from a live experiment: an AI agent independently operating an X account — topic curation, content, engagement, review — no human writes, approves, or publishes. The agent doesn't just *use* this plugin; it *improves* it: every daily review writes reusable lessons back into the plugin, and repeated lessons get merged into the skills as standing rules.

"AI agent runs its own X account" is the experiment. This repo is the lab notes, executable.

## What it does

```
radar → curate → craft → engage → review → improve
  ↑                                      │
  └──────────────── loop ────────────────┘
```

| Skill | Job |
|---|---|
| `x-market-radar` | Daily scan of AI money-making projects — records HOW they did it, feeds curation |
| `x-topic-curation` | Score candidates on a 10-point rubric (≥7 to queue), de-duplicate, one topic per slot |
| `x-post-craft` | Draft through 3 gates: viral-factor checklist → critic self-score → de-AI pass |
| `x-engagement` | Sweep fresh posts on the posters' rhythm; replies must pass a standalone first-glance test (0 replies is valid); optional one-line soft-plug of your open-source projects |
| `x-profile` | Audit the profile as a conversion page — the follow decision happens there, not on the post |
| `x-review` | Daily attribution (reach vs conversion), LESSON/EVIDENCE/ACTION log, weekly merge into skills |

Four agent definitions (`agents/`) map 1:1 to the loop: curator, creator, engager, reviewer.

## The self-improvement loop

Most growth tools are static. This one isn't:

1. `reviewer` runs daily, appends lessons to `memory/changelog.md`
2. Every 7th review, lessons seen ≥2 times are merged into the skills as standing rules
3. The plugin gets smarter weekly — no human in the loop

## Setup

```bash
git clone https://github.com/kkone1238899/x-operator.git
# install as a Claude plugin, then:
cp config/config.example.yaml config/config.yaml
# fill in your handle, niche, red lines, watch lists
```

The plugin is generic — your account identity lives in `config/config.yaml`, which you never commit.

## References

- `references/playbook.md` — the six-pillar growth playbook
- `references/human-voice.md` — native X style (EN) + 去 AI 味 checklist (ZH)
- `references/scoring.md` — topic rubric + critic rubric details

## Standing on shoulders

Ideas adapted with thanks: [nirholas/xactions](https://github.com/nirholas/xactions) (plugin format), [etherlect/yappr](https://github.com/etherlect/yappr) (config-driven agent), [apcornation/x-growth-stack](https://github.com/apcornation/x-growth-stack) (growth pillars), [kangarooking/x-skills](https://github.com/kangarooking/x-skills) (scoring, critic, humanizer).

## License

MIT — see [LICENSE](./LICENSE). Contributions welcome: [CONTRIBUTING.md](./CONTRIBUTING.md).
