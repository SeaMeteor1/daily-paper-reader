---
title: "VLA-Cache: Efficient Vision-Language-Action Manipulation via Adaptive Token Caching"
title_zh: VLA-Cache：通过自适应令牌缓存实现高效的视觉-语言-动作操作
authors: "Siyu Xu, Yunke Wang, Chenghao Xia, Dihao Zhu, Tao Huang, Chang Xu"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=QZYZ0Xm58q"
tags: ["query:vla"]
score: 8.0
evidence: 面向机器人操作的VLA模型推理加速
tldr: 视觉-语言-动作模型虽能端到端地由视觉与语言生成动作，但其巨大算力开销难以支撑机器人的实时控制。本文提出VLA-Cache，一种免训练推理加速方法，利用操作过程的时间连续性，识别相邻帧间变化极小的静态视觉令牌并复用其缓存键值表示，从而跳过冗余计算。实验表明该方法在保持操作性能的同时显著降低计算开销。该工作为VLA模型在真实机器人上的高效实时部署提供了实用方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: VLA模型推理开销大，难以满足机器人实时控制的需求。
method: 提出免训练的自适应令牌缓存方法，复用相邻帧间变化极小的静态视觉令牌的键值表示。
result: 在机器人操作任务中显著降低计算量并加速推理，同时保持动作生成质量。
conclusion: 为VLA模型的实时机器人部署提供了高效且即插即用的加速方案。
---

## Abstract
Vision-Language-Action (VLA) models have demonstrated strong multi-modal reasoning capabilities, enabling direct action generation from visual perception and language instructions in an end-to-end manner. However, their substantial computational cost poses a challenge for real-time robotic control, where rapid decision-making is essential. This paper introduces VLA-Cache, a training-free inference acceleration method that reduces computational overhead by adaptively caching and reusing static visual tokens across frames. Exploiting the temporal continuity in robotic manipulation, VLA-Cache identifies minimally changed tokens between adjacent frames and reuses their cached key-value representations, thereby circumventing redundant computations. Additionally, to maintain action precision, VLA-Cache selectively re-computes task-relevant tokens that are environmentally sensitive, ensuring the fidelity of critical visual information. To further optimize efficiency, we introduce a layer adaptive token reusing strategy that dynamically adjusts the reuse ratio based on attention concentration across decoder layers, prioritizing critical tokens for recomputation. Extensive experiments on two simulation platforms (LIBERO and SIMPLER) and a real-world robotic system demonstrate that VLA-Cache achieves up to 1.7× speedup in CUDA latency and a 15\% increase in control frequency, with negligible loss on task success rate. The code and videos can be found at our project page: https://vla-cache.github.io.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
面向机器人操作的VLA模型推理加速。

### 2. 核心内容
视觉-语言-动作模型虽能端到端地由视觉与语言生成动作，但其巨大算力开销难以支撑机器人的实时控制。本文提出VLA-Cache，一种免训练推理加速方法，利用操作过程的时间连续性，识别相邻帧间变化极小的静态视觉令牌并复用其缓存键值表示，从而跳过冗余计算。实验表明该方法在保持操作性能的同时显著降低计算开销。该工作为VLA模型在真实机器人上的高效实时部署提供了实用方案。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=QZYZ0Xm58q](https://openreview.net/forum?id=QZYZ0Xm58q)
