# protocol-driven-build

## 中文

### 协议先行的产品构建引擎

把模糊需求收敛成机器可读的产品约束，在写代码之前先定义边界、状态、数据、动作、接口、风险和可追溯性。

### 这个技能的强点

- 不是单一 PRD 模板，而是分阶段的协议栈
- `extract -> draft -> confirm`，先抽取再起草再确认
- 每一步都有硬门槛，避免“边想边写边跑偏”
- 适合 AI-native 产品、流程型功能和反向抽取已有产品

### 它解决什么

- 需求太散，团队一直在解释而不是在构建
- 逻辑隐含在脑子里，代码和文档彼此打架
- AI builder 很强，但没有约束就会乱生成
- PRD 很长，但不能直接指导实现

### 适合谁

- Founder
- PM / 产品负责人
- AI-native 产品团队
- 需要先定协议再开发的工程团队

### 你会得到什么

- 分阶段的产品定义流程
- 状态、数据、动作、接口、风险的明确约束
- 可追溯的文档链路
- 适合交给 AI agent / builder 的结构化输入

### 包含内容

- `SKILL.md`
- `workflow.md`
- `templates/`

### 工作方式

1. 先抽取已有输入。
2. 起草当前阶段。
3. 让用户确认或修正。
4. 一次只推进一个阶段。

### 安装

把这个仓库复制到你的 Codex skills 目录，或者接到你自己的 skill 加载机制里。

### 与其他 skill 的关系

它是 UI 生成工作流的上游。等协议稳定后，再接 `protocol-ui-fastlane`。

### 许可证

MIT

## English

### Protocol-first product building engine

Turn fuzzy ideas into machine-readable product constraints. Define boundaries, state, data, actions, APIs, risk, and traceability before implementation.

### Why this skill is strong

- It is not a single PRD template. It is a staged protocol stack.
- It follows `extract -> draft -> confirm`.
- Every stage has a hard gate, so the work does not drift while you build.
- It works well for AI-native products, workflow-heavy features, and reverse-specing existing products.

### What it solves

- Requirements stay vague and the team spends more time explaining than building.
- Product logic lives in people’s heads instead of in shared contracts.
- AI builders are powerful, but without constraints they invent the wrong thing.
- PRDs become long documents that do not directly guide implementation.

### Best for

- Founders
- PMs and product leads
- AI-native product teams
- Engineering teams that want to define protocol before shipping code

### What you get

- A staged product-definition workflow
- Explicit constraints for state, data, actions, APIs, and risk
- A traceable document chain
- Structured input that works well for AI agents and builders

### Included contents

- `SKILL.md`
- `workflow.md`
- `templates/`

### How it works

1. Extract existing inputs first.
2. Draft the current stage.
3. Confirm or correct with the user.
4. Advance one stage at a time.

### Install

Copy this repository into your Codex skills directory, or wire it into your own skill loader.

### Relationship

This skill is upstream of UI generation workflows. Use `protocol-ui-fastlane` after the protocol is stable.

### License

MIT
