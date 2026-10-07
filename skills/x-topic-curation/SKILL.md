---
name: x-topic-curation
description: Curate daily X content topics with a 10-point scoring rubric. Use every morning (or before any content batch) to turn raw candidates into a short queue of scored, de-duplicated topics — one per content slot. Separate topic selection from production: pick first, produce later.
---

# x-topic-curation

A bad topic fails 50% before a word is written. This skill scores candidates on a fixed rubric and only queues winners.

## Inputs

- `slots`: the day's content slots (e.g. `video`, `post-noon`, `post-evening`)
- `config`: account config (`config/config.yaml`) — niche, content pillars, red lines, watch lists
- `sources`: where candidates come from — start with `references/hotspot-sources.md` (sopilot / tophub / newsnow / aihot.news), then niche news, watch-list comments, GitHub trending, pain points

## Procedure

### 1. Review yesterday

Read the post log. Note which topic angles worked and which flopped. Working angles get a bonus today; flopped angles are avoided. One line per lesson, no essays.

### 2. Collect candidates (last 24h)

Gather 8–15 raw candidates. **Start with the hotspot layer** (`references/hotspot-sources.md`): check sopilot (X taking off), tophub (cross-platform lists), newsnow (real-time), aihot.news (AI vertical). What's rising on ≥2 of these — or 1 site + watch-list bloggers — is a candidate. A lone viral post is a lead, not a hotspot.
Then add:
- Niche hot topics: new models, product launches, industry drama
- Money angles: monetization cases, creator revenue, platform monetization updates
- High-frequency questions in watch-list creators' comment sections
- GitHub trending (top by velocity, if technical niche)
- Real user pain points in the niche

Record for each: one-line description + source link + **source tier** (T1 first-party / T2 media-personal).

### 3. Score TWICE (10-point rubric, AIHOT method)

**Score every candidate twice, independently** — second pass without looking at the first score. Take the average. **Avg ≥7 to enter the queue.** A candidate that swings wildly between passes is noise: drop it or re-examine.

**Source-tier bars**: T1 (official announcement, original launch, builder's own post) gets a lower bar — first-hand is worth covering even at modest heat. T2 (commentary, reposts, hot takes) must earn it with heat or insight.

| Dimension | Points | What it measures |
|---|---|---|
| Trend / heat | 4 | Current discussion volume, is it still fermenting |
| Controversy | 2 | Can it spark discussion or opposing views |
| Value density | 3 | Information density, actionability |
| Account fit | 1 | Fit with the account's positioning |

Kill anything under 7. No mercy — a weak topic in the queue wastes a production slot.

### 4. Cluster into events, then de-duplicate

Multiple sources on the same story = **one event**. Give it an event id; heat = number of **independent** sources in the last 48h (one outlet posting 10 times counts once). Queue the event once with the sharpest angle — never queue 3 topics that are the same story.
Then compare against topics used in the last 7 days. Kill candidates whose angle or case heavily overlaps. Better an empty slot than a repeated topic.

### 5. Assign + polish hooks

- One topic per slot; angles across slots must differ.
- For each: write the **title hook** (first line, ≤15 words/characters that stops the scroll — no setup, no throat-clearing), one-line angle, source.
- Hard exclusions from config: off-niche topics, red-line topics (politics etc. per config), pure news rewrites with no new angle.

### 6. Write the queue

Append to the topic queue file (dated section, `# YYYY-MM-DD`):

```markdown
# 2026-10-07
- [ ] {slot}: {title hook}｜angle: {one line}｜source: {link}｜score: {avg of 2 passes}｜tier: {T1/T2}｜event: {event id}
```

Production marks `[x]` when consumed.

## Output

The day's queued topics (hook + angle each, one line per slot).

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Queue full of 6-point topics | Scored generously | Recalibrate: a 7 means "I'd stop scrolling for this" |
| Same angle two days running | Dedup skipped | Enforce the 7-day comparison |
| Topics nobody discusses | Sourced from press releases | Source from comment sections and communities, not PR |
