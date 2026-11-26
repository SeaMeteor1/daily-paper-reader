---
title: "ManipTrans: Efficient Dexterous Bimanual Manipulation Transfer via Residual Learning"
title_zh: ManipTrans：基于残差学习的高效灵巧双手操作迁移
authors: "Li, Kailin, Li, Puhao, Liu, Tengyu, Li, Yuyang, Huang, Siyuan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Li_ManipTrans_Efficient_Dexterous_Bimanual_Manipulation_Transfer_via_Residual_Learning_CVPR_2025_paper.pdf"
tags: ["query:x-embodiment"]
score: 8.0
evidence: 将人类双臂操作技能迁移至灵巧机器人手
tldr: 针对数据驱动具身智能算法难以通过强化学习或真实遥操作获取大规模类人双臂操作序列的问题，本文提出ManipTrans两阶段方法，先在仿真中预训练通用轨迹模仿器以模仿手部运动，再在交互约束下微调残差模块，从而将人类双臂技能高效迁移至灵巧机器人手。实验表明该方法能准确执行复杂双臂任务，为灵巧操作技能迁移提供了高效方案。
source: CVPR-2025-Accepted
selection_source: topic_research
id: cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper
canonical_id: "work:a7dda28e64c4f89d155c9189"
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
conference_acceptance_status: accepted
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 3843, \"height\": 1278}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 695, \"height\": 690}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 3601, \"height\": 1379}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 3244, \"height\": 900}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 7, \"index\": 5, \"width\": 3309, \"height\": 1196}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 7, \"index\": 6, \"width\": 3205, \"height\": 1386}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 8, \"index\": 7, \"width\": 2039, \"height\": 868}]"
motivation: 传统强化学习和真实遥操作难以获取大规模、精确的类人双臂操作序列。
method: ManipTrans采用两阶段方法，先预训练通用轨迹模仿器，再在交互约束下微调残差模块。
result: 在仿真中将人类双臂技能迁移至灵巧机器人手，能准确执行复杂双臂任务。
conclusion: 为灵巧双臂操作技能从人类向机器人迁移提供了高效方案。
---

## 摘要
人类双手在交互中起着核心作用，这推动了灵巧机器人操作研究的不断增长。数据驱动的具身智能算法需要精确、大规模、类人的操作序列，而传统强化学习或真实世界遥操作难以获得这些序列。为解决这一问题，我们提出了 ManipTrans，一种新颖的两阶段方法，用于在仿真中高效地将人类双手技能迁移到灵巧机器人手。ManipTrans 首先预训练一个通用轨迹模仿器以模仿手部运动，然后在交互约束下微调特定的残差模块，从而能够高效学习并准确执行复杂的双手任务。实验表明，ManipTrans 在成功率、保真度和效率方面优于最先进的方法。借助 ManipTrans，我们将多个手-物体数据集迁移到机器人手，构建了 DexManipNet，这是一个大规模数据集，包含此前未探索的任务，如盖笔帽和拧开瓶盖。DexManipNet 包含 3.3K 个机器人操作回合，并且易于扩展，可促进灵巧手的进一步策略训练并支持真实世界部署。

## Abstract
Human hands play a central role in interacting, motivating increasing research in dexterous robotic manipulation. Data-driven embodied AI algorithms demand precise, large-scale, human-like manipulation sequences, which are challenging to obtain with conventional reinforcement learning or real-world teleoperation. To address this, we introduce ManipTrans, a novel two-stage method for efficiently transferring human bimanual skills to dexterous robotic hands in simulation. ManipTrans first pre-trains a generalist trajectory imitator to mimic hand motion, then fine-tunes a specific residual module under interaction constraints, enabling efficient learning and accurate execution of complex bimanual tasks. Experiments show that ManipTrans surpasses state-of-the-art methods in success rate, fidelity, and efficiency. Leveraging ManipTrans, we transfer multiple hand-object datasets to robotic hands, creating DexManipNet, a large-scale dataset featuring previously unexplored tasks like pen capping and bottle unscrewing. DexManipNet comprises 3.3K episodes of robotic manipulation and is easily extensible, facilitating further policy training for dexterous hands and enabling real-world deployments.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究动机**：数据驱动的具身智能需要大规模、精确、类人的灵巧操作序列，但传统强化学习依赖任务特定奖励函数，难以扩展到复杂双臂任务；真实遥操作则成本高、劳动密集，且数据通常绑定特定机器人本体。
- **核心问题**：如何高效地把人类双手操作技能（尤其是复杂双手协作任务）迁移到仿真中的灵巧机器人手，同时克服人手与机器人手之间的形态差异、MoCap 噪声、接触物理约束以及高维双臂动作空间带来的困难。
- **整体含义**：论文提出 **ManipTrans**，将“手部运动模仿”和“物体交互约束满足”解耦为两阶段学习，从而在仿真中生成物理合理、任务合规的机器人手操作轨迹，并进一步构建大规模数据集 **DexManipNet**，为灵巧手策略学习和真实部署提供数据基础。

## 2. 方法论

- **核心思想**：将人类操作迁移视为两阶段过程：
  1. **预训练通用手部轨迹模仿器**：只关注手部运动模仿，学习将人类手部 MoCap 轨迹映射到机器人手动作，缓解形态差异。
  2. **残差学习微调交互策略**：在预训练模仿动作基础上学习残差修正，使机器人手满足物体接触、双手协调等物理与任务约束。
- **问题建模**：将迁移建模为 MDP，用 PPO 训练。动作包括机器人手各关节的目标位置（用于 PD 控制）和作用于手腕的 6-DoF 力。双手场景中左右手分别对应人类左右手，并与两个物体交互。
- **第一阶段：手部轨迹模仿**
  - 状态包含参考手部轨迹和机器人当前本体感知（关节角、手腕位姿及其速度）。
  - 奖励由三部分组成：手腕位姿/速度跟踪奖励、手指关键点模仿奖励、平滑性奖励。
  - 手指模仿奖励对若干对应关键点计算加权指数距离，重点强调拇指、食指、中指指尖等关键点，以缓解人机手形态差异。
  - 平滑性奖励惩罚关节速度与力矩的乘积，减少抖动。
  - 训练使用手部-only 数据、镜像平衡左右手、参考状态初始化、早停和课程学习；当机器人手关键点偏离参考超过阈值时终止并重采样，阈值逐步收紧。
- **第二阶段：残差交互学习**
  - 扩展状态空间，加入物体参考轨迹、物体相对手腕位置与速度、质量、重力向量、BPS 形状表示、手-物体距离、仿真接触力等交互信息。
  - 残差策略在给定第一阶段模仿动作和当前状态后采样残差动作，最终动作为 `a_t = a_I + Δa_R`，并裁剪到关节限位内。
  - 残差模块以零均值高斯初始化并 warm-up，避免初期破坏已学到的模仿动作。
  - 奖励包括第一阶段模仿奖励、物体跟随奖励、接触力奖励。接触力奖励在 MoCap 表明人手指尖与物体距离足够近时鼓励产生适当接触力。
  - 训练采用物理松弛策略：初期将重力设为零、摩擦系数调高，使机器人先学会稳定抓取和对齐；随后逐步恢复真实重力和合适摩擦。结合 RSI、早停、课程学习和接触终止条件，促使策略学习稳定接触。
- **数据集构建**：用 ManipTrans 将 FAVOR、OakInk-V2 等手-物体交互数据迁移到机器人手，构建 DexManipNet。主平台为仿真中的 12-DoF Inspire Hand，包含 61 类任务、3.3K episodes、约 1.2K 物体、134 万帧，其中约 600 段为复杂双手任务。

## 3. 实验设计

- **数据集/场景**：
  - 定量评估使用 OakInk-V2 官方验证集，人工筛选任务完整、语义相关、时长 4–20 秒、60 fps 的 MoCap 序列，排除可变形或过大物体，得到约 80 个 episodes，约一半为双手任务。
  - 定性评估还使用 GRAB、FAVOR、ARCTIC 等数据集，并展示铰接物体操作。
  - 真实部署使用两条 7-DoF Realman 机械臂和一对升级版 Inspire Hands（真实硬件 6-DoF，带触觉传感器）。
- **Benchmark/指标**：
  - 每帧平均物体旋转误差、平移误差、平均关节位置误差、平均指尖位置误差。
  - 成功率 SR：要求上述误差分别低于 30°、3 cm、8 cm、6 cm；双手任务中任一只手失败即视为失败，因此标准更严格。
  - 策略学习 benchmark：在 DexManipNet 的瓶子重排任务上训练模仿学习策略，最终物体位置距目标 10 cm 内视为成功。
- **对比方法**：
  - RL 组合类基线：Retarget-Only、RL-Only、Retarget + Residual。
  - 优化类方法 QuasiSim：因官方完整流程和验证集不可得，仅做定性比较。
  - 策略学习对比：IBC、BET、DP-UNet、DP-Trans。
- **跨本体实验**：在 Shadow Hand（22 DoF）、铰接 MANO Hand（22 DoF）、Inspire Hand（12 DoF）、Allegro Hand（16 DoF）上验证，不改变网络超参数和奖励权重。
- **消融实验**：触觉信息三种用法（观测、奖励、终止条件）以及训练策略（放松重力、提高摩擦、放松阈值）的消融。

## 4. 资源与算力

- 实验在 **Isaac Gym** 中进行，同时模拟 **4096 个环境**，时间步长 **1/60 s**。
- 硬件为 **一台配备 NVIDIA RTX 4090 GPU 和 Intel i9-13900KF CPU 的个人计算机**。文中未明确给出 GPU 数量，按描述应为单机单卡。
- 训练使用 Actor-Critic PPO，训练 horizon 32 帧，minibatch 1024，折扣因子 0.99，Adam 初始学习率 5×10⁻⁴ 并带衰减。
- 文中未给出所有任务的完整训练总时长或总算力消耗；仅给出效率示例：对一个 60 帧的未见单手机械臂轨迹，ManipTrans 约需 **15 分钟**训练达到稳健结果，而 QuasiSim 约需 **40 小时**优化。

## 5. 实验数量与充分性

- **实验覆盖较广**：
  - 定量迁移实验：OakInk-V2 约 80 个 episodes，覆盖单手和双手任务，对比 3 类 RL 组合基线。
  - 定性实验：GRAB、FAVOR、ARCTIC、QuasiSim 对比、铰接物体操作。
  - 跨本体实验：4 种不同 DoF 和形态的机器人手。
  - 真实世界部署：双手机械臂 + Inspire Hands，展示开牙膏、盖笔帽等任务。
  - 消融实验：触觉 3 组、训练策略 3 组。
  - 策略学习 benchmark：4 种模仿学习方法，140 条瓶子重排序列，85%/15% 划分，每条 20 次 rollout。
  - 数据集构建：61 类任务、3.3K episodes、134 万帧。
- **充分性判断**：
  - 优点是多任务、多本体、仿真与真实部署结合，实验维度较全面。
  - 但定量迁移评估仅约 80 个筛选后的 episodes，规模相对有限；真实世界主要为定性展示，缺少系统量化成功率。
  - 未报告多随机种子、方差或置信区间，统计稳健性有限。
  - 部分基线因缺少公开代码而由作者重实现；QuasiSim 因完整流程和验证集不可得只能定性比较，直接公平性受限。
  - 表 1 中前四项误差指标只在成功 rollout 上计算，可能存在选择偏差；成功率阈值也较粗粒度。
- **总体评价**：实验设计覆盖面较好，能支撑方法有效性结论，但严格意义上的公平对比和统计充分性仍有提升空间。

## 6. 主要结论与发现

- ManipTrans 在 OakInk-V2 单手/双手迁移任务上优于 Retarget-Only、RL-Only、Retarget + Residual，取得更低旋转/平移/关节/指尖误差和更高成功率；双手成功率仍明显低于单手（39.5% vs 58.1%），说明双手任务仍具挑战。
- 两阶段解耦设计能有效缓解人机形态差异，并通过残差学习满足接触和物体交互约束，生成更自然、物理合理的动作。
- 方法具有跨本体泛化能力，在 Shadow、MANO、Inspire、Allegro 等不同手型上无需大幅调参即可工作。
- 真实世界回放展示了较灵巧的双手操作，如打开牙膏盖等此前较难通过遥操作或 RL 直接获得的行为。
- DexManipNet 为灵巧手策略学习提供了大规模、可扩展数据；现有模仿学习方法在该数据集上的瓶子重排成功率仍较低（IBC 4.69%、BET 9.69%、DP-UNet 18.44%、DP-Trans 14.69%），说明灵巧操作策略学习仍很困难。

## 7. 优点

- **方法简洁有效**：将手部模仿与物理交互解耦，降低高维双臂动作空间的学习难度，避免复杂任务特定奖励工程和预定义阶段划分。
- **残差学习设计合理**：在预训练模仿动作上做增量修正，零均值初始化和 warm-up 有助于稳定训练。
- **物理约束利用充分**：引入接触力、手-物体距离、物体形状 BPS、重力/摩擦松弛课程等，提升接触丰富任务的稳定性。
- **跨本体适应性强**：依赖人手指与机器人关节的对应关系，可在多种 DoF 和形态的手上迁移。
- **效率突出**：相比优化类方法训练时间显著缩短，且可在个人计算机上完成。
- **数据贡献明显**：DexManipNet 规模较大、任务多样，包含盖笔帽、拧瓶盖等此前较少探索的双手任务，并可作为策略学习 benchmark。
- **仿真到真实部署有展示**：通过指尖对齐拟合和 IK 控制实现真实机械臂回放，验证了实际可行性。

## 8. 不足与局限

- 作者自述：部分 MoCap 序列无法有效迁移，主要原因是交互位姿噪声过大，以及物体模型（尤其铰接物体）不够精确。
- 定量评估规模有限，且经过人工筛选；真实世界部署主要是定性展示，缺少系统量化成功率、鲁棒性和失败案例分析。
- 未报告多随机种子实验、方差或统计显著性，结果稳健性证据不足。
- 基线对比存在限制：RL 基线为作者重实现，QuasiSim 无法定量比较；表 1 误差指标仅在成功 rollout 上计算，可能引入选择偏差。
- 方法依赖 MoCap 物体轨迹、物体网格/凸包和仿真接触力，真实场景中物体模型误差、感知噪声和触觉标定会影响迁移效果。
- 人机关键点对应和奖励权重需人工选择，虽然跨本体实验显示一定通用性，但仍可能限制完全自动化扩展。
- 真实硬件使用 6-DoF Inspire Hand，而仿真主平台为 12-DoF，需要通过拟合降维；回放时不强制严格时间对齐，可能掩盖动态执行差异。
- 数据集主要来源于 FAVOR、OakInk-V2 等，任务和物体覆盖虽广，但仍排除可变形、超大物体，应用范围有限。

（完）
