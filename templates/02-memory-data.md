# Stage 2 - Memory / Data

只有在状态确认后再填这份。

现在只回答：

- 什么是临时状态
- 什么是需要被长期记住的数据

## 1. 功能名

[填写]

## 2. Entity ID 表

| ENTITY_ID | 实体名 | 说明 |
| --- | --- | --- |
| `ENTITY_001` | [填写] | [填写] |

## 3. 临时状态 vs 长期记忆

| 项目 | 属于哪类 | 说明 |
| --- | --- | --- |
| [例如：当前倒计时] | 临时状态 | [填写] |
| [例如：训练记录] | 长期记忆 | [填写] |

## 4. 记忆卡片表

| ENTITY_ID | 字段名 | 人话解释 | 类型 | 必填 | 例子 | 错误示范 |
| --- | --- | --- | --- | --- | --- | --- |
| `ENTITY_001` | [field] | [填写] | [string/number/boolean/enum] | [是/否] | [填写] | [填写] |

## 5. 枚举值

| 字段 | 允许值 |
| --- | --- |
| [field] | [a, b, c] |

## 6. 数据硬约束

| DATA_RULE_ID | 规则 | 说明 |
| --- | --- | --- |
| `DATA_RULE_001` | [填写] | [填写] |

## 7. Machine View

```yaml
entities:
  - id: ENTITY_001
    name: ...
    fields:
      - name: ...
        type: ...
        required: true
data_rules:
  - id: DATA_RULE_001
    rule: ...
```

## 8. 给 AI 的硬规则

- 不允许擅自改字段名
- 不允许把长期记忆和临时状态混为一谈
- 如果字段未来会被 API 或页面读取，名称必须尽早定死
- `ENTITY_ID` 进入 API、Route、Verification 后必须保持稳定
