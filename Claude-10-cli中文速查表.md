# Claude 10-cli 中文速查表

## 1. 最常用的启动方式

### 进入交互式会话

```bash
claude
```

适合：

- 多轮协作
- 看项目、改代码、持续推进任务

一句话：

进入主工作台。

### 带初始问题启动

```bash
claude "explain this project"
```

适合：

- 直接带着任务进入会话
- 快速开始某个分析主题

---

## 2. 单次执行模式

### Print 模式

```bash
claude -p "解释这个函数是做什么的"
```

或

```bash
claude --print "解释这个函数是做什么的"
```

适合：

- 单次问答
- 快速分析
- 脚本和自动化

一句话：

执行一次，输出结果，然后退出。

### 配合管道使用

```bash
cat error.log | claude -p "解释这个错误"
```

适合：

- 日志分析
- 文本总结
- 命令行流水线处理

---

## 3. 继续和恢复会话

### 继续最近一次会话

```bash
claude -c
```

或

```bash
claude --continue
```

适合：

- 接着上次工作继续

### 恢复指定会话

```bash
claude -r "auth-refactor"
```

或

```bash
claude --resume "auth-refactor"
```

适合：

- 精确回到某个项目或任务上下文

---

## 4. 模型和思考深度

### 指定模型

```bash
claude --model sonnet
claude --model opus
claude --model haiku
```

粗略理解：

- `haiku`：更快、更轻
- `sonnet`：平衡型
- `opus`：更强，适合复杂任务

### 指定思考深度

```bash
claude --effort low
claude --effort medium
claude --effort high
claude --effort max
```

适合：

- 架构设计
- 疑难 bug
- 多方案比较

一句话：

不是换任务，而是让 Claude 多想一会儿。

---

## 5. 权限和工具控制

### 使用计划模式

```bash
claude --permission-mode plan
```

适合：

- 多文件修改
- 高风险改动
- 老项目改造

一句话：

先计划，再执行。

### 限制可用工具

```bash
claude -p --tools "Read,Grep,Glob" "find all TODO comments"
```

适合：

- 只读分析
- 安全 review
- 不希望 Claude 动代码

### 允许特定工具

```bash
claude --allowedTools "Bash(git status:*)" "Bash(git log:*)"
```

适合：

- 明确放行某些安全命令

### 禁止某些工具

```bash
claude --disallowedTools "Bash(rm -rf:*)" "Edit"
```

适合：

- 限制危险操作

---

## 6. 排除环境干扰

### 裸模式

```bash
claude --bare
```

作用：

- 跳过 hooks
- 跳过 skills
- 跳过 plugins
- 跳过 MCP
- 跳过 auto memory
- 跳过 `CLAUDE.md`

适合：

- 排查是不是环境配置影响结果
- 做纯净对比测试

一句话：

把 Claude 放到最干净的状态下运行。

---

## 7. 管理系统组件

### 管理 MCP

```bash
claude mcp
```

适合：

- 查看和管理 MCP 服务

### 管理 agents

```bash
claude agents
```

适合：

- 查看和管理 subagents

### 管理 plugins

```bash
claude plugin
```

适合：

- 安装、启用、禁用插件

---

## 8. 输出格式和结构化结果

### 输出 JSON

```bash
claude -p --output-format json "list all functions in main.py"
```

适合：

- 自动化处理
- 给脚本消费输出

### 用 JSON Schema 约束输出

```bash
claude -p --json-schema '{"type":"object"}' "..."
```

适合：

- 结构化输出
- CI / 自动处理流程

一句话：

让 Claude 的输出更适合程序消费。

---

## 9. 真实开发里最常用的几种命令

### 日常开发

```bash
claude
```

用途：

- 看项目
- 改代码
- 多轮协作

### 快速单次分析

```bash
claude -p "解释这个报错"
```

用途：

- 单次问题分析

### 分析日志

```bash
cat logs.txt | claude -p "总结关键错误"
```

用途：

- 日志总结
- 问题归纳

### 高风险任务先计划

```bash
claude --permission-mode plan
```

用途：

- 复杂改动前先收敛方案

### 排查插件或技能干扰

```bash
claude --bare
```

用途：

- 验证是否是环境能力影响了行为

---

## 10. 最值得记住的命令

如果你只想记最核心的，记这几个：

```bash
claude
claude -p "..."
claude -c
claude -r "session-name"
claude --model opus
claude --effort high
claude --permission-mode plan
claude --bare
claude mcp
claude agents
claude plugin
claude -p --output-format json "..."
```

---

## 11. 一句话总结

- `claude`：长期协作
- `claude -p`：单次执行
- `-c / -r`：恢复上下文
- `--model / --effort`：调思考能力
- `--permission-mode`：控行动边界
- `--bare`：排除环境干扰
- `mcp / agents / plugin`：管理系统组件
- `json / schema`：接自动化
