# Metrics and Interpretation

## Metric groups

| Dimension | Observable indicator | Caveat |
|---|---|---|
| Encoding | 用户独立提炼条件、结论和语义锚点 | 不能只看 AI 生成的结构 |
| Retrieval | 无提示正确率、提示等级、回忆用时 | 题目熟悉度会影响表现 |
| Semantic organization | 正确关系数、区分性说明质量 | 关系数量多不等于关系正确 |
| Pattern recognition | 识别正确率、发现子问题情况 | 必须注明题目类别和难度 |
| Strategy selection | 策略适配性、理由、替代方案 | 更快不一定更稳或更准确 |
| Transfer | 在变化情境中能否正确调用知识 | 标明迁移距离 |

## Do not create a single composite score initially

六个维度可能不同步成长。初期分别展示趋势；只有在定义可靠、样本充分且用户认可时，才考虑汇总指标。

## Evidence strength

- **Observed**：实际回答或任务结果中直接可见。
- **Self-reported**：用户对自身表现的描述。
- **Inferred**：根据多次记录推断的可能原因。
- **Unverified**：尚无充分证据。

## Comparability checklist

比较两个任务前，检查：

- 是否为同一技能类别？
- 难度是否相近？
- 呈现方式是否相同？
- 提示等级是否相同？
- 计时起止点是否一致？
- 评分标准是否一致？

有重要差异时只做定性比较，或按类别分组。

## Recommended report

1. 本阶段可确认的进步（附任务证据）。
2. 仍然存在的瓶颈（区分事实和推断）。
3. 典型错误及其可能根因。
4. 下一轮 1—3 个训练目标。
5. 尚缺少哪些数据，才能验证趋势。
