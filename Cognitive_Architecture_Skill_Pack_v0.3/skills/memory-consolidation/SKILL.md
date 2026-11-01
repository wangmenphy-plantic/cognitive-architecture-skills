---
name: memory-consolidation
description: Strengthen independent memory retrieval through unaided recall, cue-based recall, ordered reconstruction, discrimination, and spaced review. Use when the user wants to review learned material, test retention, reduce confusion, or plan recall practice.
metadata:
  version: "0.3"
  language: "zh-CN"
---

# Memory Consolidation — 记忆强化与巩固 Skill

## Use When

- 用户要求复习、抽查、回忆已学知识。
- 用户经常“感觉熟悉但想不起来”。
- 相似概念、公式或数字容易互相干扰。
- 需要根据历史表现安排后续提取练习。

## Don't Use When

- 用户第一次接触某知识且尚未形成基本理解；先教学和编码。
- 用户明确要求直接查资料而不是测试记忆。
- 没有历史数据却要求给出确定的遗忘概率或科学精确的复习日期。

## Workflow

1. **确定目标知识**：从已学知识或用户指定范围选择，不用未学习内容测记忆。
2. **先无提示回忆**：要求用户尝试复述、重建或应用，不先展示答案。
3. **分类回忆情况**：完整、部分、错误、无法回忆。
4. **逐级给线索**：从语义、类别、关系、例子到局部结构，避免直接给完整答案。
5. **核对准确性**：检查定义条件、符号、数值、单位、顺序和来源。
6. **区分性练习**：对容易混淆的概念进行比较、反例辨析和条件辨析。
7. **安排下一次提取**：根据近期表现安排复习；这是可调整的训练计划，不声称精确预测遗忘。
8. **更新记忆状态**：记录无提示表现、提示后表现、错误类型、时间和下次复习建议。

## Recall modes

- `FREE_RECALL`：自由回忆，不提供线索。
- `CUE_RECALL`：提供关键词、语义或局部条件。
- `ORDERED_RECALL`：按证明结构、步骤或分类顺序恢复。
- `DISCRIMINATION`：区分相似概念、公式或数字模式。
- `APPLICATION_RECALL`：通过新问题检查能否调用旧知识。
- `MIXED_RETRIEVAL`：在不同知识主题之间交错提取，观察干扰和区分能力。

## Rules

- 回忆前不显示答案或笔记。
- 记忆测试应与知识理解测试区分；答不出可能是未理解、未编码、遗忘或提取线索不合适。
- 一次提取的成功应记录所需提示等级。
- 对精确公式、定理条件和数字，必须按准确标准核验，不能以大意正确代替。
- 复习间隔根据实际表现调整；没有数据时只给试运行建议。
- 不用“熟悉感”代替主动回忆表现。

## Examples

**用户：** 考我上周学过的定义。  
**处理：** 先自由回忆；若卡住，依次给类别、关键词和局部条件；最后核对原始定义。

**用户：** 我总把两个概念混淆。  
**处理：** 设计共同点识别、最小区别、反例和情境判断任务；将错误回馈给知识编码模块。

## Edge Cases

- **回答不完整：** 记录缺失部分，不将部分正确误记为完全掌握。
- **用错术语但理解相同：** 分别记录概念理解和术语精确度。
- **重复失败：** 检查原始编码是否清晰、知识块是否过大、检索线索是否有效。
- **复习过于简单：** 加入应用或辨析，而非单纯增加重复次数。
- **用户疲劳：** 缩短任务，只保留一个高价值提取目标。

## References

- [Recall protocol](references/recall-protocol.md)
- [Review scheduling](references/review-scheduling.md)
