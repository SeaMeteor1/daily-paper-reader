---
title: "TraceGen: World Modeling in 3D Trace Space Enables Learning from Cross-Embodiment Videos"
title_zh: TraceGen：在3D轨迹空间中的世界建模实现跨具身视频学习
authors: "Lee, Seungjae, Jung, Yoonkyo, Chun, Inkook, Lee, Yao-Chih, Cai, Zikui, Huang, Hongjia, Talreja, Aayush, Dao, Tan, Liang, Yongyuan, Huang, Jia-Bin, Huang, Furong"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Lee_TraceGen_World_Modeling_in_3D_Trace_Space_Enables_Learning_from_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 通过共享3D轨迹空间实现跨具身视频学习
tldr: 在新平台和新场景中仅凭少量演示学习新任务十分困难，而人类和其他机器人的视频虽丰富，却因具身、相机和环境差异难以直接使用。本文提出紧凑的3D轨迹空间符号表示，并构建TraceGen世界模型，在轨迹空间而非像素空间预测未来运动，从而抽象掉外观、保留操作所需的几何结构。实验表明其能有效利用跨具身、跨环境、跨任务视频。该工作为跨具身机器人学习提供了统一表示。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 916, \"height\": 633}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 640, \"height\": 400}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 518, \"height\": 322}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 640, \"height\": 400}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 640, \"height\": 400}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 640, \"height\": 400}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 1, \"index\": 7, \"width\": 1559, \"height\": 889}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 1, \"index\": 8, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 1, \"index\": 9, \"width\": 4551, \"height\": 1856}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 1, \"index\": 10, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 2, \"index\": 11, \"width\": 518, \"height\": 294}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 2, \"index\": 12, \"width\": 639, \"height\": 469}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 2, \"index\": 13, \"width\": 518, \"height\": 392}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 2, \"index\": 14, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 2, \"index\": 15, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 2, \"index\": 16, \"width\": 1472, \"height\": 1472}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 2, \"index\": 17, \"width\": 518, \"height\": 294}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 3, \"index\": 18, \"width\": 1785, \"height\": 1193}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 3, \"index\": 19, \"width\": 1785, \"height\": 1193}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-020.webp\", \"caption\": \"\", \"page\": 3, \"index\": 20, \"width\": 1785, \"height\": 1193}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-021.webp\", \"caption\": \"\", \"page\": 3, \"index\": 21, \"width\": 1576, \"height\": 994}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-022.webp\", \"caption\": \"\", \"page\": 4, \"index\": 22, \"width\": 1037, \"height\": 677}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-023.webp\", \"caption\": \"\", \"page\": 4, \"index\": 23, \"width\": 697, \"height\": 268}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-024.webp\", \"caption\": \"\", \"page\": 4, \"index\": 24, \"width\": 667, \"height\": 268}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-025.webp\", \"caption\": \"\", \"page\": 4, \"index\": 25, \"width\": 518, \"height\": 392}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-026.webp\", \"caption\": \"\", \"page\": 4, \"index\": 26, \"width\": 396, \"height\": 394}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-027.webp\", \"caption\": \"\", \"page\": 4, \"index\": 27, \"width\": 769, \"height\": 274}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-028.webp\", \"caption\": \"\", \"page\": 4, \"index\": 28, \"width\": 715, \"height\": 267}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-029.webp\", \"caption\": \"\", \"page\": 4, \"index\": 29, \"width\": 699, \"height\": 275}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-030.webp\", \"caption\": \"\", \"page\": 4, \"index\": 30, \"width\": 665, \"height\": 267}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-031.webp\", \"caption\": \"\", \"page\": 4, \"index\": 31, \"width\": 518, \"height\": 392}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-032.webp\", \"caption\": \"\", \"page\": 4, \"index\": 32, \"width\": 699, \"height\": 274}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-033.webp\", \"caption\": \"\", \"page\": 4, \"index\": 33, \"width\": 691, \"height\": 180}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-034.webp\", \"caption\": \"\", \"page\": 4, \"index\": 34, \"width\": 1193, \"height\": 593}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-035.webp\", \"caption\": \"\", \"page\": 4, \"index\": 35, \"width\": 717, \"height\": 180}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-036.webp\", \"caption\": \"\", \"page\": 4, \"index\": 36, \"width\": 553, \"height\": 274}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-037.webp\", \"caption\": \"\", \"page\": 4, \"index\": 37, \"width\": 518, \"height\": 392}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-038.webp\", \"caption\": \"\", \"page\": 4, \"index\": 38, \"width\": 518, \"height\": 392}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-039.webp\", \"caption\": \"\", \"page\": 4, \"index\": 39, \"width\": 518, \"height\": 392}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-040.webp\", \"caption\": \"\", \"page\": 4, \"index\": 40, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-041.webp\", \"caption\": \"\", \"page\": 4, \"index\": 41, \"width\": 514, \"height\": 274}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-042.webp\", \"caption\": \"\", \"page\": 5, \"index\": 42, \"width\": 640, \"height\": 400}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-043.webp\", \"caption\": \"\", \"page\": 5, \"index\": 43, \"width\": 1703, \"height\": 1083}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-044.webp\", \"caption\": \"\", \"page\": 5, \"index\": 44, \"width\": 898, \"height\": 485}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-045.webp\", \"caption\": \"\", \"page\": 6, \"index\": 45, \"width\": 1221, \"height\": 741}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-046.webp\", \"caption\": \"\", \"page\": 6, \"index\": 46, \"width\": 1258, \"height\": 737}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-047.webp\", \"caption\": \"\", \"page\": 6, \"index\": 47, \"width\": 1261, \"height\": 736}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-048.webp\", \"caption\": \"\", \"page\": 6, \"index\": 48, \"width\": 1230, \"height\": 749}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-049.webp\", \"caption\": \"\", \"page\": 7, \"index\": 49, \"width\": 5196, \"height\": 1142}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lee-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cvpr-2026-paper/fig-050.webp\", \"caption\": \"\", \"page\": 8, \"index\": 50, \"width\": 2005, \"height\": 868}]"
motivation: 在新平台与新场景中仅凭少量演示学习新任务是难点，跨具身视频难以直接利用。
method: 提出紧凑的3D轨迹空间符号表示，构建在轨迹空间预测未来运动的世界模型TraceGen，并开发大规模训练流程。
result: 实现跨具身、跨环境、跨任务视频的有效学习，缓解小数据问题。
conclusion: 轨迹空间世界建模为跨具身机器人学习提供了统一表示。
---

## Abstract
Learning new robot tasks on new platforms and in new scenes from only a handful of demonstrations remains challenging. While videos of other embodiments---humans and different robots---are abundant, differences in embodiment, camera, and environment hinder their direct use. We address the small-data problem by introducing a unifying, symbolic representation---a compact 3D "trace-space" of scene-level trajectories---that enables learning from cross-embodiment, cross-environment, and cross-task videos. We present TraceGen, a world model that predicts future motion in trace-space rather than pixel space, abstracting away appearance while retaining the geometric structure needed for manipulation. To train TraceGen at scale, we develop TraceForge, a data pipeline that transforms heterogeneous human and robot videos into consistent 3D traces, yielding a corpus of 123K videos and 1.8M observation--trace--language triplets. Pretraining on this corpus produces a transferable 3D motion prior that adapts efficiently: with just five target robot videos, TraceGen attains 80% success across four tasks while offering 50-600x faster inference than state-of-the-art video-based world models. In the more challenging case where only five uncalibrated human demonstration videos captured on a handheld phone are available, it still reaches 67.5% success on a real robot, highlighting TraceGen's ability to adapt across embodiments without heavy pixel-space generation.

---

## 论文详细总结（自动生成）

# TraceGen 论文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：如何在新机器人平台、新场景中仅凭少量演示（few-shot）学习新的操作任务。真实机器人演示采集慢、成本高，属于典型的"小数据"困境。
- **可用但难用的资源**：人类操作视频与其他机器人视频规模庞大，却因**具身差异（embodiment）、相机差异、环境差异**而难以直接复用。
- **现有范式的局限**（作者归纳为三类输出空间）：
  - **像素/视频生成空间**：为背景与纹理分配大量容量，计算昂贵，且易产生几何/可供性幻觉（如虚构夹爪、误检工具）。
  - **语言 token 空间**：VLM 规划器输出的离散 token 缺乏细粒度物体运动所需的时空分辨率。
  - **已有轨迹（trace）预测**：多在静态实验室数据上训练，且大多局限于 2D 轨迹；少数 3D 变体仅关注被操作物体，依赖目标检测与启发式过滤，无法刻画机器人自身运动，误差级联明显。
- **关键洞见**：尽管各具身的运动学与尺度不同，**被操作物体与末端执行器的运动共享一个以场景为中心的 3D 几何结构**。作者将其抽象为紧凑的符号表示——**3D trace-space（轨迹空间）**：一串 3D 轨迹序列，保留"在哪里、如何运动"，丢弃外观与背景。
- **整体含义**：在轨迹空间做世界建模，有望同时获得**相机/环境不变性**、**跨具身视频复用能力**、**高推理效率**与**样本效率**，为跨具身机器人学习提供统一表示。

## 2. 方法论

### 2.1 总体框架

- **TraceForge（数据引擎）**：把异构的人类与机器人视频统一转换为一致的 3D 轨迹标注，产出 `{observation, trace, language}` 三元组。
- **TraceGen（世界模型）**：在这些三元组上预训练，学习场景级 3D 运动先验，**直接预测未来 3D 轨迹**而非像素。

### 2.2 TraceForge 数据管线（四步）

1. **事件切分与指令生成**：利用已有的 start–end 标注切出任务相关片段（含多标签的拆分为独立 chunk）；若无标注，则用点跟踪结果剔除几乎无运动的帧来定位任务相关帧。随后用 VLM 生成三种互补指令（简短命令式、多步分解式、自然人类口吻），若数据集已有真人指令则保留并增广。
2. **相机位姿/深度预测 + 3D 点跟踪**：在每个 chunk 起始帧选参考帧，铺设 **20×20 均匀关键点网格**，跟踪 L 步。3D 轨迹点表示为 `(x, y, z)`，其中 `(x, y)` 是像平面坐标、`z` 是对应深度——使 3D 轨迹与 2D 轨迹共享同一屏幕对齐方式，便于 2D/3D 联合训练。使用 TAPIP3D（点跟踪器为 CoTracker3），并用 SpatialTrackerV2 中微调过的 VGGT 深度与相机位姿预测器**替换其 MegaSAM 组件**，精度相当但显著更快、无需 3D 优化。约 **20% 的轨迹是纯 2D**。
3. **世界→相机变换**：把世界坐标下的 3D 轨迹用参考帧 `cam_ref` 的外参变换到相机坐标，再用内参投影为像素坐标，与深度拼接成屏幕对齐的 3D 轨迹 `T^{t:t+L}_ref = [x_i, y_i, z_i]`，从而在时间上保持视角一致、补偿相机运动。
4. **速度重定向（Speed Retargeting）**：人类与机器人执行同一任务的速度/时长不同，若直接使用会让模型看到同一行为的不同时间尺度。做法是计算 3D 路径的累积弧长，按归一化弧长参数化，并在 L 个均匀目标点上重采样，从而**对齐轨迹长度而不过度扭曲局部速度模式**。

### 2.3 TraceGen 架构

- **基础架构**：基于 CogVideoX，采用 Prismatic-VLM 的多编码器融合策略。
- **多编码器特征提取**：
  - RGB：**DINOv3**（ViT-L/16，自监督、空间几何特征）+ **SigLIP**（SigLIP-Base-Patch16-384，语义对齐特征），均冻结。
  - 深度：单通道深度经 **1×1 卷积 learnable stem adapter** 投到 3 通道后送入 SigLIP，得到深度特征。
  - 文本：冻结 **T5-base**，序列长度固定 M=128，维度 D=768。
  - 融合：三路视觉特征沿特征维拼接 `F_vis = Concat(F_dino, F_siglip, F_depth)`，再线性投影到统一维度 D；视觉 token 与文本 token 组合为条件输入 `F_cond ∈ R^{(N+M)×D}`。
- **流式轨迹解码器（Flow-based Trace Decoder）**：
  - 输入为 K×L 网格：**K = 20×20 = 400 个空间关键点**，**L = 32 个未来时间步**，每点为相机系下的 `(x,y,z)`。
  - 空间 patch 化，patch 大小 2×2 → 每时间步 **10×10 个空间 token**；仿 CogVideoX 通过 **AdaLN** 分别向上下文输入与潜在轨迹 token 注入条件。
  - 不直接预测绝对网格值，而是预测**帧间差分**（速度样增量）：`ΔT_t = T_{t+1} - T_t`，隐式刻画场景 3D 运动。
- **随机插值（Stochastic Interpolant）生成框架**：
  - 插值路径 `I_τ = α_τ X_1 + σ_τ ε`，`τ ∈ [0,1]`；该框架统一了扩散与流匹配模型。
  - 学习速度场 `v(x, τ, F_cond) = E[İ_τ | I_τ = x, F_cond]`。
  - 采用**线性插值 ODE**：取 `α_τ = τ`、`σ_τ = 1−τ`，则 `X_τ = (1−τ)X_0 + τX_1`，速度场 `Ẋ_τ = X_1 − X_0` 为时间常数。
  - 损失：`L_SI = E_{τ, X_0, X_1} ‖ v_θ(X_τ, τ, F_cond) − (X_1 − X_0) ‖²`。
  - 推理时用 **100 步 ODE 积分**，仅依赖条件模型与多模态视觉-语言条件。
- **冻结策略**：DINOv3、SigLIP、T5 全部冻结，只训练融合层与解码器。
- **执行方式**：预测的 3D 轨迹经**逆运动学**映射为机器人关节命令；作者采用基础跟踪控制器作为最小化演示，更复杂的策略留待未来工作。

## 3. 实验设计

- **数据集 / Benchmark（自建）**：
  - **TraceForge-123K**：来自 **8 个来源**（人类演示、单臂机器人操作、双臂机器人操作），共 **123K 视频 / 约 1.8M observation–trace–language 三元组**，覆盖桌面、第一人称、含移动相机的野外（in-the-wild）素材。
  - 数据量约为先前工作（3DFlowAction）的 **>15×**。
- **真实机器人评测场景**：Franka Research 3 上的四个操作任务——
  - **Clothes**：折叠黑色裤子（可形变物体）
  - **Ball**：把网球放入盒子
  - **Brush**：用刷子把垃圾扫进簸箕
  - **Block**：把积木放到紫色区域
  - 每个任务 **10 次试验**；给定单帧 RGB-D 与语言指令，预测 3D 轨迹 → IK → 执行。
- **两种低数据适配设定**：
  1. **Robot→Robot**：用 5 条（以及 15 条）同域机器人演示微调；演示与测试在物体/目标配置、机器人初始位姿上不同（如 Brush 的演示省略了"下压刷子"的关键动作）。
  2. **Human→Robot**：不使用任何目标机器人数据，仅用 **5 条手持手机拍摄、未标定**的人类演示（每条 3–4 秒，不同场景/视角/背景/物体布局）微调。四个任务共 20 条演示的采集**不到 4 分钟**。
- **对比方法**：
  - 视频生成类世界模型：**AVDC**、**NovaFlow（Wan2.2）**、**NovaFlow（Veo3.1）**（统一使用同一套 video-to-trace 提取管线，不做幻觉过滤；Veo 3.1 延迟按 API 平均调用时间计）。
  - 轨迹类：**3DFlowAction**（因原掩码估计器频繁失败，提供真值掩码）。
  - 自身消融：**From Scratch**（相同架构仅用 warmup 数据训练）、**SSV2-only 预训练**（人类手部中心，35K clips）、**Agibot-only 预训练**（机器人中心，35K clips）、**TraceForge-123K 全量跨具身预训练**。
- **评价指标**：任务成功率（SR%）、推理效率（predictions/min）、成功率-效率曲线（Fig. 7）。

## 4. 资源与算力

- **论文提供的文本中未明确说明**使用的 GPU 型号、数量、训练时长、总计算量或训练步数等算力信息。
- 可间接获得的相关信息仅有：
  - 模型规模为 **0.67B 参数**（对比基线多为 >10B）；
  - 训练时冻结 DINOv3 / SigLIP / T5，仅训练融合层与解码器；
  - 预训练语料为 123K 视频 / 1.8M 三元组；
  - 推理侧：100 步 ODE 积分，比视频生成类世界模型快 50–600×，比轨迹生成类基线快 3.8×。
- 结论：**算力开销属于论文未披露项**，需查阅附录或项目主页（https://tracegen.github.io）方能确认。

## 5. 实验数量与充分性

- **实验组数概览**：
  - 4 个真实任务 × 每任务 10 次试验的主实验（零样本 + 5 视频 warmup）；
  - 两种 warmup 规模（5 / 15 条视频）× 两种初始化（预训练 / From Scratch）= 预训练作用消融；
  - 4 种预训练来源对比（无预训练 / SSV2 / Agibot / TraceForge-123K）；
  - Human→Robot 迁移实验（5 条人类视频 vs From Scratch）；
  - 效率对比（成功率-推理速度曲线，含 Veo 3.1 API 延迟测量）；
  - 附录中另有 TraceForge 轨迹精度的定量 sanity check（附录 C）、NovaFlow 人类手生成设定对比（附录 E.3）、全部 warm
