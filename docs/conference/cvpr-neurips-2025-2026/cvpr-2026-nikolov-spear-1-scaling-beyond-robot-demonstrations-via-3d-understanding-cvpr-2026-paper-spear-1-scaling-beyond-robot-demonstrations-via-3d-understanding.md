---
title: "SPEAR-1: Scaling Beyond Robot Demonstrations via 3D Understanding"
title_zh: SPEAR-1：通过三维理解超越机器人演示数据扩展
authors: "Nikolov, Nikolay, Albanese, Giuliano, Dey, Sombit, Yanev, Aleksandar, Van Gool, Luc, Zaech, Jan-Nico, Paudel, Danda Pani"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Nikolov_SPEAR-1_Scaling_Beyond_Robot_Demonstrations_via_3D_Understanding_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 通过三维理解增强VLM以提升跨形态机器人控制
tldr: 机器人基础模型作为通用端到端控制系统的跨环境、任务与形态泛化能力有限，瓶颈在于其基于互联网预训练的视觉-语言模型缺乏三维空间推理。本文提出SPEAR-1，用三维标注增强易采集的非机器人图像数据，提升预训练VLM的三维理解能力，从而在机器人控制中实现更好的泛化。该方法为构建可跨形态泛化的视觉-语言-动作基础模型提供了新路径。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-nikolov-spear-1-scaling-beyond-robot-demonstrations-via-3d-understanding-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 3, \"index\": 1, \"width\": 968, \"height\": 613}]"
motivation: 机器人基础模型跨形态泛化差，因其视觉-语言主干缺乏三维空间推理能力。
method: 用三维标注增强非机器人图像，提升预训练视觉-语言模型的三维理解。
result: 增强了模型的三维空间理解与具身控制泛化能力。
conclusion: 该策略为构建跨形态泛化的机器人基础模型提供了可扩展路径。
---

## Abstract
Robotic Foundation Models (RFMs) hold great promise as generalist, end-to-end systems for robot control.Yet their ability to generalize across new environments, tasks, and embodiments remains limited.We argue that a major bottleneck lies in their foundations: most RFMs are built by fine-tuning internet-pretrained Vision-Language Models (VLMs).However, these VLMs are trained on 2D image-language tasks and lack the 3D spatial reasoning inherently required for embodied control in the 3D world.Bridging this gap directly with large-scale robotic data is costly and difficult to scale.Instead, we propose to enrich easy-to-collect non-robotic image data with 3D annotations and enhance a pretrained VLM with 3D understanding capabilities.Following this strategy, we train SPEAR-VLM, a 3D-aware VLM that infers object coordinates in 3D space from a single 2D image.Building on SPEAR-VLM, we introduce our main contribution, SPEAR-1: a robotic foundation model that integrates grounded 3D perception with language-instructed embodied control.Trained on ~45M frames from 24 Open X-Embodiment datasets, SPEAR-1 outperforms or matches state-of-the-art models such as \pi_0-FAST and \pi_ 0.5 , while it uses 20xfewer robot demonstrations.This carefully-engineered training strategy unlocks new VLM capabilities and as a consequence boosts the reliability of embodied control beyond what is achievable with only robotic data.We make our model weights and 3D-annotated datasets publicly available.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **核心问题**：机器人基础模型（RFMs）虽有望成为通用端到端控制方案，但在新环境、新任务和新形态上的泛化能力仍有限。
- **作者判断的瓶颈**：多数 RFM 通过微调互联网预训练的视觉-语言模型（VLM）构建，而这些 VLM 主要学习 2D 图像-语言任务，缺乏 3D 世界具身控制所需的 3D 空间推理能力。
- **现有路径的问题**：直接用大规模机器人数据弥补 2D 到 3D 的鸿沟成本高、难扩展。
- **整体含义**：论文提出用易采集的非机器人 2D 图像加 3D 标注来增强 VLM 的 3D 理解，再接入机器人控制，从而减少对昂贵机器人演示数据的依赖。SPEAR-1 在约 45M 帧、24 个 Open X-Embodiment 数据集上训练，却可媲美或超过使用约 20 倍更多机器人演示数据的 π0-FAST、π0.5 等模型。

## 2. 方法论

### 2.1 总体思路

- 分阶段训练：
  - **Stage 0**：通用 VLM 预训练，如 PaliGemma。
  - **Stage 1**：构建 3D 感知 VLM，即 **SPEAR-VLM**，用非机器人 2D 图像 + 3D 标注学习空间推理。
  - **Stage 2**：在 SPEAR-VLM 上加入动作专家，训练机器人基础模型 **SPEAR-1**。
- 核心目标：先让 VLM 获得控制相关的 3D 空间理解，再学习语言指令下的具身动作。

### 2.2 SPEAR-VLM

- **架构**：
  - 基于 PaliGemma，包括 SigLIP 视觉编码器、线性投影器和 Gemma 语言模型。
  - 额外集成 **MoGe 单目深度编码器**，提供深度/点云相关特征。
  - 取 MoGe ViT 编码器最后 4 层中间特征，拼接后经随机初始化线性投影到 LLM 嵌入空间。
  - LLM 的视觉输入为 SigLIP 与 MoGe 投影输出的平均。
  - 扩展 tokenizer，增加 **1024 个 3D token**，用于表示 3D 信息。
- **3D 预训练任务**：
  - 设计接近具身控制的 VQA 任务，如：
    - 输出物体 3D 包围盒顶点；
    - 输出物体间 xyz 距离；
    - 输出物体最近点、最远
