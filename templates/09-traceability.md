# Stage 9 - Traceability

这份用于把前面阶段的 ID 串起来。

目的是让关键链路可以机械追踪，而不是只能靠人脑理解。

## 1. 功能名

[填写]

## 2. 追踪矩阵

| TRACE_ID | STATE_ID | EVENT_ID | ACTION_ID | OP_ID | ROUTE_ID / SCREEN_ID | TC_ID | 备注 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `TRACE_001` | `STATE_001` | `EVENT_001` | `ACTION_001` | `OP_001` | `ROUTE_001 / SCREEN_001` | `TC_001` | [填写或 `N/A`] |

## 3. 明确的 N/A

| TRACE_NA_ID | 哪个环节不存在 | 为什么不存在 |
| --- | --- | --- |
| `TRACE_NA_001` | [如 `OP_ID`] | [例如：纯前端状态切换，无 API] |

## 4. 一致性检查

| 检查项 | 是否通过 | 说明 |
| --- | --- | --- |
| 每个 `ACTION_ID` 都有来源 | [是/否] | [填写] |
| 每个 `OP_ID` 都能回链到 `ACTION_ID` | [是/否] | [填写] |
| 每个关键路径都有 `TC_ID` | [是/否] | [填写] |

## 5. Machine View

```yaml
traceability:
  - id: TRACE_001
    state_id: STATE_001
    event_id: EVENT_001
    action_id: ACTION_001
    op_id: OP_001
    route_id: ROUTE_001
    screen_id: SCREEN_001
    test_case_id: TC_001
```

## 6. 给 AI 的硬规则

- 不允许在 traceability 中出现“来源不明”的动作
- 如果某个环节不适用，必须显式写 `N/A`
