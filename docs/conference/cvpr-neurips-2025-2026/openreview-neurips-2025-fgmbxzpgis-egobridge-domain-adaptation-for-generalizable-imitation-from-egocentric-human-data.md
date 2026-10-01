---
title: "EgoBridge: Domain Adaptation for Generalizable Imitation from Egocentric Human Data"
title_zh: EgoBridge：从第一人称人类数据实现可泛化模仿的域自适应
authors: "Ryan Punamiya, Dhruv Patel, Patcharapong Aphiwetsa, Pranav Kuppili, Lawrence Y. Zhu, Simar Kareer, Judy Hoffman, Danfei Xu"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=FGMBxzpgis"
tags: ["query:vla"]
score: 5.0
evidence: 通过域自适应将模仿策略从人到机器人迁移
tldr: 第一人称人类经验数据可用于扩展机器人端到端模仿学习，但人机之间在视觉外观、传感模态与运动学上的域差异阻碍了知识迁移。本文提出EgoBridge统一协同训练框架，通过基于最优传输的策略隐特征与动作差异度量，显式对齐人与机器人的策略隐空间。学到的观测表征既对齐两个域，又保留对策略学习关键的动作相关信息。该框架显著提升了从人类数据向机器人迁移的泛化能力，为跨域策略迁移提供方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 人类第一人称数据可扩展机器人模仿学习，但人机在视觉外观、传感模态与运动学上的域差异阻碍知识迁移。
method: 提出EgoBridge协同训练框架，用基于最优传输的策略隐特征与动作差异度量显式对齐人与机器人策略隐空间。
result: 学到的表征既对齐人机域又保留动作相关信息，显著提升跨域迁移的泛化能力。
conclusion: 域自适应对齐策略隐空间可有效实现从人类数据到机器人的策略迁移。
---

## Abstract
Egocentric human experience data presents a vast resource for scaling up end-to-end imitation learning for robotic manipulation. However, significant domain gaps in visual appearance, sensor modalities, and kinematics between human and robot impede knowledge transfer. This paper presents EgoBridge, a unified co-training framework that explicitly aligns the policy latent spaces between human and robot data using domain adaptation. Through a measure of discrepancy on the joint policy latent features and actions based on Optimal Transport (OT), we learn observation representations that not only align between the human and robot domain but also preserve the action-relevant information critical for policy learning. EgoBridge achieves a significant absolute policy success rate improvement by 44% over human-augmented cross-embodiment baselines in three real-world single-arm and bimanual manipulation tasks. EgoBridge also generalizes to new objects, scenes, and tasks seen only in human data, where baselines fail entirely. Videos and additional information can be found at https://ego-bridge.github.io/

---

## 论文详细总结（自动生成）

### 1. 检索相关性
通过域自适应将模仿策略从人到机器人迁移。

### 2. 核心内容
第一人称人类经验数据可用于扩展机器人端到端模仿学习，但人机之间在视觉外观、传感模态与运动学上的域差异阻碍了知识迁移。本文提出EgoBridge统一协同训练框架，通过基于最优传输的策略隐特征与动作差异度量，显式对齐人与机器人的策略隐空间。学到的观测表征既对齐两个域，又保留对策略学习关键的动作相关信息。该框架显著提升了从人类数据向机器人迁移的泛化能力，为跨域策略迁移提供方案。

### 3. 对应检索需求
transfer learning across different robot embodiments。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=FGMBxzpgis](https://openreview.net/forum?id=FGMBxzpgis)
