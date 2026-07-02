# Input Routing And Source Extraction

## Classification Output

After reading the user's material, output:

```markdown
我判断你的输入属于：{明确需求/原始 PRD/竞品分析/混合材料/信息不足}
下一步我会：{提炼/澄清/合并/转写}
需要先确认：{如有，列 1-3 个选项题}
```

## Type Rules

### 明确需求

Use when the material has:

- target user or role
- usage scenario
- pain point or task
- expected product form or output

Proceed to demand definition, but still confirm scope and priority before final PRD.

### 原始 PRD

Use for long PRDs, engineering specs, Feishu/Lark links, exported docs, PDFs, or structured product docs.

Extract:

- product goal in one sentence
- user roles and permissions
- pages and workflows
- feature modules
- data objects and state transitions
- APIs, events, integrations, analytics
- AI workflow, prompts, tools, evaluation, fallback
- nonfunctional constraints that affect implementation
- explicit out-of-scope items

Remove:

- business persuasion
- market sizing and revenue story
- repeated background
- stakeholder alignment wording
- decorative wording
- launch-process details that do not change implementation

For Feishu/Lark Docx/Wiki links:

1. Use `lark-doc` or the available Lark document connector.
2. Read the current CLI/connector skill instructions before using document commands.
3. If permissions fail, ask the user to authorize, export Markdown, or paste the content.
4. Treat embedded sheets, bitables, slides, or whiteboards as optional; inspect them only if they affect implementation.

### 竞品分析

Extract:

- user problem the competitor solves
- implementable feature patterns
- information architecture
- useful interaction states
- differentiating choices

Do not copy branding, proprietary copy, or unconfirmed claims. Ask which behaviors to copy, simplify, avoid, or defer.

### 混合材料

Merge sources with precedence:

1. explicit latest user instruction
2. original PRD scope
3. competitor analysis as optional inspiration
4. inferred best practice only as a recommended option

Flag conflicts as choice questions.

### 信息不足

Do not draft the final PRD. Ask option-based questions from `02-confirmation-gates.md` until user, scenario, pain point, and product shape are clear.

## Source Summary

Before continuing, summarize source material in 3-6 bullets:

- product to build
- target users
- core scenario
- core pain
- known constraints
- missing or conflicting decisions
