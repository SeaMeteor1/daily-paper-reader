---
title: "Joint-Aligned Latent Action: Towards Scalable VLA Pretraining in the Wild"
title_zh: 联合对齐潜在动作：面向野外可扩展VLA预训练
authors: "Luo, Hao, Wang, Ye, Zhang, Wanpeng, Yuan, Haoqi, Feng, Yicheng, Xu, Haiweng, Zheng, Sipeng, Lu, Zongqing"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Luo_Joint-Aligned_Latent_Action_Towards_Scalable_VLA_Pretraining_in_the_Wild_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 异构数据上的VLA预训练
tldr: 视觉-语言-动作模型受限于大规模多样机器人数据的稀缺，而野外人类操作视频虽有潜力却缺乏可靠标注。本文提出JALA预训练框架，学习与逆动力学及真实动作联合对齐的预测性潜在动作嵌入，构建以行为为中心的过渡感知潜在空间。作者构建含750万视频、超2000小时的UniHand-Mix语料进行规模化预训练。该工作为从异构人类数据学习通用VLA策略提供了可扩展方案。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 720, \"height\": 544}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 478, \"height\": 418}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 1344, \"height\": 768}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 4, \"index\": 4, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 4, \"index\": 5, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 4, \"index\": 6, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 4, \"index\": 7, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 4, \"index\": 8, \"width\": 604, \"height\": 349}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 4, \"index\": 9, \"width\": 672, \"height\": 384}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 8, \"index\": 10, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 8, \"index\": 11, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 8, \"index\": 12, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 8, \"index\": 13, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-luo-joint-aligned-latent-action-towards-scalable-vla-pretraining-in-the-wild-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 512, \"height\": 512}]"
motivation: VLA模型受限于大规模多样机器人数据稀缺，而人类操作视频虽有潜力但标注不可靠。
method: 提出JALA预训练框架，学习与逆动力学和真实动作联合对齐的预测性潜在动作嵌入。
result: 构建含750万视频、超2000小时的UniHand-Mix语料，实现异构人类数据上的可扩展预训练。
conclusion: 该框架为从野外异构数据学习通用VLA策略提供了可扩展路径。
---

## Abstract
Despite progress, Vision-Language-Action models (VLAs) are limited by a scarcity of large-scale, diverse robot data. While human manipulation videos offer a rich alternative, existing methods are forced to choose between small, precisely-labeled datasets and vast in-the-wild footage with unreliable hand tracking labels. We present JALA, a pretraining framework that learns Jointly-Aligned Latent Actions. JALA bypasses full visual dynamic reconstruction, instead learns a predictive action embedding aligned with both inverse dynamics and real actions. This yields a transition-aware, behavior-centric latent space for learning from heterogeneous human data. We scale this approach with UniHand-Mix, a 7.5M video corpus (>2,000 hours) blending laboratory and in-the-wild footage. Experiments demonstrate that JALA generates more realistic hand motions in both controlled and unconstrained scenarios, significantly improving downstream robot manipulation performance in both simulation and real-world tasks. These results indicate that jointly-aligned latent actions offer a scalable pathway for VLA pretraining from human data.

---

## 论文详细总结（自动生成）

# 论文总结：Joint-Aligned Latent Action（JALA）

## 1. 核心问题与整体含义
- **研究动机**：视觉-语言-动作模型（VLA）受限于大规模、多样化机器人数据的稀缺；人类操作视频是有潜力的替代数据源，但存在“质量—多样性”权衡。
- **数据困境**：
  - 实验室数据：有精确 3D 手部跟踪/MANO 标注，但场景受控、多样性低。
  - 野外视频：场景丰富、行为自然，但缺乏可靠动作标签，手部跟踪噪声大。
- **核心问题**：如何有效结合标注与未标注人类视频，扩展 VLA 预训练？
- **整体含义**：论文提出 JALA，通过“联合对齐潜在动作”构建统一的、行为中心的潜在动作空间，使 VLA 能同时从实验室数据和野外视频中学习，为可扩展 VLA 预训练提供新路径。

## 2. 方法论
### 2.1 核心思想
- 不依赖完整视频动态重建，而是学习**预测性动作嵌入** \(h\)，使其同时对齐：
  - 逆动力学模型（IDM）产生的潜在动作 \(z\)；
  - 可用时的真实动作/运动标签。
- 由此得到“可从上下文预测、又编码视觉动态和动作语义”的统一潜在动作空间，兼容有标注和无标注人类视频。

### 2.2 关键技术细节
- **模型基础**：基于 Transformer 的 VLA，使用 InternVL3-2B 作为骨干，处理视觉 token、指令 token 和运动 token。
- **预测嵌入**：从预设注意力层（第 19 层，共 28 层）提取运动 token 的隐藏状态 \(h_{i,k}\)，作为预测性动作嵌入。
- **Masked Chunk Prediction（MCP）**：对有标注数据，将运动 chunk 中 token 替换为 `[MASK]`，用双向注意力在 chunk 内联合建模，预测原始运动 token，提供运动标签监督。
- **Latent Action Perceiver（LAP）**：作为逆动力学模块，输入 chunk 起始帧和结束帧，输出 \(K\) 个潜在动作向量 \(z_{i,k}\)，捕捉 chunk 级视觉动态。
- **联合对齐损失**：将预测嵌入 \(h_{i,k}\) 与潜在动作 \(z_{i,k}\) 做 L1 对齐。
- **Latent State Perceiver（LSP）**：与 LAP 配对，把 VLM 的预测上下文映射到同一潜在动作空间，缓解视觉
