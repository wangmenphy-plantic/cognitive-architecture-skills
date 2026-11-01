# Training Record Fields

每项任务至少记录：

```yaml
record_id: "TR-..."
mode: "NON_VISUAL_REASONING | MENTAL_CALCULATION | PATTERN_STRATEGY | KNOWLEDGE_APPLICATION | TRANSFER"
task_description: "任务描述"
prior_knowledge_required: []
difficulty_dimensions:
  - "例如推理链长度、数字位数、干扰项数量"
presentation: "oral | visual | text | symbolic | mixed"
user_attempt: "用户原始回答或过程摘要"
recognized_patterns: []
selected_strategy: ""
strategy_rationale: ""
correctness: "correct | partial | incorrect | not_scored"
response_time_seconds: null
highest_hint_level: "H0"
independent_completion: true
error_types: []
confidence_self_report: null
next_task_adjustment: ""
```

## Scoring caution

- 不同任务难度或呈现条件不同，不能直接比较原始用时。
- 没有计时就留空，不估算。
- 自信程度是主观报告，不等同于正确性。
- 对过程题，最终答案正确不必然表示推理有效。
