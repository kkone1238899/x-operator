# Improvement changelog

Every daily review appends lessons here in LESSON / EVIDENCE / ACTION format.
Every 7th review, repeated lessons (≥2 occurrences) are merged into the
relevant skill or reference file as standing rules, and marked MERGED.

---

## 2026-10-07 (seed)
- LESSON: Topic selection needs a fixed scoring rubric, not vibes — ≥7/10 to enter the queue.
- EVIDENCE: Seeded from kangarooking/x-skills x-filter pattern + live operation.
- ACTION: Added references/scoring.md and rubric to x-topic-curation. [MERGED]
- LESSON: Every post needs a critic self-score (avg ≥7) plus a de-AI pass before publishing.
- EVIDENCE: "AI 腔" (AI-toned copy) is the #1 audience complaint; Humanizer-zh's 24-pattern checklist addresses it directly.
- ACTION: Added Gate 3 to x-post-craft and references/human-voice.md. [MERGED]
- LESSON: Engagement replies must pass a standalone first-glance test; zero replies is a valid round.
- EVIDENCE: Early operation data — late/generic replies sink with no views.
- ACTION: Added to x-engagement skill. [MERGED]

## 2026-10-07 (kk 4 directives)
- LESSON: Engagement replies should soft-plug our open-source projects when the topic naturally overlaps (famous bloggers do this).
- EVIDENCE: kk directive 2026-10-07 — "你看下他们下面盖楼的就知道很多知名博主都这样干".
- ACTION: Added section 4 to skills/x-engagement/SKILL.md + projects: to config.example.yaml. [MERGED]
- LESSON: A money-content operation needs a dedicated market radar — daily scan of AI money-making projects with HOW they did it, feeding curation.
- EVIDENCE: kk directive 2026-10-07 — "要构建市场雷达，扫描最新通过AI挣钱的项目，分享他们是如何实现的".
- ACTION: Added skills/x-market-radar/SKILL.md, registered in plugin.json, radar feeds x-topic-curation. [MERGED]

## 2026-10-07 (kk recommended KKKKhazix/human-writing)
- LESSON: human-writing's hard bans + automated checker are a stronger de-AI gate than our manual checklist alone.
- EVIDENCE: kk sent repo https://github.com/KKKKhazix/human-writing (MIT, ~4k stars); check_prose.py verified working locally — caught every violation in a test post.
- ACTION: Vendored scripts/check_prose.py (MIT attribution kept); hardened references/human-voice.md with hard bans (中文冒号/破折号/翻案句/"先说结论"/商业黑话） + 材料规则 + 压缩试验；x-post-craft and x-engagement skills now require running the checker; local crons (noon/evening posts, engagement sweep) updated to run it before publishing. [MERGED]

## 2026-10-07 (kk: AIHOT + Jason23818126 hotspot post)
- LESSON: Hotspot collection needs a dedicated input layer (4 sites: sopilot/tophub/newsnow/aihot.news); a lone viral post is a lead, not a hotspot — ≥2 sites rising = candidate.
- EVIDENCE: @Jason23818126 post (62K views, Sep 2026) listed the 4-site stack; verified via browser read.
- ACTION: Added references/hotspot-sources.md; x-topic-curation and x-market-radar scan these sites first. [MERGED]
- LESSON: AIHOT's selection method upgrades our scoring: score twice independently with the same rubric (avg ≥7), source tiers (T1 first-party lower bar / T2 higher bar), cluster same-story into one event, heat = independent sources in 48h.
- EVIDENCE: KKKKhazix/AIHOT docs/selection.md (MIT, 6.2k stars) — verified via repo read.
- ACTION: x-topic-curation SKILL.md now: double-scoring, T1/T2 tiers, event clustering, queue entries carry score/tier/event id. [MERGED]

## 2026-10-07 (daily review #1; cumulative reviews: 1/7 — no merge)
- LESSON: Never publish the same topic twice in one day — check your own timeline for duplicates before publishing.
- EVIDENCE: 2026-10-07 evening a16z post shipped 3 times within 21 minutes (two near-identical versions 22:09/22:30 + one quote-clarification 22:14), 7 views combined, zero engagement — on a low-weight account duplicate posting reads as a malfunction.
- ACTION: Add to x-post-craft publishing checklist: read @Hjn8899 timeline before publishing; if the same topic was posted within 2h, stop and do not publish.
- LESSON: Log landing is a hard deliverable of every publishing task — "unpublished + reason" counts as one row; the review trusts only the log.
- EVIDENCE: 2026-10-07 noon blueV post (published, 17 views / 1 repost — best single post of the day), GitHub math video post, and the evening a16z posts all had zero rows in post_test_log.md; the 22:30 review had to reverse-engineer the timeline via browser read.
- ACTION: In x-daily-post-noon / x-daily-post-evening / x-github-trending-video cron files, harden the "record" step: the task must append one row at the end (including unpublished + reason); missing log = task failure.
- LESSON: Blogger blocks are an observable machine-account signal — if blocks hit >=2 in a week, auto-throttle engagement the next week.
- EVIDENCE: Since 10-03, @op7418, @oran_ge, and @lidangzzz have each blocked @Hjn8899; @lidangzzz blocked within hours of our 13:47 Lean-post reply on 10-07.
- ACTION: Add a "block circuit breaker" section to x-engagement SKILL.md: count blocks weekly; >=2 in a week -> next week max 1 reply per round, high-frequency bloggers only.

## 2026-10-07 盖楼机械感纠偏（kk 直接纠偏）
- LESSON: 盖楼回复的机械感不来自措辞，来自结构——"@人+摆数据+金句收尾"同一模板连用、从不站队、从不反驳，真人一眼看穿；英文回复同样会中招（破折号曾漏网）。
- EVIDENCE: 2026-10-07 6 条回复原文审计：第 2 条（@btcmos）结尾"让 agent 全自动跑 X"话没说完；第 3 条（@lidangzzz）用了禁用的破折号 ——；第 1 条（@0427SMtieshou）通篇数据但无立场；kk 原话"发布的概率内容过于机械和AI化"。
- ACTION: x-engagement SKILL.md 新增立场硬规则（每条必须三选一：赞同加码/反对给理由/补充关键缺失信息）、反模板规则（轮换结构，每轮 2 条不许同构）、结尾完整规则、允许轻度反驳；英文回复同样过 human-voice 硬规则。x-engagement-sweep 定时任务下次运行起生效。

## 2026-10-08 快讯直发 + 营销时机（kk 直接指令：好资讯发现就发，不等；要懂营销）
- LESSON: 热点有半衰期，等固定档（午间/晚间）再发等于把首发让给别人；标题只满足"首句≤15字"不够，必须有钩子类型（数字/反差/悬念）才有点击。
- EVIDENCE: kk 原话"你要懂得营销…发现了好的咨询马上发，还等，下一秒别人发出来了"；昨日 a16z 榜单从发现到发出隔了 14 小时。
- ACTION: ① x-engagement-sweep 加"快讯直发"规则——侦察中发现 2h 内首发、≥2 独立来源（或大号 1h 内起量）、对口、未发过的好资讯，当场发快讯帖（每天最多 1 条，不占午晚两档，发前先查时间线防重复）；② x-post-craft 加 Gate 1.5：标题钩子三选一（具体数字/强烈反差/悬念钩子）+ 营销时机矩阵（突发→快讯直发；发酵中→盖楼+档期锐评；发酵透→只做收藏型；固定栏目→固定档）。

## 2026-10-08 (daily review #2; cumulative reviews: 2/7 — no merge)
- LESSON: "Attached" is not published — before publishing a video post, confirm triple media presence in the composer (DOM file input non-empty / blue processing indicator / thumbnail preview); on "Choose Files: No file chosen", stop and do not retry, route the master to x-video-backfill or the phone version.
- EVIDENCE: 2026-10-06 and 2026-10-08 identical symptom: the upload tool reported attached (EP08 446KB, valid grant) while the composer stayed empty and the Post button disabled; stopping per the tool-chain-failure rule kept the account clean (no CAPTCHA/rate-limit/abnormality).
- ACTION: Add a "media triple-confirm" step to the x-post-craft publishing checklist; failure path routes to x-video-backfill (daily 15:00) or the 720p phone version.
- LESSON: When the evening slot publishes, quote-retweet today's best post (>6h old) with a short comment to cover a new timezone — execute the "best-post quote" tactic as a standing check.
- EVIDENCE: 2026-10-08 21:49 slot quote-retweeted the 12:46 noon post (the day's best, 18 views at the time) with "对照今晚那条看。" — two posts complement each other (threshold formula -> income ranking).
- ACTION: Add a "same-day quote-retweet" checkpoint to x-post-craft: if the noon post is >6h old and is the day's best, quote it with a ≤15-char comment at the evening slot.
- LESSON: Engagement replies with a real stance (agree-and-amplify / rebut with reasons / add missing info) look safer than the old "data + golden line" template — early signal, not yet a rule.
- EVIDENCE: 10-03 to 10-07 saw 3 blocks in 4 days (@op7418, @oran_ge, @lidangzzz); 2026-10-08's 12 replies each had a distinct stance and structure, and zero new blocks were observed across all 7 rounds.
- ACTION: Keep executing the stance rule; if zero blocks hold for 3 consecutive days, merge it as a standing rule.

## 2026-10-08 利他第一性原理（kk 指令）
- LESSON: 涨粉的根不是技巧，是利他——读者能拿走东西才会关注；"显得我很懂"的内容都是自嗨。
- EVIDENCE: kk 原话"一定要有利他的逻辑这样粉丝才多"；今日 Skills 导航（24 仓库按职业分类）是利他逻辑的正例。
- ACTION: x-post-craft 新增 Gate 0 利他测试——动笔前必须回答"读者看完能拿走什么"，答不上来不写；所有选题/生产/盖楼判断服从此条。
