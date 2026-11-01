---
name: knowledge-retrieval
description: Retrieve stored knowledge from exact terms, fuzzy semantic clues, category hierarchies, relation paths, and precise or approximate numeric anchors. Use when the user partially remembers a concept, theorem, formula, pattern, source, or technical detail.
metadata:
  version: "0.3"
  language: "zh-CN"
---

# Knowledge Retrieval — 知识检索 Skill

## Use When

- 用户记得某个概念、定理、公式或资料，但名称不完整。
- 用户提供模糊的自然语言、数字、数量级、单位或情境线索。
- 用户需要找出知识之间的前置、推广、应用或对比关系。
- 用户希望通过检索训练自己恢复知识。

## Don't Use When

- 用户正在进行必须先独立完成的记忆测试；此时先由 `memory-consolidation` 执行无提示回忆。
- 用户要求学习新知识的编码入库；转交 `knowledge-encoding`。
- 没有知识库或外部搜索能力时，不要假称已经搜索完整资料库。

## Workflow

1. **识别检索目的**：是帮助用户回忆，还是直接查证事实？
2. **提取线索**：记录用户确定的信息、模糊信息和不确定信息。
3. **选择检索路径**：精确 → 语义 → 层级 → 关系 → 数字；可根据线索并行调整。
4. **限定候选范围**：使用主分类、子分类、时间、来源和相邻概念缩小范围。
5. **生成候选**：返回少量最相关候选，附匹配依据和置信程度，不把相似结果当成确定答案。
6. **验证候选**：核对规范名称、完整陈述、条件、数值、单位和来源位置。
7. **引导用户辨认**：训练场景下先呈现关键线索或差异，不立即公布答案。
8. **记录检索结果**：检索成功不等于掌握；记录用户是否独立回忆、是否需要线索、最后是否能准确复述。

## Retrieval modes

- **Exact retrieval**：名称、关键词、符号、公式、原始数字、ID。
- **Semantic retrieval**：含义、释义、相似表达、问题情境。
- **Hierarchical retrieval**：从主分类到子分类缩小搜索空间。
- **Relation retrieval**：沿前置、推广、类比、对比、应用和推导关系展开。
- **Numeric retrieval**：精确值、单位、数量级、近似描述、比例关系和上下文。

## Rules

- 明确区分“用户记得的线索”和“系统检索出的信息”。
- 用户提供的模糊数字不能作为精确事实写回知识库。
- 返回数字时同时给出单位、量的定义和来源；缺任一关键项时标注不完整。
- 数学内容必须核对对象、定义域、映射方向、条件、量词和结论。
- 候选有多个时，说明每个候选匹配和不匹配的地方。
- 训练任务优先采用“提示—候选辨认—核对”，避免一开始泄露完整答案。
- 若外部资料与已有知识库冲突，保留双方来源并标记冲突，不静默覆盖。

## Examples

**用户：** 记得有个和紧致性、连续映射有关的定理。  
**处理：** 先询问“你记得它的结论还是使用场景？”然后搜索语义与关系索引，给出有限候选并核对原始陈述。

**用户：** 我记得大概是 0.7 秒左右的一个心算实验数据。  
**处理：** 通过“亚秒级、约七百毫秒、反应时”等线索找候选；展示精确数值、统计定义、单位和页码。

## Edge Cases

- **线索太少：** 问一个最能区分候选的问题，不连续盘问。
- **没有结果：** 扩展同义表达、上级分类和相关概念；仍无结果时说明未找到。
- **候选冲突：** 并列呈现证据和来源，保留不确定性。
- **数字近似匹配过多：** 要求单位、实验情境或量的定义，不凭数量级决定。
- **当前正在测验：** 不运行后台式答案搜索后直接公布；遵循测验规则。

## References

- [Retrieval protocol](references/retrieval-protocol.md)
- [Numeric and formula search](references/numeric-and-formula-search.md)
