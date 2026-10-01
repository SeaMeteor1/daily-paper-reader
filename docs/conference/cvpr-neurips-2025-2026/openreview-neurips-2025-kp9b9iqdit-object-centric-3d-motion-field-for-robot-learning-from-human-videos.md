---
title: Object-centric 3D Motion Field for Robot Learning from Human Videos
title_zh: 面向人类视频机器人学习的以物体为中心的三维运动场
authors: "Zhao-Heng Yin, Sherry Yang, Pieter Abbeel"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=kp9B9iQDIt"
tags: ["query:vla"]
score: 4.0
evidence: 从人类视频学习机器人策略以实现零样本控制
tldr: 从人类视频学习机器人控制策略是扩展机器人学习的重要方向，但如何提取可用的动作知识仍是难题，现有视频帧、像素流与点云流等表示存在建模复杂或信息丢失的缺陷。本文提出以物体为中心的三维运动场作为动作表示，并设计去噪估计器从视频中提取该表示，用于零样本控制。该表示提升了动作知识提取的精度，为视频驱动的机器人学习提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 从人类视频提取动作知识用于机器人策略学习困难，现有动作表示存在局限。
method: 提出以物体为中心的三维运动场表示，并训练去噪估计器从视频中提取。
result: 实现更精细的动作表示提取，支持零样本机器人控制。
conclusion: 该表示为视频驱动的机器人学习提供了更有效的动作知识表示方式。
---

## Abstract
Learning robot control policies from human videos is a promising direction for scaling up robot learning. However, how to extract action knowledge (or action representations) from videos for policy learning remains a key challenge. Existing action representations such as video frames, pixelflow, and pointcloud flow have inherent limitations such as modeling complexity or loss of information. In this paper, we propose to use object-centric 3D motion field to represent actions for robot learning from human videos, and present a novel framework for extracting this representation from videos for zero-shot control. We introduce two novel components. First, a novel training pipeline for training a ``denoising'' 3D motion field estimator to extract fine object 3D motions from human videos with noisy depth robustly. Second, a dense object-centric 3D motion field prediction architecture that favors both cross-embodiment transfer and policy generalization to background. We evaluate the system in real world setups. Experiments show that our method reduces 3D motion estimation error by over 50% compared to the latest method, achieve 55% average success rate in diverse tasks where prior approaches fail ($\lesssim 10$\%), and can even acquire fine-grained manipulation skills like insertion.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
从人类视频学习机器人策略以实现零样本控制。

### 2. 核心内容
从人类视频学习机器人控制策略是扩展机器人学习的重要方向，但如何提取可用的动作知识仍是难题，现有视频帧、像素流与点云流等表示存在建模复杂或信息丢失的缺陷。本文提出以物体为中心的三维运动场作为动作表示，并设计去噪估计器从视频中提取该表示，用于零样本控制。该表示提升了动作知识提取的精度，为视频驱动的机器人学习提供了新思路。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=kp9B9iQDIt](https://openreview.net/forum?id=kp9B9iQDIt)
