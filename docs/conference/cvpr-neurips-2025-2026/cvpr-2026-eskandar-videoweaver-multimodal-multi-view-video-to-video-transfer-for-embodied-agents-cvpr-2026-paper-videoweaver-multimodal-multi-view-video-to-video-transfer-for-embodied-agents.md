---
title: "VideoWeaver: Multimodal Multi-View Video-to-Video Transfer for Embodied Agents"
title_zh: VideoWeaver：面向具身智能体的多模态多视角视频到视频转换
authors: "Eskandar, George, Shen, Fengyi, Altillawi, Mohammad, Chen, Dong, Bai, Yang, Yang, Liudi, Liu, Ziyuan"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Eskandar_VideoWeaver_Multimodal_Multi-View_Video-to-Video_Transfer_for_Embodied_Agents_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 5.0
evidence: 通过视频转换使预训练策略迁移到新环境
tldr: 视频到视频转换可使预训练机器人策略迁移到新环境而无需额外采集数据，但现有方法一次只能处理单视角，多相机场景下独立处理会导致外观不一致，且标准Transformer难以扩展到多视角。本文提出VideoWeaver，首个多模态多视角视频转换框架，在保持跨视角外观一致的同时实现可扩展的多视角重仿真。该方法提升了具身策略迁移时的数据重仿真能力。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-eskandar-videoweaver-multimodal-multi-view-video-to-video-transfer-for-embodied-agents-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 5, \"index\": 1, \"width\": 1104, \"height\": 288}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-eskandar-videoweaver-multimodal-multi-view-video-to-video-transfer-for-embodied-agents-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 5, \"index\": 2, \"width\": 1104, \"height\": 288}]"
motivation: 预训练机器人策略迁移到新环境需要重仿真，但单视角视频转换在多相机场景下不一致。
method: 提出首个多模态多视角视频到视频转换框架VideoWeaver，解决跨视角一致性与可扩展性。
result: 实现多视角一致的视频重仿真，支持策略向新环境迁移。
conclusion: 该方法提升了具身智能体策略迁移时的数据重仿真能力。
---

## Abstract
Recent progress in video-to-video (V2V) translation has enabled realistic resimulation of embodied AI demonstrations, a capability that allows pretrained robot policies to be transferable to new environments without additional data collection. However, prior works can only operate on a single view at a time, while embodied AI tasks are commonly captured from multiple synchronized cameras to support policy learning. Naively applying single-view models independently to each camera leads to inconsistent appearance across views, and standard transformer architectures do not scale to multi-view settings due to the quadratic cost of cross-view attention. We present VideoWeaver, the first multimodal multi-view V2V translation framework. VideoWeaver is initially trained as a single-view flow-based V2V model. To achieve an extension to the multi-view regime, we propose to ground all views in a shared 4D latent space derived from a feed-forward spatial foundation model, namely, Pi3. This encourages view-consistent appearance even under wide baselines and dynamic camera motion. To scale beyond a fixed number of cameras, we train views at distinct diffusion timesteps, enabling the model to learn both joint and conditional view distributions. This in turn allows autoregressive synthesis of new viewpoints conditioned on existing ones. Experiments show superior or similar performance to the state-of-the-art on the single-view translation benchmarks and, for the first time, physically and stylistically consistent multi-view translations, including challenging egocentric and heterogeneous-camera setups central to world randomization for robot learning.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义
- **研究动机**：视频到视频（V2V）转换可把具身智能演示重仿真到新风格/新环境，从而让预训练机器人策略无需额外采集真实数据即可迁移。但现有 V2V 方法基本只处理**单视角**。
- **核心问题**：具身任务常由多个同步相机采集。若把单视角 V2V 模型独立用于每个相机，会造成跨视角外观、风格、几何不一致；而标准 Transformer 的跨视角注意力计算量随视角数二次增长，难以扩展到多相机。
- **任务定义**：给定 K 个视角的 sketch 与 depth 控制序列，以及文本提示，生成多视角 RGB 视频，使每个视角对齐自身控制，同时保持跨视角几何与风格一致。
- **整体含义**：论文提出 VideoWeaver，声称是首个多模态、多视角 V2V 转换框架，面向具身智能体的世界随机化与策略迁移数据重仿真。

## 2. 方法论
- **核心思想**：不只在 2D 图像空间强制一致性，而是把所有视角统一到共享的 **4D 潜在空间**，由前馈空间基础模型 Pi3 估计的 4D 点云提供跨视角时空对应。
- **生成框架**：基于 flow/rectified flow 的 DiT 模型。设噪声为 \(x_0\)，数据为 \(x_1\)，插值 \(x_\tau=(1-\tau)x_0+\tau x_1\)，训练速度场 \(v_\theta\) 拟合 \(x-x_0\)，损失为  
  \[
  L(\theta)=E[\|v_\theta(x_\tau,y,\tau)-(x-x_0)\|^2]
  \]
  采样时从 \(\tau=0\) 积分到 1。
- **单视角 V2V 架构**：
  - 在 3D VAE 潜在空间操作，空间和时间压缩因子为 8。
  - 输入 sketch 与 depth 序列，经 VAE 编码为潜在特征。
  - 提出 **Mixture-of-Experts（MoE）** 融合深度与草图：两个专家 \(E_s,E_d\) 分别处理 sketch/depth 特征，门控网络输出 patch 级权重 \(\alpha_\tau\)，融合控制信号  
    \[
    c_\tau=\alpha_\tau E_s(f_s)+(1-\alpha_\tau)E_d(f_d)
    \]
    再加到噪声潜在上。
  - 训练细节：增加 ego-centric 相机位姿多样性；采用均匀 timestep 采样而非偏重中间 timestep；引入小波一致性损失，约束预测潜在与真值视频的 3D 小波系数。
- **多视角扩展**：
  - 加入 camera-ray embeddings 和跨视角注意力，形成**因子化 4D 注意力**：先在单视角内对 \(T\times H\times W\) token 做注意力，再在每帧跨视角对 \(V\times H\times W\) 空间 token 做注意力。
  - 但仅靠上述设计不足，因此用 **Pi3** 从所有视角、所有帧预测全局点云、相机位姿与内参：
    \[
    F_{Pi3}(x_{k,t})\rightarrow(\hat K_k,\hat T_{k,t},\hat p_{k,t})
    \]
  - 将 Pi3 输出的逐像素 3D 点云按 \(8\times8\) patch 做深度感知池化，保留离相机最近点；时间上每 8 帧采样一次，经轻量 MLP 注入 DiT 潜在空间。
- **自回归视角生成**：
  - 原生训练 K=3 视角。为扩展到更多视角，训练时随机冻结部分视角在 \(\tau=1\)（视为已生成），只对剩余视角加噪去噪，并屏蔽干净视角的损失。
  - 这样模型同时学习联合分布与条件分布。推理时若 K>3，先生成三视角，再以部分已生成视角为条件自回归生成其他视角。

## 3. 实验设计
- **训练数据集**：
  - Droid：约 140K 视频，使用其中约三分之二；每 episode 有 3–5 相机，实验用 left、right、in-hand。
  - Agibot：75K 样本，约三分之一；三视角：left hand、right hand、head。
  - Bridgev2：22K 样本，全部；仅用于单视角阶段，因为多视角版本分辨率低。
  - 内部数据集：5K 视频，三视角 left、right、in-hand。
  - 总计约 240K 视频用于单视角训练，75K 用于多视角训练。视频统一 81 帧、480×640。
- **预处理与标注**：用 Qwen-2.5-VL 重新生成描述；Video-Depth-Anything 提取深度；Canny 提取边缘；Pi3 提取潜在分辨率 \(11\times60\times80\) 的点云和相机位姿。
- **Benchmark**：
  - 单视角测试集：310 个样本，来自 Agibot、Droid、Bridgev2，训练未见。
  - 多视角测试集：90 个样本，去掉 Bridgev2，仅 Agibot 与 Droid。
- **对比方法**：
  - 单视角 V2V 基线：VACE（14B）、Cosmos-Transfer-1（7B）、ControlVideo、Control-A-Video。
  - 多视角基线：在自家基础模型上加入 camera-ray embedding 与跨视角注意力；同时比较自己的单视角模型。
- **评价指标**：
  - 单视角：VBench、Dover、Edge-F1、Depth-siRMSE、JEDi。
  - 多视角：额外使用 Met3R 衡量跨视角一致性。
- **主要结果**：
  - 单视角多数设置优于或接近 SOTA，包括优于参数量/训练数据更多的 VACE 和 Cosmos-Transfer-1。
  - 多视角在 Droid 与 Agibot 上甚至优于单视角模型，说明多视角一致性训练有增益。
  - 在 Dover 与 VBench 美学维度上略逊，可能与 VAE 时间下采样因子 8 导致轻微模糊有关。

## 4. 资源与算力
- 基础模型为**内部 11B 参数文本到视频基础模型**，采用 MMDiT 架构。
- 训练分三阶段：单视角微调、多视角联合微调、异构 timestep 多视角训练。
- 文中明确：所有模型可在 **8 张 Ascend 910B（64 GB）** 上高效训练，约 **一周**。
- 推理：线性 flow scheduler + 离散 Euler solver，30 步积分；生成 3 个同步多视角、81 帧视频约需 **10 分钟**。
- 未详细报告总 GPU/加速器小时、能耗、不同阶段各自耗时等。

## 5. 实验数量与充分性
- **主要实验组**：
  - 表 1：在 Bridge、Droid、Agibot 上比较 4 个单视角 V2V 基线与本文单视角/多视角模型。
  - 表 2：多视角消融，比较 camera-ray baseline、加入 4D 点云、条件多视角生成。
  - 表 3：单视角消融，比较 sketch-only、depth-only、MoE、推理时丢弃 depth/sketch。
  - 图 4、图 5：定性与消融可视化。
  - 补充材料：在 Berkeley-Autolab、Robomind、私有仿真数据集上做泛化测试。
- **充分性评价**：
  - 覆盖三个具身数据集、单/多视角、多个指标和消融，整体较充分。
  - 多视角测试集仅 90 个样本，规模有限；Bridgev2 因分辨率问题被排除在多视角评测外。
  - 没有公开的多视角 V2V 基线，只能与单视角独立运行或自建多视角基线比较，公平性受限。
  - 不同基线的参数量、训练数据、训练目标不完全一致，比较并非完全受控。
  - 未报告多次随机种子、方差或统计显著性检验。

## 6. 主要结论与发现
- VideoWeaver 是首个面向具身智能的多模态多视角 V2V 流模型，可同步翻译多视角视频到由文本提示定义的新风格。
- 基于 Pi3 的 4D 点云共享潜在空间能显著提升跨视角一致性；在 Droid 上 Met3R
