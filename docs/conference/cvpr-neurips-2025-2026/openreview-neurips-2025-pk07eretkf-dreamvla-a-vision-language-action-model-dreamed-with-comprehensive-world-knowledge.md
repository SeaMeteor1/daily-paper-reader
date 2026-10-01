---
title: "DreamVLA: A Vision-Language-Action Model Dreamed with Comprehensive World Knowledge"
title_zh: DreamVLA：以综合世界知识构筑的视觉-语言-动作模型
authors: "Wenyao Zhang, Hongsi Liu, Zekun Qi, Yunnan Wang, XinQiang Yu, Jiazhao Zhang, Runpei Dong, Jiawei He, He Wang, Zhizheng Zhang, Li Yi, Wenjun Zeng, Xin Jin"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=PK07eretkF"
tags: ["query:vla"]
score: 7.0
evidence: 融合世界知识预测的VLA操作框架
tldr: 现有VLA方法虽将图像生成与动作预测结合以提升泛化与推理，但局限于图像式预测，存在冗余信息且缺乏动态、空间与语义等世界知识。DreamVLA提出融合综合世界知识预测的VLA框架，通过动态区域引导的世界知识预测支撑逆动力学建模。由此建立面向操作任务的感知-预测-动作闭环，提升机器人在复杂环境中的泛化与推理能力，为VLA引入更全面的世界知识建模。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 现有VLA方法局限于图像式预测，存在信息冗余且缺乏动态、空间与语义等关键世界知识。
method: 提出DreamVLA框架，引入综合世界知识预测以支持逆动力学建模，构建感知-预测-动作闭环。
result: 融合动态区域引导的世界知识预测后，模型在操作任务中的泛化与推理表现得到提升。
conclusion: 综合世界知识建模为VLA机器人操作提供更全面的推理基础。
---

## Abstract
Recent advances in vision-language-action (VLA) models have shown promise in integrating image generation with action prediction to improve generalization and reasoning in robot manipulation.  However, existing methods are limited to challenging image-based forecasting, which suffers from redundant information and lacks comprehensive and critical world knowledge, including dynamic, spatial and semantic information.
To address these limitations, we propose DreamVLA, a novel VLA framework that integrates comprehensive world knowledge forecasting to enable inverse dynamics modeling, thereby establishing a perception-prediction-action loop for manipulation tasks. 
Specifically, DreamVLA introduces a dynamic-region-guided world knowledge prediction,  integrated with the spatial and semantic cues, which provide compact yet comprehensive representations for action planning.
This design aligns with how humans interact with the world by first forming abstract multimodal reasoning chains before acting.
To mitigate interference among the dynamic, spatial and semantic information during training, we adopt a block-wise structured attention mechanism that masks their mutual attention, preventing information leakage and keeping each representation clean and disentangled.
Moreover, to model the conditional distribution over future actions, we employ a diffusion-based transformer that disentangles action representations from shared latent features.
Extensive experiments on both real-world and simulation environments demonstrate that DreamVLA achieves 76.7 success rate on real robot tasks and 4.44 average length on the CALVIN ABC-D benchmarks.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
融合世界知识预测的VLA操作框架。

### 2. 核心内容
现有VLA方法虽将图像生成与动作预测结合以提升泛化与推理，但局限于图像式预测，存在冗余信息且缺乏动态、空间与语义等世界知识。DreamVLA提出融合综合世界知识预测的VLA框架，通过动态区域引导的世界知识预测支撑逆动力学建模。由此建立面向操作任务的感知-预测-动作闭环，提升机器人在复杂环境中的泛化与推理能力，为VLA引入更全面的世界知识建模。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=PK07eretkF](https://openreview.net/forum?id=PK07eretkF)
