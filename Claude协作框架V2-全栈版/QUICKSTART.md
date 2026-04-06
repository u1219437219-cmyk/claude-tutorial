# 全栈版快速上手

这份文档只回答 4 个问题：

1. 先复制哪些文件
2. 先改哪些内容
3. 第一次怎么让 Claude 开始工作
4. 遇到不同任务时该用哪个 skill / plugin

## 5 分钟上手

如果你要把这套模板放进一个前后端分离、同仓协作的项目，先做这几步：

1. 复制 [CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md)
2. 复制整个 [.claude](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/.claude)
3. 打开 [CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md)，先把占位项填掉
4. 先不要急着加太多插件，优先把基础协作链路跑顺

## 先改哪些内容

最先改的是这些：

1. 项目目标
2. 前端目录 / 后端目录 / 公共目录
3. 前后端技术栈
4. 常用命令
5. 你项目里最重要的风险点

至少把这些位置补完整：

- [CLAUDE.md:3](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md#L3)
- [CLAUDE.md:9](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md#L9)
- [CLAUDE.md:19](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md#L19)
- [CLAUDE.md:40](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md#L40)

## 第一次怎么开口

如果是新项目，直接这样说：

```text
按全栈模板 + superpowers 的方式来做。先别写代码，先帮我理解项目结构、拆前后端边界、确认方案，再给执行计划。
```

如果是老项目接手，直接这样说：

```text
这是一个老的全栈项目。先按项目里的全栈规则理解目录、前后端边界和现有模式，不要急着重构；先分析影响范围，再决定怎么改。
```

如果是跨前后端功能，直接这样说：

```text
这是一个跨前后端需求。先拆成前端部分、后端部分和联动风险，再给最小可行方案；需要的话把计划落到文件里。
```

如果是新项目、长任务或高风险任务，最好顺手加一句：

```text
除了计划文件，再帮我沉淀必要的产出物，比如规划文档、接口说明或前端交互说明，避免关键信息只留在聊天记录里。
```

## 任务路由表

| 任务类型 | 先用什么 | 再用什么 | 最后补什么 |
| --- | --- | --- | --- |
| 页面视觉升级 | `frontend-design` | `frontend-feature` | `webapp-testing` |
| 普通前端功能 | `frontend-feature` | `frontend-review` | `webapp-testing` |
| 后端接口 / 服务逻辑 | `backend-feature` | `backend-review` | `code-review` |
| 前端 bug | `frontend-bugfix` | `frontend-review` | `webapp-testing` |
| 后端 bug | `backend-bugfix` | `backend-review` | `code-review` |
| 跨前后端需求 | `superpowers` 或项目规则先拆边界 | `frontend-feature` + `backend-feature` | `webapp-testing` + `code-review` |
| 长任务 / 多阶段任务 | `superpowers` | `planning-with-files` | 项目内 review / `code-review` |
| PR / 合并前复查 | 项目内 `frontend-review` / `backend-review` | `security-guidance` 已发现问题先修 | `code-review` |

## 推荐最小组合

如果你不想一开始装太多东西，最小可用组合是：

1. 项目内 [CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md)
2. 项目内 `.claude/skills/frontend-feature`
3. 项目内 `.claude/skills/backend-feature`
4. 项目内 `.claude/skills/frontend-review`
5. 项目内 `.claude/skills/backend-review`

如果你愿意再往上加一层，最推荐的增强是：

1. `superpowers`
2. `planning-with-files`
3. `context7`
4. `code-review`
5. `security-guidance`
6. `webapp-testing`

## 不确定时怎么选

记一个最简单的原则：

- 不知道怎么推进：先用 `superpowers`
- 不知道怎么拆阶段：加 `planning-with-files`
- 不知道框架当前写法：先用 `context7`
- 不知道页面有没有真的跑通：用 `webapp-testing`
- 不知道改完有没有回归风险：先项目内 review，再 `code-review`

## 继续往下看什么

需要总览时，看：
- [README.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/README.md)

需要项目规则时，看：
- [CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md)

需要插件说明时，看：
- [PLUGIN_GUIDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/PLUGIN_GUIDE.md)

需要 skill 说明时，看：
- [SKILL_GUIDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/SKILL_GUIDE.md)

需要技术栈扩展思路时，看：
- [STACK_EXTENSION_GUIDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/STACK_EXTENSION_GUIDE.md)
