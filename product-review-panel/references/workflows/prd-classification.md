# PRD Classification / PRD 类型分类

Classify the PRD into one of 5 types, then add 1-2 situational experts based on the type.

## PRD types

1. **新功能 / New feature** — building functionality the product doesn't have yet
2. **迭代优化 / Iteration** — improving an existing feature, often metric-driven
3. **商业模式 / 定价 / Business model / Pricing** — pricing, packaging, monetization, business model shift
4. **体验重构 / UX redesign** — re-doing flow / UI for existing functionality
5. **早期探索 / Early-stage exploration** — pre-PRD or barely-PRD; user wants to explore problem space *(DEFERRED to v2)*

## Classification heuristics

Scan the PRD for these signals:

| Signal in PRD | Likely type |
|---|---|
| `推出 / launch / introduce` + noun for something new | 新功能 |
| `优化 / improve / boost` + an existing metric | 迭代优化 |
| Currency symbols ($, ¥); words like `tier, subscription, free, paid, pricing` | 商业模式 |
| `redesign, 改版, 重做` + flow or screen | 体验重构 |
| Many open questions; words like `exploration, discovery, 考虑做` | 早期探索 |

If the PRD straddles two types (e.g., new feature with a new pricing tier), pick the **dominant** dimension. If genuinely 50/50, pick the type with more situational experts available.

## Situational expert mapping — Chinese panel

Core (always present): Marty Cagan + 俞军 + 大厂 P9 产品总监.

| PRD type | Add situational |
|---|---|
| 新功能 | + 张小龙 (if C 端 / 工具类 product) |
| 迭代优化 | (no situational; core panel is sufficient) |
| 商业模式 | (no situational available in v1; **note**: this is a gap; recommend adding a Chinese commerce/pricing voice in future) |
| 体验重构 | + 张小龙 (审美 / 克制视角) |
| 早期探索 | *DEFERRED to v2* |

## Situational expert mapping — International panel

Core (always present): Marty Cagan + Clayton Christensen + Senior PM Director.

| PRD type | Add situational |
|---|---|
| New feature | + Tony Fadell (story-first, "first 5 seconds" craft) |
| Iteration | + Teresa Torres (opportunity-solution tree validation) |
| Business model / Pricing | + Reid Hoffman (network effects, growth strategy, timing) |
| UX redesign | + Don Norman (affordances, mental models) |
| Early-stage exploration | *DEFERRED to v2* |

## Panel size targets

- Minimum 3 experts (core only)
- Typical 4 experts (core + 1 situational)
- Maximum 5 experts — never more; output becomes unreadable beyond this

If the PRD type maps to 2 situational candidates, pick the one most relevant to the highest-confidence concern raised during intake.

## What to do if classification fails

If the PRD is too vague to classify into any of the 5 buckets, that's itself a strong information gap signal. Behavior:

1. Skill announces: "PRD 类型不明确" / "PRD type is unclear"
2. Routes back to Step 1 (P9 intake) with one specific question: "你这次是想让我们评审哪个层面 — 是要不要做这个功能，还是怎么做，还是定价合不合理？"
3. Once PM answers, attempt classification again

Do not proceed past Step 2 with an unclassified PRD — the panel composition won't be right.

## Internal output (not printed)

Classification is **internal**. The selected panel composition shows up in Step 3's panel intro card; the bare classification label appears in the card's footer (`PRD 类型识别：[type]`). The skill should not print "I'm now classifying the PRD..." narration.
