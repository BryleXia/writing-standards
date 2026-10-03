---
name: writing-standards
description: Select the right writing standard / language style for a task - and nothing else. Use when the user invokes /writing-standards, asks which standard or 文风 to use, asks what style fits a scenario (report to advisor, academic paper, pre/slide deck, science communication 科普, technical doc, official document 公文, email), or wraps this into another writing task (txt, md, HTML, PPT, Word...) by asking to constrain the language style, follow ASD-STE100 / Simplified Technical English / plain language / BLUF / Minto Pyramid / assertion-evidence / PLS, or apply 结论先行 / 一句一义. This skill only decides the style; the calling task writes the content.
license: MIT
metadata:
  version: "2.0"
  author: BryleXia
  based_on: Karpathy's ASD-STE100 prompting trick + public writing standards research (2026-10)
---

# Writing Standards —— 只干一件事：为任务选文风

**职责边界（先读这个）**：
- ✅ 本 skill 负责：问清场景 → 选定语言标准 → 输出一份**「文风规格」**（选定标准 + 执行规则 + 验收线）。
- ❌ 本 skill 不负责：写内容本身；载体/排版（txt / md / HTML / PPT 由调用方任务决定）；实际验收执行。
- 被包裹调用时（例：「写一个 HTML，语言规范用 STE」），本 skill 只产出文风规格，交回调用方任务执行。

## 流程（三步，缺一不可）

### 第 1 步 · 先问（除非上下文已经写明）

向用户问三件事。用 AskUserQuestion 工具（1–2 个问题合并）或简短提问：

1. **目的/读者**：这份文字给谁看？要对方做什么/知道什么？
2. **场景**：汇报？论文？pre？科普？技术文档？公文？邮件？其他？
3. **上下文**：载体（txt/md/HTML/PPT…）、语气、篇幅、有无既定规范。

**跳过追问的唯一条件**：上下文已明确给出场景或点名了标准
（例：「写 HTML 教材，用 ASD-STE100 风格」→ 直接裁定，不重复追问）。
拿不准就问。问题要短。

### 第 2 步 · 裁定（选型表）

| 场景 | 主标准（管结构） | 辅标准（管句子） | 验收线 |
|---|---|---|---|
| 给老师/上级汇报 | **BLUF / Minto 金字塔**：第一句=结论+请示 | 一句一义 | 读者 10 秒抓到「要我知道/拍板什么」 |
| 学术论文 | 期刊 author guidelines + IMRaD | 方法节可套 STE 纪律 | 引注/单位/摘要合规 |
| 论文通俗版 | **PLS**（Plain Language Summary） | ClinicalTrials 用词表 | 无行话、无偏见、非推广 |
| 演示（pre/PPT） | **Assertion-Evidence**：一页一句主张 + 图证据 | 页标题=结论句 | 每页只有一个主张 |
| 科普 | Plain Language 思想 | ClinicalTrials 用词表 | Flesch 60–70（英文） |
| 技术文档/手册/交接/教程 | **ASD-STE100**（可选「80% 路」软化版） | STE 全套 | 一词一义、祈使句、步骤编号 |
| 中文正式公文 | **GB/T 9704-2012** + 条例 | GB/T 15834 标点 | 格式要素合规 |
| 邮件/日常沟通 | BLUF | 公分母 | 三行内见结论 |

无合适标准时 → 单用**公分母六条**（见规格模板）。混合场景 → 主标准管结构 + 辅标准管句子。

### 第 3 步 · 输出「文风规格」（本 skill 的唯一交付物）

按下面模板产出，交回调用方（或用户）执行。**规格之外一个字的内容都不写。**

```
【文风规格】
· 标准：<全名，英文标准用英文原名> ｜ 软化档：100% / 80% 路（仅 STE 类）
· 结构规则：<主标准怎么规定结构/顺序>
· 句子规则：<辅标准或公分母六条中适用的条目>
· 术语规则：<一词一义 / 定义位置 / 缩写处理>
· 隔离规则：<比方/引语/外来语怎么处理>
· 验收线：<上表对应栏 + 载体特有检查项（如 PPT 的一页一主张）>
```

**公分母六条**（任何场景的句子底线，也是规格的默认句子层）：

1. 一句一义。句子短（中文 25 字上下、英文 20 词上下）。
2. 主动语态。操作句用祈使句。
3. 一词一义。术语首次出现即定义。
4. 结论先行。每段第一句是该段结论。
5. 步骤编号、并列进表。
6. 禁行话、禁双关、禁比喻（比方须加「打比方」标记隔离）；缩写先展开。

## 附注

- **提示词技巧（给调用方参考）**：让 LLM 按标准写时报**标准全名**；太硬时用「80% of the way to X」软化（Karpathy 2026-10）。
- **详档**：`references/standards-map.md` —— 八大类标准细则、卡帕西档案、来源。裁定拿不准或用户追问标准来历时才读。
