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

### 1. Scan X (last 24h)

Check monetization-focused creators (indie hackers who post revenue, builders sharing numbers) for new posts about earnings, launches, or pricing experiments. Also sweep high-engagement money-topic posts in the niche.

### 2. Scan the web (last 24–48h)

Search for newly launched AI products with revenue, indie hackers shipping paid products, AI tools that started making money. Prioritize items with numbers.

### 3. Record each find

For every project, write:
- **What**: one line
- **Model**: one-line business model
- **Numbers**: revenue/price with source
- **HOW** (the important part): tech stack, distribution channel, pricing, cold-start path — at minimum the replicable key steps
- **Link**: source URL

Rules: no verified launch facts → don't record it. Can't reconstruct the how → mark it and move on, never invent. Skip off-niche and red-line topics.

### 4. File it

Append to the radar log (dated section, `# YYYY-MM-DD`). Tag each entry `` (strong topic candidate) or `` (record only).

## Output

Top 3 of the day — one line each: project + numbers + the one key implementation step.

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Log full of headlines, no how | Stopped at the numbers | The HOW section is mandatory, not optional |
| Same projects every day | Sources too narrow | Rotate in new monetization posters monthly |
| Numbers turn out fake | Copied claims without sources | Every number needs a source link |
