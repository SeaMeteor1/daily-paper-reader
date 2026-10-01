---
title: "HybridVLA: Collaborative Autoregression and Diffusion in a Unified Vision-Language-Action Model"
title_zh: HybridVLA：统一视觉-语言-动作模型中的自回归与扩散协同
authors: "Jiaming Liu, Hao Chen, Pengju An, Zhuoyang Liu, Renrui Zhang, Chenyang Gu, Xiaoqi Li, Ziyu Guo, Sixiang Chen, Mengzhen Liu, Chengkai Hou, Mengdi Zhao, KC alex Zhou, Pheng-Ann Heng, Shanghang Zhang"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=8VyjwyLuSl"
tags: ["query:vla"]
score: 7.0
evidence: 结合自回归与扩散的统一VLA模型
tldr: 该文针对现有自回归VLA方法将动作离散化破坏控制连续性、扩散VLA又未充分利用VLM预训练推理能力的问题，提出统一的自回归与扩散协同VLA模型HybridVLA。方法在同一个视觉-语言-动作框架内融合两种动作生成范式，兼顾语义推理与连续精确控制。实验表明该模型能更好地理解指令并在动态环境中执行泛化动作，为VLA动作生成架构提供了新设计。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
motivation: 自回归VLA离散化动作破坏连续性，扩散VLA未充分利用VLM推理能力。
method: 提出HybridVLA，在同一框架内协同自回归与扩散两种动作生成范式。
result: 兼顾语义推理与连续精确控制，在动态环境中执行泛化动作。
conclusion: 为VLA的动作生成架构提供了融合式设计思路。
---

## Abstract
A fundamental objective of manipulation policy design is to endow robots to comprehend human instructions, reason about scene cues, and execute generalized actions in dynamic environments. Recent autoregressive vision-language-action (VLA) methods inherit common-sense reasoning capabilities from vision-language models (VLMs) for next action-token prediction. However, these methods quantize actions into discrete bins, which disrupts the continuity required for precise control. In contrast, existing diffusion-based VLA methods incorporate an additional diffusion head to predict continuous actions solely conditioned on feature representations extracted by the VLM, without fully leveraging the VLM’s pretrained reasoning capabilities through token-level generation. To address these limitations, we introduce HybridVLA, a unified framework that absorbs the continuous nature of diffusion-based actions and the contextual reasoning of autoregression within a single large language model. To mitigate interference between the two generation paradigms, we propose a collaborative training recipe that seamlessly incorporates diffusion denoising into the next-token prediction process. With this recipe, we find these two action prediction methods not only reinforce each other but also exhibit varying strength across different tasks. Therefore, we design a collaborative action ensemble mechanism that adaptively fuses both predictions, leading to more robust control. HybridVLA outperforms previous state-of-the-art VLA methods by 14\% and 19\% in mean success rate on simulation and real-world tasks, respectively, while demonstrating stable manipulation in unseen configurations.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
结合自回归与扩散的统一VLA模型。

### 2. 核心内容
该文针对现有自回归VLA方法将动作离散化破坏控制连续性、扩散VLA又未充分利用VLM预训练推理能力的问题，提出统一的自回归与扩散协同VLA模型HybridVLA。方法在同一个视觉-语言-动作框架内融合两种动作生成范式，兼顾语义推理与连续精确控制。实验表明该模型能更好地理解指令并在动态环境中执行泛化动作，为VLA动作生成架构提供了新设计。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Rejected-Public
- OpenReview：[https://openreview.net/forum?id=8VyjwyLuSl](https://openreview.net/forum?id=8VyjwyLuSl)
