---
title: Generalizable Domain Adaptation for Sim-and-Real Policy Co-Training
title_zh: 面向仿真与真实策略协同训练的泛化域自适应
authors: "Shuo Cheng, Liqian Ma, Zhenyang Chen, Ajay Mandlekar, Caelan Reed Garrett, Danfei Xu"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=ufKaXYJt1F"
tags: ["query:vla"]
score: 5.0
evidence: 通过域自适应实现仿真到真实策略迁移
tldr: 该文针对机器人操作中真实演示采集成本高昂、仿真到真实迁移受域差异阻碍的问题，提出统一的仿真与真实协同训练框架。方法核心是学习域不变且任务相关的特征空间，通过对齐跨域观测与动作的联合分布来缩小域差距，仅需少量真实演示。实验表明该框架能有效提升策略在真实世界的泛化能力，为低成本机器人策略学习提供了可迁移的域自适应思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 真实机器人演示成本高，仿真到真实迁移受域差异阻碍。
method: 提出仿真与真实协同训练框架，学习域不变且任务相关的特征空间并对齐跨域联合分布。
result: 仅需少量真实演示即可提升真实世界泛化能力。
conclusion: 为低成本、可迁移的机器人策略学习提供了域自适应方案。
---

## Abstract
Behavior cloning has shown promise for robot manipulation, but real-world demonstrations are costly to acquire at scale. While simulated data offers a scalable alternative, particularly with advances in automated demonstration generation, transferring policies to the real world is hampered by various simulation and real domain gaps. In this work, we propose a unified sim-and-real co-training framework for learning generalizable manipulation policies that primarily leverages simulation and only requires a few real-world demonstrations. Central to our approach is learning a domain-invariant, task-relevant feature space. Our key insight is that aligning the joint distributions of observations and their corresponding actions across domains provides a richer signal than aligning observations (marginals) alone. We achieve this by embedding an Optimal Transport (OT)-inspired loss within the co-training framework, and extend this to an Unbalanced OT framework to handle the imbalance between abundant simulation data and limited real-world examples. We validate our method on challenging manipulation tasks, showing it can leverage abundant simulation data to achieve up to a 30\% improvement in the real-world success rate and even generalize to scenarios seen only in simulation.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
通过域自适应实现仿真到真实策略迁移。

### 2. 核心内容
该文针对机器人操作中真实演示采集成本高昂、仿真到真实迁移受域差异阻碍的问题，提出统一的仿真与真实协同训练框架。方法核心是学习域不变且任务相关的特征空间，通过对齐跨域观测与动作的联合分布来缩小域差距，仅需少量真实演示。实验表明该框架能有效提升策略在真实世界的泛化能力，为低成本机器人策略学习提供了可迁移的域自适应思路。

### 3. 对应检索需求
transfer learning across different robot embodiments。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=ufKaXYJt1F](https://openreview.net/forum?id=ufKaXYJt1F)
