# Stage 6 - Risk / Trust / NFR

只有在 API、Route、真实数据或用户信任问题开始具体化时再填这份。

## 1. 功能名

[填写]

## 2. 风险总表

| RISK_ID | 类别 | 风险描述 | 影响 |
| --- | --- | --- | --- |
| `RISK_001` | [auth/privacy/security/abuse/performance/availability/observability] | [填写] | [填写] |

## 3. 权限与身份

| 项目 | 当前要求 | 如果缺失会怎样 |
| --- | --- | --- |
| 身份认证 | [填写或 `N/A`] | [填写] |
| 权限控制 | [填写或 `N/A`] | [填写] |

## 4. 隐私与数据敏感性

| 数据项 | 敏感级别 | 处理要求 |
| --- | --- | --- |
| [填写] | [public/internal/sensitive] | [填写] |

## 5. 非功能约束

| NFR_ID | 类别 | 目标值 | 如何观察 |
| --- | --- | --- | --- |
| `NFR_001` | latency | [如 `p95 < 500ms`] | [日志/监控/手测] |
| `NFR_002` | availability | [填写或 `N/A`] | [填写] |
| `NFR_003` | observability | [填写] | [填写] |

## 6. 缓解措施

| RISK_ID / NFR_ID | 缓解措施 | 所有者 |
| --- | --- | --- |
| `RISK_001` | [填写] | [client/server/devops/product] |

## 7. Machine View

```yaml
risks:
  - id: RISK_001
    category: security
    mitigation: ...
nfrs:
  - id: NFR_001
    category: latency
    target: p95 < 500ms
```

## 8. 给 AI 的硬规则

- 未明确的权限、隐私、性能假设不能偷偷默认
- 如果某一项确实不适用，必须显式写 `N/A`
