# Stage 3 - Effects / Actions

只有在状态和数据确认后再填这份。

这一步先不展开 API 字段，只先定义：

- 哪个状态变化会触发哪个动作

## 1. 功能名

[填写]

## 2. 动作总表

| ACTION_ID | 触发的 STATE_ID / EVENT_ID / TRANSITION_ID | 动作 | 类型 | 说明 |
| --- | --- | --- | --- | --- |
| `ACTION_001` | [填写] | [填写] | [存储/导航/音频/震动/toast/埋点/其他] | [填写] |

## 3. 动作归属

| ACTION_ID | 应该由谁负责 |
| --- | --- |
| `ACTION_001` | [状态机/页面层/hook/服务层] |

## 4. 风险点

| RISK_REF | 风险 | 为什么危险 |
| --- | --- | --- |
| [可先填 `RISK_PENDING`] | [填写] | [填写] |

## 5. Machine View

```yaml
actions:
  - id: ACTION_001
    trigger:
      state_id: STATE_...
      event_id: EVENT_...
    kind: storage
    owner: hook
```

## 6. 给 AI 的硬规则

- 每个动作都必须能追溯到一个状态变化或显式事件
- 不允许把保存、导航、播放音频混在一个模糊回调里
- `ACTION_ID` 是后续 API、Route、Verification、Traceability 的锚点
