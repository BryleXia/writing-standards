# writing-standards

> 一个 Agent Skill：把成体系的语言标准（ASD-STE100、Plain Language、BLUF、金字塔原理、Assertion-Evidence、PLS、GB/T 9704……）用到你的每一次写作上——写汇报、论文、pre、科普、技术文档、公文之前，先选型、套规则、验收。
>
> An Agent Skill that applies established writing & language standards (ASD-STE100, plain language, BLUF, Minto Pyramid, assertion-evidence, PLS…) to any document you write — pick the right standard, apply its rules, verify readability.

灵感来自 Andrej Karpathy 的技巧（2026-10）：**在提示词里报标准全名**，让 LLM 按该标准写作——
"Ask your LLM to explain something in ASD-STE100… heavy constraints on clean writing style that I often find a lot more readable."

## 安装（Claude Code）

```bash
# 用户级（所有项目可用）——推荐
cp -r writing-standards ~/.claude/skills/

# 或项目级（只在当前仓库可用）
cp -r writing-standards .claude/skills/
```

装完即生效：Claude 在写作/改写/评审文本时会**自动触发**；也可以手动点名 `/writing-standards`。
（Agent Skills 是开放标准，Codex / Cursor 等兼容 agent 同样可读此目录。）

## 它做什么（职责很窄，故意的）

**只干一件事：为任务选文风。** 不写内容、不管载体排版——txt / md / HTML / PPT 由调用方任务负责。

1. **先问**：目的/读者、场景、上下文（除非任务里已经写明）。
2. **再裁**：按场景选型——汇报→BLUF/金字塔；pre→Assertion-Evidence；论文→期刊体例+IMRaD；科普→Plain Language+PLS；技术文档→ASD-STE100；中文公文→GB/T 9704。
3. **输出「文风规格」**：选定标准（全名）+ 结构规则 + 句子规则（公分母六条）+ 验收线——一份可注入任何写作任务的样式条款。

**包裹调用示例**：「写一个 HTML 教材，语言规范用 ASD-STE100」→ 本 skill 产出文风规格，HTML 写作由主任务执行。

另附卡帕西提示词技巧：报标准全名触发；"80% of the way to X" 软化。

## 目录结构（渐进披露，三层加载）

```
writing-standards/
├── SKILL.md                    # 第二层：命中任务才载入的操作手册（<500 行）
├── references/
│   └── standards-map.md        # 第三层：八大类标准全景档案 + 来源（按需查）
├── README.md                   # 本文件（给 GitHub 读者）
└── LICENSE                     # MIT
```

启动时只加载 `SKILL.md` 头部的 name+description（约 100 token）——上下文占用极小。

## 免责声明

本项目是独立整理的学习指南，与 ASD、ISMPP、欧盟委员会等标准组织无隶属关系。
ASD-STE100 等标准名称归其各自所有者；本项目只引名称与公开概述，不转载受版权保护的词表/规则原文。
