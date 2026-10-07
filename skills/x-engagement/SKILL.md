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
- **立场硬规则（2026-10-07，kk 纠偏：机械感来自"只摆数据不站队"）**：每条回复必须有明确立场——赞同并加码、反对并给理由、或补充原帖缺失的关键信息三选一。纯复述数据、读完不知道你站哪边的，不许发。
- **反模板规则**：不许每条都是"@人+摆数据+金句收尾"的同一结构。轮换结构：先给结论再摆证据 / 先讲亲测经历 / 只扔一句梗 / 直接提问。每轮 2 条回复不许用同一结构。
- **结尾必须完整**：不许话说一半就断（软推广的那句也必须是完整句子）。
- **允许轻度反驳**：有数据或亲测支撑时，可以直接说不同意原帖某个结论。争议是互动燃料；不许人身攻击，不许碰红线话题。
- De-AI pass per `references/human-voice.md` (hardened with KKKKhazix/human-writing hard bans): cut connectors, em-dashes, triple parallelisms; make it sound typed by a human, not generated. 英文回复同样遵守 human-voice 硬规则（无破折号、无 AI 腔），check_prose.py 只查中文，英文按硬规则人工过一遍。
- Chinese replies: run `scripts/check_prose.py` on the draft; fix every alert before publishing.
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
| Replies feel mechanical / AI-written | Template structure ("@ + data + punchline" every time), no stance, trailing-off endings | Enforce 立场硬规则 + 反模板规则: every reply takes a stance, rotate structures, complete sentences |
| Account flagged | Too many replies, too fast | Respect the per-round cap and 24h per-account limit |
