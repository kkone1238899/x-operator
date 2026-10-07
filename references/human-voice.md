# Human voice guide

The goal: every post and reply reads like a human typed it, not a model generated it. Two sections — English (native X style) and Chinese (de-AI checklist).

## English — native X style

- Lowercase, minimal punctuation, short lines — one thought per line.
- No hashtag soup (≤1), no links in the body (link tax: −30–50% reach).
- Lead with the hook. First line stops the scroll alone.
- Native devices: `→` for punchlines, `//` as separator, fragments like "ngl", "imo", "the thing is".
- Avoid: Title Case Marketing Voice, exclamation hype, emoji spray.

## Chinese — 去 AI 味检查清单

发布前逐条检查：

**删连接词**：此外、然而、值得注意的是、总而言之、说白了、底层逻辑、首先/其次/最后。真人说话不用这些起承转合。

**断排比**：删掉"不是…而是…"、"不仅…更…"、"既…又…还…"三段式。两项比三项更像人话。

**去破折号**：— 出现超过一次就删，真人很少用。

**砸模糊归因**："行业专家认为""有观点指出""据报道"——要么给具体出处，要么删掉这句。

**变节奏**：连续三句长度相同，打断一句。长短交错才像人。

**留观点**：中立正确的废话不如一句带立场的真话。允许"我觉得""让我意外的是"。

**信读者**：别解释比喻，别铺垫三句再说结论。直接说。

### 快速测试

大声读一遍。如果像新闻稿、像公众号、像 AI——重写。如果像你跟朋友微信吐槽——发。

## 硬禁令（来自 KKKKhazix/human-writing，MIT，已并入）

正文**严禁**：中文冒号、破折号、"不是……而是……"及同类翻案句、"先说结论/说白了"类硬停词、商业黑话（赋能、抓手、闭环、底层逻辑、顶层设计、颗粒度、方法论、打法、链路、心智……）。

**材料规则**：每条帖子/回复至少有一个具体材料托着——数字、案例、亲测经历、原话、代价。没有材料的帖子不发。

**压缩试验**：删掉三分之一后意思没变 = 注水，重写。

**机器检查**：成稿后必须跑一遍 `scripts/check_prose.py`（checklist 自动化版，MIT 协议引自 KKKKhazix/human-writing）。有报警就改，零报警才发。
