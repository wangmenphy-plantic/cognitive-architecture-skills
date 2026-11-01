# Numeric and Formula Search

## Numeric query representation

每条数字记录尽量包含：

```yaml
value_exact: "精确数值，使用字符串可避免格式丢失"
unit: "单位"
quantity: "数值代表的量"
statistic_type: "均值/中位数/范围/上限/下限/系数/常数/未知"
context: "实验、定理、设备或问题情境"
scale_cues: []
approximate_cues: []
relations: []
source_locator: "页码、表格、公式编号或 URL"
```

## Formula query representation

保存公式时应同时保存：

- 原始公式；
- 每个符号的含义；
- 定义域与适用条件；
- 等价变形（仅在确认成立时）；
- 典型应用场景；
- 常见错误形式；
- 来源定位。

## Query expansion

例如用户说“差不多七百毫秒的平均时间”：

- 近似词：七百毫秒、0.7 秒、不到一秒；
- 量的类型：反应时、响应延迟、开始作答时间；
- 情境：心算、问题呈现、开始回答；
- 数值核验：回到原始数据段落确认统计含义。

## Exactness guard

如检索命中多个不同精确值，按量的定义和上下文区分，不得用“相近”合并。未经核对的换算值应标记为计算所得，而非原文值。
