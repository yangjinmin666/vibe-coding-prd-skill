# Feature And MVP Design

## Demand Definition Block

Write:

- 给谁用
- 在什么场景
- 解决什么问题
- 做成什么形态
- 核心输入
- 核心输出
- 第一版成功标准
- 已知约束

## Feature Table

Use:

```markdown
| 一级模块 | 二级功能 | 功能描述 | 优先级 | 阶段 | 依赖 | 为什么现在做/不做 |
|---|---|---|---|---|---|---|
|  |  |  | P0/P1/P2/Later/不做 | MVP/v1.1/later |  |  |
```

## Priority Rules

P0:

- main user journey cannot complete without it
- creates, processes, views, saves, or exports the core result
- required for AI workflow execution if AI-native
- required for safety, permission, or data integrity in MVP

P1:

- improves editing, repeated use, management, or quality
- useful but not required for the first successful run
- can be stubbed with TODO, mock, or reserved data structure in first implementation

P2:

- nice-to-have
- analytics depth, visual polish, advanced settings, collaboration, integrations

Later / 不做:

- outside first version
- too complex for MVP
- contradicts constraints or Not in Scope

## MVP Discipline

Do not mark every feature as MVP. A good MVP has one complete end-to-end path and explicit omissions.

For coding agents, include:

- first build order
- dependencies
- data objects needed for P0
- which P1/P2 receive only interfaces/TODOs

## Confirmation

Before finalizing:

- ask which P0 features must be included
- ask which features are not built now
- ask whether the user optimizes for speed, completeness, AI quality, extensibility, or demo quality
