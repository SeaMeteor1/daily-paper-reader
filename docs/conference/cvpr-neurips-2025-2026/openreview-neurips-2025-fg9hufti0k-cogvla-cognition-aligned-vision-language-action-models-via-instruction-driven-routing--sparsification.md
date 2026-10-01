---
title: "CogVLA: Cognition-Aligned Vision-Language-Action Models via Instruction-Driven Routing & Sparsification"
title_zh: CogVLA：基于指令驱动路由与稀疏化的认知对齐视觉-语言-动作模型
authors: "Wei Li, Renshan Zhang, Rui Shao, Jie He, Liqiang Nie"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=Fg9HufTI0K"
tags: ["query:vla"]
score: 6.0
evidence: 指令驱动路由与稀疏化的认知对齐VLA
tldr: 该文针对基于预训练视觉语言模型的VLA需要大量后训练、计算开销大而难以扩展部署的问题，指出现有稀疏化策略忽视视觉-语言-动作模态间语义耦合。作者提出认知对齐的VLA框架CogVLA，通过指令驱动的路由与稀疏化在感知到控制全流程中提升效率。实验表明该方法在提高效率的同时改善性能，为可扩展的VLA部署提供了新途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: VLA模型后训练计算开销大，现有稀疏化策略忽视跨模态语义耦合。
method: 提出认知对齐框架CogVLA，采用指令驱动路由与稀疏化提升端到端效率。
result: 在提升计算效率的同时改善整体性能。
conclusion: 为可扩展、可部署的VLA模型提供了高效方案。
---

## Abstract
Recent Vision-Language-Action (VLA) models built on pre-trained Vision-Language Models (VLMs) require extensive post-training, resulting in high computational overhead that limits scalability and deployment. Existing sparsification strategies—such as Mixture-of-Depths, layer skipping, and early exit—fall short by neglecting the semantic coupling across vision-language-action modalities, and focusing narrowly on intra-LLM computation while overlooking end-to-end coherence from perception to control. To address these challenges, we propose **CogVLA**, a Cognition-Aligned Vision-Language-Action framework that leverages instruction-driven routing and sparsification to improve both efficiency and performance. CogVLA draws inspiration from human multimodal coordination and introduces a 3-stage progressive architecture. 1) **Encoder-FiLM based Aggregation Routing (EFA-Routing)** injects instruction information into the vision encoder to selectively aggregate and compress dual-stream visual tokens, forming a instruction-aware latent representation. 2) Building upon this compact visual encoding, **LLM-FiLM based Pruning Routing (LFP-Routing)** introduces action intent into the language model by pruning instruction-irrelevant visually grounded tokens, thereby achieving token-level sparsity. 3) To ensure that compressed perception inputs can still support accurate and coherent action generation, we introduce **V‑L‑A Coupled Attention (CAtten)**, which combines causal vision-language attention with bidirectional action parallel decoding.
Extensive experiments on the LIBERO benchmark and real-world robotic tasks demonstrate that CogVLA achieves state-of-the-art performance with success rates of 97.4\% and 70.0\%, respectively, while reducing training costs by 2.5$\times$ and decreasing inference latency by 2.8$\times$ compared to OpenVLA.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
指令驱动路由与稀疏化的认知对齐VLA。

### 2. 核心内容
该文针对基于预训练视觉语言模型的VLA需要大量后训练、计算开销大而难以扩展部署的问题，指出现有稀疏化策略忽视视觉-语言-动作模态间语义耦合。作者提出认知对齐的VLA框架CogVLA，通过指令驱动的路由与稀疏化在感知到控制全流程中提升效率。实验表明该方法在提高效率的同时改善性能，为可扩展的VLA部署提供了新途径。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=Fg9HufTI0K](https://openreview.net/forum?id=Fg9HufTI0K)
