# Changelog

本 skill 遵循语义化版本（SemVer）。

## v1.2.0 — 2026-09-23

### Added
- **The Closer 第一性挑战（first-principles challenge）**：终审裁决前，Closer 对**每一个**结论都跑一遍领域无关的第一性拷问——需求存在性（抛开"竞品都有""KPI 要""历史一直这样"，这个需求本身该不该存在、为谁存在）+ 底层拆解（PRD 是在动本质问题，还是只在优化表象症状）。第一性镜头放在 Closer 身上，是因为面板里两个第一性人设（马斯克 / 张一鸣）都是情境专家、经常不出场，导致普通 C 端 PRD 评审缺失第一性视角。

### Changed
- `verdict-logic.md`：新增 "First-principles challenge" 一节（对每个 verdict 生效，独立于仅在全票一致时触发的 anti-groupthink），并把它加入 Output validity checklist。若挑战发现需求服务内部指标而非用户，属价值风险硬否决，可将结论推向 NO-GO 或把"证明需求存在性"提为首要条件。
- `closer.md`：人设特质新增"First-principles by default"；中英文裁决块模板各加一行"第一性拷问 / First-principles check"；必含内容清单和裁决逻辑摘要同步更新。
- `SKILL.md` Step 7：Closer 执行清单加入第一性挑战步骤。

### Validation
- 构造一份"按框架/类比看是 3 CONDITIONAL + 1 GO、但本质服务内部 KPI"的签到红包 PRD 实测 Closer：机械执行 Step A–C 会得到"补作业式" CONDITIONAL GO；第一性挑战识别出需求为运营 KPI 而非用户存在，把"证明需求存在性"提为第一死条件、条件性质升级为"证伪即死"，并显式说明这一步改变了结论。机制生效。
- 新增 evals/evals.json 第 6 条用例固化该行为。

## v1.1.0 — 2026-09-23

### Added
- **Round 1 并行独立子 agent 评审**：Step 4 默认改为每位专家派发一个隔离的并行子 agent，各自只拿到 PRD、Step 1 intake 记录和自己的人设切片，互相不可见。消除单上下文顺序生成时的锚定效应（anchoring），使"独立评审"名副其实。新增 `references/workflows/parallel-review.md` 定义派发规则、隔离硬约束、结构化返回格式、失败降级与辩论衔接。
- **致命缺陷字段**：Round 1 返回结构新增"致命缺陷"字段，直接对接 `verdict-logic.md` 的 Step A 硬否决检查（Cagan 四风险中不可恢复的缺陷）。
- **格式归一化规则**：主线程收录子 agent 返回时，清洗从人设模板带出的装饰前缀（如 `📍 追问：`）、emoji 和重复标签，统一为四字段结构——只动格式，不改倾向标签、致命缺陷判定和理由文字。
- **evals 行为用例**：新增 `evals/evals.json`（5 条，含 CONDITIONAL 收敛、NO-GO 硬否决、子 agent 回退、格式归一化、辩论衔接）与 `evals/trigger-evals.json`（12 条触发/非触发判定）。

### Changed
- **Step 4** 由单线程平行评审改为默认并行子 agent 派发；运行时不支持子 agent 时回退单上下文模式，并在出场卡标注"⚠ 本轮为单上下文模拟独立评审"。
- **Step 6**（辩论）明确保留在主线程，不为辩论派发子 agent；引用必须来自子 agent 原文，且独立子 agent 意见优先于主线程共识。
- **全局护栏**新增第 7 条：独立子 agent 意见优先于主线程共识，倾向标签逐字保留、不得为叙事统一而改写。

### Validation
- 两份 PRD 对照实测（隔离子 agent，各 4 位专家）：
  - 外卖「每周菜谱推荐」（价值假设未验证）→ 4× CONDITIONAL 收敛，理由切入点互不重叠。
  - 外卖「餐后评价返现」（PM 自有数据已证伪）→ 4× NO-GO，3 位命中致命缺陷。
- 结论：机制具备区分力，趋同源于 PRD 本身而非锚定；子 agent 隔离消除了顺序生成的假性一致。

## v1.0.0

- 首次发布：多专家评审团，PRD 分类、P9 审讯、平行评审、The Closer 终审、Dissent 一等公民输出。中英文双面板。
