---
title: "Global Prior Meets Local Consistency: Dual-Memory Augmented Vision-Language-Action Model for Efficient Robotic Manipulation"
title_zh: 全局先验与局部一致性：面向高效机器人操作的双记忆增强视觉-语言-动作模型
authors: "Li, Zaijing, Hu, Bing, Shao, Rui, Chen, Gongwei, Jiang, Dongmei, Xie, Pengwei, Hao, Jianye, Nie, Liqiang"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Li_Global_Prior_Meets_Local_Consistency_Dual-Memory_Augmented_Vision-Language-Action_Model_for_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 双记忆增强VLA用于高效机器人操作
tldr: 该文针对分层视觉-语言-动作模型动作生成环节推理效率低、鲁棒性差的问题，指出现有方法受噪声先验与目标动作分布差距大、仅依赖当前观测而缺乏历史约束的制约。作者提出双记忆增强的VLA模型，通过全局先验与局部一致性约束改进行动生成过程。实验表明该方法能减少去噪步数、提升操作效率与鲁棒性，为高效VLA策略设计提供了新方案。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
motivation: 分层VLA模型在动作生成环节存在推理效率低与鲁棒性差的问题。
method: 提出双记忆增强VLA，用全局先验与局部一致性约束改进动作生成过程。
result: 减少去噪步数并提升操作效率与鲁棒性。
conclusion: 为高效鲁棒的VLA策略设计提供了新思路。
---

## Abstract
Hierarchical Vision-Language-Action (VLA) models have rapidly become a dominant paradigm for robotic manipulation. It typically comprising a Vision-Language backbone for perception and understanding, together with a generative policy for action generation. However, its performance is increasingly bottlenecked by the action generation proceess. (i) Low inference efficiency. A pronounced distributional gap between isotropic noise priors and target action distributions, which increases denoising steps and the incidence of infeasible samples. (ii) Poor robustness. Existing policies condition solely on the current observation, neglecting the constraint of history sequence and thus lacking awareness of task progress and temporal consistency. To address these issues, we introduce OptimusVLA, a dual-memory VLA framework with Global Prior Memory (GPM) and Local Consistency Memory (LCM). GPM replaces Gaussian noise with task-level priors retrieved from semantically similar trajectories, thereby shortening the generative path and reducing the umber of function evaluations (NFE). LCM dynamically models executed action sequence to infer task progress and injects a learned consistency constraint that enforces temporal coherence and smoothness of trajectory. Across three simulation benchmarks, OptimusVLA consistently outperforms strong baselines: it achieves 98.6% average success rate on LIBERO, improves over pi_0 by 13.5% on CALVIN, and attains 38% average success rate on RoboTwin 2.0 Hard. In Real-World evaluation, OptimusVLA ranks best on Generalization and Long-horizon suites, surpassing pi_0 by 42.9% and 52.4%, respectively, while delivering 2.9x inference speedup.

---

## 论文详细总结（自动生成）

# 论文中文总结：OptimusVLA——全局先验与局部一致性双记忆增强 VLA

## 1. 核心问题与整体含义
- **研究背景**：分层 Vision–Language–Action（VLA）模型已成为机器人操作的重要范式，通常由视觉–语言骨干负责感知与理解，生成式策略负责动作生成。
- **核心瓶颈**：论文指出动作生成环节成为性能瓶颈，主要体现在两方面：
  - **推理效率低**：标准 flow matching / diffusion 从各向同性高斯噪声出发，与结构化目标动作分布差距大，需要较多去噪步数（NFE），且容易采样到运动学不可行动作。
  - **鲁棒性差**：现有策略多只依赖当前观测，忽略历史动作序列，缺乏任务进度感知与时间一致性，导致视觉相似状态下行为不一致、控制抖动。
- **整体含义**：论文提出 **OptimusVLA**，用 **全局先验记忆（GPM）** 和 **局部一致性记忆（LCM）** 双记忆机制分别解决“先验–目标分布差距大”和“时间依赖缺失”问题，在提升成功率的同时显著加速推理。

## 2. 方法论
### 2.1 核心思想
- 在标准分层 VLA（视觉–语言骨干 + flow policy）上增加两个轻量记忆模块：
  - **GPM**：用从语义相似轨迹中检索得到的任务级动作先验，替代高斯噪声作为生成起点。
  - **LCM**：用近期已执行动作块建模局部时间一致性，并向策略输入注入一致性偏置。
- 最终动作生成仍由 flow policy 完成，但初始化更靠近目标动作流形，且带有历史一致性约束。

### 2.2 全局先验记忆（GPM）
- **Prior Head**：轻量 MLP 将多模态表示 \(E_{emb}\) 投影为检索 token \(z_{re}\)。
- **Memory Bank**：存储 \(M\) 个任务嵌入与完整轨迹的键值对 \(\{z_m, J_m\}\)；通过余弦相似度检索 \(k\) 个最近轨迹及其分数 \(s_i\)。
- **先验构造**：
  - 用 softmax 得到权重 \(\alpha_i = \mathrm{softmax}(s_i/\tau_s)\)，并计算归一化全局相似度 \(\bar{s}\)。
  - 从检索轨迹中按滑动窗口提取动作块 \(C_i\)，加权得到任务级先验均值 \(\mu\) 与方差 \(Var\)。
- **Prior-Aware Sampler**：
  - 根据相似度 \(\bar{s}\) 自适应设置噪声尺度 \(\lambda\) 和 NFE \(N\)：相似度越高，噪声越小、NFE 越少。
  - 采样初始化 \( \hat{X}_t = \mu + \lambda(\epsilon \odot \sqrt{Var})\)。
- **作用**：将生成起点从 \(N(0,I)\) 移到目标动作邻域，缩短生成路径，减少 NFE，并降低不可行采样风险；自适应噪声保留探索性，避免确定性坍缩。

### 2.3 局部一致性记忆（LCM）
- **Consistency Layer**：输入上一动作块 \(A_{t-1}\)，用自注意力建模动作间依赖，得到中间表示 \(\hat{B}_{t-1}\)。
- **Dynamic Awareness Module**：采用 Mamba 结构以线性复杂度建模跨块时间动态，预测一致性偏置 \(B_t\)。
- **注入方式**：最终策略输入为 \(X_t = \hat{X}_t + B_t\)，即全局先验采样结果加上局部一致性偏置。
- **训练目标**：冻结 GPM，训练 LCM 预测残差 \(B^*_t = A^*_t - \mu_t\)，损失为 MSE：\(\|B_t - B^*_t\|_2^2\)。
