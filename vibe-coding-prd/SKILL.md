---
name: vibe-coding-prd
description: Turn user requirements, rough PRDs, competitor analysis, links, notes, or vague product ideas into a concise Markdown PRD that can be sent directly to Claude Code, Codex, or another coding agent for Vibe coding. Use when the user says "帮我写一个用来vibe coding的PRD" or asks to extract, refine, rewrite, or produce a coding-agent-ready PRD from demand notes, original PRDs, product research, competitor analysis, or unclear feature ideas.
---

# Vibe Coding PRD

## Purpose

Create a concise PRD for a coding agent. Strip away business fluff, keep implementation-relevant context, and force explicit user confirmation before locking scope, priority, UI shape, or assumptions.

Use [references/prd-template.md](references/prd-template.md) as the final output skeleton.

## Core Rules

- Do not infer what the user wants when the requirement is unclear. Ask targeted questions before continuing.
- Prefer 2-4 choice questions when guiding a vague user. Include an "other / not sure" option when useful.
- When the runtime provides a modal/user-input tool, use it for confirmations and priority choices. If no modal tool is available, ask concise questions in chat.
- Keep the PRD lean. Write for Claude Code, Codex, or another coding agent, not for executives.
- Remove or compress commercial value, market background, vision statements, org process, and non-implementation narrative unless needed to understand product behavior.
- Every final functional requirement must have observable acceptance criteria. Avoid vague criteria such as "good experience", "fast", "beautiful", "intelligent", or "stable" unless quantified or tied to visible behavior.
- Confirm major decisions before finalizing: product definition, MVP scope, priority order, technical stack, prototype/wireframe, and any explicit exclusions.

## Input Classification

Classify the user's material first:

1. **Clear requirement**: includes a recognizable user, scenario, pain point, and desired product outcome.
   - Continue to Product Definition and Functional Design.
2. **Original PRD**: already written for engineers, often with feature lists, screens, rules, API notes, data requirements, or links.
   - Extract only information a coding agent needs.
   - If it is a Feishu/Lark document or another linked source and a relevant document skill/tool is available, read the source before summarizing. If access is unavailable, ask the user to paste the content or grant access.
3. **Competitor analysis / research**: compares products, features, flows, pricing, positioning, screenshots, or notes.
   - Convert observations into candidate user needs and feature options.
   - Ask the user to choose which competitor behaviors to adopt, avoid, or defer.
4. **Unclear idea / other**: lacks clear user, scenario, pain point, or product shape.
   - Do not start writing the PRD.
   - Ask choice-based discovery questions until the real need is clear enough.

State the classification briefly and explain what is missing or what will be extracted.

## Clarification Flow

For vague input, ask only the next useful set of questions. Prefer choices like:

- Target user: "Who is this for? A) individual users B) internal operators C) creators/sellers D) developers E) not sure"
- Scenario: "Where does this happen? A) mobile daily use B) desktop workbench C) internal admin flow D) chat/agent workflow E) other"
- Pain point: "What problem matters most? A) save time B) reduce mistakes C) organize information D) automate decisions E) improve conversion"
- Product shape: "What should we build first? A) web app B) mobile-friendly web page C) browser extension D) chatbot/agent E) script/internal tool"

Continue only after the user confirms enough of:

- user group
- scenario
- pain point
- product form
- desired output or core job-to-be-done

## Design Workflow

### 1. Product Definition

Write a short definition covering:

- who it serves
- in what scenario
- what pain it solves
- what product form to build
- what the MVP must prove

Ask the user to confirm or correct it before proceeding if any part is uncertain.

### 2. Functional Inventory

Create a function table with:

- Level 1 module
- Level 2 feature
- Description
- MVP / Later / Not doing
- Suggested priority
- Reason for priority

Ask the user to confirm:

- which features to build now
- which features not to build
- which features to defer
- whether priority should optimize for speed, demo quality, technical risk, user value, or completeness

Prioritize MVP features that unblock a usable end-to-end flow before secondary settings, analytics, admin polish, or edge-case automation.

### 3. Technical Stack Recommendation

Recommend a stack based on:

- product size
- interaction complexity
- AI/agent intensity
- data storage needs
- authentication needs
- deadline/time limit
- the user's likely technical level

Explain recommendations in plain language. Give one primary recommendation and, only when helpful, one simpler or more scalable alternative.

For each major feature, mention the likely implementation approach or relevant technology in user-friendly terms. Do not overwhelm non-technical users with unnecessary frameworks.

### 4. Wireframe / Prototype Frame

Design low-fidelity core screens in text. Include:

- screen names
- main regions
- key controls
- main user flow
- important states, such as empty, loading, error, generated result, confirmation

Ask the user to confirm the wireframe before writing detailed functional modules.

### 5. Detailed Functional Modules

For AI products, include:

- agent workflow
- role boundaries between user, app, model, tools, and storage
- prompt design for system/developer/user prompts when relevant
- tool system, including tool name, purpose, input, output, failure handling
- memory/data policy if the product stores user context
- fallback behavior when the model is uncertain

For traditional products, include:

- data model or key entities
- user actions and system responses
- permissions/authentication if needed
- state transitions
- validation rules
- integration points
- edge cases and error handling

### 6. Acceptance Criteria

Write acceptance criteria per feature. Use observable steps and outcomes:

- "When the user clicks X, Y appears."
- "Given A input, when the user submits, the system stores B and shows C."
- "If validation fails, show message D and do not proceed."

Avoid untestable criteria. Replace vague wording with specific visible behavior, data changes, or measurable thresholds.

### 7. Final PRD Output

After required confirmations, output a complete Markdown PRD using [references/prd-template.md](references/prd-template.md). The final PRD should be directly pasteable into Claude Code/Codex.

Include explicit "Not in Scope" and "Open Questions" sections. If no open questions remain, write "None".
