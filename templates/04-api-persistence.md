# Stage 4 - API / Persistence

只有在确实需要和存储层或后端握手时再填这份。

## 1. 功能名

[填写]

## 2. OP_ID

| OP_ID | 对应的 ACTION_ID | 说明 |
| --- | --- | --- |
| `OP_001` | `ACTION_001` | [填写] |

## 3. 这次握手是干什么的

[一句人话说明]

## 4. 这是哪类握手

- [ ] 本地持久化
- [ ] 远端 HTTP API
- [ ] 其他：[填写]

## 5. 调用时机

| OP_ID | 什么时候触发 | 谁触发 | 是否允许重复触发 |
| --- | --- | --- | --- |
| `OP_001` | [填写] | [填写] | [是/否] |

## 6. 我发出去的快递单

| OP_ID | 字段名 | 来源字段/计算规则 | 含义 | 类型 | 例子 |
| --- | --- | --- | --- | --- | --- |
| `OP_001` | [field] | [ENTITY.field / derived] | [填写] | [填写] | [填写] |

## 7. 对方回给我的快递单

| OP_ID | 字段名 | 含义 | 类型 | 例子 |
| --- | --- | --- | --- | --- |
| `OP_001` | [field] | [填写] | [填写] | [填写] |

## 8. 失败时回什么

| OP_ID | 字段名 | 含义 | 类型 | 例子 |
| --- | --- | --- | --- | --- |
| `OP_001` | [field] | [填写] | [填写] | [填写] |

## 9. 时间与失败语义

| OP_ID | timeout | retry policy | idempotency | cancel behavior | duplicate handling | rollback / compensation |
| --- | --- | --- | --- | --- | --- | --- |
| `OP_001` | [如 `3000ms` 或 `N/A`] | [none / fixed / backoff] | [如何保证] | [如何取消] | [如何去重] | [失败后怎么补偿] |

## 10. 握手规则

- [填写]
- [填写]

## 11. Machine View

```yaml
operations:
  - id: OP_001
    action_id: ACTION_001
    transport: local_persistence
    request:
      - field: ...
        source: ENTITY_...
    semantics:
      timeout: 3000ms
      retry: none
      idempotency: ...
      cancel: ...
      duplicate_handling: ...
      compensation: ...
```

## 12. 给 AI 的硬规则

- 请求字段必须和数据模板一致
- 成功与失败必须能映射回状态模板
- `timeout / retry / idempotency / cancel / duplicate handling / compensation` 不得留空
- 如果当前不需要某项语义，必须显式写 `N/A`，而不是省略
