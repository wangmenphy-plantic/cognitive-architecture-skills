# Record Schemas

## TrainingRecord

```yaml
id: "TR-..."
date: "YYYY-MM-DD"
mode: "recall | reasoning | calculation | strategy | transfer"
task:
  description: ""
  category: ""
  difficulty: ""
  presentation: "oral | visual | text | symbolic | mixed"
knowledge_ids: []
performance:
  correctness: "correct | partial | incorrect | not_scored"
  response_time_seconds: null
  highest_hint_level: "H0-H5"
  independent_completion: true
  confidence_self_report: null
strategy:
  recognized_patterns: []
  selected_strategy: ""
  rationale: ""
errors: []
evidence_type: "observed | self_reported | mixed"
next_action: ""
```

## ErrorRecord

```yaml
id: "ER-..."
task_id: "TR-..."
knowledge_ids: []
type: "knowledge_gap | retrieval_failure | concept_confusion | strategy_error | logical_error | calculation_error | interference | execution_error"
observed_error: ""
possible_root_cause: ""
root_cause_status: "confirmed | hypothesis | unknown"
correction: ""
discriminating_cue: ""
follow_up_task: ""
```

## Human knowledge growth snapshot

```yaml
snapshot_date: "YYYY-MM-DD"
period: "本周/本阶段"
indicators:
  independent_encoding: "evidence + status"
  unaided_retrieval: "evidence + status"
  semantic_organization: "evidence + status"
  pattern_recognition: "evidence + status"
  strategy_selection: "evidence + status"
  transfer: "evidence + status"
limitations: []
next_targets: []
```

## Persistence rule

如果没有真实存储连接：将快照作为文本交给用户保存；不要声称自动形成跨会话历史。
