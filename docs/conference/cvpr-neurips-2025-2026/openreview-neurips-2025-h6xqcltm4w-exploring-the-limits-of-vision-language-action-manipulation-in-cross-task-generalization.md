---
title: Exploring the Limits of Vision-Language-Action Manipulation in Cross-task Generalization
title_zh: 探索视觉-语言-动作操作在跨任务泛化中的极限
authors: "Jiaming Zhou, Ke Ye, Jiayi LIU, Teli Ma, Zifan Wang, Ronghe Qiu, Kun-Yu Lin, Zhilin Zhao, Junwei Liang"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=h6xQClTm4W"
tags: ["query:vla"]
score: 6.0
evidence: 评估VLA操作跨任务泛化的基准
tldr: VLA模型对未见任务的泛化能力是实现开放世界通用机器人操作的关键，但现有VLA的跨任务泛化能力研究不足。本文提出AGNOSTOS，一个用于严格评估操作中跨任务零样本泛化的仿真基准，包含23个与常见训练分布不同的未见操作任务，并设置两级泛化难度评估鲁棒性。系统评测表明，即便在多样数据上训练，当前VLA模型仍难以泛化。该基准揭示了VLA泛化的局限，为后续研究提供评估工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: VLA模型对未见任务的泛化能力是通用机器人操作的关键，但现有模型的跨任务泛化能力研究不足。
method: 提出AGNOSTOS仿真基准，包含23个未见操作任务与两级泛化难度，用于评估VLA零样本跨任务泛化。
result: 系统评测显示当前VLA模型即便在多样数据上训练，仍难以泛化到未见任务。
conclusion: 该基准揭示了VLA跨任务泛化的局限，为评估与改进提供工具。
---

## Abstract
The generalization capabilities of vision-language-action (VLA) models to unseen tasks are crucial to achieving general-purpose robotic manipulation in open-world settings.
However, the cross-task generalization capabilities of existing VLA models remain significantly underexplored.
To address this gap, we introduce **AGNOSTOS**, a novel simulation benchmark designed to rigorously evaluate cross-task zero-shot generalization in manipulation. 
AGNOSTOS comprises 23 unseen manipulation tasks for test—distinct from common training task distributions—and incorporates two levels of generalization difficulty to assess robustness. 
Our systematic evaluation reveals that current VLA models, despite being trained on diverse datasets, struggle to generalize effectively to these unseen tasks. 
To overcome this limitation, we propose **Cross-Task In-Context Manipulation (X-ICM)**, 
a method that conditions large language models (LLMs) on in-context demonstrations from seen tasks to predict action sequences for unseen tasks.
Additionally, we introduce a **dynamics-guided sample selection** strategy that identifies relevant demonstrations by capturing cross-task dynamics. 
On AGNOSTOS, X-ICM significantly improves cross-task zero-shot generalization performance over leading VLAs, achieving improvements of 6.0\% over $\pi_0$ and 7.9\% over VoxPoser.
We believe AGNOSTOS and X-ICM will serve as valuable tools for advancing general-purpose robotic manipulation.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
评估VLA操作跨任务泛化的基准。

### 2. 核心内容
VLA模型对未见任务的泛化能力是实现开放世界通用机器人操作的关键，但现有VLA的跨任务泛化能力研究不足。本文提出AGNOSTOS，一个用于严格评估操作中跨任务零样本泛化的仿真基准，包含23个与常见训练分布不同的未见操作任务，并设置两级泛化难度评估鲁棒性。系统评测表明，即便在多样数据上训练，当前VLA模型仍难以泛化。该基准揭示了VLA泛化的局限，为后续研究提供评估工具。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=h6xQClTm4W](https://openreview.net/forum?id=h6xQClTm4W)
