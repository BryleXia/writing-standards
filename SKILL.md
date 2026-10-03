---
name: writing-standards
description: Apply established writing and language standards to anything the user writes, rewrites, reviews, or asks to simplify - reports to advisors/teachers, academic papers, slide decks (pre/演示), science communication (科普), technical docs, official documents (公文/GB-T 9704), emails, README, runbooks. Use when the user asks to write or change the style of a document; asks which standard/framework fits a scenario; names ASD-STE100, Simplified Technical English, plain language, BLUF, Minto Pyramid, assertion-evidence, plain language summary (PLS); wants an LLM prompt that commands a named writing standard (Karpathy trick); or wants text made clearer, 结论先行, 一句一义, or checked for readability.
license: MIT
metadata:
  version: "1.0"
  author: BryleXia
  based_on: Karpathy's ASD-STE100 prompting trick + public writing standards research (2026-10)
---

# Writing Standards Toolkit

把成体系的语言标准用到写作上。选型 → 套规则 → 验收，三步走。
详细标准档案见 `references/standards-map.md`（含卡帕西推文档案与全部来源）。

## 1. 工作流（每次写作任务都走）

1. **选型**：按第 2 节表选「主标准」（管结构）+「辅标准」（管句子）。
2. **套规则**：结构层用主标准的骨架；句子层套第 3 节公分母（或第 4 节对应标准的硬规则）。
3. **验收**：第 5 节检查清单过一遍。对外文稿用可读性公式复核（第 5 节）。

## 2. 场景选型表

| 场景 | 主标准（结构层） | 辅标准（句子层） | 验收 |
|---|---|---|---|
| 给老师/上级汇报 | **BLUF / Minto 金字塔**：第一句=结论+请示 | 一句一义 | 对方 10 秒内抓到「要我知道什么/要我拍什么板」 |
| 学术论文 | 期刊 author guidelines + IMRaD | 方法节可套 STE 纪律 | 引注/单位/摘要合规 |
| 论文通俗版 | **PLS**（Plain Language Summary，ICMJE 认可的二次发表，可带 DOI） | ClinicalTrials 用词表 | 无行话、无偏见、非推广 |
| 演示（pre） | **Assertion-Evidence**：一页一句完整主张 + 图形证据；页序按金字塔 | 页标题=结论句 | 每页只有一个主张 |
| 科普 | Plain Language（美联邦指南 / 欧盟 style guide 思想） | ClinicalTrials 用词表 | Flesch 60–70 |
| 技术文档/手册/交接 | **ASD-STE100**（或「80% 的路」软化版） | STE 全套 | 一词一义、祈使句、步骤编号 |
| 中文正式公文 | **GB/T 9704-2012** + 《党政机关公文处理工作条例》（15 文种） | GB/T 15834 标点 | 格式要素合规 |
| 邮件/日常沟通 | BLUF | 公分母 | 三行内见结论 |

## 3. 公分母（任何场景的句子底线）

受控语言们殊途同归的六条。无合适标准时单独使用也有 80% 收益：

1. **一句一义**。句子短（中文 25 字上下、英文 20 词上下）。复合长句拆开。
2. **主动语态**。操作句用祈使句（「运行此命令。」「检查此值。」）。
3. **一词一义**。同一概念全文只用一个词。术语首次出现即定义。
4. **结论先行**。每段第一句是该段的结论。
5. **步骤编号、并列进表**。不用大段散文罗列操作。
6. **禁行话、禁双关、禁比喻**（比方须加「打比方」标记隔离）。缩写先展开。

## 4. 卡帕西提示词技巧（让 LLM 按标准写）

出处：Andrej Karpathy，2026-10（x.com/karpathy/status/2105819303471976479）。要点：LLM 熟悉这些标准，在提示词里**报标准全名**。

```
# 基础款（英文标准，英文原名触发最稳）
请用 ASD-STE100 Simplified Technical English 的风格重写这段。
# 软化旋钮（全标准太硬时）
请写到 ASD-STE100 80% 的程度：保留一句一义、主动语态、术语统一，放开词表限制。
# 结构 + 句子组合拳
用 Minto 金字塔结构组织（结论先行、三个论点），句子用 STE 纪律（一句一义、祈使句）。
# 中文场景
按受控中文写：一句一义、主动语态、术语统一、步骤编号、比方降级到「打比方」框。
```

注意事项（实测者提醒）：报**标准全名**比口语描述（"写清楚点" / "simple technical English"）效果稳定；
不同模型遵从度不同，写完仍要按第 5 节验收。

## 5. 验收清单 + 可读性量尺

**通用清单**：
- [ ] 第一句就是结论/主张？（F/G 类场景）
- [ ] 有没有一句塞两件事的长句？
- [ ] 同一概念有没有换词叫？
- [ ] 术语都定义了吗？缩写都展开了吗？
- [ ] 操作都改祈使句了吗？步骤都编号了吗？
- [ ] 行话/比喻/双关清干净了吗（或已隔离标记）？

**可读性公式**（英文文本；中文暂无等价标准公式，人工按公分母查）：

| 公式 | 目标 |
|---|---|
| Flesch Reading Ease | 大众 60–70；技术文档 40–60；学术 30–50 |
| Flesch-Kincaid 年级 | 一般 <8–10 年级 |

## 6. 参考档案（按需读，勿整读）

- `references/standards-map.md` —— 八大类标准全景、各标准细则、卡帕西推文档案、来源链接。
  需要某标准的详细规则、写 PLS/公文/合同等少见场景、或要向用户解释标准来历时才读。
