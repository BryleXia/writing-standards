[![English](https://img.shields.io/badge/-English-lightgrey?style=flat-square)](README.md)

# writing-standards

为任务选文风。只干这一件事。

这是一个 Agent Skill。兼容 Claude Code 和其他同类工具。它问三个问题。它按你的场景选定语言标准。它返回一份文风规格。写内容的任务拿到规格后照此执行。

灵感来自 Andrej Karpathy（2026-10）：在提示词里报标准全名（例如 ASD-STE100），语言模型就会按标准写作。

## 职责：做什么，不做什么

本 skill 只做三件事：

1. **问**。目的和读者。场景。上下文（载体、语气、篇幅）。
2. **裁**。主标准一份，管结构。辅标准一份，管句子。
3. **出规格**。内容是：标准全名、结构规则、句子规则、验收线。

本 skill 不写内容。不处理载体和排版。txt、md、HTML、PPT 归调用方任务管。不执行验收检查。

## 安装

```bash
# 用户级（所有项目可用）——推荐
cp -r writing-standards ~/.claude/skills/

# 或项目级（单个仓库可用）
cp -r writing-standards .claude/skills/
```

Claude Code 会在需要文风决策的任务中自动加载本 skill。你也可以用 `/writing-standards` 手动唤起。

## 用法

**直接用**：问「这段文字该用什么标准？」。

**包裹用**：把文风作为约束条件，写进更大的任务里。

> 写一份 SSH 入门的 HTML 教程。语言规范用 ASD-STE100 Simplified Technical English。先调用 /writing-standards 产出文风规格，再动笔。

skill 返回规格。主任务套用规格。若任务上下文已写明场景，skill 跳过追问，直接裁定。

## 场景选型表（简表）

| 场景 | 主标准（管结构） | 辅标准（管句子） |
|---|---|---|
| 给老师、上级汇报 | BLUF / Minto 金字塔 | 一句一义 |
| 学术论文 | 期刊规范 + IMRaD | 方法节套 STE 纪律 |
| 论文通俗版 | Plain Language Summary（PLS） | ClinicalTrials 用词表 |
| 演示、PPT | Assertion-Evidence | 页标题写主张 |
| 科普 | 平实语言思想 | ClinicalTrials 用词表 |
| 技术文档、手册、教程 | ASD-STE100，或其「80% 路」 | STE 规则 |
| 中文正式公文 | GB/T 9704-2012 | GB/T 15834 标点 |
| 邮件 | BLUF | 公分母规则 |

详尽档案（八大类标准、各标准细则、来源链接）在 [references/standards-map.md](references/standards-map.md)。

## 目录结构

```
writing-standards/
├── SKILL.md                  # 选型流程；命中任务时载入
├── references/
│   └── standards-map.md      # 标准档案 + 来源；按需载入
├── README.md                 # 英文版
├── README.zh-CN.md           # 本文件
└── LICENSE                   # MIT
```

## 致谢与免责声明

提示词技巧出自 Andrej Karpathy，2026-10（[原推](https://x.com/karpathy/status/2105819303471976479)）。全部调研来源列在档案里。

本项目是独立整理的学习指南。本项目与 ASD、ISMPP、欧盟委员会无隶属关系。标准名称归各自所有者。本项目只引名称与公开概述。本项目不转载受版权保护的词表和规则原文。
