---
name: x-post-craft
description: Draft an X post from a queued topic through three quality gates: viral-factor checklist, critic self-score, and de-AI pass. Use for every post before publishing — the goal is a post that reads like a human wrote it and earns the stop-scroll.
---

# x-post-craft

Takes a queued topic (hook + angle + source) and produces a publish-ready post. Three gates, in order. A post that fails a gate goes back, not forward.

## Inputs

- `topic`: title hook, angle, source (from the topic queue)
- `format`: text-opinion / image-card / quote-with-take / question (pick one; vary across the day's slots)
- `config`: voice rules and hard constraints (`config/config.yaml`)

## Procedure

### Gate 0 — 利他测试（kk 2026-10-08：有利他的逻辑粉丝才多，这是第一性原理）

动笔前先回答一句话：**读者看完能拿走什么？** 答不上来就不写。
能拿走的东西越具体越好：一个可复制的方法、一份整理好的名单、一组反直觉的数字、一个能避的坑。
"显得我很懂"不算利他，"让读者变强"才算。所有 Gate 1–3 的判断都服从这一条。

### Gate 1 — Viral-factor checklist (need ≥3)

1. **Demand**: pain / itch / pleasure point — at least one, felt by the reader *right now*
2. **Hook**: first line ≤15 words, stops the scroll alone, zero setup
3. **Value**: emotional resonance, practical utility, or genuinely new information — at least one
4. **Format bonus**: listicle, contrast, screenshot, poll

Fewer than 3 → rework the angle or kill the topic.

### Gate 1.5 — 标题钩子三选一 + 营销时机（kk 2026-10-08：要懂营销，标题决定生死，时机决定热度）

**标题钩子必须三占其一**（只满足"首句≤15字"不够，还要有钩子类型）：
- **具体数字**：反直觉的数字（"4.5% 的人在为 AI 付费"、"2 个月 $69K/月"）——数字越具体越像真事；
- **强烈反差**：预期违背（"50 个最赚钱 AI，29 个你没听过"、"流量≠收入"）；
- **悬念钩子**：开环不闭环（"16 块 3 个月蓝 V，羊毛还是坑？"），答案放正文。
三者全无 → 回炉重想标题，不许带着平标题进 Gate 2。

**营销时机矩阵**（什么信息什么时候发）：
- 突发热点（首发 2h 内）→ 快讯直发，抢首发窗口，1 小时内必须发出；
- 正在发酵（2–12h）→ 盖楼早回复 + 午间/晚间档锐评，借现成流量；
- 发酵透了（12h+）→ 不做纯新闻，只做收藏型清单/拆解（换角度吃长尾）；
- 固定栏目（GitHub 最火、Muse 每日一招）→ 固定档，不追热点。

### Gate 2 — Draft

- Human voice, per `references/human-voice.md`. Read it out loud: if it sounds like a press release, rewrite.
- No links in the body (link tax costs 30–50% reach — link goes in the first reply if needed).
- ≤2 hashtags. Zero invite codes, zero ads in the body.
- End with a real question or a debatable point — replies outweigh likes ~27:1 in the algorithm.
- Respect the character budget (280 for standard accounts; CJK chars count double-ish — estimate `cjk_chars×2 + other_chars`).

### Gate 3 — Critic self-score + de-AI pass

**Critic**: score the draft 0–10 on each — hook strength, information density, readability, credibility, account fit. Average <7 → rewrite once, then ship the better version.

**De-AI pass** (from `references/human-voice.md`, hardened with KKKKhazix/human-writing hard bans):
- Delete filler connectors ("moreover", "it's worth noting", "in today's fast-paced…")
- Break em-dash habits, triple parallelisms ("not X but Y", "not only… but also…"), vague attributions ("experts say")
- Chinese posts: hard bans — no 中文冒号, no 破折号, no "不是……而是……" flip sentences, no "先说结论/说白了", no business jargon (赋能/抓手/闭环/底层逻辑/方法论/打法/链路…)
- Vary sentence length — if three sentences in a row are the same length, break one
- Keep the opinion and the "I". Cut anything that is technically true and completely boring.

**Machine gate**: save the draft to a temp file and run `scripts/check_prose.py` on it (Chinese drafts). Fix every alert. Zero alerts → publish. Compression test: if deleting a third changes nothing, it's padded — rewrite.

## Output

Publish-ready post text + the critic scores (one line). Log the draft and scores to the post log.

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Reads correct but dead | Passed gates mechanically, no real opinion | Gate 1 demand check was skipped — go back |
| Hook gives everything away | Hook summarizes instead of teasing | Hook should open a loop, not close it |
| Good post, zero reach | Link in body / hashtag soup | Enforce Gate 2 constraints |
