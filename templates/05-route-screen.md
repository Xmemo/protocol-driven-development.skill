# Stage 5 - Route / Screen Contract

只有在功能需要挂到页面或路由时再填这份。

## 1. 功能名

[填写]

## 2. 路由承接表

| ROUTE_ID | SCREEN_ID | 场景 | 入口 | 承接页面/路由 | 退出去哪里 |
| --- | --- | --- | --- | --- | --- |
| `ROUTE_001` | `SCREEN_001` | [填写] | [填写] | [填写] | [填写] |

## 3. 页面职责

| SCREEN_ID | 页面/路由 | 负责什么 | 不负责什么 |
| --- | --- | --- | --- |
| `SCREEN_001` | [填写] | [填写] | [填写] |

## 4. 导航行为

| ROUTE_ID | 前置条件 / guard | 返回键行为 | 深链 / reopen 行为 | 刷新 / resume 行为 |
| --- | --- | --- | --- | --- |
| `ROUTE_001` | [填写或 `N/A`] | [填写] | [填写或 `N/A`] | [填写或 `N/A`] |

## 5. Machine View

```yaml
routes:
  - route_id: ROUTE_001
    screen_id: SCREEN_001
    guard: ...
    back_behavior: ...
    deep_link: ...
    resume: ...
```

## 6. 给 AI 的硬规则

- 路由只是承接状态，不应反过来发明业务逻辑
- `ROUTE_ID / SCREEN_ID` 必须能回链到状态和动作
