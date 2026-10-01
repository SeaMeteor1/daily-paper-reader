---
title: "From Experts to a Generalist: Toward General Whole-Body Control for Humanoid Robots"
title_zh: 从专家到通才：面向人形机器人的通用全身控制
authors: "Yuxuan Wang, Ming Yang, Ziluo Ding, Yu Zhang, Weishuai Zeng, Xinrun Xu, Haobin Jiang, Zongqing Lu"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=ZBSkyMwdEB"
tags: ["query:vla"]
score: 5.0
evidence: 专家-通才策略，类似一脑多体思想
tldr: 人形机器人通用敏捷全身控制面临动作多样与数据冲突难题，现有方法只能训练单一动作专用策略，难以泛化。本文提出BumbleBee专家-通才学习框架，先用自编码器聚类将行为相似的动作分组并训练专家策略，再结合仿真到现实适配将其整合为通用控制器。该方法在多样化全身动作上提升了泛化能力，其专家-通才思路对多形态共享策略具有借鉴意义。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 人形机器人全身控制难以泛化到多样动作，存在控制需求冲突与数据分布不匹配。
method: 用自编码器聚类动作并训练专家策略，再经仿真到现实适配蒸馏为通才控制器。
result: 在多种全身动作上实现了更强的泛化与敏捷控制能力。
conclusion: 专家-通才框架为通用全身控制提供思路，可启发多形态共享策略研究。
---

## Abstract
Achieving general agile whole-body control on humanoid robots remains a major challenge due to diverse motion demands and data conflicts. While existing frameworks excel in training single motion-specific policies, they struggle to generalize across highly varied behaviors due to conflicting control requirements and mismatched data distributions. In this work, we propose BumbleBee (BB), an expert-generalist learning framework that combines motion clustering and sim-to-real adaptation to overcome these challenges. BB first leverages an autoencoder-based clustering method to group behaviorally similar motions using motion features and motion descriptions. Expert policies are then trained within each cluster and refined with real-world data through iterative delta action modeling to bridge the sim-to-real gap. Finally, these experts are distilled into a unified generalist controller that preserves agility and robustness across all motion types. Experiments on two simulations and a real humanoid robot demonstrate that BB achieves state-of-the-art general whole-body control, setting a new benchmark for agile, robust, and generalizable humanoid performance in the real world.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
专家-通才策略，类似一脑多体思想。

### 2. 核心内容
人形机器人通用敏捷全身控制面临动作多样与数据冲突难题，现有方法只能训练单一动作专用策略，难以泛化。本文提出BumbleBee专家-通才学习框架，先用自编码器聚类将行为相似的动作分组并训练专家策略，再结合仿真到现实适配将其整合为通用控制器。该方法在多样化全身动作上提升了泛化能力，其专家-通才思路对多形态共享策略具有借鉴意义。

### 3. 对应检索需求
Approaches for one brain multiple bodies: learning a shared policy for heterogeneous robots。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=ZBSkyMwdEB](https://openreview.net/forum?id=ZBSkyMwdEB)
