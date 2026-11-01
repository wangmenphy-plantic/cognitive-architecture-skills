# Knowledge Unit Schema

以下是通用数据契约。具体知识类型可以扩展字段，但不要改变核心字段的含义。

```yaml
id: "KU-YYYYMMDD-序号"
version: 1
title: "知识名称"
knowledge_type: "concept | definition | theorem | formula | method | pattern | fact | error_lesson"
classification:
  main: "主分类"
  sub: ["子分类"]
  tags: []
content:
  canonical_statement: "精确原文或规范表达"
  plain_explanation: "通俗解释"
  conditions: []
  conclusion: "核心结论"
  proof_or_process_outline: []
  examples: []
  counterexamples: []
semantic_index:
  keywords: []
  natural_language_cues: []
  alternative_phrasings: []
  application_scenarios: []
numeric_index:
  exact_values: []
  units: []
  magnitude_labels: []
  approximate_descriptions: []
  relations: []
relations:
  prerequisites: []
  generalizes: []
  specializes: []
  analogous_to: []
  contrasts_with: []
  derived_from: []
  used_in: []
  counterexample_to: []
discrimination:
  similar_concepts: []
  distinguishing_features: []
  common_confusions: []
retrieval:
  direct_queries: []
  semantic_queries: []
  problem_patterns: []
  recall_cues: []
provenance:
  source_title: ""
  author: ""
  locator: "页码/章节/公式号/链接"
  source_type: "textbook | paper | lecture | user_derivation | conversation | web"
  verification_status: "verified | partial | unverified"
  last_checked: ""
learning_status:
  first_seen: ""
  last_reviewed: ""
  unaided_recall_level: 0
  applied_successfully: false
  notes: "用户掌握状态，不等同于内容核验状态"
```

## Field rules

- `canonical_statement` 用来保存准确内容；`plain_explanation` 用来帮助理解。
- 定理应把条件和结论分别列出，避免检索时丢失条件。
- `relations` 中保存的 ID 必须指向已存在单元；未建立时可写待链接名称。
- `verification_status` 描述来源可信度与核验程度；`learning_status` 描述用户掌握程度。
- `unaided_recall_level` 使用 0—5 操作性等级，必须有训练记录支持，不凭印象填高。
