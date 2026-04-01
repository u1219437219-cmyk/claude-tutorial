# Claude How-To 最值得抄的样例文件清单

## 使用建议

这份清单只列“最值得直接借鉴”的样例，不追求覆盖全部文件。优先顺序按“最容易迁移到你自己的项目里”排序。

---

## 第一优先级：最该先抄

### 1. `03-skills/code-review/SKILL.md`

路径：
[03-skills/code-review/SKILL.md](/Users/lfs/Desktop/apple-app/claude-howto-main/03-skills/code-review/SKILL.md)

为什么值得抄：

- 结构简单
- 场景高频
- 很适合改造成自己的 review skill

建议怎么抄：

- 保留触发描述结构
- 保留审查维度
- 改成你自己的项目 review 口径

适合改造成：

- `review`
- `frontend-review`
- `backend-review`

### 2. `04-subagents/code-reviewer.md`

路径：
[04-subagents/code-reviewer.md](/Users/lfs/Desktop/apple-app/claude-howto-main/04-subagents/code-reviewer.md)

为什么值得抄：

- 最适合理解 subagent 长什么样
- 可以直接变成你项目里的 reviewer agent

建议怎么抄：

- 保留角色定义方式
- 按你项目特点收窄职责

### 3. `04-subagents/debugger.md`

路径：
[04-subagents/debugger.md](/Users/lfs/Desktop/apple-app/claude-howto-main/04-subagents/debugger.md)

为什么值得抄：

- bug 排查是高频场景
- 很适合做成项目常驻 agent

建议怎么抄：

- 明确它优先做“定位根因”而不是直接修

### 4. `02-memory/project-CLAUDE.md`

路径：
[02-memory/project-CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-howto-main/02-memory/project-CLAUDE.md)

为什么值得抄：

- 这是你未来最常用的资产之一
- 直接影响 Claude 的长期稳定性

建议怎么抄：

- 不要照搬内容
- 重点抄“应该写哪些栏目”

### 5. `10-cli/README.md`

路径：
[10-cli/README.md](/Users/lfs/Desktop/apple-app/claude-howto-main/10-cli/README.md)

为什么值得抄：

- 不是复制文件，而是复制“命令使用方式”
- 对日常使用价值最高

建议怎么抄：

- 从里面提炼自己的常用命令清单

---

## 第二优先级：复杂任务时很值

### 6. `04-subagents/implementation-agent.md`

路径：
[04-subagents/implementation-agent.md](/Users/lfs/Desktop/apple-app/claude-howto-main/04-subagents/implementation-agent.md)

为什么值得抄：

- 适合做功能开发 agent
- 和 reviewer/debugger 很互补

### 7. `07-plugins/pr-review/commands/review-pr.md`

路径：
[07-plugins/pr-review/commands/review-pr.md](/Users/lfs/Desktop/apple-app/claude-howto-main/07-plugins/pr-review/commands/review-pr.md)

为什么值得抄：

- 适合理解“工作流入口命令”怎么写
- 能帮你把 review 流程做得更完整

### 8. `07-plugins/pr-review/agents/security-reviewer.md`

路径：
[07-plugins/pr-review/agents/security-reviewer.md](/Users/lfs/Desktop/apple-app/claude-howto-main/07-plugins/pr-review/agents/security-reviewer.md)

为什么值得抄：

- 适合做专项 reviewer
- 能帮你理解 plugin 里的 agent 怎么组织

### 9. `07-plugins/pr-review/.claude-plugin/plugin.json`

路径：
[07-plugins/pr-review/.claude-plugin/plugin.json](/Users/lfs/Desktop/apple-app/claude-howto-main/07-plugins/pr-review/.claude-plugin/plugin.json)

为什么值得抄：

- 最适合理解 plugin 的最小入口长什么样

### 10. `08-checkpoints/README.md`

路径：
[08-checkpoints/README.md](/Users/lfs/Desktop/apple-app/claude-howto-main/08-checkpoints/README.md)

为什么值得抄：

- 不是抄文件内容
- 是抄“安全试错流程”

建议怎么抄：

- 形成自己的高风险任务协作口径

---

## 第三优先级：流程成熟后再看

### 11. `06-hooks/README.md`

路径：
[06-hooks/README.md](/Users/lfs/Desktop/apple-app/claude-howto-main/06-hooks/README.md)

为什么值得抄：

- 当你发现“总忘记做某一步”时很有价值

### 12. `05-mcp/README.md`

路径：
[05-mcp/README.md](/Users/lfs/Desktop/apple-app/claude-howto-main/05-mcp/README.md)

为什么值得抄：

- 当你要接 GitHub、数据库、Notion 等外部系统时再深入

### 13. `07-plugins/documentation/*`

路径：
[07-plugins/documentation/README.md](/Users/lfs/Desktop/apple-app/claude-howto-main/07-plugins/documentation/README.md)

为什么值得抄：

- 如果你经常做文档生成和同步，这组样例很有用

### 14. `07-plugins/devops-automation/*`

路径：
[07-plugins/devops-automation/README.md](/Users/lfs/Desktop/apple-app/claude-howto-main/07-plugins/devops-automation/README.md)

为什么值得抄：

- 如果你有部署、巡检、回滚等流程，适合后续参考

---

## 最推荐的抄法顺序

如果你只想尽快把这个项目的价值带到自己工作里，推荐按这个顺序：

1. 抄 `02-memory/project-CLAUDE.md` 的结构，写自己的 `CLAUDE.md`
2. 抄 `03-skills/code-review/SKILL.md`，做自己的 `review` skill
3. 抄 `04-subagents/code-reviewer.md`，做自己的 reviewer agent
4. 抄 `04-subagents/debugger.md`，做自己的 debugger agent
5. 抄 `07-plugins/pr-review/commands/review-pr.md` 的思路，做自己的 review 入口

---

## 最后建议

不要一上来就抄 plugin 全家桶。

最稳的做法通常是：

1. 先抄 `CLAUDE.md`
2. 再抄一个 skill
3. 再抄一个 agent
4. 流程跑顺后，再抄 plugin / hook / MCP
