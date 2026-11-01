---
name: cognitive-training
description: Design and conduct deliberate practice for non-visual logical reasoning, mental calculation, pattern recognition, strategy selection, and transfer. Use when the user asks to train, solve practice tasks, improve independent reasoning, or compare solution strategies.
metadata:
  version: "0.3"
  language: "zh-CN"
---

# Cognitive Training — 认知能力训练 Skill

## Use When

- 用户希望训练非视觉逻辑推理、心算或模式识别。
- 用户希望通过练习提高策略选择、知识调用和独立解题能力。
- 用户要求出题、循序渐进提示、诊断练习或迁移训练。

## Don't Use When

- 用户只需要一次性答案或完整讲解，且明确不要求训练。
- 当前任务首先需要核验资料或查找旧知识；先使用检索模块。
- 用户疲劳或时间紧张；不要以训练名义强行增加负担。

## Workflow

1. **确定训练目标**：逻辑推理、心算、模式识别、策略选择、知识调用或迁移。
2. **确定任务范围**：使用已学知识，避免把未教内容误测为记忆失败。
3. **设置难度**：从用户目前可以独立完成但需要思考的水平起步；一次优先改变一个主要难度因素。
4. **先独立尝试**：默认 H0，不展示解法、图示或答案。
5. **按需提示**：遵循 H0—H5 提示阶梯，每次只提供最小必要帮助。
6. **要求策略说明**：完成后询问识别了什么模式、为何选此策略、是否有替代方案。
7. **核验过程和结果**：分别检查答案正确性、逻辑有效性、计算准确性和条件是否完整。
8. **记录表现**：保存任务难度、用时、提示级别、策略、错误类型和独立程度。
9. **安排下一题**：根据错误调整训练，不只增加题目数量。

## Training modes

- `NON_VISUAL_REASONING`：减少图像和图示依赖，以语言、符号和逻辑关系维护问题结构。
- `MENTAL_CALCULATION`：训练心算、数字分块、快速提取和计算策略。
- `PATTERN_STRATEGY`：识别熟悉结构，并在多个策略间作选择。
- `KNOWLEDGE_APPLICATION`：调用旧知识解决当前问题。
- `TRANSFER`：在表面形式改变或新情境中使用已学结构。
- `MIXED`：组合多个能力，但复盘时分开诊断。

## Rules

- 先正确、再稳定、后提速；速度不能补偿错误推理。
- 不把书写、符号演算或草稿一概视为失败；“非视觉”训练的重点是减少对预制图像和外部答案的依赖，而不是禁止合理的外部认知工具。
- 只有训练目标明确要求时才隐藏图示、计算器或笔记。
- 训练题必须和目标技能相关；不能以陌生知识造成伪难度。
- 不预先泄露策略名称或答案，除非用户请求示范。
- 对数学题明确对象、定义域、条件、量词和推理依据；不以“显然”掩盖关键步骤。
- 心算训练要区分算术事实提取、数字模式识别、算法执行和工作记忆错误。
- 允许用户报告“卡住了”；不要把困难解释成能力不足。

## Examples

**心算：** 给出一组逐渐变化的计算题，记录用户识别的数字结构、策略和正确性；之后才比较其他策略。

**逻辑推理：** 给出不含图示的条件推理题，先要求用户复述已知和目标，再逐步提示。

**迁移：** 在熟悉的定义或定理上改变对象、表达方式或情境，检查能否识别底层结构。

## Edge Cases

- **用户使用纸笔：** 允许；记录目标是无图像心算还是总体逻辑推理，不将笔记使用自动算作失败。
- **答案正确但过程错误：** 标记为偶然正确或依据不足，不记为完全掌握。
- **过程合理但算错：** 将逻辑能力和算术执行分开记录。
- **题目超出已学范围：** 改为教学或知识补充，不作为能力基线。
- **策略尚未成熟：** 允许试验，比较策略的准确性、步骤、记忆负担和稳定性。

## References

- [Training modes and task design](references/training-modes.md)
- [Hint ladder](references/hint-ladder.md)
- [Training record fields](references/training-record-fields.md)
