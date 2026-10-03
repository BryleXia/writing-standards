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

## 它做什么

1. **选型**：按场景表选「主标准」（管结构）+「辅标准」（管句子）。
   汇报→BLUF/金字塔；pre→Assertion-Evidence；论文→期刊体例+IMRaD；科普→Plain Language+PLS；技术文档→ASD-STE100；中文公文→GB/T 9704。
2. **套规则**：结构层用主标准骨架；句子层用「公分母六条」（一句一义、主动语态、术语统一、结论先行、步骤编号、禁行话）。
3. **验收**：清单自查 + Flesch 可读性量尺（大众 60–70 / 技术 40–60 / 学术 30–50）。

另含**卡帕西提示词配方**（报标准全名、"80% of the way" 软化旋钮、结构×句子组合拳）。

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
