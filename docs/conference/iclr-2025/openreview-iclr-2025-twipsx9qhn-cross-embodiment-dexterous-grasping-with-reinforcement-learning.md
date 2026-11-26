---
title: Cross-Embodiment Dexterous Grasping with Reinforcement Learning
title_zh: 基于强化学习的跨具身灵巧抓取
authors: "Haoqi Yuan, Bohan Zhou, Yuhui Fu, Zongqing Lu"
date: 2025-01-22
pdf: "https://proceedings.iclr.cc/paper_files/paper/2025/file/ca8c6f28d8ba1e732e3f217ab05c4ec0-Paper-Conference.pdf"
tags: ["query:x-embodiment"]
score: 9.0
evidence: 基于特征抓取空间的通用策略控制多种灵巧手
tldr: 现有灵巧抓取研究多针对单一机械手设计策略，能够控制多种灵巧手的通用策略仍鲜有探索。本文研究基于强化学习的跨具身灵巧抓取，受人类手遥操作多种机械手启发，提出以人手特征抓取为基础的统一动作空间，策略输出特征抓取动作并经重定向映射为各机械手的关节动作。作者还简化了机械手本体感知输入。实验表明该通用策略可驱动多种灵巧手完成抓取任务，推动了跨具身通用控制的发展。
source: ICLR-2025-Accepted
selection_source: topic_research
id: openreview-iclr-2025-twipsx9qhn
canonical_id: "work:dd363ddb5553853a98fa35d4"
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
official_pdf_url: "https://proceedings.iclr.cc/paper_files/paper/2025/file/ca8c6f28d8ba1e732e3f217ab05c4ec0-Paper-Conference.pdf"
official_link: "https://proceedings.iclr.cc/paper_files/paper/2025/hash/ca8c6f28d8ba1e732e3f217ab05c4ec0-Abstract-Conference.html"
conference_acceptance_status: accepted
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-004.webp\", \"caption\": \"\", \"page\": 2, \"index\": 4, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-005.webp\", \"caption\": \"\", \"page\": 2, \"index\": 5, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-006.webp\", \"caption\": \"\", \"page\": 2, \"index\": 6, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-007.webp\", \"caption\": \"\", \"page\": 2, \"index\": 7, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-008.webp\", \"caption\": \"\", \"page\": 2, \"index\": 8, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-009.webp\", \"caption\": \"\", \"page\": 2, \"index\": 9, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-010.webp\", \"caption\": \"\", \"page\": 2, \"index\": 10, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-011.webp\", \"caption\": \"\", \"page\": 2, \"index\": 11, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-012.webp\", \"caption\": \"\", \"page\": 2, \"index\": 12, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-013.webp\", \"caption\": \"\", \"page\": 2, \"index\": 13, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-014.webp\", \"caption\": \"\", \"page\": 2, \"index\": 14, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-015.webp\", \"caption\": \"\", \"page\": 2, \"index\": 15, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-016.webp\", \"caption\": \"\", \"page\": 2, \"index\": 16, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-017.webp\", \"caption\": \"\", \"page\": 2, \"index\": 17, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-018.webp\", \"caption\": \"\", \"page\": 2, \"index\": 18, \"width\": 400, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-019.webp\", \"caption\": \"\", \"page\": 20, \"index\": 19, \"width\": 1366, \"height\": 415}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-020.webp\", \"caption\": \"\", \"page\": 20, \"index\": 20, \"width\": 1366, \"height\": 415}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-021.webp\", \"caption\": \"\", \"page\": 20, \"index\": 21, \"width\": 1366, \"height\": 415}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-022.webp\", \"caption\": \"\", \"page\": 20, \"index\": 22, \"width\": 1366, \"height\": 415}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-023.webp\", \"caption\": \"\", \"page\": 20, \"index\": 23, \"width\": 1366, \"height\": 415}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-024.webp\", \"caption\": \"\", \"page\": 21, \"index\": 24, \"width\": 1490, \"height\": 412}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-025.webp\", \"caption\": \"\", \"page\": 21, \"index\": 25, \"width\": 1490, \"height\": 412}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-twipsx9qhn/fig-026.webp\", \"caption\": \"\", \"page\": 21, \"index\": 26, \"width\": 1490, \"height\": 412}]"
motivation: 已有研究多针对单一机械手学习策略，缺乏能控制多种灵巧手的通用策略。
method: 构建基于人手特征抓取的统一动作空间，经重定向映射为各机械手关节动作并用强化学习训练。
result: 通用策略能够驱动多种不同结构的灵巧手完成抓取任务。
conclusion: 统一动作空间加重定向可实现跨具身灵巧抓取的通用控制。
---

## 摘要
灵巧手在复杂的真实世界抓取任务中展现出巨大潜力。尽管近期研究主要集中于为特定机械手学习策略，但控制多种灵巧手的通用策略的开发在很大程度上仍未被探索。本文研究使用强化学习（RL）学习跨具身灵巧抓取策略。受人类手通过遥操作控制各种灵巧手的能力启发，我们提出一种基于人手特征抓取（eigengrasps）的通用动作空间。策略输出特征抓取动作，然后通过重定向映射转换为每个机械手的具体关节动作。我们将机械手的本体感觉简化为仅包含指尖和手掌的位置，从而为不同机械手提供统一的观测空间。我们的方法使用单一基于视觉的策略，在四种不同具身形态上从YCB数据集抓取物体时达到80%的成功率。此外，我们的策略对两个此前未见过的具身形态表现出零样本泛化能力，并在高效微调中取得显著提升。更多细节和视频请访问我们的项目主页（https://sites.google.com/view/crossdex）。

## Abstract
Dexterous hands exhibit significant potential for complex real-world grasping tasks. While recent studies have primarily focused on learning policies for specific robotic hands, the development of a universal policy that controls diverse dexterous hands remains largely unexplored.
In this work, we study the learning of cross-embodiment dexterous grasping policies using reinforcement learning (RL). Inspired by the capability of human hands to control various dexterous hands through teleoperation, we propose a universal action space based on the human hand's eigengrasps. The policy outputs eigengrasp actions that are then converted into specific joint actions for each robot hand through a retargeting mapping. We simplify the robot hand's proprioception to include only the positions of fingertips and the palm, offering a unified observation space across different robot hands. Our approach demonstrates an 80\% success rate in grasping objects from the YCB dataset across four distinct embodiments using a single vision-based policy. Additionally, our policy exhibits zero-shot generalization to two previously unseen embodiments and significant improvement in efficient finetuning. For further details and videos, visit our project page (https://sites.google.com/view/crossdex).

---

## 论文详细总结（自动生成）

# 论文结构化总结：Cross-Embodiment Dexterous Grasping with Reinforcement Learning

## 1. 核心问题与整体含义

- **研究背景**：多指灵巧手在复杂真实抓取中潜力巨大，但现有工作大多针对单一机械手（如 ShadowHand）训练策略；换一种灵巧手往往需要重新采集数据、搭建仿真、调参和训练。
- **核心问题**：能否用强化学习训练一个**跨具身（cross-embodiment）通用灵巧抓取策略**，用单一策略控制不同自由度、不同手指数量、不同关节限位和几何形状的灵巧手，并能零样本迁移到训练中未见过的灵巧手？
- **关键难点**：
  - 不同灵巧手的自由度、手指数量、关节限位和运动学结构差异大，动作空间难以统一；
  - 不同手的尺寸、形状和接触几何不同，接触丰富的抓取任务对具身差异敏感；
  - 若在观测中加入具身特定信息（如关节角、机器人标签），策略容易依赖这些信息，难以泛化到新具身。
- **整体含义**：论文提出 CrossDex，借鉴人类通过遥操作控制多种机械手的经验，以人手姿态空间作为跨具身接口，向“通用灵巧抓取策略”迈出一步。

## 2. 方法论

### 2.1 核心思想

- 将**人手姿态**作为不同灵巧手之间的共享表示：
  - 策略不直接输出某个机械手的关节角，而是输出低维**人手特征抓取（eigengrasp）动作**；
  - 再通过**重定向映射（retargeting）**把该人手姿态转换为目标机械手的关节位置；
  - 观测中去除具身特定的手部关节角，仅保留跨具身一致的**指尖与手掌 3D 位置**。

### 2.2 统一动作空间：Eigengrasp 动作

- 使用 MANO 人手模型表示人手姿态 \((\theta,\beta)\)，其中 \(\theta\) 为关节轴角，\(\beta\) 为手形参数。
- 在 GRAB 人手抓取数据集上对 \(\theta\) 做 PCA，保留前 \(k\) 个特征向量 \(\{e_i\}_{i=1}^k\)，即 eigengrasps。
- 策略输出 \(k\) 维权重 \(w=(w_1,\dots,w_k)\)，组合得到人手姿态：
  \[
  \theta=\sum_{i=1}^k w_i e_i
  \]
- 再由 MANO 得到关键点位置，并通过 DexPilot 风格的重定向优化映射到目标灵巧手的关节位置。
- 重定向优化目标大致为：
  - 最小化机器人手与人手在指尖/手掌相对位置上的差异；
  - 加入时序平滑项 \(\|J_t^h-J_{t-1}^h\|^2\)；
  - 满足目标手的关节限位约束。
- **神经重定向加速**：由于优化式重定向速度仅约 300 fps，而 IsaacGym 并行仿真可达数万 fps，作者为每种手训练一个 MLP \(P_\xi^h\)，拟合从人手轴角 \(\theta\) 到该手关节位置 \(J^h\) 的映射，以支持批量并行计算。

### 2.3 统一观测空间

- 去除具身特定的手部关节位置 \(J^h\)，仅保留：
  - 手掌位置；
  - 前四根手指（拇指、食指、中指、无名指）的指尖 3D 位置；
  - 五指手忽略小指；少于四指的手将未使用位置置零。
- 状态策略形式：
  \[
  \pi^S_\psi(\hat J^a_t,w_t \mid J^a_t,x^h_t,b_t,v_\omega,\hat J^a_{t-1},w_{t-1})
  \]
  其中 \(J^a\) 为机械臂关节，\(x^h\) 为指尖/手掌位置，\(b\) 为物体位姿，\(v_\omega\) 为物体视觉编码。
- 视觉策略将物体位姿替换为物体点云 \(p_t\)：
  \[
  \pi^V_\phi(\hat J^a_t,w_t \mid J^a_t,x^h_t,p_t,\hat J^a_{t-1},w_{t-1})
  \]

### 2.4 训练流程

- 采用 **teacher-student / 多任务蒸馏** 框架：
  1. **教师学习**：按物体分组，为每个物体训练状态基策略，使用 PPO；并行环境轮换所有训练灵巧手。
  2. **蒸馏**：用 DAgger 将多个状态教师蒸馏为单一基于点云的视觉策略；在物体与手的组合并行环境中收集轨迹，用教师动作重标注并行为克隆。
- 多任务分组只按物体划分，不按具身划分；作者发现跨具身共同训练略优于逐手单独训练。
- 加入**具身随机化**：对灵巧手与机械臂连接原点位置加高斯噪声，提升对新安装位置/具身的鲁棒性。
- 奖励由距离项、抬升项、水平位移惩罚和成功奖励组成；成功定义为物体保持在一定高度且手靠近物体若干步。

## 3. 实验设计

### 3.1 数据集与场景

- **仿真环境**：IsaacGym。
- **抓取对象**：YCB 数据集中筛选出的 45 个日常物体；排除非刚体、凸包过多、过大或过扁等物体。
- **人手先验与重定向训练**：GRAB 数据集，约 160 万帧人手抓取数据。
- **微调新物体**：GRAB 中 55 个未见物体。
- **灵巧手**：6 种 URDF：
  - 训练手：ShadowHand（22 DoF，5 指）、Allegro Hand（16 DoF，4 指）、Schunk SVH Hand（20 DoF，5 指）、Ability Hand（10 DoF，5 指）；
  - 测试手：LEAP Hand（16 DoF，4 指）、Inspire Hand（12 DoF，5 指）。
- **机械臂**：仿真与真实均使用 6-DoF RealMan RM65；真实系统配 LEAP Hand 和 RealSense D435i RGB-D 相机。

### 3.2 Benchmark 与对比方法

- 主要指标：YCB 物体抓取成功率；另有零样本成功率、微调成功率、训练曲线和消融结果。
- 对比基线：
  - **MT-Raw-OA**：原始完整本体感知 + 原始关节动作，零填充对齐维度，并加入具身 one-hot 标签；
  - **MT-Raw-A**：原始动作 + 本文统一观测；
  - **MT-Raw-O**：原始观测 + 本文 eigengrasp 动作；
  - **No-Pretrain**：微调实验中从零训练；
  - **Individual**：逐手单独训练；
  - 重定向方法对比：Position retargeting、Vector retargeting、DexPilot；
  - eigengrasp 维度消融：1-E、3-E、9-E、18-E、36-E、MANO 原始 45 维动作；
  - 具身随机化与具身特定观测消融；
  - 训练手数量消融：1、2、3、4 只手；
  - 三指 D’Claw Gripper 扩展实验。
- 所有主要基线采用相同 teacher-student 训练框架，以尽量保证比较公平。

## 4. 资源与算力

- 文中明确提到：
  - 8,192 并行环境的实验可在**单张 NVIDIA RTX 4090** 上完成；
  - 16,384 并行环境 + PointNet 的大规模视觉蒸馏实验使用**单张 NVIDIA A800**；
  - 视觉策略在 16,384 环境下约 **10 小时**完成训练；
  - 同样性能也可用 4,096 环境在 RTX 4090 上实现，约 **2 天**；
  - PPO 状态策略训练 40,000 次迭代；DAgger 蒸馏 20,000 次迭代；微调 10,000–20,000 次迭代。
- **未明确说明**：总共使用了多少张 GPU、总 GPU 小时、所有实验累计训练成本。文中只给出单次/单类实验的硬件与时长信息。

## 5. 实验数量与充分性

- 实验覆盖大致包括：
  - 主实验：45 个 YCB 物体 × 4 个训练手 + 2 个未见手，比较 4 种方法（CrossDex 与 3 个 MT-Raw 基线），并区分状态策略与视觉策略；
  - 微调实验：未见 LEAP 手上的 5 个 YCB 物体状态微调、全 YCB 多任务视觉微调、55 个 GRAB 未见物体多任务视觉微调，比较 5 种设置；
  - 消融：3 种重定向方法、6 种动作空间配置、4 种随机化/观测组合、4 种训练手数量；
  - 扩展：三指 D’Claw 实验；
  - 真实世界：RealMan RM65 + LEAP Hand 的定性演示。
- **充分性评价**：
  - 覆盖了动作空间、观测空间、重定向、具身随机化、训练手数量等关键因素，消融较系统；
  - 同时评估训练手、未见手、零样本和微调，较全面地回应“跨具身”主张；
  - 但主表 Table 1 未报告方差或置信区间，部分比较的统计显著性不明确；
  - 真实实验仅有视频演示，缺少定量真实世界成功率；
  - 训练具身仅 4 种，仍属小规模具身集合；
  - 基线虽共享训练框架，但 MT-Raw 系列依赖人工对齐 URDF 的关节顺序和方向，这种对齐本身可能影响公平性，作者也承认其泛化不如 eigengrasp 对齐。

## 6. 主要结论与发现

- **单一视觉策略可控制多种灵巧手**：CrossDex 在四个训练具身上视觉策略平均成功率为 **80.0%**，优于 MT-Raw-OA 的 78.2%、MT-Raw-A 的 72.8%、MT-Raw-O 的 77.9%。
- **零样本迁移到未见手**：在两个未见手上，CrossDex 视觉策略平均零样本成功率为 **35.2%**，高于基线（14.5%–21.0%）；状态策略为 39.1%，也高于基线。
- **微调优势明显**：在未见 LEAP 手上，CrossDex 微调后在 5 个 YCB 物体状态任务上达 **87.2%**，全 YCB 多任务视觉任务达 **64.3%**，55 个 GRAB 新物体多任务视觉任务达 **74.0%**，均优于基线和从零训练。
- **跨具身共同训练有效**：与逐手单独训练相比，跨具身共同训练略提升稳定性和效率，性能相当。
- **动作空间鲁棒**：eigengrasp 维度在 1–36 范围内变化时性能较稳定；但 1 维动作容量不足，直接使用 45 维 MANO 轴角在零样本迁移上更差。
- **重定向方法不敏感**：Position、Vector、DexPilot 三种重定向性能接近，说明方法对重定向目标选择较鲁棒。
- **统一观测很重要**：加入具身特定观测会拉大状态策略与视觉策略差距，并降低对未见手的泛化；具身随机化有助于泛化。
- **训练手数量增加可提升未见手性能**：1、2、3、4 个训练手时，未见手成功率分别约为 12.9%、32.8%、43.4%、48.2%。
- **可扩展到三指手**：D’Claw Gripper 成功率约 85.3%，但形态差异导致部分姿态一致性较差。

## 7. 优点

- **跨具身接口设计巧妙**：用人类手部 eigengrasp 作为统一动作空间，避免直接对齐不同机械手的关节空间，思想简洁且与遥操作实践一致。
- **观测空间统一且具身无关**：仅使用指尖和手掌位置，避免策略依赖机器人标签或关节角，有利于零样本迁移。
- **神经重定向显著提升训练效率**：用 MLP 拟合优化式重定向，解决仿真高吞吐与重定向低速之间的瓶颈。
- **训练框架可扩展**：teacher-student + PPO + DAgger 的组合适合多物体、多具身的大规模并行训练。
- **实验维度较丰富**：覆盖训练手/未见手、零样本/微调、动作空间、重定向、随机化、训练手数量和不同手指数，结论较有说服力。
- **工程价值明确**：给出仿真与真实系统配置、点云构建方式、训练超参和算力信息，复现性较好。

## 8. 不足与局限

- **训练具身数量有限**：仅 4 种训练手，跨具身泛化能力受限于具身多样性；作者也将其列为局限。
- **零样本性能仍不高**：未见手视觉策略平均成功率约 35.2%，虽优于基线，但距离实用仍有差距。
- **任务范围窄**：仅研究桌面抓取与抬升，未覆盖手内重定向、动态交接、功能性抓取等更复杂任务。
- **真实世界验证不足**：仅有 RealMan RM65 + LEAP Hand 的定性视频，缺少真实场景定量成功率、sim-to-real 差距分析。
- **依赖人手先验与重定向质量**：方法建立在 MANO、GRAB 和 DexPilot 式重定向上；对非拟人手（如 D’Claw）一致性下降，形态差异大时可能受限。
- **观测简化可能损失信息**：忽略小指、仅保留前四指、少于四指零填充，可能丢失部分抓取相关信息；对某些依赖小指或特殊接触的任务不一定最优。
- **主结果统计报告不完整**：Table 1 未给方差/置信区间；部分比较的显著性和稳定性证据不足。
- **基线公平性存在讨论空间**：MT-Raw 基线依赖人工对齐 URDF 关节顺序和方向，虽作者说明其泛化较弱，但不同对齐方式可能影响结论。
- **计算成本较高**：大规模视觉蒸馏需 16,384 并行环境和 A800，尽管可用 4090 以更长时间完成，仍对资源有一定要求。

（完）
