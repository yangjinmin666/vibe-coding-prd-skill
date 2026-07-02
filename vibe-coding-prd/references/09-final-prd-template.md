# Final Vibe Coding PRD Template

Use this template for the final Markdown PRD. Delete sections that do not apply. Do not wrap the final PRD in a code block unless the user explicitly asks.

# {Product Name} Vibe Coding PRD

## 1. 一句话目标

{这个产品给谁，在什么场景下，解决什么问题，第一版做成什么形态。}

## 2. 输入来源与处理方式

- 输入类型：{明确需求/原始 PRD/竞品分析/混合材料/信息不足}
- 已保留：{编码 Agent 需要的信息}
- 已删除：{商业汇报、背景铺垫、重复描述等}
- 仍有假设：{如有}

## 3. 需求定义

- 目标用户：
- 使用场景：
- 核心痛点：
- 产品形态：
- 核心输入：
- 核心输出：
- 第一版成功标准：
- 已知约束：

## 4. 范围与优先级

### 第一版要做

| 顺序 | 一级模块 | 二级功能 | 功能描述 | 优先级 | 依赖 |
|---|---|---|---|---|---|

### 后续做

| 阶段 | 功能 | 推迟原因 |
|---|---|---|

### 明确不做

- 

## 5. 核心用户流程

1. 

## 6. 页面与原型框架

### 页面结构

| 页面 | 入口 | 核心区域 | 关键操作 | 状态/反馈 |
|---|---|---|---|---|

### 核心页面线框图

```text
{ASCII wireframe}
```

## 7. 技术方案

### 推荐栈

- Frontend:
- Backend:
- Database:
- Auth:
- Storage:
- AI/Agent:
- Deployment:

### 功能到技术映射

| 功能/模块 | 推荐实现 | 原因 | 取舍 |
|---|---|---|---|

### 架构与部署

- 

## 8. 功能明细

### {Module}

#### {Feature}

- 目标：
- 前置条件：
- 用户操作：
- 系统行为：
- 输入与校验：
- 输出：
- 状态与异常：
- 数据/接口：

## 9. AI / Agent 设计（如适用）

### Agent 工作流

| Node | Trigger | Input | Output | State Read/Write | Failure Path |
|---|---|---|---|---|---|

### Prompt 设计

- System role:
- Inputs:
- Output schema:
- Constraints:
- Fallback behavior:

### Tool 体系

| Tool | Purpose | Trigger | Input | Output | Permission/Side Effect | Failure Handling |
|---|---|---|---|---|---|---|

### Memory / State / Evaluation

- Short-term state:
- Persistent memory:
- Version binding:
- Evaluation/golden set:
- Human review:
- Kill switch/fallback:

## 10. 数据与接口

### 核心数据实体

| Entity | Fields | State/Relationship |
|---|---|---|

### APIs / Events

| API/Event | Method/Trigger | Input | Output | Failure |
|---|---|---|---|---|

## 11. 验收标准

### {Feature}

- [ ] Given ..., when ..., then ...
- [ ] If ..., then ...

## 12. 建议开发顺序

1. 

## 13. 给编码 Agent 的开工提示词

```text
请根据以上 PRD 实现第一版产品。

执行要求：
1. 优先完成 P0/MVP 主链路。
2. P1/P2 只预留接口、数据结构或 TODO，除非 PRD 明确要求本期实现。
3. 不实现 Not in Scope。
4. 遇到不明确处，先列 Open Question 或使用最小 mock，不要擅自扩大范围。
5. 每完成一个模块，运行测试或给出本地验收步骤。
```

## 14. Open Questions

- None

## 15. Confirmation Log

- Demand definition:
- Feature priority:
- Technical stack:
- Wireframe:
- Final scope:
