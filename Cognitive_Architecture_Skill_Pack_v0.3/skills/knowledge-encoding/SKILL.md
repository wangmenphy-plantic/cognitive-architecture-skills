---
name: knowledge-encoding
description: Capture and structure durable knowledge as meaningful chunks with stable classifications, semantic cues, exact-value anchors, relations, and discriminating features. Use when adding or reorganizing concepts, theorems, formulas, strategies, patterns, or lessons from errors.
metadata:
  version: "0.3"
  language: "zh-CN"
---

# Knowledge Encoding — 知识编码与存储 Skill

## Use When

- 用户提供了值得长期保存的新知识、定理、公式、策略或模式。
- 用户要求对笔记、摘录或学习成果分类、分块、结构化。
- 需要为易混淆知识建立区别特征。
- 需要把数字、单位、精确公式和模糊语义锚点共同入库。

## Don't Use When

- 用户只要求临时解释，不需要长期保存。
- 任务主要是查找已存在知识；优先使用 `knowledge-retrieval`。
- 用户尚未确认一段推测性内容，且没有可靠来源。此时先标记待核验。

## Workflow

1. **识别来源与用途**：教材、论文、课堂、用户推导、AI 讨论或训练发现。
2. **判断保存价值**：优先保存高复用、关键、易忘、易混淆或由用户独立发现的内容；不把所有聊天自动入库。
3. **识别知识类型**：概念、定义、定理、公式、方法、模式、事实或错误经验。
4. **分块**：按逻辑边界拆分，避免整段复制或把不可分割定义拆得失去意义。
5. **分类**：指定一个稳定主分类，可有多个子分类和标签；用关系边处理跨领域联系。
6. **语义编码**：提炼正式名称、通俗解释、关键词、自然语言线索、应用场景和常见问法。
7. **关系编码**：记录前置、推广、特殊情形、类比、对比、推导来源、应用和反例关系。
8. **区分性编码**：找出相似知识的关键区别、必要条件、常见误读和辨析例子。
9. **精确信息保护**：数字、单位、符号、公式、量词、定义条件和出处必须保持精确；模糊锚点只增加搜索入口。
10. **输出候选知识单元**：展示分类与结构，指出不确定字段，请用户确认重要改动。
11. **持久化声明**：只有真实写入知识库或文件成功后才说已保存；否则给出可复制记录并标记 `pending_write`。

## Rules

- 原文、规范表述、通俗解释和 AI 推论分字段保存，不互相替代。
- 数学定义和定理必须保留全部条件、量词、对象类型、映射方向和结论。
- 对用户自创的策略，记录“提出者/情境/效果证据”，不要包装成公认定理。
- 每条关系都要有明确语义，不用含糊的“相关”替代具体关系。
- 一个知识单元应能被独立引用；过大的知识拆成多个单元，再用关系连接。
- 不要为了追求层级数量而过度分类；主分类保持稳定，辅助检索依赖标签和关系。
- 记录来源位置，尤其是论文页码、教材章节、公式编号或原始链接。

## Examples

**输入：** 用户提供某个定理的原文、自己的解释和一个例子。  
**输出：** 一个 theorem 知识单元，分别保存正式陈述、条件、结论、证明结构、例子、相关概念和来源。

**输入：** 用户记住一个技术值“大概几百毫秒”，但原文有精确均值。  
**输出：** 精确值和单位进入 `exact_values`；“几百毫秒”作为 `approximate_descriptions`，不可覆盖精确值。

## Edge Cases

- **同一知识属于多个学科：** 指定一个主分类，其他领域用子分类、标签或 `used_in` / `analogous_to` 关系表达。
- **内容尚未核实：** 标记 `partial` 或 `unverified`，不写成确定事实。
- **与旧记录重复：** 先比较定义、条件、来源和内容；确认重复后更新原单元或建立版本关系，不盲目复制。
- **用户不同意 AI 分类：** 以用户最终确认的分类为准，并保留变更说明。
- **无法真正写入外部库：** 明确告知尚未持久化，提供可复制的 YAML/JSON。

## References

- [Knowledge-unit schema](references/knowledge-unit-schema.md)
- [Taxonomy and semantic coding](references/taxonomy-and-semantic-coding.md)
- [Numeric anchors](references/numeric-anchors.md)
