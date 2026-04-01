# Claude 协作框架 V2 前端版

这套模板适合：

- React / Vue / Next.js / Nuxt 等前端项目
- 页面、组件、状态、交互、样式是主要工作内容的项目

包含：

1. `CLAUDE.md`
2. `.claude/skills/review/SKILL.md`
3. `.claude/skills/bugfix/SKILL.md`
4. `.claude/skills/feature/SKILL.md`
5. `.claude/skills/refactor/SKILL.md`
6. `.claude/agents/debugger.md`
7. `.claude/agents/implementer.md`
8. `.claude/agents/reviewer.md`
9. `.claude/hooks/hooks.json`

## 前端版和通用版的区别

前端版更强调：

- 页面和组件边界
- UI 回归风险
- 交互一致性
- 状态管理复杂度
- 样式和响应式影响范围

## 推荐优先修改

1. `CLAUDE.md` 里的技术栈、目录、命令
2. `review` skill 里的前端审查重点
3. `implementer` 和 `reviewer` agent 的前端职责描述
4. `bugfix` / `debugger` 中更贴近你的页面和状态问题
