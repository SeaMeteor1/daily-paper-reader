---
title: "EgoRoC: Towards Egocentric Robotic Control via Task-Agnostic Visual Alignment"
title_zh: EgoRoC：通过任务无关视觉对齐实现以自我为中心的机器人控制
authors: "Feng, Wei, Zhang, Chi, Li, Nan, Zhang, Qian, Zhang, Qi, Li, Mingyan"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Feng_EgoRoC_Towards_Egocentric_Robotic_Control_via_Task-Agnostic_Visual_Alignment_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 解耦视觉与动作以支持跨硬件迁移的VLA模型
tldr: 现有端到端VLA模型将视觉理解与任务动作纠缠在一起，导致需收集完整操作序列、参数冗余，且第三人称相机设置因隐含手眼假设而难以跨硬件迁移。本文提出EgoRoC，一个即插即用的以自我为中心对齐头，置于任务策略之前，仅暴露6自由度位姿接口以建立任务无关的视角一致性。实验表明其能在不同硬件与视角下改善操作表现。该工作指出解耦机器人如何看与如何动是VLA系统的关键原语。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 782, \"height\": 504}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 458, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 6, \"index\": 3, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 6, \"index\": 4, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 6, \"index\": 5, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 6, \"index\": 6, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 6, \"index\": 7, \"width\": 720, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 6, \"index\": 8, \"width\": 720, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 6, \"index\": 9, \"width\": 720, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-egoroc-towards-egocentric-robotic-control-via-task-agnostic-visual-alignment-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 6, \"index\": 10, \"width\": 720, \"height\": 540}]"
motivation: 端到端VLA将视觉理解与任务动作纠缠，导致参数冗余且难以跨硬件迁移。
method: 提出即插即用的以自我为中心对齐头，前置任意任务策略，仅暴露6自由度位姿接口建立任务无关视角一致性。
result: 在无需微调的情况下改善跨硬件与视角下的操作表现。
conclusion: 解耦视觉与动作是VLA系统缺失的关键原语。
---

## Abstract
Recent Vision-Language-Action (VLA) models map visual-textual inputs to robotic actions via end-to-end architectures, yet this approach entangles visual understanding with task-specific actions. This leads to an exhaustive collection of full operational sequences and parameter redundancy across tasks, while generic third-person camera setups require fine-tuning for different hardware due to implicit hand-eye assumptions. We argue that decoupling how robots see from how robots act is a missing primitive in VLA systems. We present EgoRoC, a plug-and-play egocentric alignment head that precedes any task policy and exposes only a thin 6-DoF pose interface. EgoRoC establishes task-agnostic viewpoint consistency from a wrist-mounted (first-person) camera and then alternates alignment with manipulation, while a diffusion-based online hand-eye module corrects the action in the end-effector frame for hardware-agnostic deployment. Trained once from static wrist-target image pairs with relative poses, rather than full manipulation trajectories, EgoRoC leaves downstream VLAs unchanged. By turning egocentric alignment into a reusable capability, EgoRoC reduces training redundancy, strengthens zero-shot cross-scene transfer, and scales across VLA backbones without manual calibration. Across simulation and real settings, attaching EgoRoC consistently boosts success rates, especially on long-horizon and out-of-distribution tasks, and improves data efficiency during fine-tuning.

---

## 论文详细总结（自动生成）

# EgoRoC 论文中文总结

## 1. 核心问题与整体含义
- **研究动机**：现有 Vision-Language-Action
