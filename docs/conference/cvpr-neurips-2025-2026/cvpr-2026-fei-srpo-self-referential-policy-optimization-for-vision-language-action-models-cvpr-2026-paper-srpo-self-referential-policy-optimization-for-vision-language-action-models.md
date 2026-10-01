---
title: "SRPO: Self-Referential Policy Optimization for Vision-Language-Action Models"
title_zh: SRPO：面向视觉-语言-动作模型的自指策略优化
authors: "Fei, Senyu, Wang, Siyin, Ji, Li, Li, Ao, Zhang, Shiduo, Liu, Liming, Hou, Jinlong, Gong, Jingjing, Zhao, Xianzhong, Qiu, Xipeng"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Fei_SRPO_Self-Referential_Policy_Optimization_for_Vision-Language-Action_Models_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 面向机器人操作的VLA模型强化学习后训练
tldr: 该文针对视觉-语言-动作模型过度依赖专家演示、强化学习奖励稀疏的问题，提出自指策略优化SRPO框架。方法利用模型自身产生的成功轨迹构建自指奖励信号，无需外部演示或人工奖励设计，缓解失败轨迹中信息浪费的问题。实验表明其训练效率与性能优于现有VLA强化学习方法，为VLA后训练提供了高效且无需演示的新范式。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 1140, \"height\": 1135}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 1136, \"height\": 1130}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 822, \"height\": 818}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 427, \"height\": 389}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 3, \"index\": 7, \"width\": 720, \"height\": 346}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 3, \"index\": 8, \"width\": 756, \"height\": 340}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 3, \"index\": 9, \"width\": 740, \"height\": 362}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 3, \"index\": 10, \"width\": 1828, \"height\": 976}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 3, \"index\": 11, \"width\": 334, \"height\": 449}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 3, \"index\": 12, \"width\": 1304, \"height\": 648}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 3, \"index\": 13, \"width\": 2387, \"height\": 1111}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 3, \"index\": 14, \"width\": 2141, \"height\": 936}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 3, \"index\": 15, \"width\": 429, \"height\": 286}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 3, \"index\": 16, \"width\": 469, \"height\": 314}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 3, \"index\": 17, \"width\": 1412, \"height\": 1209}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 3, \"index\": 18, \"width\": 1180, \"height\": 860}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 3, \"index\": 19, \"width\": 673, \"height\": 511}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-020.webp\", \"caption\": \"\", \"page\": 3, \"index\": 20, \"width\": 310, \"height\": 532}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-021.webp\", \"caption\": \"\", \"page\": 3, \"index\": 21, \"width\": 310, \"height\": 532}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-022.webp\", \"caption\": \"\", \"page\": 3, \"index\": 22, \"width\": 309, \"height\": 532}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-023.webp\", \"caption\": \"\", \"page\": 3, \"index\": 23, \"width\": 286, \"height\": 449}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-024.webp\", \"caption\": \"\", \"page\": 3, \"index\": 24, \"width\": 641, \"height\": 641}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-025.webp\", \"caption\": \"\", \"page\": 3, \"index\": 25, \"width\": 310, \"height\": 533}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-026.webp\", \"caption\": \"\", \"page\": 3, \"index\": 26, \"width\": 309, \"height\": 532}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-027.webp\", \"caption\": \"\", \"page\": 3, \"index\": 27, \"width\": 309, \"height\": 532}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-028.webp\", \"caption\": \"\", \"page\": 3, \"index\": 28, \"width\": 310, \"height\": 533}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-029.webp\", \"caption\": \"\", \"page\": 3, \"index\": 29, \"width\": 310, \"height\": 532}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-030.webp\", \"caption\": \"\", \"page\": 3, \"index\": 30, \"width\": 1632, \"height\": 682}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-031.webp\", \"caption\": \"\", \"page\": 3, \"index\": 31, \"width\": 1784, \"height\": 822}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-032.webp\", \"caption\": \"\", \"page\": 3, \"index\": 32, \"width\": 2453, \"height\": 1219}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-033.webp\", \"caption\": \"\", \"page\": 3, \"index\": 33, \"width\": 641, \"height\": 641}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-034.webp\", \"caption\": \"\", \"page\": 3, \"index\": 34, \"width\": 850, \"height\": 262}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-035.webp\", \"caption\": \"\", \"page\": 3, \"index\": 35, \"width\": 496, \"height\": 330}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-036.webp\", \"caption\": \"\", \"page\": 3, \"index\": 36, \"width\": 493, \"height\": 317}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-037.webp\", \"caption\": \"\", \"page\": 3, \"index\": 37, \"width\": 1125, \"height\": 1111}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-038.webp\", \"caption\": \"\", \"page\": 3, \"index\": 38, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-039.webp\", \"caption\": \"\", \"page\": 3, \"index\": 39, \"width\": 812, \"height\": 436}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-040.webp\", \"caption\": \"\", \"page\": 7, \"index\": 40, \"width\": 2372, \"height\": 1172}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-041.webp\", \"caption\": \"\", \"page\": 7, \"index\": 41, \"width\": 2322, \"height\": 1147}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-042.webp\", \"caption\": \"\", \"page\": 7, \"index\": 42, \"width\": 2352, \"height\": 1162}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-043.webp\", \"caption\": \"\", \"page\": 7, \"index\": 43, \"width\": 2352, \"height\": 1162}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-044.webp\", \"caption\": \"\", \"page\": 7, \"index\": 44, \"width\": 2352, \"height\": 1162}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-045.webp\", \"caption\": \"\", \"page\": 7, \"index\": 45, \"width\": 2379, \"height\": 1175}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-046.webp\", \"caption\": \"\", \"page\": 7, \"index\": 46, \"width\": 2890, \"height\": 1919}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-047.webp\", \"caption\": \"\", \"page\": 7, \"index\": 47, \"width\": 2890, \"height\": 1919}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-048.webp\", \"caption\": \"\", \"page\": 8, \"index\": 48, \"width\": 3218, \"height\": 1593}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-049.webp\", \"caption\": \"\", \"page\": 8, \"index\": 49, \"width\": 1735, \"height\": 1608}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-050.webp\", \"caption\": \"\", \"page\": 8, \"index\": 50, \"width\": 1819, \"height\": 1611}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-srpo-self-referential-policy-optimization-for-vision-language-action-models-cvpr-2026-paper/fig-051.webp\", \"caption\": \"\", \"page\": 8, \"index\": 51, \"width\": 3229, \"height\": 1606}]"
motivation: VLA模型过度依赖专家演示导致演示偏差，现有强化学习方法又受严重奖励稀疏困扰。
method: 提出自指策略优化框架，利用模型自身成功轨迹构建奖励，无需外部演示与人工奖励工程。
result: 有效缓解奖励稀疏问题，提升训练效率与机器人操作性能。
conclusion: 为VLA强化学习后训练提供了无需演示的高效解决方案。
---

## Abstract
Vision-Language-Action (VLA) models excel in robotic manipulation but are constrained by their heavy reliance on expert demonstrations, leading to demonstration bias and limiting performance. Reinforcement learning (RL) is a vital post-training strategy to overcome these limits, yet current VLA-RL methods, including group-based optimization approaches, are crippled by severe reward sparsity. Relying on binary success indicators wastes valuable information in failed trajectories, resulting in low training efficiency. To solve this, we propose Self-Referential Policy Optimization (SRPO), a novel VLA-RL framework. SRPO eliminates the need for external demonstrations or manual reward engineering by leveraging the model's own successful trajectories, generated within the current training batch, as a self-reference. This allows us to assign a progress-wise reward to failed attempts. A core innovation is the use of Latent World Representations to measure behavioral progress robustly. Instead of relying on raw pixels or requiring domain-specific fine-tuning, we utilize the compressed, transferable encodings from a world model's latent space. These representations naturally capture progress patterns across environments, enabling accurate, generalized trajectory comparison. Empirical evaluations on the LIBERO benchmark demonstrate SRPO's efficiency and effectiveness. Starting from a supervised baseline with 48.9% success, SRPO achieves a new state-of-the-art success rate of 99.2% in just 200 RL steps, representing a 103% relative improvement without any extra supervision. Furthermore, SRPO shows substantial robustness, achieving a 167% performance improvement on the LIBERO-Plus benchmark.

---

## 论文详细总结（自动生成）

## 1. 论文核心问题与整体含义

- **研究动机**：Vision-Language-Action（VLA）模型在机器人操作中表现突出，但高度依赖专家演示，容易产生“演示偏差”，限制其超越人类演示水平。
- **现有问题**：强化学习（RL）是重要的后训练手段，但当前 VLA-RL 方法普遍受**奖励稀疏**困扰；基于组优化的 GRPO 类方法仅依赖二元成功信号（0/1），失败轨迹中的有价值信息被浪费，训练效率低。
- **已有补救方案的局限**：过程奖励建模（PRM）或手工任务分解虽可提供更密集反馈，但通常依赖专家演示或任务特定先验，难以扩展到自主在线学习。
- **整体含义**：论文提出 **Self-Referential Policy Optimization（SRPO）**，用模型自身在当前训练批次中产生的成功轨迹作为“自参考”，为失败轨迹分配进度奖励，从而在不依赖外部演示和人工奖励工程的情况下缓解奖励稀疏，提升 VLA 后训练效率与性能。

## 2. 方法论

- **核心思想**：将监督问题从“如何获得专家标签”转为“如何从自身成功轨迹中提取进度奖励”。成功轨迹作为参考标准，失败轨迹根据其与成功行为模式的接近程度获得进度奖励。
- **关键组件**：
  - 策略在环境中 rollout，收集一个批次内的成功与失败轨迹。
  - 使用预训练世界模型编码器（如 V-JEPA 2）将轨迹观测编码到**潜在世界表示空间**。
  - 对成功轨迹表示进行 **DBSCAN 聚类**，得到若干代表性中心。
  - 对每条失败轨迹，计算其表示到最近成功中心的 **L2 距离**；距离越小，表示行为越接近成功，奖励越高。
- **奖励设计**：
  - 成功轨迹奖励设为 1.0。
  - 失败轨迹奖励通过距离归一化和激活函数映射到 (0,1) 区间。
  - 采用**轨迹级奖励**而非过度细粒度奖励塑形，以避免策略收敛到次优解。
- **策略优化**：
  - 沿用 GRPO 风格的组相对优势估计：将奖励标准化为优势，计算新旧策略概率比。
  - 使用裁剪代理目标，并加入与参考策略的 KL 正则项以保持训练稳定。
  - 整体目标为裁剪代理目标的期望加上 KL 正则项。
- **算法流程简述**：
  1. 当前批次 rollout，得到成功/失败轨迹。
  2. 世界模型编码轨迹，聚类成功轨迹中心。
  3. 计算失败轨迹到成功中心的距离并生成进度奖励。
  4. 基于组内奖励计算优势。
  5. 用裁剪目标与 KL 正则更新策略。

## 3. 实验设计

- **数据集 / 场景**：
  - 仿真主实验：**LIBERO** 基准，包括 Spatial、Object、Goal、Long 四个 suite，每个 suite 10 个任务。
  - 鲁棒性实验：**LIBERO-Plus**，引入七类扰动维度：Camera、Robot-Init、Language、Light、Background、Noise、Layout。
  - 真实世界：X-ARM 7 机器人上的五个操作任务，包括 Put apple into the plate、Put pear into the plate、Folding towels、Cleaning whiteboard、Select Poker。
- **模型 / 基座**：
  - 仿真使用改进版 OpenVLA，加入 action chunking 和 parallel decoding，记为 **OpenVLA***。
  - OpenVLA*-One：每个任务仅一条演示的 SFT 基线；OpenVLA*-Full：全量 SFT。
  - 真实世界比较 π0 与 π0-FAST 两种 VLA 策略。
- **对比方法**：
  - RL 方法：SimpleVLA-RL、RIPT-VLA、RLinf（GRPO）、VLA-RL（PPO）、GRAPE、TGRPO、World-Env 等。
  - 模仿学习 / 其他 VLA 方法作为参考：OpenVLA、Pi0、Pi0+fast、FASTer、SmolVLA、WorldVLA、NORA、CoT-VLA、UniVLA、TraceVLA、MolmoAct、ThinkAct、GR00T N1、3D-CAVLA、OpenVLA-OFT 等。
- **评价指标**：
  - LIBERO：成功率。
  - LIBERO-Plus：七类扰动下的成功率。
  - 进度奖励评估：Spearman Correlation、Monotonicity、MMD、JS Divergence、Standardized Mean Difference。
- **实验设置**：
  - 从官方 checkpoint 出发，每任务单条演示 SFT，再进行 SRPO 在线 RL 后训练。
  - 使用 SiiRL 训练框架，世界模型使用大规模视频预训练的 V-JEPA 2。

## 4. 资源与算力

- 论文正文提到：“Training details and compute reports are provided in the Appendix F.”
- 但在给定提取文本中**未包含附录 F 的具体内容**，因此无法确认 GPU 型号、数量、训练时长、总计算量等细节。
- 可确认的算力相关信息仅有：
  - 使用 **V-JEPA 2** 作为世界模型编码器。
  - 使用 **SiiRL** 作为训练框架。
  - 主实验 RL 步数较少：Spatial 79 步、Object 59 步、Goal 103 步、Long 219 步。
- **结论**：论文声称有计算报告，但当前材料未提供具体算力细节，无法复现其资源开销。

## 5. 实验数量与充分性

- **主要实验组数概览**：
  - LIBERO 四个 suite 主性能对比。
  - LIBERO-Plus 七维扰动鲁棒性对比。
  - 进度奖励定性可视化与定量 benchmark：700 条成功轨迹 + 300 条失败轨迹，对比 Pixel-level、ImageBind、SRPO。
  - 训练效率对比：SRPO vs GRPO，在 LIBERO-Long、LIBERO-Object 上比较。
  - 动作空间探索分析：Full-shot SFT vs One-shot SFT + SRPO，LIBERO-Spatial。
  - 真实世界实验：五个任务，π0 与 π0-FAST 两种 backbone，对比 SFT 与离线 RL。
  - 在线 / 离线 SRPO 对比：OpenVLA*-One + Offline SRPO 与 + Online SRPO。
- **充分性评价**：
  - 覆盖了主性能、鲁棒性、奖励质量、训练效率、探索行为、真实世界迁移，整体较充分。
  - 奖励设计有与 Pixel-level、ImageBind 的对比，验证了潜在世界表示优于像素级和通用视觉嵌入。
  - 真实世界实验增强了结论的外部有效性。
- **客观性与公平性**：
  - 在 LIBERO 上与多种 RL 方法比较，且基于统一 OpenVLA* 基座，较有参考性。
  - 部分模仿学习基线使用额外模态（多相机、本体感知、3D 数据）或不同预训练数据，作者也声明仅作参考，因此并非完全同条件比较。
  - 消融维度仍有限：正文未详细展示世界模型选择、聚类方法、激活函数、轨迹级 vs 细粒度奖励等完整消融。
  - 算力与训练细节缺失，影响复现和公平性判断。

## 6. 主要结论与发现

- **LIBERO 主结果**：
  - OpenVLA*-One 基线成功率 48.9%。
  - Online SRPO 在仅 200 RL 步内达到 **99.2%** 平均成功率，相对提升 **103%**，取得新的 SOTA。
  - Offline SRPO 也可从 48.9% 提升到 92.5%，说明方法在离线和在线设置下均有效。
- **LIBERO-Plus 鲁棒性**：
  - OpenVLA*-One 总成功率为 19.4%，Online SRPO 提升到 59.6%。
  - 论文报告相对性能提升 **167%**，在七类扰动下均显著优于单样本 SFT 基线。
- **奖励建模有效性**：
  - 潜在世界表示奖励在 SC、Mono、MMD、JS、SMD 五项指标上均优于 Pixel-level 和 ImageBind。
  - 训练曲线显示 SRPO 奖励收敛更稳定、最终性能更高；ImageBind 早期快但停滞，Pixel-level 收敛慢。
- **训练效率**：
  - SRPO 比 GRPO 具有更陡峭的效率斜率，尤其在长时程任务中优势明显。
  - 能利用“接近成功”的失败轨迹，而不是像 GRPO 那样丢弃失败样本。
- **探索能力**：
  - 与 Full-shot SFT 相比，SRPO 策略能探索更广的动作空间和此前不可达区域，轨迹更分散。
- **真实世界迁移**：
  - 在 π0 和 π0-FAST 上，离线 RL 奖励塑形均带来显著提升。
  - 论文报告平均增益分别为 **+66.8%** 和 **+86.7%**，表明进度感知奖励可迁移到真实机器人任务。

## 7. 优点

- **无需外部演示与人工奖励工程**：利用模型自身成功轨迹构建奖励，降低对专家数据和任务特定奖励设计的依赖。
- **缓解奖励稀疏**：将失败轨迹转化为进度信号，更充分利用 rollout 信息，提高样本效率。
- **潜在世界表示设计合理**：使用世界模型潜空间而非像素或通用视觉嵌入，能捕捉跨环境的行为进度模式，泛化性更强。
- **与 GRPO 兼容**：在组相对策略优化框架中自然集成，改动清晰，易于与现有 VLA-RL 流程结合。
- **实验覆盖较广**：涵盖仿真主基准、扰动鲁棒性、奖励质量指标、训练效率、探索行为和真实机器人。
- **结果突出**：200 步达到 99.2% LIBERO 成功率，且仅使用第三人称视觉和语言输入，却优于部分使用额外模态的方法。
- **真实世界验证**：在两种不同 VLA 架构上均有效，增强方法实用价值。

## 8. 不足与局限

- **算力与训练细节缺失**：正文仅指向附录 F，当前材料未提供 GPU 型号、数量、时长等，复现成本不明确。
- **主要实验集中于 LIBERO 仿真**：虽然包含 LIBERO-Plus 和真实世界，但真实世界任务数量有限，且为离线 RL，不是完整在线部署验证。
- **奖励质量依赖世界模型**：潜在表示的进度度量依赖预训练世界模型质量；若世界模型对目标域覆盖不足，奖励可能失真。
- **超参数与聚类细节未充分展开**：DBSCAN 参数、激活函数选择、距离归一化方式等对奖励稳定性可能有影响，正文未给出完整敏感性分析。
- **消融不够全面**：缺少对世界模型类型、轨迹级 vs 细粒度奖励、不同聚类策略、奖励函数形式的系统消融。
- **比较公平性有限**：部分基线使用不同输入模态、预训练数据或训练设置，作者虽声明仅作参考，但横向比较仍需谨慎。
- **潜在偏差风险**：成功轨迹来自当前策略批次，若初期成功率极低，自参考信号可能不足；失败轨迹若远离成功模式，奖励区分度可能有限。
- **应用限制**：方法假设任务成功可被可靠判定，且环境可提供足够 rollout；在长时程、多阶段、成功稀疏的真实任务中，仍可能面临探索与奖励估计挑战。

（完）
