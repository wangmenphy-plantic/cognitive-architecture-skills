# Workflow and Routing

## Session state

每次训练会话尽量保留以下状态：

```yaml
session:
  session_id: "唯一标识；无持久化工具时可用临时标识"
  date: "YYYY-MM-DD；未知则留空"
  context: "当前学习主题"
  mode: "PRE_STUDY | GUIDED_PRACTICE | POST_STUDY | ..."
  target_skills: []
  target_knowledge_ids: []
  baseline: "用户当前自述或测试表现"
  constraints:
    time_budget: null
    visual_support: "默认按用户任务要求"
    hint_policy: "H0 起步"
```

## Decision sequence

1. 识别用户当前意图，不将所有请求都解释成训练请求。
2. 确认是否有可用的历史知识记录。
3. 决定“先回忆”还是“先查找”。训练记忆时先回忆；查证事实或用户要求直接检索时可以先搜索。
4. 只调用当前任务需要的专业模块。
5. 在回复中区分已核实事实、用户自述、AI 推断和待验证假设。
6. 结束时给出一个下一步训练目标或待办，不生成无必要的长计划。

## Routing triggers

- 新概念、定理、策略、数字规律 → `knowledge-encoding`。
- “我记得有个……/大概是……/那个公式是什么” → `knowledge-retrieval`。
- 需要心算、推理或问题解决练习 → `cognitive-training`。
- “考我/复习/不看笔记回忆/容易忘” → `memory-consolidation`。
- “分析我最近进步/错误/训练效率” → `performance-analysis`。

## Evidence labels

每项结论尽可能标为：

- `observed`：在本次回答或测试中直接观察到。
- `self_reported`：用户自述，尚未独立验证。
- `inferred`：根据多条记录作出的解释。
- `unverified`：缺少证据或来源。

不要将 inferred 或 self_reported 伪装为 observed。
