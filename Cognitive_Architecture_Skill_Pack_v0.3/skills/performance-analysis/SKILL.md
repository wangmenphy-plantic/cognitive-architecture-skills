---
name: performance-analysis
description: Analyze learning and training records to identify knowledge, retrieval, reasoning, calculation, strategy, interference, and transfer patterns. Use for post-study reviews, progress reports, error diagnosis, and adaptive training decisions.
metadata:
  version: "0.3"
  language: "zh-CN"
---

# Performance Analysis — 表现分析与自适应 Skill

## Use When

- 用户完成学习、训练或一个阶段，希望复盘。
- 用户想知道人脑知识管理系统是否成长。
- 需要分析错误根源、提示依赖、提取效率或策略变化。
- 需要据历史表现调整后续训练。

## Don't Use When

- 只有单次自我感觉，没有实际任务或可观察结果，却要求做强结论。
- 任务只需要保存知识内容；优先使用 `knowledge-encoding`。
- 不同难度、不同呈现方式或不同任务类别的数据不具备可比性时，不做直接排名。

## Workflow

1. **收集证据**：用户原始回答、任务要求、正确标准、提示等级、用时、策略和错误记录。
2. **区分来源**：标记 observed、self_reported、inferred 或 unverified。
3. **分类错误**：知识缺失、检索失败、概念混淆、策略选择、逻辑、计算、干扰或执行错误。
4. **分维度分析**：自主编码、提取、语义组织、模式识别、策略选择、迁移。
5. **比较可比记录**：尽量使用同类任务、相近难度和相同呈现条件。
6. **判断趋势**：区分单次波动与持续变化；没有足够样本时明确说样本不足。
7. **给出可检验假设**：例如“目前更像检索线索不足”，而不是断言根因。
8. **制定下一步**：只选择 1—3 个最重要训练目标。
9. **更新记录**：将分析结论和依据写入训练记录；更改知识单元时交给编码模块。

## Core dimensions

- **自主编码**：能否独立提炼知识块和关键条件。
- **自主检索**：能否无提示恢复准确知识。
- **语义组织**：能否建立正确分类、联系和区别。
- **模式识别**：能否发现熟悉结构或子问题。
- **策略选择**：能否选出适合当前问题的策略并说明理由。
- **迁移能力**：能否在陌生表达或新情境中调用旧知识。

## Rules

- 不把知识条目数量当作人脑成长指标。
- 不把 AI 搜索命中当作用户自主记忆成功。
- 不把主观信心当作正确性证据。
- 不把单次用时变化当作能力提升；先检查题目难度和呈现方式。
- 不把所有错误归因于“记忆不好”；要区分理解、编码、检索、策略和执行。
- 不输出缺乏依据的 IQ、天赋或心理诊断。
- 没有持久历史记录时，只描述当前样本，不声称长期趋势。
- 下一轮建议要可执行、可检验，且不超过 1—3 项。

## Examples

**用户：** 我最近复习定义越来越快了吗？  
**处理：** 比较相同定义或同类任务的无提示准确率、用时与提示等级；样本不足时说明不足。

**用户：** 我总在证明题里卡住。  
**处理：** 分析卡点是否属于知识提取、条件识别、策略选择或推理执行，再提出针对性任务。

## Edge Cases

- **没有计时数据：** 不估算反应时间，只分析正确性和提示依赖。
- **记录不完整：** 标注缺失字段，避免计算不可靠的指标。
- **任务难度不同：** 分组比较，不能直接做纵向快慢结论。
- **多种错误同时出现：** 记录主要错误和次要错误，避免强行单因解释。
- **用户自评与表现冲突：** 温和呈现差异，并安排一个小测试验证。

## References

- [Metrics and interpretation](references/metrics-and-interpretation.md)
- [Record schemas](references/record-schemas.md)
- [Post-study review template](../../templates/post-study.md)
