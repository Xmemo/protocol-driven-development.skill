# Stage 8 - Verification Matrix

在准备实现、提测或交付前填这份。

## 1. 功能名

[填写]

## 2. 验证用例矩阵

| TC_ID | 场景 | 前置条件 | 操作步骤 | 预期结果 | 阻塞级别 |
| --- | --- | --- | --- | --- | --- |
| `TC_001` | [填写] | [填写] | [填写] | [填写] | [release_blocker/high/medium/low] |

## 3. 失败路径用例

| TC_ID | 失败场景 | 预期系统行为 |
| --- | --- | --- |
| `TC_FAIL_001` | [填写] | [填写] |

## 4. 发布阻塞项

| BLOCKER_ID | 什么问题会阻止发布 | 怎么确认它已解决 |
| --- | --- | --- |
| `BLOCKER_001` | [填写] | [填写] |

## 5. 可观察点

| 观察点 | 去哪里看 |
| --- | --- |
| [状态变化] | [页面/日志/network/localStorage] |

## 6. Machine View

```yaml
test_cases:
  - id: TC_001
    kind: happy_path
    expected: ...
blockers:
  - id: BLOCKER_001
    rule: ...
```

## 7. 给 AI 的硬规则

- 每个关键路径至少有一个 `TC_ID`
- 没有验证矩阵的功能不能宣称“ready”
