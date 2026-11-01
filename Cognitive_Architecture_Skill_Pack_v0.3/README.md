# Cognitive Architecture — Personal Expert Skill Training System

**版本：v0.3（首套可用 Skill 文件）**  
**语言：中文为主，保留关键英文术语**  
**理论依据：James J. Staszewski, *Skill and Skilled Memory* (1990)**

## 1. 项目定位

这套 Skill 不是让 AI 代替用户记忆和推理，而是让 AI 作为认知教练、知识工程助手和检索助手，帮助用户逐步形成能够自主编码、组织、检索、调用和运用知识的认知机制。

系统区分三种成长对象：

1. **人脑认知能力**：自主编码、回忆、语义组织、模式识别、策略选择、推理和迁移。
2. **外部知识库质量**：知识单元、分类、关系、来源、精确值和检索锚点。
3. **AI 辅助能力**：任务规划、按需检索、提示控制、错误分析和训练调整。

外部知识库变丰富，不等于用户已经记住；AI 找到答案，不等于用户能够自主提取。训练记录必须区分这些结果。

## 2. 目录结构

```text
Cognitive_Architecture_Skill_Pack_v0.3/
├── README.md
├── skills/
│   ├── cognitive-architecture/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── knowledge-encoding/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── knowledge-retrieval/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── cognitive-training/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── memory-consolidation/
│   │   ├── SKILL.md
│   │   └── references/
│   └── performance-analysis/
│       ├── SKILL.md
│       └── references/
└── templates/
    ├── pre-study.md
    ├── in-session.md
    ├── post-study.md
    └── deep-review.md
```

## 3. 六个 Skill 的分工

| Skill | 责任 | 典型触发场景 |
|---|---|---|
| `cognitive-architecture` | 总控、识别当前情境、安排模块与交互流程 | 开始学习、综合复盘、请求认知训练计划 |
| `knowledge-encoding` | 捕获、分块、分类、语义编码、关系编码 | 新概念、新定理、新策略、新数字知识入库 |
| `knowledge-retrieval` | 精确、语义、层级、关系、数字检索 | 模糊回忆、查找旧定理、查找技术数字 |
| `cognitive-training` | 逻辑推理、非视觉推理、心算、模式与策略训练 | 出题、练习、解决问题、策略训练 |
| `memory-consolidation` | 无提示回忆、线索提取、抗干扰、复习安排 | 复习、回忆测试、相似概念辨析 |
| `performance-analysis` | 训练数据、错误类型、趋势、自适应决策 | 学习后复盘、阶段报告、训练计划调整 |

六个 Skill 是可分别安装的目录。支持多 Skill 的 Agent 可以按需加载；不支持 Skill 间自动调用的环境，应由总控 Skill 按路由规则指导使用者切换相应 Skill。

## 4. 安装方式

将 `skills/` 下的六个子目录分别放入目标 Agent 支持的 Skills 目录中。每个子目录本身就是一个独立 Skill。保留各自的 `references/` 文件夹，不要只复制 `SKILL.md`。

`templates/` 是用户可直接复制的汇报模板，不是独立 Skill。

## 5. 使用约定

- 默认先训练用户自主回忆和推理，再进行 AI 检索或解释。
- 默认不提前泄露题目答案；使用渐进式提示 H0—H5。
- 记录用户原始回答、提示等级、准确性、用时和策略；不要把 AI 辅助成功记成自主掌握。
- 精确数字、单位、符号、公式、定义条件和原始来源必须保留；模糊语义锚点只增加检索入口，不能覆盖原值。
- 只有在确有持久化工具或文件写入成功时，才声称“已保存/已更新”。否则生成可复制的结构化记录，并明确尚未写入持久知识库。
- 不要把每日汇报变成高负担长问卷。默认使用简化复盘；只有阶段性总结时才使用深度复盘。

## 6. 论文依据与适用边界

Staszewski (1990) 报告总结了数字跨度记忆训练和心算训练两项纵向研究。论文提出熟练记忆理论的三个原则：记忆存储原则、提取结构原则和加速原则；对 DD 的分析进一步讨论语义编码系统、提取结构和情境编码系统。心算研究还讨论了数字模式识别、计算策略选择、检索替代部分计算，以及减少中间结果的作用。

本套 Skill 将这些思想迁移为 AI 辅助的学习与训练设计。论文并未直接验证本 Skill 的实施效果，也没有证明这些机制会自动迁移到所有数学证明或一般推理任务。相关迁移应通过个人训练数据持续检验。

## 7. 行数要求

本包中的每个 `SKILL.md` 均少于 500 行。附属参考文件也保持短小，便于按需加载。
