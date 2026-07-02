# AI Product And Product Engineer Agent Design

Use this for AI-native or AI-heavy products.

## Product Engineer Lens

Do not describe "AI generates" as a black box. Expose:

- client layer
- API/event entry
- domain service owner
- AI orchestrator
- model gateway/provider adapter
- retrieval/rerank/tool dependencies
- rule engine or validation layer
- data stores and versioned configs
- state machine
- human review route
- observability, audit, metrics, feedback
- fallback, rollback, kill switch
- MVP boundary

## Agent Workflow

Write the runtime flow as nodes:

```markdown
1. input_intake_node
2. classify_or_plan_node
3. retrieve_context_node
4. tool_call_node
5. generation_node
6. validation_or_audit_node
7. human_review_node
8. save_output_node
9. feedback_or_evaluation_node
```

For each node:

- trigger
- input
- output
- state read/write
- tool/model used
- failure path

## Prompt Design

Include:

- system role
- developer/task instructions
- input variables
- output schema
- constraints
- refusal/uncertainty behavior
- examples only if they clarify format

Do not write huge prompt essays. Give coding agents a structured prompt skeleton.

## Tool System

Use:

```markdown
| Tool | Purpose | Trigger | Input | Output | Permission/Side Effect | Failure Handling |
|---|---|---|---|---|---|---|
```

## Memory And State

Specify:

- short-term state
- persistent memory
- user-visible memory
- deletable memory
- version bindings: model, prompt, retrieval index, rule config, evaluation set

## Quality And Evaluation

Include:

- golden set or test cases
- normal cases
- edge cases
- hallucination checks
- low-confidence path
- human review thresholds
- release gate

## Cost And Safety

When relevant:

- cost unit: per run, per document, per minute, per token, per export
- throttling lever
- budget alert
- non-AI fallback
- kill switch or disable strategy
