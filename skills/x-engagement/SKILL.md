---
name: x-engagement
description: Run an engagement sweep — find fresh hot posts in the niche and draft replies that work as standalone micro-content. Use on a cadence (e.g. every 2h), following the posters' rhythm: check the last 2h of posts, newest first. Zero replies is a valid outcome.
---

# x-engagement

Borrowed reach beats owned reach at small follower counts. Every reply must work as a standalone micro-post: valuable or interesting enough that a stranger screenshots it.

## Inputs

- `config`: watch lists, red lines, reply budget per round (`config/config.yaml`)
- `window`: how far back to look (default: last 2 hours)

## Procedure

### 1. Find targets

- Check watch-list creators newest-first, then high-engagement niche posts inside the window.
- Target criteria: posted within ~3h, high and still-growing engagement, active comment section, on-niche topic.
- Skip: politics / current affairs / social controversies (or per config red lines), already-replied posts, accounts already replied-to twice in 24h.

### 2. The first-glance test

For each candidate reply ask: *as a standalone screenshot, would a stranger stop for this?* It must be valuable (learn something / solve something / exclusive info) or interesting (a great joke, a sharp counter-view, a question that begs a follow-up). "Great post!" and "support" are never replies.

Good reply shapes:
- A counter-intuitive data point or case
- A first-hand "I tried this and here's the trap" lesson
- A surgical joke or a one-line different angle
- A question that pulls the author into a thread

### 3. Draft + de-AI pass

- Match the language of the original post. Keep it tight (short!).
- No invite codes, no hashtags, no ads, no empty praise.
- De-AI pass per `references/human-voice.md`: cut connectors, em-dashes, triple parallelisms; make it sound typed by a human, not generated.
- Max 2 replies per round. If nothing meets the bar: **0 replies**. Never force it.

### 4. Soft-plug your projects (optional, high-leverage)

When the original post's topic naturally overlaps your open-source projects (AI agents, automation, dev tools, growth), end the reply with one natural line — e.g. "we open-sourced this playbook as x-operator". Rules: value first, plug second (one line max); max 1 plugged reply per round; never force it on unrelated topics; no link in the reply body (link goes in your own follow-up reply or is omitted).

### 5. Publish + log

Publish each reply. Log `date / original post link / reply link` to the engagement log. Never like / retweet / follow as part of this skill unless config explicitly allows it.

## Output

Reply links posted this round, or the reason for zero replies (no worthy targets / quiet hours).

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Replies sink with no views | Replied too late (hours after posting) | Follow posters' rhythm — check every 1–2h, newest first |
| Replies read as bot spam | Generic praise or off-topic | Enforce the first-glance test, 0 is valid |
| Account flagged | Too many replies, too fast | Respect the per-round cap and 24h per-account limit |
