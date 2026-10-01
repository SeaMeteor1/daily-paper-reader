---
title: "VideoVLA: Video Generators Can Be Generalizable Robot Manipulators"
title_zh: VideoVLA：视频生成器可成为可泛化的机器人操作器
authors: "Yichao Shen, Fangyun Wei, Zhiying Du, Yaobo Liang, Yan Lu, Jiaolong Yang, Nanning Zheng, Baining Guo"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=UPHlqbZFZB"
tags: ["query:vla"]
score: 7.0
evidence: 将视频生成模型改造为可泛化机器人VLA
tldr: 现有VLA模型虽借助大规模预训练理解模型进行感知与指令跟随，但在新任务、新物体与新环境上的泛化能力仍然有限。VideoVLA探索将大型视频生成模型转化为机器人VLA操作器的潜力，基于多模态扩散Transformer联合建模视频、语言与动作模态。给定语言指令与图像，模型同时预测动作序列与未来视觉结果。该工作提升了机器人在开放世界中的泛化能力，为利用生成模型做操作策略提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 现有VLA模型借助预训练理解模型做感知与指令跟随，但对新任务、新物体与新环境的泛化能力有限。
method: 提出VideoVLA，将大型视频生成模型改造成VLA操作器，用多模态扩散Transformer联合建模视频、语言与动作。
result: 模型可同时预测动作序列与未来视觉结果，增强了开放世界操作任务的泛化表现。
conclusion: 证明视频生成模型可作为可泛化的机器人VLA操作器。
---

## Abstract
Generalization in robot manipulation is essential for deploying robots in open-world environments and advancing toward artificial general intelligence. While recent Vision-Language-Action (VLA) models leverage large pre-trained understanding models for perception and instruction following, their ability to generalize to novel tasks, objects, and settings remains limited. In this work, we present VideoVLA, a simple approach that explores the potential of transforming large video generation models into robotic VLA manipulators. Given a language instruction and an image, VideoVLA predicts an action sequence as well as the future visual outcomes.  Built on a multi-modal Diffusion Transformer, VideoVLA jointly models video, language, and action modalities, using pre-trained video generative models for joint visual and action forecasting. Our experiments show that high-quality imagined futures correlate with reliable action predictions and task success, highlighting the importance of visual imagination in manipulation. VideoVLA demonstrates strong generalization, including imitating other embodiments' skills and handling novel objects. This dual-prediction strategy—forecasting both actions and their visual consequences—explores a paradigm shift in robot learning and unlocks generalization capabilities in manipulation systems.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
将视频生成模型改造为可泛化机器人VLA。

### 2. 核心内容
现有VLA模型虽借助大规模预训练理解模型进行感知与指令跟随，但在新任务、新物体与新环境上的泛化能力仍然有限。VideoVLA探索将大型视频生成模型转化为机器人VLA操作器的潜力，基于多模态扩散Transformer联合建模视频、语言与动作模态。给定语言指令与图像，模型同时预测动作序列与未来视觉结果。该工作提升了机器人在开放世界中的泛化能力，为利用生成模型做操作策略提供了新思路。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=UPHlqbZFZB](https://openreview.net/forum?id=UPHlqbZFZB)
