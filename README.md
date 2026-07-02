# Vibe Coding PRD Skill

> 把需求、原始 PRD、竞品分析或模糊想法，提炼成可以直接交给 Claude Code / Codex 的精简 PRD。

![Skill](https://img.shields.io/badge/Codex-Skill-111827?style=for-the-badge)
![PRD](https://img.shields.io/badge/Output-Markdown_PRD-2563EB?style=for-the-badge)
![Language](https://img.shields.io/badge/Language-ZH%2FEN-16A34A?style=for-the-badge)

## 这个 Skill 解决什么

很多需求文档适合给人看，但不适合直接给编码 Agent 开工。这个 skill 会把材料压缩成编码 Agent 真正需要的信息：

| 输入材料 | Skill 会做什么 | 最终输出 |
|---|---|---|
| 明确需求 | 补全产品定义、功能范围、技术建议、验收标准 | 可开发 PRD |
| 原始 PRD | 去掉商业背景和冗余叙事，保留工程关键信息 | 精简 PRD |
| 竞品分析 | 提炼可借鉴功能，并让用户选择取舍 | MVP 功能方案 |
| 模糊想法 | 用选择题引导用户说清真实需求 | 澄清后的 PRD |

## 触发方式

在 Codex 中说：

```text
帮我写一个用来vibe coding的PRD
```

也可以这样使用：

```text
Use $vibe-coding-prd to turn this rough product idea into a PRD for Claude Code.
```

## 工作流

```mermaid
flowchart TD
    A["用户输入需求 / PRD / 竞品分析"] --> B{"判断输入类型"}
    B -->|明确需求| C["定义用户、场景、痛点、产品形态"]
    B -->|原始 PRD| D["提炼编码 Agent 需要的信息"]
    B -->|竞品分析| E["转成候选功能与取舍问题"]
    B -->|需求不清晰| F["用选择题继续澄清"]
    F --> C
    D --> C
    E --> C
    C --> G["功能模块与 MVP 优先级"]
    G --> H["技术栈推荐"]
    H --> I["核心界面框架 / 原型图"]
    I --> J["详细模块设计"]
    J --> K["逐功能验收标准"]
    K --> L["输出完整 Markdown PRD"]
```

## 产出结构

```mermaid
mindmap
  root((Vibe Coding PRD))
    Product Definition
      用户
      场景
      痛点
      产品形态
    Scope
      In Scope
      Not in Scope
    Functional Modules
      一级模块
      二级功能
      MVP 优先级
    Technical Stack
      推荐方案
      功能实现建议
    Wireframe
      核心界面
      主流程
      状态设计
    Detailed Design
      AI Agent 工作流
      Tool 体系
      传统产品技术设计
    Acceptance Criteria
      可观察
      可点击
      可验证
```

## 安装

把仓库里的 `vibe-coding-prd` 文件夹复制到本地 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R vibe-coding-prd ~/.codex/skills/
```

安装后重启或刷新 Codex，即可通过触发语使用。

## 仓库结构

```text
.
├── README.md
└── vibe-coding-prd/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        └── prd-template.md
```

## 设计原则

- 不替用户脑补需求，范围不清楚就先确认
- 用选择题帮助非技术用户表达真实需求
- PRD 保持精简，避免商业黑话和冗余背景
- 优先定义 MVP，明确哪些现在不做
- 技术栈用普通话解释，给出推荐而不是堆名词
- 验收标准必须可观察、可点击、可验证

## License

MIT
