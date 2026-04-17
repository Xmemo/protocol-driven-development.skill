# protocol-driven-build

Protocol-first product building for AI-native workflows.

面向 AI 原生产品构建的「协议先行」工作流技能。

## At a glance / 一句话看懂

- EN: Define product boundaries, state, data, API, risk, and traceability before implementation.
- 中文：在写代码之前，先把产品边界、状态、数据、接口、风险和可追溯性定义清楚。

## What this repo is / 这个仓库是什么

This is a standalone skill pack for stage-gated product definition.

这是一个独立可发布的 skill 包，用来做分阶段、可追溯的产品定义。

## Best for / 适合什么场景

- EN: AI-native products
- 中文：AI 原生产品
- EN: Workflow-heavy features
- 中文：流程复杂的功能
- EN: Features that need contracts before code
- 中文：需要先定协议再实现的功能
- EN: Reverse-specing existing products
- 中文：反向抽取已有产品规范

## What is included / 包含内容

- `SKILL.md`
- `workflow.md`
- `templates/`

## What it is not / 不是什么

- EN: Not a UI-first design skill
- 中文：不是 UI 先行设计 skill
- EN: Not a freeform PRD dumping ground
- 中文：不是把 PRD 一次性倒完的模板仓库
- EN: Not tied to one app or one codebase
- 中文：不绑定单一项目或单一代码库

## How it works / 工作方式

1. Extract existing inputs first.
2. Draft the current stage.
3. Confirm or correct with the user.
4. Advance one stage at a time.

1. 先抽取已有输入。
2. 先起草当前阶段。
3. 再让用户确认或修正。
4. 一次只推进一个阶段。

## Install / 安装

Copy this repository into your Codex skills directory, or wire it into your own skill loader.

把这个仓库复制到你的 Codex skills 目录，或者接到你自己的 skill 加载机制里。

## Relationship / 与其他 skill 的关系

This skill is upstream of UI generation workflows. Use `protocol-ui-fastlane` after the protocol is stable.

这个 skill 是 UI 生成工作流的上游。等协议稳定后，再接 `protocol-ui-fastlane`。

## License / 许可证

MIT
