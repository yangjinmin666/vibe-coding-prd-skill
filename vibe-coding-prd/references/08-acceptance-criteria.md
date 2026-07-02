# Acceptance Criteria

Acceptance criteria must be convertible to manual checks or tests.

## Format

Use:

```markdown
### {Feature}

- [ ] Given {precondition}, when {user action}, then {observable system result}.
- [ ] If {error/edge condition}, then {message/state/fallback}, and {data remains unchanged or retry is available}.
```

Chinese equivalent:

```markdown
### {功能}

- [ ] 已登录用户在{页面}点击{按钮}后，系统{可观察结果}。
- [ ] 当{异常条件}时，系统显示{明确提示}，并且{不会产生错误数据/允许重试/保留输入}。
```

## Cover These Cases

- success path
- required field validation
- permission denied
- empty data
- loading/processing
- retryable failure
- non-retryable failure
- data saved/updated/deleted
- export/download if relevant
- AI low confidence, no data, tool failure, hallucination guard if relevant

## Bad Criteria To Rewrite

- "体验良好"
- "页面美观"
- "响应快"
- "AI 准确"
- "流程顺畅"

Rewrite with a threshold or visible behavior:

- "点击提交后 1 秒内按钮进入 loading，成功后跳转详情页。"
- "未找到资料时显示空状态和上传入口。"
- "AI 未找到事实依据时输出 `[待补充]`，不得编造数字。"
