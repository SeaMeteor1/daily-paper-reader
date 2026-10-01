---
title: "CUBic: Coordinated Unified Bimanual Perception and Control Framework"
title_zh: CUBic：协调统一的双手感知与控制框架
authors: "Wang, Xingyu, Ding, Pengxiang, Xu, Jingkai, Wang, Donglin, Fan, Zhaoxin"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Wang_CUBic_Coordinated_Unified_Bimanual_Perception_and_Control_Framework_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 4.0
evidence: 面向双手机器人控制的统一共享表示视觉运动策略
tldr: 视觉运动策略学习已使机器人能直接由视觉输入进行控制，但从单臂扩展到双手操作仍需同时满足独立感知与双臂协调，现有方法往往偏向解耦或强耦合一方。本文提出CUBic，将双手协调重构为统一的感知建模问题，学习连接感知与控制的共享令牌化表示，兼顾独立性与协调性。实验表明该框架在双手操作任务上取得协调统一的表现。该工作为双手操作提供了统一处理框架。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-wang-cubic-coordinated-unified-bimanual-perception-and-control-framework-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 8, \"index\": 1, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-wang-cubic-coordinated-unified-bimanual-perception-and-control-framework-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 8, \"index\": 2, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-wang-cubic-coordinated-unified-bimanual-perception-and-control-framework-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 8, \"index\": 3, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-wang-cubic-coordinated-unified-bimanual-perception-and-control-framework-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 8, \"index\": 4, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-wang-cubic-coordinated-unified-bimanual-perception-and-control-framework-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-wang-cubic-coordinated-unified-bimanual-perception-and-control-framework-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 8, \"index\": 6, \"width\": 640, \"height\": 480}]"
motivation: 从单臂扩展到双手操作需兼顾独立感知与双臂协调，现有方法偏重一方。
method: 将双手协调重构为统一感知建模问题，学习连接感知与控制的共享令牌化表示。
result: 在双手操作任务上实现协调统一的感知与控制。
conclusion: 为双手操作提供了统一处理框架。
---

## Abstract
Recent advances in visuomotor policy learning have enabled robots to perform control directly from visual inputs. Yet, extending such end-to-end learning from single-arm to bimanual manipulation remains challenging due to the need for both independent perception and coordinated interaction between arms. Existing methods typically favor one side--either decoupling the two arms to avoid interference or enforcing strong cross-arm coupling for coordination--thus lacking a unified treatment. We propose CUBic, a Coordinated and Unified framework for Bimanual perception and control that reformulates bimanual coordination as a unified perceptual modeling problem. CUBic learns a shared tokenized representation bridging perception and control, where independence and coordination emerge intrinsically from structure rather than from hand-crafted coupling. Our approach integrates three components: unidirectional perception aggregation, bidirectional perception coordination through two codebooks with shared mapping, and a unified perception-to-control diffusion policy. Extensive experiments on the RoboTwin benchmark show that CUBic consistently surpasses standard baselines, achieving marked improvements in coordination accuracy and task success rates over state-of-the-art visuomotor baselines.

---

## 论文详细总结（自动生成）

# CUBic 论文中文结构化总结

## 1. 核心问题与研究动机

- **背景**：视觉运动策略学习（visuomotor policy learning）已使机器人能够直接从视觉输入进行端到端控制，但绝大多数工作集中于**单臂操作**。
- **核心挑战**：将端到端学习从单臂扩展到**双手协同操作**时，需要同时满足两个相互矛盾的需求：
  - **独立感知**：每条手臂需具备独立感知与行动能力；
  - **协调交互**：双臂间需保持空间与时间一致性。
- **现有方法的缺陷**：
  - 一类方法（如 AnyBimanual）**解耦双臂**，避免相互干扰，但牺牲跨臂一致性；
  - 另一类方法（如 cross-attention 类）**强制耦合**以增强协调，但削弱可解耦性与鲁棒性；
  - 两者目标（独立 vs. 交互）本质冲突，缺乏统一处理。
- **核心问题**：如何将"独立"与"协调"这两个对立目标统一到一个连贯的双手操作框架中？
- **论文主张**：将双手协调**重构为统一的感知建模问题**，让独立性与协调性从共享令牌化表示的结构中**自然涌现**，而非通过人工耦合机制强制施加。

---

## 2. 方法论

### 2.1 核心思想
学习一个连接感知与控制的**共享令牌化表示（shared tokenized representation）**，使双臂协调从模型结构中内在涌现。

### 2.2 三大组件

**(1) 单向感知聚合（Unidirectional Perception Aggregation）**
- **输入分类**：腕部相机与关节状态视为"臂特定信息"（局部感知）；头部/外部相机视为"共享全局上下文"。
- **实现**：ResNet-18 提取各视角 RGB 特征；MLP 将本体感知信号投影到同一特征空间。
- **潜在令牌**：定义两组可学习潜在动作令牌 $a_q^{left}, a_q^{right} \in \mathbb{R}^{N \times d}$。
- **单向注意力掩码**：左臂令牌只关注自身臂特定令牌与共享头视角特征；臂特定令牌仅关注共享特征；右臂对称。该设计**严格隔离双臂信息**，同时将两个潜在动作空间锚定到共同感知基础。

**(2) 双向感知协调（Bidirectional Perception Coordination）**
- **双码本共享映射**：建立两个码本 $Z^{left}, Z^{right} \in \mathbb{R}^{K \times d_z}$，共享统一映射空间。
- **量化过程**：
  - 分别计算潜在令牌到各自码本条目的距离 $d_{left,i} = \|a_q^{left} - a_{z,i}^{left}\|_2^2$，$d_{right,i}$ 同理；
  - 取**联合距离最小**的索引 $i^* = \arg\min_i (d_{left,i} + d_{right,i})$；
  - 使双臂收敛到联合一致的潜在表示。
- **增强表达**：采用**残差向量量化（RVQ）** 层级结构。
- **效果**：在共享码本动态中隐式建立双臂耦合，同时保留功能独立性。

**(3) 统一感知到控制（Unified Perception-to-Control Diffusion Policy）**
- 将量化令牌 $a_z^{left}, a_z^{right}$ 与对应臂特定令牌 $c^{left}, c^{right}$ 拼接，得到条件嵌入 $Q^{left}, Q^{right}$：
  - $Q^{left} = \text{concat}(a_z^{left}, c^{left})$，$Q^{right}$ 同理。
- 采用 **DiT（Diffusion Transformer）** 作为策略网络，通过 **cross-attention** 注入感知条件。
- 扩散过程：$a_H^k = \sqrt{\bar\alpha_k} a_H^0 + \sqrt{1-\bar\alpha_k}\epsilon$，优化目标 $L_{diff} = \mathbb{E}\|D_\theta(a_H^k, k, Q) - \epsilon\|^2$。
- **训练配置**：训练用 100 步扩散，推理用 DDIM 确定性采样降至 10 步。

### 2.3 两阶段训练范式
- **阶段 1：单臂预训练（Single-Arm Pre-training）**
  - 两臂策略分支独立训练，各自拥有 self-attention / cross-attention / FFN；
  - 将动作序列 $a_H$ 按运动维度均分为 $a_H^{left}, a_H^{right}$；
  - 损失 $L_{phase1} = L_{diff}^{left} + L_{VQ} + L_{diff}^{right}$；
  - 向量量化采用直通梯度估计：$a_z = sg[a_z - a_q] + a_q$；
  - 码本目标：$L_{VQ} = \|sg[a_q] - a_z\|_2^2 + \beta\|a_q - sg[a_z]\|_2^2$（含 commitment loss）。
- **阶段 2：双臂协调后训练（Dual-Arm Coordination Post-training）**
  - **冻结全部感知模块**，保留已学的协作感知表示；
  - 将 DiT 中的 self-attention 层**合并为双臂共享**，允许相互可见，在扩散噪声中引入结构化相关性；
  - 各臂的 cross-attention 路径保持分离，维护感知-控制流的完整性；
  - 损失 $L_{phase2} = L_{diff}^{left} + L_{diff}^{right}$。
- **效果**：从"感知协作"渐进过渡到"动作协作"，形成统一且可解释的感知-控制映射。

---

## 3. 实验设计

### 3.1 仿真实验（RoboTwin Benchmark）
- **基准**：RoboTwin（基于 ManiSkill，含更复杂场景），由 3D 生成模型与 LLM 生成专家演示；每任务 100 条演示，跨度 250–850 步。
- **对比方法**：
  - **Diffusion Policy (DP)**：条件去噪扩散的视觉运动策略；
  - **3D Diffusion Policy (DP3)**：稀疏点云 + 轻量 MLP 编码器；
  - **GR-MG**：基于 GR-1 的多模态目标条件生成策略。
- **评测任务（7 个）**：Pick Apple Messy、Dual Bottles Pick (Easy)、Blocks Stack (Easy)、Dual Bottles Pick (Hard)、Block Handover、Dual Shoes Place、Put Apple Cabinet。
- **指标**：3 个随机初始种子下、每次 50 次执行的成功率均值与标准差。

### 3.2 真实世界实验
- **平台**：双臂 Agibot，头部 + 双腕共 3 个 Intel RealSense D435 相机。
- **6 个任务**：Apple to Plate、Bowl to Plate、Dual Banana Grasp、Dual Bottle Grasp、Banana Handover to Plate、Apple to Drawer。
- **数据与评测**：每任务 100 条专家轨迹，50 次评估试验；采用**分步评分制**（各子任务分数累加至 100）。
- **对比**：仅与 Diffusion Policy (DP) 对比；分 In-Domain（训练位置）与 Out-of-Domain（随机位置）。

### 3.3 消融实验
- 共享映射 vs. 独立码本；
- 两阶段训练 vs. 端到端训练；
- 潜在令牌数量（N = 0 / 4 / 8）与码本大小（K = 256 / 512）。

---

## 4. 资源与算力

论文中明确给出：
- **GPU**：4 张 NVIDIA 4090；
- **批大小**：每 GPU 32，总批大小 128；
- **训练轮数**：两阶段各 900 epochs；
- **评测**：使用最新保存的 checkpoint。

> 未明确说明的部分：总训练时长（小时/天）、单次训练的实际耗时、真实世界数据采集与训练的具体算力开销，论文均未给出。

---

## 5. 实验数量与充分性

**实验组数概览**：
- 仿真：7 个任务 × 3 种子 × 50 次执行（每个任务），对比 3 个基线；
- 真实世界：6 个任务 × 50 次试验 × 2 种域设置，对比 1 个基线；
- 消融：3 组（共享映射、两阶段训练、令牌/码本规模），其中令牌/码本规模为 3 种代表配置。

**充分性评估**：
- **优点**：
  - 仿真与真实世界**双重验证**，增强结论可信度；
  - 消融设计覆盖了方法的两大关键组件，逻辑清晰；
  - 报告了标准差，说明进行了多次随机种子评测，具统计意识。
- **不足与偏差风险**：
  - 真实世界实验**仅对比 DP 一个基线**，未与 DP3、GR-MG 等更强方法比较，公平性受限；
  - 真实世界任务规模较小（每任务 100 条轨迹），样本量有限；
  - 未报告失败案例分析或统计显著性检验；
  - 消融中"令牌/码本规模"仅列 3 种代表配置，未做完整网格搜索。

---

## 6. 主要结论与发现

- **仿真结果**：CUBic 平均成功率 **51.8%**，超越 DP3 12.0%、DP 13.3%、GR-MG 43.8%；在长时程协调任务（Pick Apple Messy、Blocks Stack Easy）上优势尤为明显。
- **真实世界结果**：
  - In-Domain 平均分 **43.1**（DP 为 19.5，提升 +23.6）；
  - Out-of-Domain 平均分 **34.7**（DP 为 12.7，提升 +22.0）；
  - 物体位置变化对 CUBic 影响较小，泛化性较强。
- **消融结论**：
  - 移除共享映射，性能从 51.8% 降至 32.6%（-19.2%），说明共享码本映射是协调的关键；
  - 仅用两阶段训练（无共享映射）或仅用共享映射（无两阶段训练），增益分别只有 +7.5% 和 +9.5%，两者**协同**才带来最大增益；
  - 完全移除潜在令牌（N=0）时成功率降至 **0.0%**，说明潜在令牌是感知协调的必要桥梁；
  - N=8、K=512 时性能反而下降（40.2%），说明令牌数与码本规模需**适配**。
- **总体结论**：统一建模对捕获双手任务复杂的时空动态至关重要，统一策略结构优于传统解耦或强耦合方法。

---

## 7. 优点与亮点

- **统一视角**：将"独立 vs. 交互"的对立重构为统一感知建模问题，思路新颖，跳出传统结构权衡的框架。
- **共享令牌化表示**：通过双码本共享映射在隐空间实现隐式协调，协调性"涌现"而非"强加"，设计优雅。
- **两阶段训练范式**：先感知协作、后动作协作，阶段 2 冻结感知模块，既保留预训练感知能力又引入控制层交互，逻辑合理。
- **单向注意力掩码**：巧妙利用视角分类（腕部=局部、头部=全局）实现信息隔离与共享的平衡。
- **多模态评测**：同时覆盖仿真（RoboTwin）与真实世界（Agibot），并包含 In/Out-of-Domain 泛化测试，验证较全面。
- **消融设计具有说服力**：通过移除潜在令牌导致 0% 成功率的极端结果，有力佐证了核心设计必要性。

---

## 8. 不足与局限

- **真实世界基线过少**：仅与 DP 对比，未纳入 DP3、GR-MG 等更强基线，难以充分说明相对 SOTA 的优势。
- **算力与训练成本未充分披露**：未报告总训练时长、真实世界数据采集成本，900 epochs × 两阶段的开销可能较高。
- **任务覆盖有限**：仿真 7 任务、真实 6 任务，且多为抓取-放置类，未涉及更复杂的接触丰富或动态交互任务。
- **超参数敏感性**：消融显示 N=8、K=512 时性能下降，说明方法对令牌数与码本规模较敏感，缺乏系统性的敏感性分析。
- **泛化边界未探明**：真实世界 Out-of-Domain 测试仅涉及位置随机化，未测试新物体、新任务或跨具身泛化。
- **失败案例缺失**：未分析失败模式（如协调失败、感知错误、量化误差），不利于后续改进。
- **统计严谨性**：未报告显著性检验；真实世界仅 50 次试验/任务，统计效力有限。
- **应用限制**：方法依赖固定的三相机配置（头部+双腕），换用不同传感器布局时需重新设计；共享码本的规模随任务复杂度增长可能成为瓶颈。

---

（完）
