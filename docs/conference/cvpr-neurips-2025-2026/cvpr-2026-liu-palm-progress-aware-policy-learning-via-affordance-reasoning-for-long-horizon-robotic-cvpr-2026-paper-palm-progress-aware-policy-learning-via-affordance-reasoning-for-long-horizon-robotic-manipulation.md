---
title: "PALM: Progress-Aware Policy Learning via Affordance Reasoning for Long-Horizon Robotic Manipulation"
title_zh: PALM：面向长程机器人操作的可供性推理进度感知策略学习
authors: "Liu, Yuanzhe, Zhu, Jingyuan, Mo, Yuchen, Li, Gen, Cao, Xu, Jin, Jin, Shen, Yifan, Li, Zhengyuan, Yu, Tianjiao, Yuan, Wenzhen, Ding, Fangqiang, Lourentzou, Ismini"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Liu_PALM_Progress-Aware_Policy_Learning_via_Affordance_Reasoning_for_Long-Horizon_Robotic_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 面向机器人操作的VLA策略学习框架
tldr: 现有VLA模型在长程多步机器人操作任务中常出现重复动作、漏步与提前终止等问题，因为缺乏识别交互线索与追踪子任务进度的内部推理机制。PALM构建了一个以交互为中心的可供性推理与子任务进度线索驱动的VLA框架，蒸馏出包含物体相关性、接触几何、空间布局与运动动力学的互补可供性表征。该方法提升了长程操作的一致性与成功率。其贡献在于为VLA引入进度感知的可供性推理范式。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 1807, \"height\": 1552}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 683, \"height\": 778}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 1, \"index\": 7, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 1, \"index\": 8, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 1, \"index\": 9, \"width\": 684, \"height\": 761}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 1, \"index\": 10, \"width\": 522, \"height\": 529}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 1, \"index\": 11, \"width\": 408, \"height\": 307}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 1, \"index\": 12, \"width\": 446, \"height\": 335}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 1, \"index\": 13, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 8, \"index\": 15, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 8, \"index\": 16, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 8, \"index\": 17, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 8, \"index\": 18, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 8, \"index\": 19, \"width\": 684, \"height\": 456}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-palm-progress-aware-policy-learning-via-affordance-reasoning-for-long-horizon-robotic-cvpr-2026-paper/fig-020.webp\", \"caption\": \"\", \"page\": 8, \"index\": 20, \"width\": 2409, \"height\": 1606}]"
motivation: 现有VLA模型在长程多步操作中缺乏识别交互线索和追踪子任务进度的推理机制，导致重复动作、漏步与提前终止。
method: 提出PALM框架，围绕以交互为中心的可供性推理与子任务进度线索组织策略学习，蒸馏物体相关性、接触几何、空间布局与运动动力学等可供性表征。
result: 该方法缓解了长程多步操作中的执行错误，提升了任务的连续性与成功率。
conclusion: 将进度感知的可供性推理引入VLA策略学习，为长程机器人操作提供有效范式。
---

## Abstract
Recent advancements in vision-language-action (VLA) models have shown promise in robotic manipulation, yet they continue to struggle with long-horizon, multi-step tasks. Existing methods lack internal reasoning mechanisms that can identify task-relevant interaction cues or track progress within a subtask, leading to critical execution errors such as repeated actions, missed steps, and premature termination. To address these challenges, we introduce PALM, a VLA framework that structures policy learning around interaction-centric affordance reasoning and subtask progress cues. PALM distills complementary affordance representations that capture object relevance, contact geometry, spatial placements, and motion dynamics, and serve as task-relevant anchors for visuomotor control. To further stabilize long-horizon execution, PALM predicts continuous within-subtask progress, enabling seamless subtask transitions. Across extensive simulation and real-world experiments, PALM consistently outperforms baselines, achieving a 91.8% success rate on LIBERO-LONG, a 12.5% improvement in average length on CALVIN ABC->D, and a 2ximprovement over real-world baselines across three long-horizon generalization settings.

---

## 论文详细总结（自动生成）

# PALM 论文深度总结

## 一、核心问题与研究动机

- **背景**：视觉-语言-动作（VLA）模型通过预训练的视觉-语言骨干网络，将图像观测与语言指令直接映射为机器人动作，在短程操作上表现优异。
- **核心痛点**：现有 VLA 方法在**长程、多步任务**（如“清理凌乱桌面”）中普遍失败，往往在任务初期成功、中途崩溃。
- **根因分析**：
  - 缺乏**结构化的可供性（affordance）线索**：模型无法明确“下一步该操作哪个物体、哪个部位/区域可交互、物品应放到哪里、应采取何种运动”。
  - 缺乏**显式的进度追踪机制**：没有对子任务内推进程度的在线估计，策略无法可靠判断“继续、切换阶段还是终止”。
- **导致的典型失败模式**：重复动作、跳过必要子任务、提前终止，甚至在错误状态下宣告成功。
- **整体含义**：论文主张将“以交互为中心的可供性推理”与“子任务连续进度估计”整合进 VLA 的闭环感知–行动循环中，从而支撑可靠的长程操作。

## 二、方法论

### 2.1 核心思想

PALM 在统一的端到端框架中耦合两个互补能力：
1. **细粒度可供性预测**：预测未来时刻的结构化可供性隐变量，作为任务相关的中间推理表征。
2. **进度感知策略生成**：在可供性条件下，用扩散 Transformer 联合解码动作序列与连续进度值。

### 2.2 问题形式化

- 任务分布 T = {τ_k}，每个任务定义观测–动作分布 p(o_t, a_t | τ) 及隐式的时序阶段推进。
- 策略扩展为 π: O×T → Ã，其中 Ã = A×P，P ⊆ [0,1] 为连续进度空间。
- 在时刻 t，给定 o_t、任务 τ 和预测的可供性隐变量，策略同时输出动作 a_t 与进度标量 p_t。

### 2.3 架构细节

- **多模态编码器**：CLIP 文本编码指令；MAE 编码图像并经 Perceiver Resampler 下采样为任务相关视觉 token；机器人状态经轻量 MLP 投影；三者拼接为统一多模态序列。
- **骨干网络**：GPT-2 风格 Transformer，采用因果注意力与跨模态注意力。
- **两组可学习查询**：
  - **细粒度可供性查询**：含 `<Global>`、`<Local>`、`<Spatial>`、`<Dynamic>` 四个子查询，分别关注不同尺度的任务相关信息，输出可供性隐变量 F̂_{t+n}。
  - **动作–进度查询**：汇聚控制相关上下文，并以可供性隐变量为条件，支撑进度感知的逆动力学解码。
- **结构化注意力**：可供性子查询仅关注共享上下文 token 以保持解耦；两类查询均使用因果注意力以维持时序一致性。
- **解码器**：动作头为去噪扩散 Transformer（DiT），输出 horizon-n 的动作与进度轨迹：
  - (â_{t:t+n-1}, p̂_{t:t+n-1}) = DiT(l, o_t, s_t, F̂_{t+n})

### 2.4 四类可供性预测与损失函数

| 类型 | 作用 | 监督目标构建 | 损失 |
|---|---|---|---|
| **Global** | 识别指令所指物体及其大致区域 | Grounding DINO 解析指代 + SAM 分割为二值掩码，掩码池化提取物体特征 | 焦点损失 + Dice 损失 |
| **Local** | 预测物体上的接触似然分布（精细接触几何） | 标注接触点转为高斯热力图（沿用 GLOVER++） | 焦点损失 + KL 散度 |
| **Spatial** | 将欠定空间语言转为可执行的放置候选点 | SpatialVLM 转空间语义 + RoboPoint 采样 2D 坐标 | 集合匹配损失（预测候选点与目标点最近邻 L2） |
| **Dynamic** | 预测夹爪与可动物体像素及其未来运动区域 | N×N 网格 + CoTracker 跟踪，累积位移超阈值保留 | 掩码重建损失（ELBO + KL 正则） |

### 2.5 进度感知策略与逆动力学

- **思路**：先从可供性隐变量推断当前子任务阶段并导出阶段嵌入，再预测标量 p_t ∈ [0,1] 量化阶段内完成度；将 p_t 附加到动作输出，使策略在共享多模态上下文下联合预测 (a_t, p_t)。
- **作用**：缓解视觉相似但阶段不同的状态歧义，鼓励隐状态单调、阶段一致地演化，平滑子策略边界过渡，无需独立高层控制器。
- **训练目标**：标准扩散去噪目标，y 为目标动作–进度向量，ε 为高斯噪声，t_d 为扩散时间，ᾱ 为累积噪声调度；噪声预测器 ε_θ 以 l、o_t、s_t、F̂_{t+n} 和 t_d 为条件。

### 2.6 训练流程

- **预训练**：混合数据集——机器人数据 DROID、BridgeData V2；长程视频数据 EPIC-KITCHENS、RoboCerebra（提供细粒度子步骤与时间分段标注，监督语义进度估计）。
- **微调**：从机器人数据中选取 942 条轨迹，用半自动方法标注可供性数据与连续进度标签。

## 三、实验设计

### 3.1 仿真 Benchmark

- **CALVIN ABC→D**：34 个任务、4 个环境，在 ABC 预训练、在未见 D 环境评测，考察长程语言条件策略。每个任务 1000 次 rollout，报告前三个 checkpoint 的平均成功率及连续完成 5 条指令的平均长度（Avg. Len.）。
- **LIBERO**：四个任务套件（Spatial、Object、Goal、Long），各 10 任务、50 演示，每套件 3 个随机种子 × 500 episode，报告平均成功率与标准误。

### 3.2 真实世界场景

- **硬件**：UFACTORY xArm6 + Gripper G2，两个 RealSense D455 相机（eye-on-hand 与 eye-on-base）。
- **任务**：单条高层指令驱动的 6 连子任务序列（如“把菠萝放白盘、葡萄放白碗、橙子放蓝碗”）。
- **三种泛化设置**：随机目标位姿（Random Localization）、未见光照（Unseen Lighting）、视觉干扰物（Visual Distraction）。
- **微调数据**：xArm 上采集的 200 条演示（RGB、机器人状态、动作）。
- **指标**：20 次真实 rollout，每次最多 3 次尝试，报告成功率与平均长度。

### 3.3 对比方法

- **CALVIN**：RT-1、Robo-Flamingo、OpenVLA（自回归）；Diffusion Policy、π0（扩散）；3D-VLA、3D Diffuser Actor、RoboUniview（3D 感知）；Susie、GR-1、Seer（预测式）。
- **LIBERO**：OpenVLA、Diffusion Policy、Octo、SpatialVLA、CoT-VLA、TraceVLA、CoA-VLA。
- **真实世界**：OpenVLA、Octo。
- **公平性控制**：所有模型在同一数据集上微调、训练相同迭代数、使用最终 checkpoint 评测。

### 3.4 消融实验

- **可供性组件消融**：在 vanilla VLA 上逐步加入 `<G>`、`<G,L>`、`<G,L,S>`、`<G,L,S,D>`（即完整 PALM），在 CALVIN 与 LIBERO-LONG 上对比。
- **PALM 模块消融**：分别移除可供性预见、逆动力学预测、进度预测，在预训练与微调两种设置下对比。
- **训练数据组成消融**：分别移除 In-the-Wild 数据、长程视频数据、人工标注数据、仿真预训练数据。

## 四、资源与算力

- **论文正文未明确说明**所使用的 GPU 型号、数量、训练时长、显存占用或总计算量等算力细节。
- 文中仅提及训练分预训练与微调两阶段、数据集规模与微调轨迹数量（942 条），以及“所有基线训练相同迭代数”的公平性设定。
- **结论**：算力开销属于本文信息缺口，若需复现或评估成本，需查阅附录或作者补充材料。

## 五、实验数量与充分性

- **实验组数概览**：
  - 2 个仿真 benchmark（CALVIN ABC→D、LIBERO 四套件）；
  - 1 组真实世界实验，含 3 种泛化设置、6 连子任务、20 次 rollout；
  - 3 大类消融（可供性组件、PALM 模块、训练数据组成），每种消融覆盖多个配置。
- **充分性评估**：
  - 覆盖仿真与真实、短程与长程、多种泛化维度，实验面较广；
  - CALVIN 每任务 1000 次 rollout、LIBERO 每套件 1500 episode（3×500），统计量较充足；
  - 消融设计系统，能分别定位各模块贡献，并区分预训练/微调阶段的作用。
- **客观性与公平性**：
  - 基线种类全面（自回归、扩散、3D 感知、预测式），并在真实世界中统一微调数据与训练迭代数；
  - 真实世界每次最多 3 次尝试、20 次 rollout，样本量相对有限，统计置信度可能弱于仿真；
  - 未报告真实世界实验的多次运行方差或置信区间。

## 六、主要结论与发现

- **CALVIN ABC→D**：PALM（预测+进度）在第 1 子任务达 96.9%，第 5 子任务达 82.0%，相比最强基线 Seer（64.3%）绝对提升 17.7%；平均长度 4.48，超过 Seer（3.98）与 π0（3.92），整体提升约 12.5%。
- **LIBERO**：平均成功率 94.5%，其中 LIBERO-LONG 达 91.8%，比最强基线 CoT-VLA（69.0%）高 22.8%。
- **真实世界**：三种泛化设置下平均长度分别为 3.05、3.80、3.55，约为基线（OpenVLA/Octo）的 2 倍。
- **消融发现**：
  - 移除进度预测在预训练阶段损失最大（4.48→3.73），说明大规模长程视频数据对学习进度先验尤为关键；
  - 移除可供性预见在微调阶段损失最大（4.48→3.58），说明结构化未来可供性对下游精确长程规划至关重要；
  - 四类可供性累加均带来增益，其中 Dynamic 与 Spatial 结合效果最佳；Local 在 LIBERO-LONG 上略有波动（视角导致的几何偏差）；
  - 任一数据类型缺失都会导致性能下降，In-the-Wild 与人工标注数据影响最显著。

## 七、优点

- **方法亮点**：
  - 将可供性推理从“单一类型”扩展为**四类互补结构化表征**（全局语义、局部接触、空间放置、动态运动），覆盖长程操作的关键决策要素。
  - 将**连续进度信号**显式纳入动作空间，与动作联合扩散解码，无需额外高层规划器或层级控制器，实现平滑子任务切换。
  - 采用**可学习查询 + 结构化注意力**，在推理时可移除可供性头，保持策略轻量。
- **训练策略亮点**：
  - 融合机器人数据与长程视频数据预训练，利用视频中的子步骤/时间分段标注监督进度学习，提升数据利用效率。
  - 半自动标注管线降低人工成本。
- **实验亮点**：
  - 同时覆盖仿真与真实、多类泛化设置，长程序列长度达到 5–6 步；
  - 消融设计区分预训练与微调阶段，定位各模块作用，分析较细致。

## 八、不足与局限

- **算力信息缺失**：未报告 GPU 型号、数量、训练时长等，难以评估训练成本与可复现性。
- **真实世界规模有限**：仅 6 连子任务、20 次 rollout、单机器人平台（xArm6），任务与物体多样性有限，结论外推需谨慎。
- **统计严谨性**：真实世界实验未报告方差或置信区间；每次允许 3 次尝试的设定可能影响成功率解读。
- **标注依赖**：可供性监督依赖 Grounding DINO、SAM、SpatialVLM、RoboPoint、CoTracker 等外部模型生成伪标签，可能引入上游误差与偏差；微调仍需人工标注。
- **消融中的不一致**：Local 可供性在 LIBERO-LONG 上引入轻微下降，说明几何特征对视角变化敏感，方法在该维度上的鲁棒性尚有提升空间。
- **泛化边界未充分探索**：未讨论跨具身（不同机器人平台）、跨任务类别、动态环境或人机交互场景的表现；三种真实泛化设置（位姿、光照、干扰物）仍属较受控的桌面场景。
- **失败模式分析缺失**：论文未系统量化重复动作、漏步、提前终止等具体失败模式在 PALM 下的残余发生率。

（完）
