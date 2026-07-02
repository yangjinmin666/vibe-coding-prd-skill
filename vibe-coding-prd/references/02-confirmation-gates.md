# Confirmation Gates And Question Flow

Use this file whenever information is ambiguous or a major product decision affects implementation.

## Question Shape

Each gate question must:

1. summarize current understanding in 1-2 lines
2. present 2-4 numbered options
3. mark one recommended option when possible
4. ask the user to reply with the option number

```markdown
当前我理解的是：...

请确认这一项：
1. ...（推荐）：...
2. ...：...
3. ...：...

回复选项编号即可，我再继续下一步。
```

If a modal/user-input tool is available, use it for these confirmations.

## Gate 1: Demand Definition

Confirm:

- target user
- usage scenario
- pain point or job-to-be-done
- product form
- input and output
- first-version success
- explicit exclusions

If unclear, ask in this order:

### Target User

```markdown
先确认这是谁要用的：
1. 个人用户：偏轻量工具或个人效率
2. 团队内部人员（推荐）：偏工作流、权限、协作和数据管理
3. 企业客户/外部用户：需要更完整的账号、权限和交付体验
4. 还不确定：先按最小 MVP 验证
```

### Usage Scenario

```markdown
核心使用场景更接近：
1. 高频日常操作：要优先效率和快捷入口
2. 低频复杂任务（推荐）：要优先流程引导、状态保存和可追溯
3. 内容生成/信息整理：要优先输入、生成、编辑、导出
4. 数据录入/查询/管理：要优先表单、列表、权限和状态
```

### Core Pain

```markdown
最想解决的问题更接近：
1. 太费时间（推荐）：优先自动化和主链路闭环
2. 流程太乱：优先状态机和步骤引导
3. 信息太分散：优先知识库、检索和整理
4. 不会做：优先 AI Agent 和模板化输出
```

### Product Shape

```markdown
产品形态更接近：
1. Web 页面/后台（推荐）：适合复杂工作台和文件处理
2. AI Agent/自动化流程：适合以对话或任务流为核心
3. 浏览器插件/桌面工具：适合嵌入已有工作环境
4. CLI/API：适合开发者或内部自动化
```

## Gate 2: Feature And Priority Confirmation

After drafting features, ask:

```markdown
我把功能拆成了候选清单。第一版范围你更想：
1. 只做 P0 MVP（推荐）：先跑通核心闭环
2. P0 + 少量 P1：第一版更完整，但开发更久
3. 全量 P0/P1/P2：适合写完整 PRD，不一定第一版实现
4. 你先给我保守推荐：我来压缩范围
```

Then confirm:

- what to do now
- what not to do
- what to defer
- MVP internal order
- priority basis: speed, completeness, AI quality, extensibility, demo quality

## Gate 3: Technical Stack Confirmation

Ask:

```markdown
技术方案我建议按这个方向选：
1. 最快做出可跑 MVP（推荐）：少依赖，方便编码 Agent 实现
2. 更接近生产：多一些权限、队列、监控和部署设计
3. 后续扩展优先：架构更完整，但第一版更慢
4. 尽量无后端/低成本：适合小工具或演示
```

## Gate 4: Wireframe Confirmation

Ask:

```markdown
核心界面我先按这个框架设计。下一步你希望：
1. 保持结构，继续写详细 PRD（推荐）
2. 减少页面数量，先聚焦 MVP
3. 调整布局后再继续
4. 增加一个关键页面或区域
```

## AI Role Confirmation

If AI involvement is unclear:

```markdown
AI 在这个产品里的角色更接近：
1. 辅助功能：传统产品为主，AI 只是增强
2. 核心工作流一部分：需要 AI 流程和工具调用
3. Agent 核心产品（推荐）：需要完整 Agent workflow、prompt、tool、评测和兜底
4. 暂时不做 AI：只保留接口或 TODO
```

## Stop Condition

If the user cannot confirm basics, stop with:

```markdown
# 待确认项

- 目标用户：
- 核心场景：
- 核心痛点：
- 产品形态：
- MVP 时间要求：

以上信息未确认前，不继续生成正式 PRD。
```
