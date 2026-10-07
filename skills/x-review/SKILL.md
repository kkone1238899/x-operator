---
name: x-review
description: Run the daily review — attribute follower/content performance, extract reusable lessons, and feed them back into the plugin. Use once a day. This skill is the self-improvement loop: every review must produce at least one concrete plugin improvement or explicitly record why none was needed.
---

# x-review

Growth = reach × conversion. The review diagnoses which one is broken, attributes what moved the needle, and — most importantly — writes the lesson back into the operating system so tomorrow runs smarter.

## Inputs

- `post_log`: date / format / topic / link / views / likes / replies / reposts per post
- `engagement_log`: replies posted, their performance
- `follower_count`: today vs yesterday
- `memory/changelog.md`: the running improvement log

## Procedure

### 1. Score the day

- Follower delta and its likely drivers (which post/reply thread moved it?)
- Per-post: views (reach), engagement rate (content quality), profile clicks if available (conversion)
- Diagnose the bottleneck: is reach broken (low views) or conversion broken (views but no follows)?

### 2. Topic hook autopsy

For each post: did the title hook stop the scroll? Was the promised value delivered? Tag each topic: `winner` / `neutral` / `loser`. Winners get amplified next week; losers get cut.

### 3. Extract lessons (the important part)

Write 1–3 lessons in this exact format to `memory/changelog.md`:

```markdown
## 2026-10-07
- LESSON: {one sentence, reusable beyond today}
- EVIDENCE: {post link + numbers}
- ACTION: {which skill/reference file to change and how}
```

Rules:
- A lesson must be reusable — "post X got 100 views" is data, not a lesson.
- If no lesson emerged, write `NO-LESSON: {why — e.g. sample too small, no posts today}`. Never invent one.

### 4. Consolidate (weekly)

Every 7th review, read the week's changelog entries. If the same lesson appears ≥2 times, merge it into the relevant skill or reference file as a standing rule, and mark it `MERGED` in the changelog. This is how the plugin gets smarter without human input.

## Output

Day score (followers ±N, best/worst post), the lessons appended, and any merges performed.

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Lessons are platitudes | Wrote data, not reusable rules | Enforce the LESSON/EVIDENCE/ACTION format |
| Plugin never changes | Consolidation skipped | The 7th-review merge is mandatory, not optional |
| Attribution is guesswork | No per-post numbers | Fix logging first — review needs data |
