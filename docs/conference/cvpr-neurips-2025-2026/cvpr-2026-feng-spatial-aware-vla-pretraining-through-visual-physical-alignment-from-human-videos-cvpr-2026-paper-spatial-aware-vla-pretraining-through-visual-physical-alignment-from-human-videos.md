---
title: Spatial-Aware VLA Pretraining through Visual-Physical Alignment from Human Videos
title_zh: 通过人类视频的视觉-物理对齐实现空间感知的VLA预训练
authors: "Feng, Yicheng, Zhang, Wanpeng, Wang, Ye, Luo, Hao, Yuan, Haoqi, Zheng, Sipeng, Lu, Zongqing"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Feng_Spatial-Aware_VLA_Pretraining_through_Visual-Physical_Alignment_from_Human_Videos_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 面向机器人学习的VLA预训练范式
tldr: 视觉-语言-动作模型为机器人学习提供了有前景的范式，但多数方法依赖二维视觉输入在三维物理环境中执行动作，造成感知与动作接地之间的鸿沟。本文提出空间感知VLA预训练范式，利用大规模人类演示视频提取三维视觉与三维动作标注，形成新的监督信号，在策略学习前对齐二维观测与三维空间推理。该方法为构建空间感知的VLA模型提供了有效途径。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-spatial-aware-vla-pretraining-through-visual-physical-alignment-from-human-videos-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 8, \"index\": 1, \"width\": 1768, \"height\": 727}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-spatial-aware-vla-pretraining-through-visual-physical-alignment-from-human-videos-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 8, \"index\": 2, \"width\": 428, \"height\": 317}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-spatial-aware-vla-pretraining-through-visual-physical-alignment-from-human-videos-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 8, \"index\": 3, \"width\": 609, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-spatial-aware-vla-pretraining-through-visual-physical-alignment-from-human-videos-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 8, \"index\": 4, \"width\": 428, \"height\": 312}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-feng-spatial-aware-vla-pretraining-through-visual-physical-alignment-from-human-videos-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 428, \"height\": 312}]"
motivation: 现有VLA依赖二维视觉在三维环境中行动，存在感知与动作接地的鸿沟。
method: 提出空间感知VLA预训练，从人类视频提取三维视觉与动作标注进行对齐。
result: 使模型在策略学习前获得三维空间理解，缩小感知-动作差距。
conclusion: 该范式为空间感知VLA模型与机器人学习提供了新的预训练思路。
---

## Abstract
Vision-Language-Action (VLA) models provide a promising paradigm for robot learning by integrating visual perception with language-guided policy learning. However, most existing approaches rely on 2D visual inputs to perform actions in 3D physical environments, creating a significant gap between perception and action grounding. To bridge this gap, we propose a Spatial-Aware VLA Pretraining paradigm that enables models to acquire 3D spatial understanding before robot policy learning. Starting from pretrained vision-language models, we leverage large-scale human demonstration videos to extract 3D visual and 3D action annotations, forming a new source of supervision that aligns 2D visual observations with 3D spatial reasoning. We instantiate this paradigm with VIPA-VLA, a dual-encoder architecture that incorporates a 3D visual encoder to augment semantic visual representations with 3D-aware features, and aligns the two through visual-physical alignment pretraining. When adapted to downstream robot tasks, VIPA-VLA achieves significantly improved grounding between 2D vision and 3D action, resulting in more robust and generalizable robotic policies.

---

## 论文详细总结（自动生成）

# 论文总结：Spatial-Aware VLA Pretraining through Visual-Physical Alignment from Human Videos

## 1. 核心问题与整体含义
- **研究动机**：现有 Vision-Language-Action（VLA）模型通常以 2D 视觉输入驱动 3D 物理环境中的动作执行，造成“视觉感知”与“动作接地”之间的显著鸿沟。
- **核心问题**：VLA 不仅要理解图像语义，还必须将 2D 像素映射到 3D 几何与物理动作空间。现有方法大多缺乏显式 3D 空间理解，导致空间接地弱、泛化能力受限。
- **整体含义**：论文提出 **Spatial-Aware VLA Pretraining** 范式，利用大规模人类演示视频中的 3D 视觉与 3D 动作信息，在机器人策略学习前先让模型获得 3D 空间感知与视觉-物理对齐能力。
- **代表模型**：作者实例化为 **VIPA-VLA**（Visual-Physical-Alignment-VLA），并构建数据集 **Hand3D**，目标是在下游机器人任务中获得更稳健、更可泛化的策略。

## 2. 方法论
### 2.1 核心思想
- 从预训练 VLM 出发，利用人类操作视频中天然存在的“2D 视觉观察—3D 物理动作”对应关系，提取 3D 视觉标注和 3D 动作标注。
- 通过 **视觉-物理对齐预训练**，让模型在学习机器人控制前先学会将 2D 视觉输入与 3D 空间关系、手部运动轨迹、任务完成方式对齐。
- 整体流程分为三阶段：两阶段空间感知预训练 + 一阶段机器人任务后训练。

### 2.2 Hand3D 数据构建
- **人类视频来源**：聚合 9 类异构人类操作视频源，包括 Arctic、HOI4D、FPHA、H2O、OAKINK2、TACO、DexYCB、EgoDex、Taste-Rob。
- **手部标注统一**：将不同数据集的手部标注对齐到 MANO 参数化表示，获得归一化手部轨迹。
- **3D 视觉标注**：
  - 使用 Cut3R 估计逐帧稠密点云 \(P=\{(x_i,y_i,z_i)\}\)。
  - 使用 Gemini-2.5-flash 生成物体候选，GroundingDINO 获取 2D 物体框。
  - 结合 MANO 手部参数、相机内外参，将手部关节投影到图像平面，过滤手部不可见帧。
  - 进行尺度校准：利用绝对手部关节深度与点云估计深度匹配，估计尺度因子  
    \[
    s=\text{median}_{k\in\Omega}(j^z_k/\tilde j^z_k)
    \]
    得到与真实物理尺度一致的 3D 表示。
- **指令数据构建**：生成四类 VQA 监督：
  - Spatial Relationship：手与物体在连续帧中的 3D 空间关系。
  - Task Completion：给定任务描述与帧，说明手应如何 3D 移动以操作目标。
  - Hand Movement：两帧间手部 3D 轨迹、方向与距离。
  - Camera Movement：两帧间相机相对 3D 旋转与平移。
  - 方向用离散语言 token 表示，例如若 \(| \hat x |>\gamma\) 则 right/left，若 \(| \hat y |>\gamma\) 则 up/down，若 \(| \hat z |>\gamma\) 则 forward/backward。
- **数据规模**：
  - 约 4K 视频片段标注，生成约 300K 指令-答案对，记为 **Hand3D-visual**。
  - 从手部运动序列提取腕部轨迹并离散为 motion tokens，获得约 4M video-instruction-motion 对，过滤后得到约 1M 的 **Hand3D-action**。

### 2.3 VIPA-VLA 架构
- **双编码器设计**：
  - 语义视觉编码器：提取高层语义视觉表示 \(V_{\text{sem}}\)。
  - 3D 视觉编码器：采用 Cut3R，提取显式几何空间表示 \(V_{\text{spa}}\)。
- **融合层**：使用 cross-attention，语义特征作为 query，3D 空间特征作为 key/value，得到融合视觉表示 \(V_f\)。
- **运动 token**：扩展 LLM 词表，加入离散化 3D 物理空间的 motion tokens，用于表示细粒度 3D 运动轨迹。

### 2.4 三阶段训练流程
- **Stage 1：3D 视觉对齐预训练**
  - 初始化自预训练 VLM，加入预训练 3D 编码器和随机初始化融合层。
  - 冻结所有预训练参数，只训练融合层。
  - 使用 3D 视觉标注 VQA 数据，对齐语义嵌入与空间嵌入，学习 3D 空间关系推理。
- **Stage 2：3D 动作预训练**
  - 扩展 LLM 词表加入 motion tokens。
  - 冻结语义编码器和空间编码器，训练 LLM。
  - 在融合视觉与文本条件下预测 motion tokens，学习视觉线索到物理运动模式的映射。
- **Stage 3：机器人任务后训练**
  - 接上动作头，使用 Diffusion Transformer（DiT）。
  - 从 VLM backbone 提取 action queries 的隐藏状态作为条件 \(h_{\text{cond}}\)。
  - 使用 flow matching：将随机噪声 \(\epsilon\) 与真实动作 \(a_t\) 线性插值得到带噪动作  
    \[
    \tilde a_t(\tau)=(1-\tau)\epsilon+\tau a_t,\quad \tau\sim U(0,1)
    \]
  - DiT 输入为带噪动作与机器人状态嵌入的拼接，条件于 \(h_{\text{cond}}\)，预测瞬时流向量 \(v_\theta\)。
  - 损失为  
    \[
    L_{\text{FM}}=\mathbb E[\|v_\theta-(a_t-\epsilon)\|_2^2]
    \]
  - 训练时仅更新 LLM backbone 与动作头。

## 3. 实验设计
### 3.1 数据集与场景
- **仿真基准**：LIBERO，包括四个任务套件：Spatial、Object、Goal、Long，每个套件评估 500 次。
- **真实机器人**：7-DoF Franka Research 3 机械臂、6-DoF Inspire 手、两个 RealSense L515 相机。
  - 任务：Put-Three-Obj、Wipe-Board、Water-Plant。
  - 每个任务采集 50 条遥操作轨迹用于后训练，评估 10 次。
  - 另设 unseen environments 评估。
- **空间理解测试**：Hand3D-test，包含 2K 个来自未见视频的 VQA 对，评估距离误差与方向准确率。

### 3.2 对比方法
- **LIBERO 单视角**：TraceVLA、OpenVLA、SpatialVLA、DiT Policy、CoT-VLA、ThinkAct、TriVLA、4D-VLA、GR00T N1.5。
- **LIBERO 双视角**：MaIL、π0-FAST、MolmoAct、GR00T N1、π0、UniVLA、π0.5。
- **真实机器人**：GR00T N1.5、Being-H0、InternVL3.5。
- **消融对比**：VIPA-VLA 去掉预训练、去掉双编码器、两者都去掉；空间理解对比 InternVL3.5、InternVL3.5+Hand3D、VIPA-VLA-PT。

## 4. 资源与算力
- 模型初始化：InternVL3.5-2B。
- 训练设备：**8 × A800 GPUs**。
- 学习率：预训练 \(1e-5\)，后训练 \(5e-5\)。
- 视频帧采样率：1 fps。
- **未明确说明**：论文未报告训练总时长、总 GPU 小时、数据标注总成本或推理资源。

## 5. 实验数量与充分性
- **实验组数概览**：
  - LIBERO 四个套件，单视角与双视角两套设置，每套 500 次试验。
  - 真实机器人三个任务，另加 unseen 环境评估；每任务 10 次评估。
  - 空间理解测试
