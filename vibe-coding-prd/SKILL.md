---
name: vibe-coding-prd
description: Turn fuzzy ideas, clear requirements, raw engineering PRDs, Feishu/Lark docs, competitor analysis, research notes, screenshots, or mixed product material into a concise but complete Markdown PRD that can be sent directly to Claude Code, Codex, or another coding agent. Use when the user says "帮我写一个用来vibe coding的PRD", asks for a Vibe Coding PRD, wants to transform requirements into coding-agent-ready implementation instructions, or needs product clarification before coding.
---

# Vibe Coding PRD

Create an implementation-ready PRD for coding agents. Keep it concise, but do not omit decisions that affect scope, architecture, data, AI workflow, UI states, failure handling, or acceptance.

## Non-Negotiable Rules

- Do not guess core intent. If user, scenario, pain point, product shape, MVP scope, technical direction, or wireframe is unclear, ask before continuing.
- Use modal/user-input confirmation tools when available. If unavailable, ask numbered choice questions in chat.
- Every blocking question must be option-based: 2-4 choices, one recommended choice when possible, and a short tradeoff note. Use open-ended questions only when choices would be misleading.
- Move through the four confirmation gates in order: demand definition, feature/MVP priority, technical stack, core wireframe. Do not output the final PRD until all gates are confirmed or explicitly marked as assumed by the user.
- Strip business persuasion, market sizing, vision slogans, organization background, and repeated narrative unless it changes implementation.
- Preserve implementation signals: users, roles, workflows, pages, states, data objects, permissions, APIs/events, AI prompts/tools, evaluation, fallbacks, observability, and acceptance criteria.
- For AI products, expose the Product Engineer route: client action, API/event entry, domain service, orchestrator, model/tool/retrieval dependency, data read/write, state transition, human review/fallback, trace/metric/audit, cost or release control.
- Acceptance criteria must be observable and reproducible. Avoid vague criteria such as "体验良好", "更智能", "页面美观", or "性能优秀".
- Default to the user's language. If the user writes in Chinese, ask and output in Chinese while preserving useful technical terms.
- The skill produces PRDs, not product code. If the user asks to implement after the PRD, treat that as a separate coding task.

## Workflow Map

1. **Classify and extract input**: read [references/01-input-routing.md](references/01-input-routing.md).
2. **Clarify with gates**: read [references/02-confirmation-gates.md](references/02-confirmation-gates.md).
3. **Design features and MVP**: read [references/03-feature-mvp.md](references/03-feature-mvp.md).
4. **Recommend technical stack**: read [references/04-tech-stack.md](references/04-tech-stack.md).
5. **Draft core wireframe**: read [references/05-wireframe.md](references/05-wireframe.md).
6. **Write detailed modules**: read [references/06-detailed-modules.md](references/06-detailed-modules.md).
7. **For AI products or AI-heavy modules**: also read [references/07-ai-pe-agent-design.md](references/07-ai-pe-agent-design.md).
8. **Write acceptance criteria**: read [references/08-acceptance-criteria.md](references/08-acceptance-criteria.md).
9. **Generate final PRD**: read [references/09-final-prd-template.md](references/09-final-prd-template.md).

Read only the references needed for the current phase. If the user provides a raw PRD link, read the source material before summarizing. For Feishu/Lark Docx/Wiki links, use the available `lark-doc` or equivalent document connector/skill; if access fails, ask the user to grant access, export Markdown, or paste the content.

## Input Classification

Classify the material as exactly one primary type:

- `明确需求`: already includes user, scenario, pain point, and product form/output.
- `原始 PRD`: long or structured product/engineering document, Feishu/Lark doc, Markdown, PDF, or PRD-like spec.
- `竞品分析`: mainly describes other products, screenshots, comparisons, flows, or feature inspiration.
- `混合材料`: multiple source types with possible conflicts.
- `信息不足`: missing user, scenario, pain point, or product shape.

State the classification briefly, what will be extracted, and whether confirmation is needed.

## Confirmation Gates

Gate 1: Demand definition.

- 给谁用
- 什么场景
- 解决什么问题
- 什么产品形态
- 核心输入/输出
- 明确不做

Gate 2: Feature list and priority.

- 一级模块、二级功能、功能描述
- P0/P1/P2/Later/不做
- MVP development order
- dependencies and reason for priority

Gate 3: Technical stack.

- one recommended plan and, only when useful, one simpler or more scalable alternative
- explain tradeoffs in plain language for non-technical users
- map important features to implementation choices

Gate 4: Core wireframe.

- 1-3 core pages or interfaces
- ASCII/text wireframes
- key actions, states, empty/error/loading/success states
- main click path

## Final PRD Standard

The final Markdown PRD must let a coding agent start without guessing:

- what to build and what not to build
- first version scope and priority order
- pages, modules, states, and flows
- technical stack and architecture route
- data entities, APIs/events, permissions, and integrations when relevant
- AI agent workflow, prompts, tools, memory, evaluation, and fallback when relevant
- acceptance criteria that can become tests or manual checks
- suggested coding-agent execution order

If confirmation is incomplete, output a `待确认项` section and ask the next option-based question instead of pretending the PRD is final.
