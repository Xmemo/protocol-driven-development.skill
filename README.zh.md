# protocol-driven-build

面向 AI 原生产品构建的「协议先行」工作流技能。

## 一句话看懂

在写代码之前，先把产品边界、状态、数据、接口、风险和可追溯性定义清楚。

## 这个仓库是什么

这是一个独立可发布的 skill 包，用来做分阶段、可追溯的产品定义。

## 适合什么场景

- AI 原生产品
- 流程复杂的功能
- 需要先定协议再实现的功能
- 反向抽取已有产品规范

## 包含内容

- `SKILL.md`
- `workflow.md`
- `templates/`

## 不是什么

- 不是 UI 先行设计 skill
- 不是把 PRD 一次性倒完的模板仓库
- 不绑定单一项目或单一代码库

## 工作方式

1. 先抽取已有输入。
2. 先起草当前阶段。
3. 再让用户确认或修正。
4. 一次只推进一个阶段。

## 安装

把这个仓库复制到你的 Codex skills 目录，或者接到你自己的 skill 加载机制里。

## 与其他 skill 的关系

这个 skill 是 UI 生成工作流的上游。等协议稳定后，再接 `protocol-ui-fastlane`。

## 许可证

MIT

- English version: [README.en.md](./README.en.md)

