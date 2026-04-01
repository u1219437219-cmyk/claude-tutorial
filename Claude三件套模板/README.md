# Claude 协作框架 V2 模板

这套模板包含：

1. `CLAUDE.md`
2. `.claude/skills/review/SKILL.md`
3. `.claude/skills/bugfix/SKILL.md`
4. `.claude/skills/feature/SKILL.md`
5. `.claude/skills/refactor/SKILL.md`
6. `.claude/agents/debugger.md`
7. `.claude/agents/implementer.md`
8. `.claude/agents/reviewer.md`
9. `.claude/hooks/hooks.json`

适合场景：

- 新项目起步
- 老项目接手
- 想先建立一个可持续升级的 Claude 协作框架

## 推荐使用顺序

1. 先把 `CLAUDE.md` 放到项目根目录
2. 再把整个 `.claude/` 目录放进项目
3. 先改 `CLAUDE.md`
4. 再改 `review / bugfix / feature / refactor` skills
5. 再按项目类型调整 `implementer / debugger / reviewer` agents
6. 最后按需要启用或调整 `hooks.json`

## 这三件分别解决什么

- `CLAUDE.md`
  解决：Claude 长期需要记住什么

- `review skill`
  解决：代码审查应该怎么做

- `bugfix skill`
  解决：bug 修复流程应该怎么走

- `feature skill`
  解决：新功能应该怎么分步骤实现

- `refactor skill`
  解决：重构时怎么控范围、保行为、降风险

- `debugger agent`
  解决：复杂 bug 应该怎么分步骤定位和修复

- `implementer agent`
  解决：新功能或修改需求应该怎么稳定、小步地实现

- `reviewer agent`
  解决：实现完成后怎么做独立复查

- `hook`
  解决：改完后自动提醒说明验证和风险

## 建议你先改的地方

### `CLAUDE.md`

- 项目目标
- 技术栈
- 目录约定
- 常用命令
- 默认协作方式

### `review skill`

- 按你的项目类型调整审查维度
- 前端项目补 UI/交互/状态
- 后端项目补契约/一致性/日志

### `bugfix skill`

- 调整成你项目常见 bug 类型
- 补充你项目更关心的验证方式

### `feature skill`

- 调整成你项目的新功能实施节奏
- 明确先分析、再计划、再实现的要求

### `refactor skill`

- 调整成你项目对重构的容忍度
- 明确“行为不变”和“验证要求”

### `debugger agent`

- 调整成你更常见的 bug 类型
- 补充你项目常用的排查方式

### `implementer agent`

- 调整成你项目更偏前端、后端或通用开发
- 补充你希望它优先遵守的实现原则

### `reviewer agent`

- 调整成你项目更关注的 review 维度
- 明确它优先抓回归风险还是结构问题

### `hook`

- 先保持简单
- 如果你还不确定要不要自动触发，可以先只保留配置作为模板

## 最后建议

先别急着继续加 plugin、hook、MCP。

先把这三件跑顺：

1. Claude 能稳定理解项目
2. Claude 能稳定实现功能
3. Claude 能稳定做 review
4. Claude 能稳定定位和修复 bug
5. Claude 能按统一流程推进新功能和重构
6. Claude 改完后能被提醒输出验证和风险

这时再继续扩展，收益最高。
