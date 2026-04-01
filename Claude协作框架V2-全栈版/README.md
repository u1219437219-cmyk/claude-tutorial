# Claude 协作框架 V2 全栈版

这套模板适合：

- 一个仓库里同时包含前端和后端
- Monorepo
- 管理后台 + API 服务
- Web 前后端一起维护的项目

## 设计原则

全栈版不直接把“前端版”和“后端版”原样叠加，而是：

1. 使用一份统一的 `CLAUDE.md`
2. 保留一套通用协作规则
3. 前后端的 skills 分开命名
4. 前后端的 agents 分开命名
5. 避免同名冲突

## 包含内容

1. `CLAUDE.md`
2. `.claude/skills/frontend-review/SKILL.md`
3. `.claude/skills/backend-review/SKILL.md`
4. `.claude/skills/frontend-bugfix/SKILL.md`
5. `.claude/skills/backend-bugfix/SKILL.md`
6. `.claude/skills/frontend-feature/SKILL.md`
7. `.claude/skills/backend-feature/SKILL.md`
8. `.claude/agents/frontend-implementer.md`
9. `.claude/agents/backend-implementer.md`
10. `.claude/agents/frontend-reviewer.md`
11. `.claude/agents/backend-reviewer.md`
12. `.claude/agents/frontend-debugger.md`
13. `.claude/agents/backend-debugger.md`
14. `.claude/hooks/hooks.json`

## 推荐使用方式

### 做前端任务时

- 用 `frontend-*` skills
- 用 `frontend-*` agents

### 做后端任务时

- 用 `backend-*` skills
- 用 `backend-*` agents

### 做跨前后端任务时

- 先按通用规则分析影响范围
- 再拆成前端部分和后端部分分别推进

## 最后建议

如果任务只动一边，就只用那一边的 skill 和 agent。

如果任务同时影响前后端，最好先让 Claude 拆边界，再分别处理。
