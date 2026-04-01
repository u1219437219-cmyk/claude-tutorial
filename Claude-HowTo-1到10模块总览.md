# Claude How-To 1-10 模块总览

## 文档目的

这份文档用于总结 `claude-howto` 项目中 `01` 到 `10` 这十个核心模块的结构、定位和作用，方便快速建立整体认知。

这个仓库不是传统业务应用，而是一套围绕 Claude Code 的教程型知识库。它的核心目标是教你如何把 Claude Code 从一个聊天助手，逐步用成一个有规则、有记忆、有分工、有自动化能力的开发工作系统。

---

## 一、整体主线

你可以把整个项目理解成 4 层：

### 1. 基础入口层

- `01-slash-commands`
- `10-cli`

解决的问题：

- 怎么触发 Claude
- 怎么运行 Claude
- 怎么从交互式使用走向命令行和脚本化使用

### 2. 长期协作层

- `02-memory`
- `03-skills`

解决的问题：

- 怎么让 Claude 长期记住项目背景
- 怎么把高频工作流沉淀下来
- 怎么减少重复解释、提高协作稳定性

### 3. 复杂系统能力层

- `04-subagents`
- `05-mcp`
- `06-hooks`

解决的问题：

- 怎么让不同 agent 分工协作
- 怎么接入外部工具和实时数据
- 怎么通过事件触发自动化

### 4. 工程化和高阶能力层

- `07-plugins`
- `08-checkpoints`
- `09-advanced-features`

解决的问题：

- 怎么把工作流打包
- 怎么安全试错和回退
- 怎么系统化地使用 Claude Code

---

## 二、1-10 模块逐个说明

## 01. Slash Commands

目录：

- `01-slash-commands`

核心定位：

Slash Commands 是 Claude Code 的基础入口层。

主要解决：

- 用户如何触发 Claude 的各种能力
- 内置命令、自定义命令、skill 命令、plugin 命令之间是什么关系

你可以理解为：

- `/xxx` 是你对 Claude 发起能力调用的统一入口

一句话总结：

`01-slash-commands` 解决“怎么触发”。

---

## 02. Memory

目录：

- `02-memory`

核心定位：

Memory 负责长期上下文。

主要解决：

- Claude 怎么长期记住项目背景
- 怎么减少重复介绍项目结构、命令、规则
- `CLAUDE.md` 里应该写什么

你可以理解为：

- `CLAUDE.md` 是给 Claude 看的项目长期说明书

一句话总结：

`02-memory` 解决“Claude 长期需要记住什么”。

---

## 03. Skills

目录：

- `03-skills`

核心定位：

Skills 是高频任务的能力封装。

主要解决：

- 某类工作怎么标准化
- 高频任务怎么复用
- 怎么把经验沉淀为 Claude 可重复调用的能力

典型场景：

- 代码审查
- bug 排查
- 文档生成
- 功能实现

你可以理解为：

- `skill` 不是普通 prompt，而是一套可复用的任务模板

一句话总结：

`03-skills` 解决“某类任务应该怎么做”。

---

## 04. Subagents

目录：

- `04-subagents`

核心定位：

Subagents 是多 agent 分工协作机制。

主要解决：

- 一个复杂任务怎么拆给多个角色
- 不同 agent 各自负责什么
- 如何避免主会话上下文被复杂任务污染

你可以理解为：

- 主 agent 像项目负责人
- subagents 像专项角色，例如 reviewer、debugger、writer

一句话总结：

`04-subagents` 解决“复杂任务怎么分工”。

---

## 05. MCP

目录：

- `05-mcp`

核心定位：

MCP 是 Claude 接外部世界的桥。

主要解决：

- Claude 怎么访问外部服务
- 怎么连接 GitHub、数据库、Notion、Slack 等系统
- 实时数据和外部工具怎么接入 Claude

你可以理解为：

- Memory 偏静态上下文
- MCP 偏动态能力接入

一句话总结：

`05-mcp` 解决“Claude 怎么接外部工具和实时数据”。

---

## 06. Hooks

目录：

- `06-hooks`

核心定位：

Hooks 是事件驱动自动化机制。

主要解决：

- Claude 在动作前后怎么自动执行额外逻辑
- 怎么做预检查、后验证、自动收尾

典型用途：

- 改完代码自动提醒验证
- 执行前做安全检查
- 任务结束时自动总结

一句话总结：

`06-hooks` 解决“Claude 怎么自动化执行固定动作”。

---

## 07. Plugins

目录：

- `07-plugins`

核心定位：

Plugins 是整套工作流的打包方式。

主要解决：

- 如何把 commands、agents、hooks、mcp、scripts 等组合成完整方案
- 如何把单个能力模块上升为可复用的工作系统

你可以理解为：

- `skill` 是能力模块
- `plugin` 是整套工作流打包

一句话总结：

`07-plugins` 解决“怎么打包完整工作流”。

---

## 08. Checkpoints

目录：

- `08-checkpoints`

核心定位：

Checkpoints 是会话快照和回退机制。

主要解决：

- Claude 改代码时怎么安全试错
- 试一种方案不满意后怎么回退
- 如何保留思路同时压缩上下文

你可以理解为：

- Checkpoint 是会话级安全网
- 不是 Git 替代品

一句话总结：

`08-checkpoints` 解决“怎么安全试错和回退”。

---

## 09. Advanced Features

目录：

- `09-advanced-features`

核心定位：

Advanced Features 是 Claude Code 的系统能力层。

主要解决：

- Planning Mode
- Extended Thinking
- Background Tasks
- Scheduled Tasks
- Permission Modes
- Sandboxing
- Worktrees
- Remote / Desktop / Web Sessions

你可以理解为：

- 这部分不是单点功能，而是在讲 Claude Code 如何成为一个更完整的工作系统

一句话总结：

`09-advanced-features` 解决“怎么系统化地使用 Claude Code”。

---

## 10. CLI

目录：

- `10-cli`

核心定位：

CLI 是 Claude Code 的命令行入口和系统管理入口。

主要解决：

- Claude 怎么启动
- 交互模式和 print 模式怎么用
- 怎么控制模型、权限、工具、输出格式
- 怎么管理 MCP、agents、plugins、session

你可以理解为：

- Claude Code 不只是聊天窗口，也是一个命令行工作系统

一句话总结：

`10-cli` 解决“怎么运行 Claude，以及怎么从终端管理整个系统”。

---

## 三、模块之间的关系

可以用下面这条链路来理解这十个模块：

1. `01-slash-commands`
   先学会怎么触发 Claude

2. `10-cli`
   再学会怎么从终端运行和管理 Claude

3. `02-memory`
   让 Claude 长期记住项目

4. `03-skills`
   把高频任务封装成能力

5. `04-subagents`
   让 Claude 学会分工协作

6. `05-mcp`
   让 Claude 接入外部工具和实时数据

7. `06-hooks`
   让 Claude 在事件节点上自动执行动作

8. `07-plugins`
   把前面的能力打包成完整工作流

9. `08-checkpoints`
   给试错和探索提供安全网

10. `09-advanced-features`
    让 Claude Code 进入更系统化的使用阶段

---

## 四、如果只想抓最重要的模块

如果你的目标不是“全读完”，而是“尽快会用”，最值得优先掌握的是：

### 第一优先级

- `02-memory`
- `03-skills`
- `10-cli`

原因：

- 直接影响日常使用
- 最容易迁移到自己的项目里

### 第二优先级

- `04-subagents`
- `07-plugins`
- `08-checkpoints`

原因：

- 能显著提高复杂任务处理能力

### 第三优先级

- `05-mcp`
- `06-hooks`
- `09-advanced-features`

原因：

- 更偏系统扩展和工程化，后续按需深入

---

## 五、这个项目真正想教你的是什么

这个仓库真正想教你的不是“Claude 有哪些功能”，而是：

1. 如何把 Claude 从聊天助手变成长期协作搭档
2. 如何把经验固化成规则和模板
3. 如何让 Claude 接入工具、分工协作、自动执行
4. 如何把这些能力工程化和系统化

一句话总结：

这个项目是在教你如何把 Claude Code 变成一个真正可持续使用的开发工作系统。
