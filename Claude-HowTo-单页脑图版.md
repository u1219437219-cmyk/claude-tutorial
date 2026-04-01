# Claude How-To 单页脑图版

```mermaid
mindmap
  root((Claude How-To))
    基础入口层
      01-slash-commands
        解决: 怎么触发 Claude
        关键词: /commands /skills /入口
      10-cli
        解决: 怎么运行 Claude
        关键词: 交互模式 Print 模式 CLI 管理
    长期协作层
      02-memory
        解决: 长期记住项目背景
        关键词: CLAUDE.md 项目规则 长期上下文
      03-skills
        解决: 复用高频任务
        关键词: 能力封装 工作流模板 标准做法
    复杂系统能力层
      04-subagents
        解决: 多 agent 分工
        关键词: reviewer debugger implementer
      05-mcp
        解决: 接外部工具和实时数据
        关键词: GitHub 数据库 Notion Slack
      06-hooks
        解决: 事件驱动自动化
        关键词: PreToolUse PostToolUse Stop
    工程化和高阶能力层
      07-plugins
        解决: 打包完整工作流
        关键词: commands agents hooks mcp scripts
      08-checkpoints
        解决: 安全试错和回退
        关键词: rewind 快照 恢复代码/对话
      09-advanced-features
        解决: 系统化使用 Claude Code
        关键词: plan thinking background permission worktree
    最推荐先学
      02-memory
      03-skills
      10-cli
    核心目标
      把 Claude 从聊天助手
      变成长期协作系统
```

## 一句话总结

- `01 + 10`：先会触发、会运行
- `02 + 03`：再让 Claude 稳定合作、复用经验
- `04 + 05 + 06`：再学分工、接工具、做自动化
- `07 + 08 + 09`：最后把能力打包、回退、系统化

## 最短学习路径

1. `10-cli`
2. `02-memory`
3. `03-skills`
4. `04-subagents`
5. `07-plugins`
6. `08-checkpoints`
7. `09-advanced-features`

## 最终目标

这个项目真正想教你的不是“Claude 有哪些功能”，而是：

- 怎么建立长期协作规则
- 怎么沉淀高频任务
- 怎么让 Claude 分工和接工具
- 怎么把工作流工程化
