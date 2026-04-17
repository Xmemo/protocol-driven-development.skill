# Stage 0 - Boundary / Intent + Minimum Acceptance

这份模板的默认用法不是“从零填写”。

默认流程是：

1. AI 先从 PRD 和现有文档里提取
2. AI 先生成待确认草稿
3. 用户再修改和确认

现在不要展开 API、路由、环境变量。

## 1. 功能名

[用一句短话命名，不要超过 12 个字]

## 2. FEATURE_ID

[稳定 ID，建议格式：`FEAT_<domain>_<verb>_<object>`]

例子：

`FEAT_PRACTICE_SAVE_RESULT`

## 3. Scope Level

- [ ] `app-level`
- [ ] `feature-level`

## 4. 模式

- [ ] `spec-first`
- [ ] `reverse-spec`
- [ ] `hybrid`

## 5. 一句话目标

[这个功能存在的唯一核心目的是什么]

例子：

- 当训练自然结束后，系统要先进入完成后流程，而不是直接退出

## 6. 当前协议 / 能力清单

| CAP_ID | 类型 | 名称 | 当前状态 | 说明 |
| --- | --- | --- | --- | --- |
| `CAP_001` | [protocol/learning/reward/other] | [填写] | [active/deferred/removed] | [填写] |

## 7. 范围内

| 这次一定要做 | 为什么要做 |
| --- | --- |
| [填写] | [填写] |
| [填写] | [填写] |

## 8. 范围外

| 这次明确不做 | 为什么现在不做 |
| --- | --- |
| [填写] | [填写] |
| [填写] | [填写] |

## 9. 发布路径

| 项目 | 当前 | 后续 |
| --- | --- | --- |
| 平台 | [填写] | [填写] |
| 语言 | [填写] | [填写] |
| 版本阶段 | [填写] | [填写] |

## 10. 产品锚点变化

| CHANGE_ID | 项目 | 变化 | 影响 |
| --- | --- | --- | --- |
| `ANCHOR_001` | [如品牌角色/核心入口/协议列表] | [填写] | [填写] |

## 11. 术语标准表

| TERM_ID | 产品术语 | 英文术语 | 代码枚举值 | 备注 |
| --- | --- | --- | --- | --- |
| `TERM_001` | [填写] | [填写] | [填写] | [填写] |

## 12. 能力变更记录

| CHANGE_ID | 动作 | 对象 | 原值 | 新值 | 原因 |
| --- | --- | --- | --- | --- | --- |
| `CAP_CHANGE_001` | [add/remove/rename/defer] | [填写] | [填写或 `N/A`] | [填写] | [填写] |

## 13. 成功标准

| 成功算什么 | 怎么观察到 |
| --- | --- |
| [填写] | [填写] |

## 14. 失败标准

| 什么情况算失败 | 怎么观察到 |
| --- | --- |
| [填写] | [填写] |

## 15. 最小验收口径

| MIN_ACC_ID | 最低可接受结果 | 如何快速验证 |
| --- | --- | --- |
| `MIN_ACC_001` | [填写] | [填写] |

## 16. 绝不能发生

| MUST_NOT_ID | 绝不能发生什么 | 为什么危险 |
| --- | --- | --- |
| `MUST_NOT_001` | [填写] | [填写] |

## 17. Machine View

```yaml
feature_id: FEAT_...
scope_level: app-level
mode: hybrid
goal: ...
capabilities:
  - id: CAP_001
    type: protocol
    status: active
terms:
  - id: TERM_001
    product: ...
    code: ...
in_scope:
  - ...
out_of_scope:
  - ...
minimum_acceptance:
  - id: MIN_ACC_001
    rule: ...
must_not_happen:
  - id: MUST_NOT_001
    rule: ...
```

## 18. 给 AI 的硬规则

- 在 Stage 0 没确认前，不准扩写技术实现
- 不准自行添加范围外能力
- 如果“成功标准”不可观察，必须先追问
- `FEATURE_ID` 一旦进入后续模板，不应随意改名
- 先基于项目输入生成草稿，再请用户确认
- 协议名、产品名、代码枚举值必须进入术语标准表
- 增删改能力必须进入能力变更记录
