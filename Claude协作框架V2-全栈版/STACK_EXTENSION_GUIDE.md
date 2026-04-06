# 全栈版技术栈扩展指南

这份文档说明怎么在不污染通用全栈模板的前提下，给特定技术栈增加附加规则。

目标是：

1. 保持通用模板足够干净
2. 让特定技术栈有单独的补充规则
3. 避免把 Python、Node、React、Next.js 之类的细节全部塞进主 `CLAUDE.md`

## 为什么要做成附录

通用全栈模板更适合承载：

- 前后端边界
- 任务推进方式
- 计划文件要求
- 安全与 review 顺序
- 通用插件协作方式

技术栈细节更适合放到附录里，比如：

- React / Next.js 的组件和路由约定
- NestJS / Express 的接口和模块约定
- Python / FastAPI 的类型和依赖注入约定
- Tailwind / CSS Modules / 组件库约束

这样做的好处是：

- 主模板不容易越写越重
- 不同项目可以只拿自己需要的附录
- 技术栈变化时，只改附录，不用频繁改主模板

## 推荐目录

如果后续要继续扩展，推荐在全栈版目录下增加一个 `stack-guides/`：

```text
Claude协作框架V2-全栈版/
  CLAUDE.md
  README.md
  PLUGIN_GUIDE.md
  STACK_EXTENSION_GUIDE.md
  stack-guides/
    react-nextjs.md
    vue-nuxt.md
    node-nestjs.md
    node-express.md
    python-fastapi.md
    python-django.md
```

不需要一开始就全建出来。

只在你真的有对应项目时，再补那个文件。

## 每个技术栈附录建议写什么

每份附录建议控制在几个固定栏目里：

1. 适用范围
2. 目录约定
3. 常用命令
4. 实现偏好
5. review 重点
6. 风险提醒
7. 推荐插件或工具

## 示例

以 `python-fastapi.md` 为例，可以写：

1. 适用范围
- FastAPI API 服务
- Pydantic schema
- SQLAlchemy / Prisma / async DB 访问

2. 目录约定
- `app/api/` 放路由
- `app/services/` 放业务逻辑
- `app/schemas/` 放输入输出模型

3. 实现偏好
- 优先补类型
- 输入输出通过 schema 明确
- 路由层保持薄，逻辑放 service

4. review 重点
- 契约一致性
- 异步边界
- 错误处理
- 数据校验

## 怎么和主模板配合

推荐方式不是把附录内容全贴进主 `CLAUDE.md`，而是：

1. 主模板保留通用规则
2. 技术栈差异写进对应附录
3. 项目落地时，在项目自己的 `CLAUDE.md` 里引用或吸收 relevant 部分

也就是说：

- 模板仓库保留“通用层 + 技术栈附录层”
- 真实项目按自己技术栈选用对应附录

## 推荐使用方式

### 通用全栈项目

只用主模板：

- [CLAUDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/CLAUDE.md)
- [PLUGIN_GUIDE.md](/Users/lfs/Desktop/apple-app/claude-tutorial/Claude协作框架V2-全栈版/PLUGIN_GUIDE.md)

### 已确定技术栈的项目

用法是：

1. 先套主模板
2. 再补对应技术栈附录
3. 最后在真实项目里把附录内容项目化

## 当前建议

如果你要继续扩展这套模板，最值得优先补的附录通常是：

1. `react-nextjs.md`
2. `node-nestjs.md`
3. `python-fastapi.md`

因为这三类最常见，也最容易和当前全栈模板形成互补。
