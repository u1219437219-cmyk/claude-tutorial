# 全栈版 Skill 选型与使用说明

这份文档说明：

1. 哪些 skill 适合纳入这套全栈模板
2. 哪些 skill 更适合按需使用
3. 每个 skill 在实际协作里该怎么用

## 结论先看

结合 [skills-main](/Users/lfs/Desktop/apple-app/skills-main) 这个仓库目前的 skill 清单，对这套“一个仓库、前后端分离、需要跨边协作”的全栈模板，最值得关注的是：

1. `frontend-design`
2. `webapp-testing`
3. `doc-coauthoring`
4. `mcp-builder`

其中：

- `frontend-design` 已经适合纳入当前模板
- `webapp-testing` 已经纳入当前模板，作为验证增强层
- `doc-coauthoring` 和 `mcp-builder` 更适合写成按需增强，不建议一开始就做成默认必备

## 建议纳入模板

### frontend-design

定位：
- 前端视觉设计层

为什么适合纳入：
- 全栈项目里并不只有接口和联调，很多需求同时带有页面视觉升级、设计语言统一、仪表盘优化、落地页或后台页面美化
- 它和 `frontend-feature` 的分工清晰，不会互相替代

适合场景：
- 页面改版
- 仪表盘美化
- 设计语言升级
- 落地页
- 需要明显提升页面气质和辨识度的前端任务

怎么用：
- 直接说 `前端部分优先按 frontend-design 来做`
- 直接说 `这个页面先做设计方向，不要直接按普通功能页写`

推荐搭配：
- 和 `frontend-feature` 搭配
- 常见顺序是：先 `frontend-design` 定视觉方向，再 `frontend-feature` 落地功能

### webapp-testing

定位：
- Web 应用验证层

为什么适合纳入：
- 全栈项目最容易出问题的地方之一就是联调后的真实链路验证
- 它不是替代单元测试或接口测试，而是补“页面实际能不能跑通、交互有没有坏、联调后行为是否符合预期”
- 它对前端页面、后台系统、表单流程、登录流程、列表筛选、跨前后端关键路径都很有帮助

适合场景：
- 联调后验证关键链路
- 回归验证登录、筛选、表单、列表、分页、导出等功能
- 复现和排查前端交互 bug
- 截图留证或查看浏览器日志

怎么用：
- 直接说 `这个改动做完后，用 webapp-testing 帮我验证关键链路`
- 直接说 `先跑一遍登录到列表筛选的真实页面流程`
- 直接说 `用 webapp-testing 复现这个页面问题并截图`

推荐搭配：
- 和 `frontend-feature` / `backend-feature` 搭配，在实现后补真实链路验证
- 和 `security-guidance`、`code-review` 搭配，形成“实现 -> 安全提醒 -> 页面验证 -> PR 复查”的顺序

环境建议：
- 如果 Claude 环境里已经安装 `playwright` 插件，优先直接用插件提供的浏览器自动化能力
- 如果后面需要纯 Python 脚本化、批量化执行，或者必须完全按原始 `webapp-testing` skill 的方式运行，再补装 Python Playwright
- 可以理解成：Claude `playwright` 插件是默认方案，Python Playwright 是备用方案

是否建议接进全栈版：
- 建议

推荐定位：
- 不替代现有 `frontend-review` / `backend-review`
- 作为“验证增强层”接入更合适
- 最适合写进 `README.md`、`CLAUDE.md` 和这份说明文档，告诉使用者在关键链路、前后端联调和页面回归时优先使用

当前环境下的推荐落地方式：
- 优先用 Claude `playwright` 插件做页面验证
- 保留 `webapp-testing` 的方法论和场景判断
- 暂时不要求所有机器都预装 Python Playwright

当前模板状态：
- 已加入项目内 `.claude/skills/webapp-testing/`
- 项目内可以直接复用它的 `SKILL.md`、`scripts/with_server.py` 和示例脚本

## 建议按需增强，不做默认必备

### doc-coauthoring

定位：
- 文档协作层

为什么适合保留：
- 适合写设计文档、方案文档、RFC、决策记录和技术说明
- 对模板仓库本身的文档建设也有帮助

为什么不建议默认纳入：
- 它更适合“写文档”场景，不是所有全栈开发任务都需要
- 和业务实现流程不是同一层

适合场景：
- 写技术方案
- 写设计文档
- 写决策记录
- 写多人协作需要沉淀的说明文档

怎么用：
- 直接说 `这个需求先按 doc-coauthoring 的方式写一个设计文档`
- 直接说 `我们先把这个方案整理成一份可以评审的文档`

### mcp-builder

定位：
- 能力扩展层

为什么适合保留：
- 如果后面希望这套模板继续接更多外部工具或服务，MCP 是非常自然的扩展方向
- 这个 skill 对“开发自己的 MCP server”很有帮助

为什么不建议默认纳入：
- 它属于“开发能力基础设施”的任务，不是日常全栈业务开发的常规流程
- 大多数项目不会一开始就需要自己造 MCP server

适合场景：
- 需要把某个外部系统能力做成 MCP
- 想给 Claude 增加项目专用工具能力
- 准备把内部接口、平台能力或查询能力标准化给 AI 调用

怎么用：
- 直接说 `我们要给这个项目加一个 MCP server，按 mcp-builder 的方式来做`
- 直接说 `先设计这个 MCP server 的职责和接口，再落实现`

## 建议保留，但不建议纳入当前模板

### web-artifacts-builder

定位：
- Artifact / 展示型网页生成层

为什么不建议纳入：
- 更适合做 Claude artifact、单文件 HTML 展示稿、原型页
- 不是全栈项目协作模板的核心能力

适合场景：
- 做演示用页面
- 做可分享的 HTML 原型
- 做展示型交互产物

### theme-factory

定位：
- 视觉主题层

为什么不建议纳入：
- 更像演示物料和视觉统一工具
- 对通用全栈项目规则帮助有限

适合场景：
- 给文档、页面、演示稿统一主题
- 快速套一套视觉风格

### skill-creator

定位：
- 模板维护层

为什么不建议纳入默认规则：
- 适合继续维护和扩展这套模板的人
- 不适合作为所有项目成员的日常协作默认层

适合场景：
- 新增项目专用 skill
- 优化现有 skill
- 持续演进这套全栈模板

## 当前最推荐的 skill 组合

如果只考虑你现在这套全栈模板，最实用的组合是：

1. `frontend-design`
2. `frontend-feature` / `backend-feature`
3. `frontend-review` / `backend-review`
4. `webapp-testing`

可以理解成：

- `frontend-design` 管页面设计方向
- `frontend-feature` / `backend-feature` 管实现
- `frontend-review` / `backend-review` 管项目内审查口径
- `webapp-testing` 管真实页面和联调链路验证

## 推荐使用顺序

### 普通跨前后端需求

1. 先按项目规则拆前端部分和后端部分
2. 前端用 `frontend-feature`，后端用 `backend-feature`
3. 完成后先按项目内 review 口径自检
4. 关键链路再用 `webapp-testing` 做真实页面验证

### 前端视觉升级类需求

1. 先用 `frontend-design` 明确设计方向
2. 再按 `frontend-feature` 落地交互和功能
3. 改完后用 `webapp-testing` 跑关键页面流程

### 写方案或长期沉淀文档

1. 先按 `doc-coauthoring` 建立文档结构
2. 再把评审后的长期规则沉淀进项目文档

## 可直接复制的提示词

### 用 webapp-testing 做关键链路验证

```text
这个改动做完后，用 webapp-testing 的方式帮我验证关键链路。优先用 Claude 的 playwright 插件跑真实页面流程，重点检查从登录到列表筛选再到详情页的路径，如果有异常就定位并说明问题出在哪一层。
```

### 用 frontend-design + frontend-feature 做页面升级

```text
这个页面既要提升视觉质量，也要保留现有功能。先按 frontend-design 明确设计方向，再按 frontend-feature 落地交互和实现。完成后再用 webapp-testing 跑一遍关键页面流程。
```

### 用 doc-coauthoring 写方案

```text
这个需求先不要急着写代码，先按 doc-coauthoring 的方式整理成一份可评审的设计文档，重点写清楚前后端边界、接口契约、风险和验证方式。
```

### 用 mcp-builder 做能力扩展

```text
我们准备给这个项目接一个 MCP server。先按 mcp-builder 的方式设计职责边界、接口和实现方案，再决定是否开始编码。
```
