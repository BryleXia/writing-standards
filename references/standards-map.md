# 语言标准全景档案（references）

> 本文是 `writing-standards` skill 的详尽参考。按需查阅，勿整读。
> 最后核实：2026-10-03。来源链接在文末「来源」节。

---

## A 类 · 受控语言（Controlled Natural Language）——限词表 + 限句法

### ASD-STE100 Simplified Technical English（STE）

- **出身**：1986 年 AECMA Simplified English（欧洲航空业要求：非英语母语的机务人员不能误读维修手册——误读会死人）。
  2005 年成为规范（specification），**2025 年成为国际标准**。维护方 ASD STEMG（1983 年至今）。
- **机制**：约 **870–900 个核准词** + 约 **60–65 条写作规则**。核心铁律：
  - 一词一义一词性（"test" 只作名词；"follow" 只取「come after」不取「obey」）
  - 优先短词常用词；动作用动词不用动名词化名词（Rule 3.7）
  - 祈使句写操作；一句一个指令
- **生态**：官方免费下载（asd-ste100.org，版权归 ASD）；检查器 HyperSTE / MAXit / Oxygen 插件等。
- **注意**：STE 与 plain English 不同——STE 是为技术写作定制的精确规则（ASD FAQ 原文：「more strictly controlled」）。
  且官方声明 STE 不应替代完整 style guide。

### 其他受控语言

| 名称 | 出处 | 机制 | 用途 |
|---|---|---|---|
| Basic English | Ogden 1930 | 850 核心词 + 极简语法 | 教学、国际化写作 |
| Simple English Wikipedia | — | Basic English 改良 | 儿童/二语百科 |
| Attempto Controlled English (ACE) | 苏黎世大学 1995→ | 受限句法 + 形式语义（机器可读、可解析） | 软件规格说明 |
| Gellish / ClearTalk / SBVR | — | 机器可读受控英语 | 工业知识表示、业务规则 |
| Inform 7 | — | 英语语法的编程语言 | 互动小说（同族思想） |

---

## B 类 · 平实语言（Plain Language）——公共信息必须能懂

| 标准 | 效力 | 要点 |
|---|---|---|
| 美国 **Plain Writing Act 2010** + 《Federal Plain Language Guidelines》 | 联邦法律 | 公共文件须「公众能懂能用」：去行话、去冗余、组织清晰、按读者写。2022 年 Clear and Concise Content Act 提案拟加码 |
| 欧盟 **English Style Guide**（DGT，132 页） | 机构规范 | 「clear, simple and accessible as possible」；立法文本的精确性另有专门手册 |
| 欧盟 **Interinstitutional Style Guide** | 24 官方语 | 体例统一 |
| 德国 Leichte Sprache / 瑞典 Klarspråk | 政府倡议 | 简易语言/清晰语言运动（本轮未展开核验细则） |

---

## C 类 · 医疗患者沟通（Plain Language Summaries, PLS）

- **PLS**：论文/会议摘要的通俗版。ISMPP 主导推进；**ICMJE 已承认 PLS 为合法二次发表**（PLS-P，带独立 DOI 可引用）。
- **最低标准**（Rosenberg et al. 2021）：「摘要体量、可理解可读、无技术行话、无偏见、非推广、经同行评审、易获取」。
- **ClinicalTrials.gov 官方撰写指南**（可操作到词级）：
  - 用 "participants" 不用 "subjects"/"patients"；用 "people with diabetes" 不用 "diabetes patient"
  - 用 "lower/raise" 不用 "reduce/increase"（避免定性词）
  - 以人为先，不以病定义人

---

## D 类 · 法律与立法起草

| 标准 | 要点 |
|---|---|
| 欧盟《Joint Practical Guide》（2000→） | 立法起草明确性原则；欧洲议会/理事会/委员会三机构共同基准 |
| Plain Legal Language 运动（Clarity International 等） | 法律文本平实化 |
| Manual of Style for Contract Drafting（MSCD，Ken Adams） | 合同起草去古奥（业界知名；本轮未直接命中检索） |

---

## E 类 · 学术写作——体例规范派（没有词表级标准）

如实说明：论文领域**不存在** STE 式受控语言。管论文的是三层：
1. **结构**：IMRaD（Introduction–Methods–Results–Discussion）
2. **体例**：APA / Chicago / GB/T 7713 科技报告规则（引注、单位、摘要）
3. **语言**：期刊 author guidelines + hedging/boosting 学术措辞惯例
方法节（Methods）最适合套 STE 纪律：步骤化、祈使句、一词一义。

---

## F 类 · 汇报结构框架——「信息怎么摆」

| 框架 | 出身 | 机制 |
|---|---|---|
| **Minto 金字塔原理** | 麦肯锡 Barbara Minto | 结论先行；下挂 3 个论点各配证据；排序法：演绎/时间/结构/比较 |
| **BLUF**（Bottom Line Up Front） | 军队→商界 | 第一句=结论；细节后置 |
| SBAR（Situation-Background-Assessment-Recommendation） | 医疗交接 | 固定四段装内容 |
| A3 / Amazon 六页纸 | 丰田 / 亚马逊 | 一页叙事说清问题与建议（同族思想） |

---

## G 类 · 演示（Pre）——一页一主张

| 标准 | 机制 |
|---|---|
| **Assertion-Evidence**（宾州州立，assertion-evidence.com） | 每页：一句完整主张（assertion）+ 图形证据（evidence）。禁 bullet 堆砌。口号：演讲者最大的错误是沿用 PowerPoint 默认 |
| Six P's 框架 | Perspective → Problem → Principle → Proposal → Proof → Process |
| 金字塔 × PPT | 页标题 = 结论句（金字塔尖），不是名词短语 |

---

## H 类 · 可读性公式——风格的客观量尺

| 公式 | 年代 | 公式/换算 | 目标 |
|---|---|---|---|
| Flesch Reading Ease | 1948 | 206.835 − 1.015×(词/句) − 84.6×(音节/词)；0–100 越高越易读 | 大众 60–70；技术 40–60；学术 30–50 |
| Flesch-Kincaid Grade Level | 1975（美海军委托） | 同原料 → 美国年级数 | 一般 <8–10 |
| Fry / Gunning Fog / Spache / Dale-Chall / Lix | 各年代 | 同族变体 | 各行业自选 |

---

## 中文世界

| 标准 | 要点 |
|---|---|
| **GB/T 9704-2012《党政机关公文格式》** + 《党政机关公文处理工作条例》（2012） | 15 文种（决议/决定/命令/公报/公告/通告/意见/通知/通报/报告/请示/批复/议案/函/纪要）；格式细到字体字号页边距 |
| GB/T 15834-2011《标点符号用法》 | 国标级标点规范 |
| 科普创作规范 | 中国有行业倡导；**本轮未核到强制性标准文件**（如实标注） |

---

## 卡帕西推文档案（2026-10）

原文（x.com/karpathy/status/2105819303471976479）：

> "We'll be spending a lot more time trying to understand the outputs of language models. A few thoughts, tips & tricks: Writing. Something I've had success with: Ask your LLM to explain something in ASD-STE100… LLMs well-versed in this language and it comes with heavy constraints on clean writing style that I often find a lot more readable. Sometimes I've tried to soften it a bit e.g. ask for '80% of the way to ASD-STE100'."

- 技巧：提示词里报标准全名，让 LLM 按标准写/解释
- 软化旋钮："80% of the way to ASD-STE100"
- 生态：Search Engine Journal 报道（"Make LLMs Write Like An Aircraft Manual"）；社区 skill：github.com/danyuchn/asd-ste100-skill；HN 讨论金句 "AI slop dies as a side effect"
- **反方实验**（allaboutcoding.ghinda.com）：不报全名只说 "Simple Technical English" 时，Claude/Codex 表现有升有降 → 结论：报全名更稳，但非万灵，写完仍要验收

---

## 元规律

1. 报标准**全名** > 口语描述。
2. 可组合：结构标准（F/G）管「说什么什么顺序」，受控语言（A）管「句子怎么写」，公式（H）管「验收」。
3. 各标准公分母：一句一义、主动语态、短句、结论先行、禁行话。
4. 中文场景无 STE 等价物 → 用「受控中文」自拟（公分母 + GB/T 系列格式规范）。

---

## 来源

- [ASD-STE100 官网](https://www.asd-ste100.org) ｜ [Wikipedia: Simplified Technical English](https://en.wikipedia.org/wiki/Simplified_Technical_English) ｜ [ASD FAQ](https://www.asd-europe.org/standards-specifications/simplified-technical-english/faq-simplified-technical-english-ste)
- Karpathy 原推：[x.com/karpathy/status/2105819303471976479](https://x.com/karpathy/status/2105819303471976479) ｜ [SEJ 报道](https://www.searchenginejournal.com/karpathy-llm-aircraft-manual-writing/591813) ｜ [反方实验](https://allaboutcoding.ghinda.com/explain-to-me-in-simple-technical-english)
- Plain Language：[PlainWriting.gov](https://www.plainlanguage.gov) ｜ [EU English Style Guide (PDF)](https://knowledge-centre-translation-interpretation.ec.europa.eu/sites/default/files/ckeditor5-files/styleguide_english_dgt_en.pdf) ｜ [EU plain language](https://translation.ec.europa.eu/languages-and-translation-european-commission/plain-language-making-european-commission-texts-clear_en)
- PLS：[ISMPP](https://www.ismpp.org/patient-engagement) ｜ [ClinicalTrials.gov 撰写指南](https://clinicaltrials.gov/submit-studies/prs-help/plain-language-guide-write-brief-summary)
- 汇报/演示：[Assertion-Evidence](https://www.assertion-evidence.com) ｜ [Minto Pyramid (untools)](https://untools.co/minto-pyramid) ｜ [Six P's](https://accendoreliability.com/podcast/qdd/qdd-151-revolutionize-your-technical-presentations-mastering-the-assertion-evidence-model-and-the-six-ps-framework)
- 受控语言：[ACE (Wikipedia)](https://en.wikipedia.org/wiki/Attempto_Controlled_English) ｜ [agentskills.io/specification](https://agentskills.io/specification)（本 skill 的打包规范）
- 中文：[GB/T 9704-2012](https://openstd.samr.gov.cn/bzgk/std/newGbInfo?hcno=F3CC9BEF482524C895FDA7A08BB4A70E)
- 可读性：[Flesch 公式详解](https://clickhelp.com/clickhelp-technical-writing-blog/flesch-reading-ease-formula-a-complete-guide) ｜ [readable.com 公式大全](https://readable.com/readability/readability-formulas)

**免责声明**：本档案是独立整理的学习指南，与 ASD、ISMPP、欧盟委员会等标准组织无隶属关系。
ASD-STE100 等名称归其各自所有者。本文只引名称与公开概述，不转载受版权保护的词表/规则原文。
