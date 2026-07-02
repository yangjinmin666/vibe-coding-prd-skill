# Technical Stack Recommendation

Recommend a stack that a coding agent can implement, not an architecture slide.

## Inputs To Consider

- product size
- interaction complexity
- AI intensity
- data sensitivity
- file or media processing
- auth/permission needs
- existing system integrations
- deployment target
- time limit
- user's technical level

## Output Shape

```markdown
## 技术栈建议

### 推荐方案

- Frontend:
- Backend:
- Database:
- Object/file storage:
- Auth:
- AI/model:
- Agent orchestration:
- RAG/vector store:
- Async jobs:
- Export/rendering:
- Deployment:
- Observability:

### 为什么这样选

- ...

### 功能到技术映射

| 功能/模块 | 推荐实现 | 原因 | 取舍 |
|---|---|---|---|
```

## Plain-Language Rule

For non-technical users, explain by tradeoff:

- fastest MVP
- lowest maintenance
- easiest coding-agent implementation
- production-ready
- scalable but slower

## Defaults

Small Web MVP:

- Next.js + TypeScript + Tailwind/shadcn
- Supabase or SQLite/PostgreSQL
- simple file storage
- deploy on Vercel/Render/Fly.io

Internal workflow/dashboard:

- React/Next.js
- FastAPI or Node backend
- PostgreSQL
- RBAC
- background jobs if long-running processing exists

AI workflow or Agent product:

- Next.js frontend
- FastAPI backend
- LangGraph for workflow orchestration when multi-step Agent state matters
- model provider adapter
- retrieval/rerank/tool layer
- queue for long-running generation
- trace logs and evaluation hooks

Document-generation product:

- document parser
- chunk store and vector search
- generation run table
- citation map
- export service
- report/job state machine

## Avoid Over-Engineering

Do not recommend Kubernetes, microservices, complex event buses, or custom auth unless the requirement clearly needs them. If a heavy tool is useful later, mark it as a future migration option.

## Version Rule

Do not invent exact package versions. Use "current stable version" unless the user or source material specifies a version.
