# Shared Data Contracts

## KnowledgeUnit minimum fields

```yaml
id: "KU-..."
title: "知识名称"
knowledge_type: "concept | definition | theorem | formula | method | pattern | fact | error_lesson"
classification:
  main: "主分类"
  sub: ["子分类"]
canonical_content: "原始准确内容"
plain_explanation: "通俗解释"
semantic_cues: []
relations: []
source:
  title: "来源名称"
  locator: "页码/章节/链接/对话位置"
  verification: "verified | partial | unverified"
```

## TrainingRecord minimum fields

```yaml
id: "TR-..."
date: "YYYY-MM-DD"
mode: "recall | reasoning | calculation | transfer | mixed"
task_id: "任务标识"
knowledge_ids: []
result:
  correctness: "correct | partial | incorrect | not_scored"
  response_time_seconds: null
  highest_hint_level: "H0-H5"
  independent: true
  confidence: null
strategy:
  recognized_pattern: []
  selected_strategy: ""
  rationale: ""
notes: "简要观察"
```

## ErrorRecord minimum fields

```yaml
id: "ER-..."
task_id: "任务标识"
knowledge_ids: []
type: "knowledge_gap | retrieval_failure | concept_confusion | strategy_error | logical_error | calculation_error | interference | execution_error"
observed_error: "实际错误"
root_cause: "已验证或待验证的原因"
correction: "正确内容"
discriminating_cue: "避免再次混淆的线索"
follow_up: "下一次如何练习"
```

## Integrity rules

- 使用唯一 ID；不能确认时使用临时 ID 并标注。
- 原始内容与解释分开。
- 数值保留原值、单位、有效位数和上下文；近似描述不能覆盖精确值。
- 关系记录应标明方向和关系类型。
- `verification` 与 `learning_status` 不能混为一谈：内容正确不代表用户掌握。
- 缺失字段留空，不编造。
