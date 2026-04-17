# Stage 7 - Env / Integration

只有在真实接入开始时再填这份。

## 1. 功能名

[填写]

## 2. 环境变量表

| ENV_ID | 变量名 | 用途 | 必填环境 | 示例值 |
| --- | --- | --- | --- | --- |
| `ENV_001` | [ENV_NAME] | [填写] | [local/test/prod] | [填写] |

## 3. 外部依赖

| DEP_ID | 依赖 | 用途 | 缺失会怎样 |
| --- | --- | --- | --- |
| `DEP_001` | [填写] | [填写] | [填写] |

## 4. 平台边界

| 平台 | 是否支持 | 说明 |
| --- | --- | --- |
| [web/ios/android/weapp] | [是/否] | [填写] |

## 5. 运行拓扑

| 项目 | local | test | prod |
| --- | --- | --- | --- |
| API base URL | [填写或 `N/A`] | [填写或 `N/A`] | [填写或 `N/A`] |
| 存储方式 | [填写] | [填写] | [填写] |

## 6. Machine View

```yaml
env:
  - id: ENV_001
    name: ...
    required_in:
      - local
dependencies:
  - id: DEP_001
    name: ...
```

## 7. 给 AI 的硬规则

- 没定义的环境变量不能擅自假设
- 平台限制必须前置说明
