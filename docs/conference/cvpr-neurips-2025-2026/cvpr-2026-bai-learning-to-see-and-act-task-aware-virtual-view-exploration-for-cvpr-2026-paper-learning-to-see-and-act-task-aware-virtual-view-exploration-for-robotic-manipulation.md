---
title: "Learning to See and Act: Task-Aware Virtual View Exploration for Robotic Manipulation"
title_zh: 学会看与行动：面向机器人操作的任务感知虚拟视角探索
authors: "Bai, Yongjie, Wang, Zhouxia, Liu, Yang, Luo, Kaijun, Wen, Yifan, Dai, Mingtong, Chen, Weixing, Chen, Ziliang, Liu, Lingbo, Li, Guanbin, Lin, Liang"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Bai_Learning_to_See_and_Act_Task-Aware_Virtual_View_Exploration_for_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 6.0
evidence: 面向VLA机器人操作的虚拟视角探索
tldr: 现有VLA多任务操作模型依赖固定相机与共享视觉编码器，在遮挡和跨任务迁移时表现受限。本文提出任务感知虚拟视角探索TVVE，学习选择任务相关的虚拟相机视角，并基于重建场景表示动态重渲染观测，同时在伪环境中训练视角探索策略。此外引入任务感知混合专家视觉编码器，将视觉特征路由到任务专属专家以缓解任务干扰。该方法提升了遮挡场景与跨任务迁移下的操作性能。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-bai-learning-to-see-and-act-task-aware-virtual-view-exploration-for-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 790, \"height\": 734}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-bai-learning-to-see-and-act-task-aware-virtual-view-exploration-for-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 3, \"index\": 2, \"width\": 458, \"height\": 426}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-bai-learning-to-see-and-act-task-aware-virtual-view-exploration-for-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 3, \"index\": 3, \"width\": 520, \"height\": 467}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-bai-learning-to-see-and-act-task-aware-virtual-view-exploration-for-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 4, \"index\": 4, \"width\": 2171, \"height\": 995}]"
motivation: VLA多任务操作模型依赖固定相机与共享视觉编码器，在遮挡和跨任务迁移时性能受限。
method: 提出TVVE框架，学习选取任务相关虚拟视角并从重建场景重渲染观测，配合任务感知混合专家视觉编码器路由特征。
result: 在遮挡与跨任务迁移场景中提升了VLA操作性能，缓解了任务间特征干扰。
conclusion: 任务感知的主动视角选择与专家编码为VLA多任务操作提供改进方案。
---

## Abstract
Recent vision-language-action (VLA) models for multi-task robot manipulation often rely on fixed camera setups and shared visual encoders, which limit their performance under occlusions and during cross-task transfer. To address these challenges, we propose Task-aware Virtual View Exploration (TVVE), a framework that learns to select task-relevant virtual camera viewpoints and dynamically re-render observations from a reconstructed scene representation using the selected viewpoints. To enable efficient view selection, we train an exploration policy in a pseudo-environment. In addition, we introduce a Task-aware Mixture-of-Experts (TaskMoE) visual encoder that routes visual features to task-specialized experts, mitigating interference in multi-task learning. To evaluate robustness under distribution shifts, we construct RLBench-OG, an out-of-distribution benchmark with visual perturbations and camera pose variations. Experiments on RLBench and RLBench-OG demonstrate that TVVE achieves higher success rates than strong baselines, while real-robot experiments further confirm its robustness to visual disturbances and unseen instructions. Code and visualizations are available at: https://hcplab-sysu.github.io/TAVP.

---

## 论文详细总结（自动生成）

# 论文总结：Learning to See and Act: Task-Aware Virtual View Exploration for Robotic Manipulation

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：视觉-语言-动作（VLA）模型（如 OpenVLA、π0、RVT-2、ARP）已成为多任务机器人操作的主流范式，通常以语言指令 + RGB-D 观测直接映射到低层动作。
- **核心问题一：固定视角导致的观测不完整**。现有方法多依赖单一视角或少数固定相机位（前视、左右肩视、腕部），在杂乱或动态场景中，目标物体或末端执行器（EEF）常被遮挡。例如论文图 1 中指令"Put the sugar in the cupboard"，前视只见柜子、肩视只见糖，任何单一视角都无法同时覆盖目标与末端执行器，导致动作预测失败。
- **核心问题二：共享编码器带来的任务干扰**。RVT、RVT-2 等语言条件 Transformer 方法用共享视觉编码器处理所有任务，面对视觉与语义差异大的任务（如"抓苹果"vs"开抽屉"）时出现特征冲突，限制多任务泛化与扩展性。
- **整体含义**：论文主张机器人应具备"主动看"的能力——动态探索任务相关视角，并让视觉特征按任务进行专家化路由，从而让"看"服务于"做"（Learning to See and Act）。

## 2. 方法论：核心思想与关键技术

### 2.1 整体框架（TVVE）

- 输入：语言指令 + 多路 RGB-D 观测 + 夹爪状态。
- 流程：
  1. 将 RGB-D 转为点云，聚合为世界坐标系下的**全局点云**；
  2. 分两路：**橙色分支**做 Coarse Grounding 预测末端执行器大致位置，将点云中心移至该位置并裁剪缩放；**绿色分支**将全局点云输入 MVEP 预测最优相机参数；
  3. 用预测参数从处理后的点云中**重渲染 2D 图像**；
  4. 渲染图像输入 Fine Grounding，预测最终动作（末端位置、旋转、夹爪状态、碰撞状态）。
- 关键：特征提取与动作生成均嵌入 TaskMoE，以获取任务专属表示。

### 2.2 Task-aware Mixture-of-Experts（TaskMoE）

两个核心设计：
- **跨模态路由线索**：不只用任务 ID，而是用跨注意力机制建模指令与视觉的交互，得到上下文感知特征，再通过 FiLM 层与任务 ID 融合，实现更自适应的专家选择。
- **解耦门控策略**：设置 $N_G$ 个门控对应 $N_J$ 个任务（$N_G < N_J$），允许语义/视觉相似任务（如两个"开抽屉"任务）共享门控但激活不同专家，语义不同任务分配不同门控。这鼓励发现潜在任务簇，并提升对未见任务的泛化。所有任务共享 $N_E$ 个专家池，每次仅激活 top-k 个专家。

### 2.3 Multi-Viewpoint Exploration Policy（MVEP）

- **输入**：点云 $P \in \mathbb{R}^{N\times 3}$ 与 RGB 特征 $F_{img}\in\mathbb{R}^{N\times 3}$ 拼接为 $X=\text{Concat}(P,F_{img})\in\mathbb{R}^{N\times 6}$。
- **输出**：K 个相机位姿，每个用 look-at 模型以 5 维球坐标表示 $p_i=(\theta_i,\phi_i,r_i,\theta_i^{up},\phi_i^{up})\in\mathbb{R}^5$，相机始终朝向原点。
- **可微采样**：MVEP 输出每个位姿的均值与对数标准差 $[\mu_i,\log\sigma_i]$，用重参数化技巧采样 $\tilde{p}_i=\mu_i+\sigma_i\odot\epsilon_i$，$\epsilon_i\sim\mathcal{N}(0,I)$，实现端到端训练。
- **约束**：用 sigmoid 将各分量映射到合法球坐标范围（$\theta\in[0,\pi]$、$\phi\in[0,2\pi]$、$r\in[r_{min},r_{max}]$）。

### 2.4 三阶段训练策略

- **Stage 1**：训练固定视角 TVVE（前/左/顶三视角），损失 $L_{s1}=L_{hc}+L_{hf}+L_{rot}+L_{gri}+L_{col}$，即粗/细 grounding 热图交叉熵、旋转、夹爪、碰撞损失。
- **Stage 2**：冻结其他组件，仅用 PPO 优化 MVEP。引入**伪环境交互机制**：以固定视角 TVVE 为参考模型，其损失 $L_{ref}=[L_{hf},L_{rot},L_{gri},L_{col}]$ 作为性能下界，MVEP 的损失 $L_{TVVE}=[L'_{hf},L'_{rot},L'_{gri},L'_{col}]$。三项奖励：
  - $r_0=L_{ref}-L_{TVVE}$（任务损失奖励）
  - $r_1=-\frac{1}{K}\sum_{i=1}^{K}H(\text{softmax}(H_i))$（细 grounding 热图负熵，即置信度奖励）
  - $r_2=\frac{1}{K(K-1)}\sum_{i\neq j}(1-\cos(p_i,p_j))$（视角多样性奖励）
  - 总奖励 $r=\sum_{i=0}^{2}w_i\cdot\mathcal{N}(r_i)$，权重可学习，用 Welford 算法在线归一化并裁剪到 $[-10,10]$。
- **Stage 3**：用 Stage 1 相同损失微调除 MVEP 外的整个 TVVE，使 MVEP 更好适配动作生成。

## 3. 实验设计

### 3.1 数据集与场景

- **RLBench**：CoppeliaSim 仿真，7-DoF Franka Panda，128×128 RGB-D，4 个固定视角（前、左肩、右肩、腕部）。两种配置：
  - 多视角：18 个操作任务（每任务 2–60 个变体）；
  - 单视角：10 个任务，仅前视相机。
- **RLBench-OG（论文新建 OOD benchmark）**：包含两个套件：
  - **Occlusion Suite**：两种配置——(1) 训练与测试均在遮挡下；(2) 原始设定训练、遮挡下零样本测试；
  - **Generalization Suite**：改变光照、桌面颜色/纹理、背景颜色/纹理、加入干扰物、调整观测相机位姿等扰动。
- **真实世界**：Franka Research 3（单台 ORBBEC Femto Bolt 前置相机）与 Dobot Nova 2（3 台 Intel RealSense：D435i 侧上方、D455 前侧、D405 腕部）。5 个任务：Pick Grape、Stack Bowls、Push Buttons、Collect Fruits、Put Item In Drawer，每任务 50 条专家示范。

### 3.2 对比方法

- Diffusion Policy、C2F-ARM-BC、PerAct、HiveFormer、PolarNet、RVT、RVT-2、Act3D、3D Diffuser Actor、GNFactor、ARP 等 10+ 种 SOTA。

### 3.3 实现设置

- 视角数 $K=3$，TaskMoE 门控数 $N_G=8$，专家数 $N_E=16$，每任务选 top-2 专家。

## 4. 资源与算力

- **明确提到**：训练使用 **4 张 NVIDIA RTX A800 GPU**；测试时在**单张 RTX A800** 上顺序评估任务。
- **未明确说明**：训练时长、总 GPU 小时数、各阶段具体训练步数/epoch、推理延迟具体数值等均未在正文给出（仅提及多视角重渲染会略微增加推理延迟）。
- 训练数据规模：仿真每任务 50 episodes，真实世界每任务 50 条示范（仅保留关键帧）。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 表 1：RLBench 多视角 18 任务，对比 9 种方法；
  - 表 2：RLBench 单视角 10 任务，对比 4 种方法；
  - 表 3：RLBench-OG 上 2 种遮挡 + 6 类泛化扰动（光照、桌面颜色/纹理、背景纹理、干扰物、相机位姿），对比 3 种方法；
  - 表 4：真实世界 2 个机器人平台 × 5 任务；
  - 表 5：消融（w/o TaskMoE、固定视角、随机视角）；
  - 表 6：TaskMoE 在已见/未见任务（Open Drawer）上的泛化；
  - 表 7：超参数 K（2/3/4）与径向约束 r（0.75~1.3 / 0.60~1.56 / 0.90~1.04）的消融。
- **充分性评价**：
  - **较为充分**：覆盖仿真多视角/单视角、OOD 基准、真实双平台、多组消融，且报告了 3 次独立运行的均值±标准差（仿真）与 10 次试验（真实世界），统计上较规范。
  - **公平性**：与 RVT-2、ARP 等最强基线在同一 RLBench 协议下比较，平均排名指标（Avg. Rank）也给出，比较客观。
  - **潜在不足**：部分任务上 TVVE 并非最优（如 Put in Safe 78.0% vs RVT-2 96.0%、Stack Blocks 64.0% vs RVT-2 69.0%、Background Texture 60.2% vs RVT-2 63.4%），说明方法并非在所有维度都占优，但论文以平均值和排名论证整体优势。

## 6. 主要结论与发现

- **RLBench 多视角**：TVVE 平均成功率 **86.6%**，比此前 SOTA ARP（81.6%）高约 5%，平均排名 **2.17**（最优）；Insert Peg 从 65.6%→98.0%，Sort Shape 从 36.0%→62.0%。
- **RLBench 单视角**：TVVE 平均 **83.2%**，排名 2.15（最优）。
- **RLBench-OG**：TVVE 平均 **67.0%±6.2**，排名 **1.1**（最优），优于 ARP（63.7%）和 Diffusion Policy（23.8%）；在背景纹理偏移（74.3% vs 68.1%）和相机位姿变化（73.2% vs 69.7%）下表现更稳健。
- **真实世界**：Dobot 上 TVVE 平均 **88.0%** vs Diffusion Policy 68.0%（Push Buttons +30%、Stack Bowls +20%）；Franka 上 TVVE **78.0%** vs Diffusion Policy 58.0%、ARP 72.0%。
- **消融结论**：
  - 去掉 TaskMoE：86.6%→85.6%；在未见任务 Open Drawer 上，有 TaskMoE 72.0% vs 无 60.0%；
  - 固定视角：83.3%；随机视角：仅 8.9%，证明 MVEP 学到的视角具有实质信息价值；
  - 视角数 K 从 2→3→4 成功率 27.2%→49.6%→55.2%，权衡算力选 K=3；
  - 径向约束收紧至 (0.90~1.04)m 提升至 56.0%，过松（0.60~1.56）略降至 48.8%。
- **总体结论**：动态视角规划 + 任务感知表示学习能显著提升机器人操作的准确性与鲁棒性；动态"看"是稳健"做"的基础。

## 7. 优点（方法/实验亮点）

- **方法层面**：
  - 将"主动视角探索"引入 VLA 操作，用**可微高斯采样 + PPO**实现端到端视角优化，思路新颖；
  - **伪环境交互机制**避免与真实环境反复交互的高昂成本，用参考模型的损失差作为奖励，设计巧妙；
  - **奖励设计多维**：任务损失、热图置信度、视角多样性三者互补，且权重可学习、在线归一化、裁剪保证稳定；
  - **TaskMoE 解耦门控**（$N_G < N_J$）允许相似任务共享门控、不同任务隔离路由，兼顾参数共享与任务专精，且支持对未见任务的迁移；
  - 用 FiLM + 跨注意力融合指令与视觉线索进行路由，而非仅依赖任务 ID，更贴合多任务实际操作。
- **实验层面**：
  - 构建 **RLBench-OG** 新 OOD 基准，覆盖遮挡与多类视觉扰动，填补现有基准在鲁棒性评估上的空白；
  - 仿真（多/单视角）+ OOD + 真实双机器人平台的完整验证链；
  - 消融覆盖组件（TaskMoE、MVEP）、视角数、径向约束等关键超参数；
  - 报告均值±标准差与平均排名，统计规范，对比方法广泛（10+ 种 SOTA）。

## 8. 不足与局限

- **作者自述局限**：
  - 多视角重渲染**略微增加推理延迟**，影响实时性；
  - 依赖**精确的全局点云**，对**反光或透明物体**难以处理；
  - 未来需融合多传感器数据与域适应以提升真实世界鲁棒性。
- **实验覆盖与偏差风险**：
  - 真实世界实验仅 5 个任务、每任务 10 次试验，样本量偏小，统计置信度有限；
  - Franka 与 Dobot 采用不同实验配置（相机数量与布置不同），跨平台结果可比性受限（表 4 已标注 *）；
  - 部分任务上 TVVE 明显低于 RVT-2（Put in Safe、Stack Blocks、Background Texture 扰动），说明方法在某些任务/扰动类型上并非普适最优，论文对失败案例的分析较少；
  - RLBench-OG 为论文自建，其扰动设计可能与真实分布偏移存在差距，存在"自设基准自证优势"的偏差风险。
- **应用限制**：
  - 三阶段训练流程较复杂，Stage 2 的

PPO 微调依赖参考模型损失作为奖励，需冻结其他模块并额外维护伪环境交互，工程实现与调参成本较高；奖励权重虽可学习，但归一化、裁剪范围与参考模型选择仍引入额外超参数。  
  - TaskMoE 的门控数 $N_G$、专家数 $N_E$、top-k 选择等需针对任务集合调整，任务数量增长时路由结构与负载均衡可能变得更复杂。  
  - 全局点云依赖多视角标定与融合，真实部署中相机外参误差、点云配准误差会传播至视角探索与动作预测，影响稳定性。  
  - 论文未明确说明代码、模型权重与 RLBench-OG 基准是否开源，复现与公平比较成本较高。  
  - 对透明、反光物体的失败限制了在厨房、玻璃器皿整理等场景的应用；作者也承认需融合多传感器与域适应来提升真实世界鲁棒性。

## 9. 总体评价与启发

- **核心贡献**：将“主动视角探索”从主动感知/导航领域系统性地引入多任务机器人操作，并与任务感知的 MoE 表示学习结合，形成“先看哪里、再看什么、最后怎么做”的闭环，切中了固定视角与共享编码器两大痛点。
- **方法启发性**：可微高斯视角采样 + PPO 伪环境交互，为难以在真实环境大量试错的操作策略提供了一种可训练的视角规划方案；用参考模型损失差构造奖励，避免真实交互成本，具有迁移到其他感知-控制任务的潜力。
- **实验价值**：仿真多/单视角、RLBench-OG 遮挡与泛化套件、真实双平台验证链较完整；平均排名与均值±标准差报告提升了统计可信度。
- **局限与风险**：部分任务和扰动下并未超过 RVT-2 等最强基线，说明动态视角并非普适解；RLBench-OG 为自建基准，存在“自设基准自证优势”的偏差风险；真实实验样本量偏小，跨平台配置不一致也削弱了结论外推能力。
- **未来方向**：可探索更高效的可微渲染或 3D 高斯泼溅表示以降低重渲染延迟；将视角规划与扩散/流匹配动作策略结合；引入透明物体感知、在线标定与域适应，并在更多真实任务与机器人平台上验证。

（完）
