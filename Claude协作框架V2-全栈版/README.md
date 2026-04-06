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
8. `.claude/skills/frontend-design/SKILL.md`
9. `.claude/agents/frontend-implementer.md`
10. `.claude/agents/backend-implementer.md`
11. `.claude/agents/frontend-reviewer.md`
12. `.claude/agents/backend-reviewer.md`
13. `.claude/agents/frontend-debugger.md`
14. `.claude/agents/backend-debugger.md`
15. `.claude/hooks/hooks.json`

## 推荐使用方式

### 先说明一个原则

- 这个全栈版模板更适合放项目私有规则
- `superpowers` 更适合作为全局安装的流程型技能库
- 推荐做法不是把整个 `superpowers` 仓库复制进 `.claude/`
- 推荐做法是：全局安装 `superpowers`，项目内保留这套全栈版模板

### 做前端任务时

- 用 `frontend-*` skills
- 用 `frontend-*` agents
- 如果任务重点是页面视觉、设计语言、落地页、仪表盘或 UI 美化，优先用 `frontend-design`
- 如果任务重点是功能实现和交互逻辑，优先用 `frontend-feature`

### 做后端任务时

- 用 `backend-*` skills
- 用 `backend-*` agents

### 做跨前后端任务时

- 先按通用规则分析影响范围
- 再拆成前端部分和后端部分分别推进

### 和 Superpowers 搭配使用

- `superpowers` 负责流程，比如 brainstorming、writing-plans、test-driven-development、code review、worktree 和分代理执行
- 这个全栈版模板负责项目上下文和前后端边界，比如目录结构、常用命令、前端 skill、后端 skill、agent 分工
- 两者一起用时，可以理解成：`superpowers` 管方法，这个模板管项目细节

### 和 claude-md-management 搭配使用

- `claude-md-management` 负责维护 `CLAUDE.md`
- 其中 `claude-md-improver` 适合在项目规则变化后审计 `CLAUDE.md` 是否仍然准确
- `/revise-claude-md` 适合在一次协作结束后，把本次暴露出的缺失上下文补进 `CLAUDE.md`
- 这个插件不替代全栈模板本身，它更像是模板维护工具

### 和 context7 搭配使用

- `context7` 负责查最新官方文档和代码示例
- 它特别适合在前端框架、后端框架、ORM、状态管理、样式库、构建工具和测试工具上查版本相关用法
- 当你不确定某个库当前版本的 API、配置方式或最佳实践时，优先用 `context7`
- 这个插件不负责项目规则，它更像是全栈开发时的官方文档检索层

### 和 code-review 搭配使用

- 项目内的 `frontend-review` / `backend-review` 负责定义 review 口径
- `code-review` 插件更适合在 PR 或合并前做自动化复查
- 可以理解成：项目内 review skills 管标准，`code-review` 管 PR 阶段的自动执行
- 如果变更同时涉及前后端，建议先按项目内 review 口径自检，再在 PR 阶段补一轮 `code-review`

### 和 security-guidance 搭配使用

- `security-guidance` 更适合在编辑和实现阶段提供实时安全提醒
- 它对前端的 XSS、危险渲染和输入处理问题有帮助，也对后端的命令注入、危险拼接和输入校验缺失有帮助
- 可以理解成：`security-guidance` 管编辑期安全提醒，`code-review` 管 PR 阶段复查，项目内 review skills 管业务和架构风险
- 它不替代业务 review，但很适合作为全栈项目的基础安全兜底层

### 和 planning-with-files 搭配使用

- `planning-with-files` 适合承接复杂需求、长任务和跨前后端任务的计划持久化
- 它适合把计划写进文件、持续更新状态，并在中断后恢复上下文
- 可以理解成：`superpowers` 管方法和流程，`planning-with-files` 管计划文件和执行状态，项目模板管前后端边界和项目细节
- 如果任务涉及多个阶段、多次会话或多边协作，优先考虑用 `planning-with-files` 固化计划

### Codex 下的推荐安装方式

- 按 `superpowers` README 和 Codex 安装说明，它更适合全局安装，而不是拷进项目目录
- 典型做法是把仓库 clone 到 `~/.codex/superpowers`
- 再把它的 `skills` 目录软链到 `~/.agents/skills/superpowers`
- 重启 Codex 让技能被发现

参考：
- [superpowers README](https://github.com/obra/superpowers/blob/main/README.md)
- [Codex 安装说明](https://raw.githubusercontent.com/obra/superpowers/main/.codex/INSTALL.md)
- [claude-md-management 插件](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/claude-md-management)
- [context7 插件](https://github.com/anthropics/claude-plugins-official/tree/main/external_plugins/context7)
- [code-review 插件](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/code-review)
- [security-guidance 插件](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/security-guidance)
- [planning-with-files](https://github.com/othmanadi/planning-with-files)

## 最后建议

更完整的插件分类和使用方式见：
- [PLUGIN_GUIDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/PLUGIN_GUIDE.md)

如果任务只动一边，就只用那一边的 skill 和 agent。

如果任务同时影响前后端，最好先让 Claude 拆边界，再分别处理。

如果前端任务同时涉及功能实现和视觉升级，可以先用 `frontend-design` 明确设计方向，再按 `frontend-feature` 的节奏落地实现。

如果你已经安装了 `superpowers`，建议把它作为默认流程层，把这个全栈版模板作为项目专属规则层。

如果你已经安装了 `claude-md-management`，建议定期用它检查 `CLAUDE.md` 是否仍然和项目现状一致。

如果你已经安装了 `context7`，建议在查前后端框架、库和工具的最新官方用法时优先使用它，而不是依赖过期记忆。

如果你已经安装了 `code-review`，建议把它放在 PR 或合并前阶段使用，而不是替代项目内已有的 `frontend-review` / `backend-review`。

如果你已经安装了 `security-guidance`，建议把它作为编辑阶段的安全提醒层使用，帮助尽早发现前后端常见安全风险。

如果你已经安装了 `planning-with-files`，建议在复杂需求、长任务和跨前后端协作时用它来持久化计划和执行状态。
