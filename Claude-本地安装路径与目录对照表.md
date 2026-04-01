# Claude 本地安装路径与目录对照表

## 文档目的

这份文档解决一个非常实际的问题：

**Claude 的这些文件，到底应该放在哪里？**

适合场景：

- 项目级配置怎么放
- 用户级配置怎么放
- `CLAUDE.md`、skills、agents、hooks 分别放哪

---

## 一、两种作用范围

### 1. 项目级

只对当前项目生效。

推荐路径：

```text
your-project/
  CLAUDE.md
  .claude/
```

适合：

- 项目专用规则
- 团队共享
- 跟项目一起版本管理

### 2. 用户级

对你本机所有项目生效。

推荐路径：

```text
~/.claude/skills/
~/.claude/agents/
```

适合：

- 个人常用 skill
- 个人常用 agent
- 不依赖某个具体项目的能力

---

## 二、各类文件该放哪

### `CLAUDE.md`

项目级放法：

```text
your-project/CLAUDE.md
```

作用：

- 项目长期规则
- 项目背景
- 默认协作方式

### skills

项目级放法：

```text
your-project/.claude/skills/<skill-name>/SKILL.md
```

用户级放法：

```text
~/.claude/skills/<skill-name>/SKILL.md
```

### agents

项目级放法：

```text
your-project/.claude/agents/<agent-name>.md
```

用户级放法：

```text
~/.claude/agents/<agent-name>.md
```

### hooks

项目级放法：

```text
your-project/.claude/hooks/hooks.json
```

### plugin（项目内参考结构）

通常是项目里的单独目录，示例结构大致是：

```text
plugin-name/
  .claude-plugin/plugin.json
  commands/
  agents/
  hooks/
  mcp/
  scripts/
```

### MCP

更常见的是通过 Claude 自己的 MCP 配置去接，不一定都作为项目文件落地。

项目里更适合保留：

- 文档说明
- 配置样例
- 只读型接入约定

---

## 三、项目最常见的最小目录结构

```text
your-project/
  CLAUDE.md
  .claude/
    skills/
      review/
        SKILL.md
      bugfix/
        SKILL.md
    agents/
      implementer.md
      reviewer.md
      debugger.md
    hooks/
      hooks.json
```

这就是最常见的“项目级 Claude 起步框架”。

---

## 四、什么时候用项目级，什么时候用用户级

### 优先用项目级

如果它满足这些条件：

- 跟当前项目强相关
- 团队要共享
- 应该进入版本管理

### 优先用用户级

如果它满足这些条件：

- 是你个人通用习惯
- 不依赖具体项目
- 不需要团队一起用

一句话：

**项目相关的放项目里，个人通用的放用户目录。**

---

## 五、一句话总结

如果你拿到一套 Claude 协作框架，最稳的放法通常是：

- `CLAUDE.md` 放项目根目录
- `skills / agents / hooks` 放项目里的 `.claude/`
- 真正通用的个人习惯，再放到 `~/.claude/`
