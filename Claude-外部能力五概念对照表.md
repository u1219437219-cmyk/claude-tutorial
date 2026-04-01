# Claude 外部能力五概念对照表

## 文档目的

这份文档用来快速区分 5 个最容易混淆的概念：

- skill
- agent
- plugin
- MCP
- hook

目标不是讲很多定义，而是让你一眼看懂：

- 它是什么
- 它解决什么问题
- 它最像什么
- 什么时候该用

---

## 一、先记一句总口诀

**skill 管方法，agent 管角色，hook 管时机，MCP 管外部连接，plugin 管整套打包。**

---

## 二、五概念总对照表

| 概念 | 最简单理解 | 解决什么问题 | 最像什么 | 典型例子 |
|------|------------|--------------|----------|----------|
| `skill` | 一套固定工作方法 | 同类任务做法不稳定、重复讲规则 | SOP / 模板 | `review`、`bugfix`、`feature` |
| `agent` | 一个专门角色 | 复杂任务需要分工 | 团队岗位 | `implementer`、`reviewer`、`debugger` |
| `plugin` | 一整套工作流打包 | 零散能力太多，不好复用 | 工具包 / 整机 | PR review 插件、文档插件 |
| `MCP` | Claude 接外部系统的桥 | Claude 看不到外部世界 | 连接器 / 数据通道 | GitHub、数据库、Notion、日志平台 |
| `hook` | 某个时机自动触发动作 | 某一步总忘做、想自动提醒 | 守门员 / 自动提醒器 | 改完提醒总结、结束后提醒验证 |

---

## 三、逐个解释

## 1. Skill

### 最简单理解

一套固定工作方法。

### 它解决什么问题

- 同类任务反复出现
- 你不想每次重新教 Claude 怎么做
- 希望输出结构稳定

### 最像什么

- 模板
- SOP
- 标准工作方法

### 典型例子

- `review`
- `bugfix`
- `feature`
- `refactor`

### 一句话记忆

**skill = 这类任务应该怎么做**

---

## 2. Agent

### 最简单理解

一个专门角色。

### 它解决什么问题

- 一个 Claude 做所有事容易乱
- 复杂任务需要分工
- 想让“实现”和“审查”分开

### 最像什么

- 团队岗位
- 专项角色
- 子助手

### 典型例子

- `implementer`
- `reviewer`
- `debugger`

### 一句话记忆

**agent = 谁来做这件事**

---

## 3. Plugin

### 最简单理解

一整套工作流打包。

### 它解决什么问题

- 单个 skill / agent 太零散
- 某个流程已经成熟，想整体复用
- 想把 commands、agents、hooks、scripts 打成一包

### 最像什么

- 工具包
- 工作流产品
- 整机

### 典型例子

- PR review 插件
- 文档生成插件
- DevOps 自动化插件

### 一句话记忆

**plugin = 把多种能力打包成一整套**

---

## 4. MCP

### 最简单理解

Claude 和外部系统之间的桥。

### 它解决什么问题

- Claude 只看本地上下文，不知道外部世界
- 需要实时数据
- 需要查 GitHub、数据库、Notion、日志平台

### 最像什么

- 外部接口
- 连接器
- 数据通道

### 典型例子

- GitHub MCP
- 数据库 MCP
- Notion MCP
- 日志平台 MCP

### 一句话记忆

**MCP = 让 Claude 看见外部世界**

---

## 5. Hook

### 最简单理解

在某个时机自动触发的动作。

### 它解决什么问题

- 总忘某一步
- 想自动提醒
- 想在固定事件节点上插动作

### 最像什么

- 自动提醒器
- 守门员
- 事件触发器

### 典型例子

- 改完后提醒总结
- 改完后提醒说明验证
- 任务结束后提醒输出结论

### 一句话记忆

**hook = 在什么时候自动做动作**

---

## 四、最容易混淆的对比

## 1. skill vs agent

### skill

- 管方法
- 关注“怎么做”

### agent

- 管角色
- 关注“谁来做”

一句话：

- `skill` = 做法
- `agent` = 角色

---

## 2. skill vs plugin

### skill

- 一项能力

### plugin

- 一整套方案

一句话：

- `skill` 是零件
- `plugin` 是整机

---

## 3. MCP vs plugin

### MCP

- 连接外部系统

### plugin

- 打包工作流

一句话：

- `MCP` 负责“连出去”
- `plugin` 负责“装起来”

---

## 4. hook vs skill

### hook

- 在某个时机自动触发

### skill

- 规定整类任务怎么做

一句话：

- `hook` 管时机
- `skill` 管方法

---

## 五、用一个场景串起来

假设你在做一个 PR review 流程。

### skill

定义 review 应该看什么：

- 回归风险
- 测试缺口
- 边界情况

### agent

定义谁来做：

- `reviewer`
- `security-reviewer`
- `test-checker`

### plugin

把整个 review 流程打包：

- commands
- agents
- hooks
- 相关配置

### MCP

让 Claude 能读取：

- GitHub PR
- diff
- 评论

### hook

在 review 结束后自动提醒：

- 输出风险总结
- 标明残余风险

---

## 六、最推荐的理解顺序

如果你现在还容易混，建议按这个顺序学：

1. `skill`
2. `agent`
3. `hook`
4. `MCP`
5. `plugin`

原因：

- `skill` 最贴近日常使用
- `agent` 是下一层分工
- `hook` 是流程自动化
- `MCP` 是外部连接
- `plugin` 是整合打包

---

## 七、一句话最终总结

如果你只记一句，就记这个：

**skill 管方法，agent 管角色，hook 管时机，MCP 管外部连接，plugin 管整套打包。**
