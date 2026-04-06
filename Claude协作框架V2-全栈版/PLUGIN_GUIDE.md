# 全栈版插件选型与使用说明

这份文档说明：

1. 哪些插件建议纳入这套全栈模板
2. 哪些插件建议保留安装但不要写进模板默认规则
3. 每个插件在实际协作里该怎么用

## 建议纳入模板

这些插件和“一个仓库、前后端分离、需要跨边协作”的全栈项目高度匹配，适合写进项目规则层。

### superpowers

定位：
- 流程层

适合场景：
- 新功能设计
- 复杂需求拆分
- 跨前后端需求澄清
- 计划制定
- review 和执行流程控制

怎么用：
- 直接说 `按 superpowers 的流程来做`
- 直接说 `先 brainstorm，再出 plan`
- 直接说 `这个需求先不要写代码，先拆方案`

推荐搭配：
- 和 `planning-with-files` 搭配，用它管流程，再把计划落文件
- 和项目内 `frontend-feature` / `backend-feature` 搭配，用它定方法，再按前后端分边实现

### planning-with-files

定位：
- 计划持久化层

适合场景：
- 长任务
- 多阶段任务
- 跨前后端联动需求
- 多次会话推进
- 做到一半可能中断、需要恢复上下文的任务

怎么用：
- 直接说 `这个任务先用 planning-with-files 建计划文件`
- 直接说 `把这个跨前后端任务拆成计划并持续更新状态`
- 直接用它提供的 `/plan`、`/plan:status` 之类命令

推荐搭配：
- 和 `superpowers` 搭配，`superpowers` 负责流程，`planning-with-files` 负责计划落地

### superpowers 和 planning-with-files 怎么更好地结合

最简单的分工是：

- `superpowers` 负责想清楚事情怎么做
- `planning-with-files` 负责把想清楚的东西存下来并持续维护

可以把它们理解成：

1. `superpowers` 决定方法
2. `planning-with-files` 决定载体

最推荐的结合方式：

1. 先用 `superpowers` 做需求澄清、方案比较、边界拆分
2. 方案清楚后，立即用 `planning-with-files` 建计划文件
3. 后续实现过程中持续更新计划状态，而不是只靠聊天记录
4. 任务跨多轮会话时，优先回到计划文件继续推进

什么时候只用 `superpowers`：

- 任务很小
- 一轮对话内就能完成
- 不需要跨会话恢复

什么时候一定加上 `planning-with-files`：

- 需求复杂
- 前后端都要改
- 预计会拆多个阶段
- 需要中断后恢复
- 需要长期跟踪待办和状态

一套比较稳的串联方式：

1. `按 superpowers 的流程先拆方案`
2. `把确认后的方案用 planning-with-files 落成计划`
3. `按计划逐步执行，并在每一步后更新状态`
4. `下次继续时先回读计划文件，不从聊天记录重新猜上下文`

适合直接复制的组合提示词：

```text
这个任务按 superpowers + planning-with-files 一起做。先用 superpowers 帮我澄清需求、拆前后端边界、比较方案；方案确认后，立即用 planning-with-files 把计划持久化到文件里，并在后续实现过程中持续更新状态。后面每次继续这个任务时，先从计划文件恢复上下文。
```

如果是跨前后端长任务，推荐这样说：

```text
这是一个跨前后端长任务。先按 superpowers 拆成前端部分、后端部分和联动风险，再用 planning-with-files 生成可持续更新的计划。实现时按计划逐项推进，每完成一项就更新状态，不要只靠会话上下文记忆。
```

### claude-md-management

定位：
- `CLAUDE.md` 维护层

适合场景：
- 项目规则变了
- 目录结构变了
- 常用命令变了
- 技术栈变了
- 你发现 Claude 总是遗漏同一类上下文

怎么用：
- 用 `claude-md-improver` 审计当前 `CLAUDE.md`
- 用 `/revise-claude-md` 把本次协作里暴露出的缺失信息补进去

推荐搭配：
- 和当前项目的 [CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md) 配合使用

### context7

定位：
- 官方文档检索层

适合场景：
- 查前端框架文档
- 查后端框架文档
- 查 ORM、状态管理、构建工具、测试工具文档
- 查某个库当前版本的 API 或配置方式

怎么用：
- 直接说 `用 context7 查一下这个库当前版本的官方用法`
- 直接说 `先查 Next.js 官方文档再改`
- 直接说 `先确认 Prisma 这个 API 的最新写法`

推荐搭配：
- 和 `frontend-feature` / `backend-feature` 搭配，在实现前先查准版本用法

### code-review

定位：
- PR 自动复查层

适合场景：
- PR 前复查
- 合并前复查
- 改动较大，想再补一轮自动化审查

怎么用：
- 直接用 `/code-review`
- 或直接说 `在 PR 前跑一轮 code-review`

注意：
- 它不替代项目内已有的 `frontend-review` / `backend-review`
- 最好的用法是：先按项目内 review 口径自检，再用 `code-review` 做 PR 阶段复查

### security-guidance

定位：
- 编辑期安全提醒层

适合场景：
- 前端输入处理
- 富文本、HTML 渲染
- 后端命令执行
- SQL/命令/模板拼接
- 权限和输入校验

怎么用：
- 它更多是被动生效的 hook 型提醒
- 实际协作里就是：看到它的安全提示时，优先处理，不要拖到 PR 前

注意：
- 它不替代业务 review
- 它更适合作为“尽早发现明显安全风险”的第一层

### frontend-design

定位：
- 前端视觉设计层

适合场景：
- 页面改版
- 仪表盘美化
- 落地页
- 设计语言升级
- 视觉风格强化

怎么用：
- 直接说 `前端部分优先按 frontend-design 来做`
- 直接说 `这个页面先做设计方向，不要直接按普通功能页写`

推荐搭配：
- 和 `frontend-feature` 搭配
- 常见组合是：先 `frontend-design` 定视觉方向，再 `frontend-feature` 落地功能

### context7、security-guidance 和 code-review 怎么更好地结合

这三个插件最适合串成一条实现到合并前的链路：

1. `context7` 负责先查准官方用法
2. `security-guidance` 负责在实现过程中尽早提醒安全问题
3. `code-review` 负责在 PR 或合并前补一轮自动化复查

可以把它们理解成：

- `context7` 管“先别写错”
- `security-guidance` 管“写的时候别留下明显安全坑”
- `code-review` 管“合并前再整体查一遍”

最推荐的结合方式：

1. 改框架、库、配置或版本相关逻辑前，先用 `context7` 查最新官方文档
2. 开始实现后，优先处理 `security-guidance` 给出的实时安全提醒
3. 实现完成后，先按项目内 review 口径自检
4. PR 或合并前，再补一轮 `code-review`

什么时候特别应该这样用：

- 改鉴权、权限、表单、上传、富文本、HTML 渲染
- 改接口契约、输入校验、数据库读写、命令执行
- 改框架升级后的配置和 API

一套比较稳的串联方式：

1. `先用 context7 查官方用法`
2. `按项目规则实现`
3. `实现时优先处理 security-guidance 的安全提醒`
4. `合并前先自检，再跑 code-review`

适合直接复制的组合提示词：

```text
这个改动先用 context7 查一下当前版本的官方用法，再按项目规则实现。实现过程中如果 security-guidance 有安全提醒，优先处理。改完后先按项目内 review 口径自检，PR 前再补一轮 code-review。
```

如果是安全敏感改动，推荐这样说：

```text
这个改动涉及输入处理/权限/接口安全。先用 context7 确认当前框架和库的官方安全用法，再实现。实现过程中优先处理 security-guidance 的提醒，最后在合并前补一轮 code-review。
```

### claude-md-management、superpowers 和 planning-with-files 怎么更好地结合

这三个更适合组成“长期项目演进链路”：

1. `superpowers` 负责把需求、方案和执行路径想清楚
2. `planning-with-files` 负责把计划持续保存下来
3. `claude-md-management` 负责把长期有效的项目经验沉淀进 `CLAUDE.md`

可以把它们理解成：

- `superpowers` 管一次任务怎么推进
- `planning-with-files` 管这次任务如何跨阶段持续推进
- `claude-md-management` 管这次任务里沉淀出的长期规则怎么留下来

最推荐的结合方式：

1. 新需求开始时，先按 `superpowers` 澄清需求、拆方案、定路径
2. 方案成型后，用 `planning-with-files` 建立和维护计划文件
3. 任务推进中，如果发现项目规则、目录约定、命令、协作方式已经和 `CLAUDE.md` 不一致，先记下来
4. 任务结束后，用 `claude-md-improver` 或 `/revise-claude-md` 把值得长期保留的经验沉淀进 `CLAUDE.md`

什么时候特别适合这样用：

- 项目还在快速演进
- 团队协作规则不断成熟
- 前后端目录和命令经常调整
- 你希望 Claude 后面越来越懂这个项目，而不是每次都重新解释

一套比较稳的串联方式：

1. `先按 superpowers 把任务想清楚`
2. `用 planning-with-files 把任务计划持续化`
3. `任务结束后审视这次有没有形成新的项目规则`
4. `如果有，就用 claude-md-management 更新 CLAUDE.md`

适合直接复制的组合提示词：

```text
这个任务按 superpowers + planning-with-files + claude-md-management 的方式来做。先用 superpowers 拆清需求、边界和方案，再用 planning-with-files 把计划持久化并持续更新状态。任务结束后，如果这次形成了新的目录约定、命令、协作规则或长期有效经验，再用 claude-md-management 审计并更新 CLAUDE.md。
```

如果是老项目持续演进，推荐这样说：

```text
这是一个会持续演进的老项目。先按 superpowers 明确这次任务的方案，再用 planning-with-files 管理执行过程。如果这次改动让现有 CLAUDE.md 过时了，最后用 claude-md-management 把新的项目规则沉淀下来。
```

## 建议保留安装，但不要写进模板默认规则

这些插件有价值，但不适合放进“通用全栈模板”的默认规则层。

### commit-commands

定位：
- Git 操作自动化

为什么不写进模板：
- 更偏个人 Git 工作流
- 不是项目协作规则本身

怎么用：
- `/commit`
- `/commit-push-pr`
- `/clean_gone`

### code-simplifier

定位：
- 代码简化/整理层

为什么不写进模板：
- 有用，但优先级低于流程、review、文档、安全这些基础设施

怎么用：
- 在你明确要“保行为不变地降低复杂度”时使用
- 比如说：`帮我简化这段实现，但不要改行为`

### skill-creator

定位：
- skill 维护层

为什么不写进模板：
- 更适合维护这套模板的人
- 不是日常业务开发的默认能力

怎么用：
- 你要新建 skill、改现有 skill、跑 skill 评测时再用

### claude-mem

定位：
- 动态跨会话记忆层

为什么不写进模板：
- 属于个人环境增强能力
- 会影响整体上下文体验，不适合作为项目默认要求

怎么用：
- 更适合你个人长期维护同一个复杂项目时使用

### pyright-lsp

定位：
- Python 静态分析层

为什么不写进模板：
- 只适合 Python 后端
- 不适合当前这份通用全栈模板

怎么用：
- 如果后端是 Python，就让它作为日常类型和诊断支持

## 当前不建议纳入这套模板

### feature-dev

原因：
- 和 `superpowers + frontend-feature/backend-feature` 的重叠很大
- 容易让 feature 开发流程打架

### ralph-loop

原因：
- 更像实验性循环执行模式
- 侵入性强
- 不适合作为默认项目规则

## 推荐使用顺序

### 做复杂新功能

1. 用 `superpowers` 做澄清和方案
2. 用 `planning-with-files` 落计划
3. 前端部分走 `frontend-feature` 或 `frontend-design`
4. 后端部分走 `backend-feature`
5. 需要查库文档时用 `context7`
6. PR 前补 `code-review`

### 修 bug

1. 先按项目内 `frontend-bugfix` / `backend-bugfix` 分边定位
2. 改动过程中接受 `security-guidance` 的安全提醒
3. 涉及框架或库行为时用 `context7`
4. 合并前补 `code-review`

### 维护项目规则

1. 改完目录、命令、技术栈、协作方式后
2. 用 `claude-md-improver` 检查 `CLAUDE.md`
3. 必要时用 `/revise-claude-md` 更新项目记忆

## 新项目怎么用

新项目更推荐：

- `superpowers` 主导流程
- `planning-with-files` 管计划落地
- 项目内全栈 skill 负责前后端分边实现

推荐顺序：

1. 先用 `superpowers` 做需求澄清和方案比较
2. 再用 `planning-with-files` 建计划文件
3. 前端部分按 `frontend-feature` 或 `frontend-design` 推进
4. 后端部分按 `backend-feature` 推进
5. 查框架和库的官方资料时优先用 `context7`
6. 改动过程中接受 `security-guidance` 的安全提醒
7. PR 前用项目内 review 口径自检，再补一轮 `code-review`

适合直接复制的提示词：

```text
按 superpowers + 全栈模板的方式来做这个新项目。先不要写代码，先帮我澄清需求、拆前后端边界、比较 2-3 个方案，然后输出计划。计划请用 planning-with-files 持久化。前端功能走 frontend-feature，页面视觉升级走 frontend-design，后端功能走 backend-feature。
```

## 老项目怎么用

老项目更推荐：

- 项目内全栈模板先主导边界和风险控制
- `superpowers` 作为复杂任务的流程增强
- `planning-with-files` 用于长任务和多次会话推进

推荐顺序：

1. 先按项目内规则理解现有目录、调用链和前后端边界
2. 中小需求直接按 `frontend-feature` / `backend-feature` 或 `frontend-bugfix` / `backend-bugfix` 推进
3. 复杂需求再引入 `superpowers` 做设计和计划
4. 长任务和跨会话任务用 `planning-with-files` 保持计划状态
5. 需要查当前版本框架用法时用 `context7`
6. 改动过程中接受 `security-guidance` 的安全提醒
7. 合并前先按项目内 review 口径自检，再补 `code-review`

适合直接复制的提示词：

```text
这是一个老的全栈项目。先按项目里的全栈规则理解现有结构、前后端边界和已有模式，不要急着写代码或重构。中小改动直接按最小修改推进；如果需求复杂，再按 superpowers 做方案和计划。这个任务如果跨度较大，请用 planning-with-files 持久化计划。
```

## 常用提示词模板

### 跨前后端新功能

```text
这是一个跨前后端需求。按 superpowers 先拆边界和方案，再用 planning-with-files 固化计划。前端按 frontend-feature 推进，后端按 backend-feature 推进；如果涉及页面视觉升级，前端优先参考 frontend-design。
```

### 前端页面改版

```text
这个任务重点是页面视觉和体验升级。前端优先按 frontend-design 来做，先明确设计方向，再落具体实现；如果涉及复杂功能联动，再补 frontend-feature 的实现节奏。
```

### 老项目修 bug

```text
这是老项目里的一个 bug。先按项目规则定位根因，区分前端问题、后端问题还是联动问题，不要急着改代码。需要的话再按 superpowers 的调试流程推进；如果任务会跨多轮会话，请用 planning-with-files 记录排查计划。
```

### 合并前复查

```text
这个改动准备合并。先按项目内 frontend-review / backend-review 口径自检，再补一轮 code-review。实现过程中如果有安全提醒，先处理 security-guidance 提示的问题。
```

## 一句话总结

这套全栈模板最推荐的组合是：

- `superpowers` 管流程
- `planning-with-files` 管计划
- `claude-md-management` 管项目规则维护
- `context7` 管官方文档
- `code-review` 管 PR 复查
- `security-guidance` 管安全提醒
- `frontend-design` 管前端视觉设计
- 项目内 `.claude/skills` 和 `.claude/agents` 管前后端边界和具体执行

## 推荐安装清单

### 最低配

如果你只想先把这套全栈模板跑起来，最低配建议安装：

- `superpowers`
- `context7`
- `code-review`
- `security-guidance`

适合：
- 希望先把流程、文档查询、PR 复查和安全提醒跑顺
- 不想一开始就把体系搭得太复杂

### 推荐配

如果你准备长期用这套全栈模板，推荐安装：

- `superpowers`
- `planning-with-files`
- `claude-md-management`
- `context7`
- `code-review`
- `security-guidance`
- `frontend-design`

适合：
- 一个仓库内前后端长期协作
- 任务经常跨前后端
- 需要多阶段推进和计划恢复
- 希望前端页面也有明确的视觉设计能力

### 按需选装

这些按项目类型或个人工作流决定：

- `pyright-lsp`
  适合 Python 后端

- `commit-commands`
  适合希望把提交、推送、建 PR 自动化的人

- `code-simplifier`
  适合经常做小范围整理和历史代码清理的人

- `skill-creator`
  适合持续维护和扩展这套 `.claude/skills` 的人

- `claude-mem`
  适合个人长期维护复杂项目、希望跨会话记忆更强的人

### 当前不建议默认加入

- `feature-dev`
- `ralph-loop`

原因：
- 前者和现有 feature 流程重叠过大
- 后者更像实验性执行模式，不适合作为默认规则
