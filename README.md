[![简体中文](https://img.shields.io/badge/-简体中文-blue?style=flat-square)](README.zh-CN.md)

# writing-standards

Select the right writing standard for a task. Nothing else.

An Agent Skill for Claude Code and compatible agents. It asks three questions. It picks a language standard for your scenario. It returns a style specification. The calling task then writes the content in that style.

Inspired by Andrej Karpathy (2026-10): name a writing standard in your prompt (for example, ASD-STE100), and language models follow it well.

## What it does — and does not do

This skill does three things:

1. Ask. Purpose and reader. Scenario. Context (format, tone, length).
2. Select. One main standard for structure. One secondary standard for sentences.
3. Return. A style specification: standard name, structure rules, sentence rules, acceptance checks.

This skill does not write content. It does not handle layout or file format. Format (txt, md, HTML, PPT) belongs to the calling task. It does not run acceptance checks.

## Install

```bash
# user level (all projects) — recommended
cp -r writing-standards ~/.claude/skills/

# or project level (one repository)
cp -r writing-standards .claude/skills/
```

Claude Code loads the skill when a task needs a style decision. You can also invoke it with `/writing-standards`.

## Use

Direct use: ask which standard fits your text.

Wrapped use: set the style as a constraint inside a larger task.

> Write an HTML tutorial about SSH. For the language style, use ASD-STE100 Simplified Technical English. Run /writing-standards first and return the style specification.

The skill returns the specification. The main task applies it. The skill skips its questions when the context already states the scenario.

## Scenario map (short form)

| Scenario | Main standard (structure) | Sentence standard |
|---|---|---|
| Report to an advisor or manager | BLUF / Minto Pyramid | one idea per sentence |
| Academic paper | journal guidelines + IMRaD | STE discipline in Methods |
| Plain version of a paper | Plain Language Summary (PLS) | ClinicalTrials word list |
| Slide deck | Assertion-Evidence | slide title states the claim |
| Science communication | plain language ideas | ClinicalTrials word list |
| Technical documentation | ASD-STE100, or its "80% path" | STE rules |
| Chinese official document | GB/T 9704-2012 | GB/T 15834 punctuation |
| Email | BLUF | common rules |

The full archive (eight standard families, per-standard rules, sources) lives in [references/standards-map.md](references/standards-map.md).

## Repository layout

```
writing-standards/
├── SKILL.md                  # selection workflow; loads when triggered
├── references/
│   └── standards-map.md      # standards archive + sources; loads on demand
├── README.md                 # this file
├── README.zh-CN.md           # Chinese version
└── LICENSE                   # MIT
```

## Credits and disclaimer

Prompt trick: Andrej Karpathy, 2026-10 ([original post](https://x.com/karpathy/status/2105819303471976479)). All research sources are listed in the archive.

This project is an independent guide. It is not affiliated with ASD, ISMPP, or the European Commission. Standard names belong to their owners. This project cites names and public summaries only. It does not reproduce copyrighted dictionaries or rule texts.
