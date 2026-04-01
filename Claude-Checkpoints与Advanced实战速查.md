# Claude Checkpoints 与 Advanced Features 实战速查

## 文档目的

这份文档补的是两块容易“知道概念，但不太会用”的内容：

- Checkpoints
- Advanced Features

重点不是定义，而是：

**实际开发里什么时候该开、怎么开、为什么开。**

---

## 一、Checkpoints 最该怎么用

### 它最适合什么场景

- 大改动前留后路
- 想比较两种实现方案
- 重构时怕把现有逻辑改坏
- Claude 跑偏后想迅速回退

### 最推荐的用法

在这些任务前，优先把 checkpoint 当成安全网：

- 重构
- 多文件修改
- 风险高的结构调整
- 尝试不同方案

一句话：

**不确定这轮改动会不会顺时，先把 checkpoint 当保险。**

---

## 二、Advanced Features 最该怎么用

### 1. Planning Mode

什么时候开：

- 复杂需求
- 多文件改动
- 老项目高风险改造

一句话：

先计划，再实现。

### 2. Extended Thinking

什么时候开：

- 疑难 bug
- 架构取舍
- 边界情况复杂

一句话：

让 Claude 多想一会儿再回答。

### 3. Background Tasks

什么时候开：

- 长耗时分析
- 批量扫描
- 不想阻塞当前对话

一句话：

能后台跑的活，不要卡住主线程。

### 4. Permission Modes

什么时候调：

- 高风险任务先保守
- 简单明确任务可以更自动

一句话：

权限模式决定 Claude 的行动自由度。

### 5. Worktrees

什么时候用：

- 并行尝试不同方案
- 不想污染当前工作目录

一句话：

worktree 是项目级隔离实验室。

---

## 三、最推荐的组合

### 复杂需求

- `Planning Mode`
- `Checkpoints`

### 疑难 bug

- `Extended Thinking`
- `Checkpoints`

### 长时间分析

- `Background Tasks`

### 多方案尝试

- `Checkpoints`
- `Worktrees`

---

## 四、实战建议

如果你不知道该不该开这些能力，可以先按下面这个简单规则：

- 不确定需求：开 `Planning`
- 不确定原因：开 `Thinking`
- 不确定结果：用 `Checkpoints`
- 不确定会不会弄乱环境：用 `Worktree`
- 不想卡当前会话：用 `Background`

---

## 五、一句话总结

`Checkpoints` 和 `Advanced Features` 真正的价值，不是“高级”，而是：

**让 Claude 在复杂任务里更稳、更安全、更可控。**
