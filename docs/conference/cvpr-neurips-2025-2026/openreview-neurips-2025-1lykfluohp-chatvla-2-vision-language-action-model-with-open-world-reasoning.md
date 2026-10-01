---
title: "ChatVLA-2: Vision-Language-Action Model with Open-World Reasoning"
title_zh: ChatVLA-2：具备开放世界推理能力的视觉-语言-动作模型
authors: "Zhongyi Zhou, Yichen Zhu, Xiaoyu Liu, Zhibin Tang, Junjie Wen, Yaxin Peng, Chaomin Shen, Yi Xu"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=1lyKflUOhp"
tags: ["query:vla"]
score: 7.0
evidence: 保留VLM开放世界推理的泛化VLA
tldr: 该文针对现有端到端VLA在微调适配特定机器人任务时丢失预训练VLM核心能力的问题，主张泛化VLA应保留并扩展开放世界推理与推理跟随能力。作者提出ChatVLA-2框架，使模型既能识别VLM可识别的对象、完成数学与视觉空间推理，又能将其转化为可执行的机器人步骤。实验表明该框架在保持推理能力的同时提升操作泛化，为通用VLA模型设计提供了新方向。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 端到端VLA在微调适配特定任务时会丢失预训练VLM的开放世界推理能力。
method: 提出ChatVLA-2框架，保留并扩展VLM的开放世界推理与推理跟随能力。
result: 在保持推理能力的同时提升机器人操作泛化性。
conclusion: 为兼顾推理与操作的通用VLA设计提供了新方向。
---

## Abstract
Vision-language-action (VLA) models have emerged as the next generation of models in robotics. However, despite leveraging powerful pre-trained Vision-Language Models (VLMs), existing end-to-end VLA systems often lose key capabilities during fine-tuning as the model adapts to specific robotic tasks. We argue that a generalizable VLA model should retain and expand upon the VLM's core competencies: 1) **Open-world reasoning** - the VLA should inherit the knowledge from VLM, i.e., recognize anything that the VLM can recognize, capable of solving math problems, possessing visual-spatial intelligence, 2) **Reasoning following** – effectively translating the open-world reasoning into actionable steps for the robot. In this work, we introduce **ChatVLA-2**, a novel mixture-of-expert VLA model coupled with a specialized three-stage training pipeline designed to preserve the VLM’s original strengths while enabling actionable reasoning. To validate our approach, we design a math-matching task wherein a robot interprets math problems written on a whiteboard and picks corresponding number cards from a table to solve equations. Remarkably, our method exhibits exceptional mathematical reasoning and OCR capabilities, despite these abilities not being explicitly trained within the VLA. Furthermore, we demonstrate that the VLA possesses strong spatial reasoning skills, enabling it to interpret novel directional instructions involving previously unseen objects. Overall, our method showcases reasoning and comprehension abilities that significantly surpass state-of-the-art imitation learning methods such as OpenVLA, DexVLA, and $\pi_0$. This work represents a substantial advancement toward developing truly generalizable robotic foundation models endowed with robust reasoning capacities.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
保留VLM开放世界推理的泛化VLA。

### 2. 核心内容
该文针对现有端到端VLA在微调适配特定机器人任务时丢失预训练VLM核心能力的问题，主张泛化VLA应保留并扩展开放世界推理与推理跟随能力。作者提出ChatVLA-2框架，使模型既能识别VLM可识别的对象、完成数学与视觉空间推理，又能将其转化为可执行的机器人步骤。实验表明该框架在保持推理能力的同时提升操作泛化，为通用VLA模型设计提供了新方向。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=1lyKflUOhp](https://openreview.net/forum?id=1lyKflUOhp)
