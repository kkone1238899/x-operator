---
name: x-market-radar
description: Scan for the newest AI money-making projects and record HOW they did it. Use daily, before topic curation — this skill feeds fresh, real-world monetization ammo into the content pipeline. Especially valuable for money-angle content pillars.
---

# x-market-radar

Fresh money cases are the highest-leverage content fuel. This skill finds them and extracts the replicable path, not just the headline number.

## Inputs

- `config`: watch lists of monetization posters, niche (`config/config.yaml`)
- `window`: lookback period (default: last 24–48h)

## Procedure

### 1. Scan the hotspot layer (last 24h)

Start with `references/hotspot-sources.md`: sopilot (X taking off), tophub (cross-platform), newsnow (real-time), aihot.news (AI vertical). Filter for money angles — new paid AI products, revenue posts, pricing experiments.

### 2. Scan X money posters + the web (last 24–48h)

Check monetization-focused creators (indie hackers who post revenue, builders sharing numbers) for new posts about earnings, launches, or pricing experiments. Also web-search newly launched AI products with revenue. Prioritize items with numbers.

### 3. Record each find

For every project, write:
- **What**: one line
- **Model**: one-line business model
- **Numbers**: revenue/price with source
- **HOW** (the important part): tech stack, distribution channel, pricing, cold-start path — at minimum the replicable key steps
- **Link**: source URL

Rules: no verified launch facts → don't record it. Can't reconstruct the how → mark it and move on, never invent. Skip off-niche and red-line topics.

### 4. Cluster, then file

Same story from multiple sources = one event (heat = independent source count). Append to the radar log (dated section, `# YYYY-MM-DD`). Tag each entry 【推荐选题】 (strong topic candidate) or 【仅记录】 (record only).

## Output

Top 3 of the day — one line each: project + numbers + the one key implementation step.

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Log full of headlines, no how | Stopped at the numbers | The HOW section is mandatory, not optional |
| Same projects every day | Sources too narrow | Rotate in new monetization posters monthly |
| Numbers turn out fake | Copied claims without sources | Every number needs a source link |
