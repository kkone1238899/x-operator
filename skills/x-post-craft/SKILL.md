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

### Gate 1 — Viral-factor checklist (need ≥3)

1. **Demand**: pain / itch / pleasure point — at least one, felt by the reader *right now*
2. **Hook**: first line ≤15 words, stops the scroll alone, zero setup
3. **Value**: emotional resonance, practical utility, or genuinely new information — at least one
4. **Format bonus**: listicle, contrast, screenshot, poll

Fewer than 3 → rework the angle or kill the topic.

### Gate 2 — Draft

- Human voice, per `references/human-voice.md`. Read it out loud: if it sounds like a press release, rewrite.
- No links in the body (link tax costs 30–50% reach — link goes in the first reply if needed).
- ≤2 hashtags. Zero invite codes, zero ads in the body.
- End with a real question or a debatable point — replies outweigh likes ~27:1 in the algorithm.
- Respect the character budget (280 for standard accounts; CJK chars count double-ish — estimate `cjk_chars×2 + other_chars`).

### Gate 3 — Critic self-score + de-AI pass

**Critic**: score the draft 0–10 on each — hook strength, information density, readability, credibility, account fit. Average <7 → rewrite once, then ship the better version.

**De-AI pass** (from `references/human-voice.md`):
- Delete filler connectors ("moreover", "it's worth noting", "in today's fast-paced…")
- Break em-dash habits, triple parallelisms ("not X but Y", "not only… but also…"), vague attributions ("experts say")
- Vary sentence length — if three sentences in a row are the same length, break one
- Keep the opinion and the "I". Cut anything that is technically true and completely boring.

## Output

Publish-ready post text + the critic scores (one line). Log the draft and scores to the post log.

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Reads correct but dead | Passed gates mechanically, no real opinion | Gate 1 demand check was skipped — go back |
| Hook gives everything away | Hook summarizes instead of teasing | Hook should open a loop, not close it |
| Good post, zero reach | Link in body / hashtag soup | Enforce Gate 2 constraints |
