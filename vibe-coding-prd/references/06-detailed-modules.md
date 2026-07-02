# Detailed Module Design

Use this after demand, feature priority, stack, and wireframe are confirmed.

## Product Type Branch

Ask or infer, then confirm:

- AI-native product
- traditional product
- mixed product

For mixed products, mark which modules use AI and which are ordinary product flows.

## Traditional Module Detail

For each module:

```markdown
### {Module}

- Purpose:
- Entry:
- User actions:
- System behavior:
- Data/entities:
- State transitions:
- Permissions:
- APIs/events:
- Validation:
- Empty/loading/error states:
- Edge cases:
```

## AI Module Detail

For AI modules, also include:

- Agent role
- workflow steps
- input/output contracts
- prompt design
- tool system
- memory/context strategy
- retrieval/data dependency
- human confirmation points
- evaluation method
- fallback and retry

Read `07-ai-pe-agent-design.md` for AI-heavy products.

## PE Completeness Checklist

For each important workflow, answer:

- What user action or system trigger starts it?
- What client behavior happens?
- What API or event is called?
- Which domain service owns the result?
- What data objects are read and written?
- What state transition happens?
- What can fail?
- What retry, fallback, human review, or rollback exists?
- What log, metric, audit, trace, or feedback event is needed?

## Data And Interface Section

Include when relevant:

```markdown
### Core Data Objects

| Object | Fields | State/Relationship |
|---|---|---|

### APIs / Events

| API/Event | Method/Trigger | Input | Output | Failure |
|---|---|---|---|---|
```
