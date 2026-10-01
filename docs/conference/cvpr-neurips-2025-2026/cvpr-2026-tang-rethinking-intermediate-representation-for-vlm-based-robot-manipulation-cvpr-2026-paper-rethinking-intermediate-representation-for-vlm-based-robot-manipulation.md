---
title: Rethinking Intermediate Representation for VLM-based Robot Manipulation
title_zh: 重新思考基于VLM的机器人操作的中间表示
authors: "Tang, Weiliang, Gao, Jialin, Pan, Jia-Hui, Wang, Gang, Li, Li Erran, Liu, Yun-Hui, Ding, Mingyu, Heng, Pheng-Ann, Fu, Chi-Wing"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Tang_Rethinking_Intermediate_Representation_for_VLM-based_Robot_Manipulation_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 面向机器人操作的VLM中间表示设计
tldr: 视觉语言模型已成为稳健机器人操作的重要组件，但将人类指令转化为可解析动作的中间表示时，往往难以兼顾VLM可理解性与泛化性。本文受上下文无关文法启发，提出语义装配表示SEAM，将中间表示分解为语义丰富的操作词汇与VLM友好的语法，并结合上下文学习实现开放词汇分割以定位精细部件。实验表明该方法能处理多样未见任务。该工作为VLM驱动的机器人操作提供了更泛化的表示设计。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 1002, \"height\": 718}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 946, \"height\": 830}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 3, \"index\": 3, \"width\": 1108, \"height\": 816}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 3, \"index\": 4, \"width\": 930, \"height\": 694}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 3, \"index\": 5, \"width\": 930, \"height\": 694}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 3, \"index\": 6, \"width\": 908, \"height\": 828}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 3, \"index\": 7, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 4, \"index\": 8, \"width\": 404, \"height\": 316}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 4, \"index\": 9, \"width\": 400, \"height\": 316}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 4, \"index\": 10, \"width\": 404, \"height\": 348}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 4, \"index\": 11, \"width\": 431, \"height\": 345}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 4, \"index\": 12, \"width\": 517, \"height\": 344}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 6, \"index\": 13, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 6, \"index\": 14, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 6, \"index\": 15, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 6, \"index\": 16, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 6, \"index\": 17, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 6, \"index\": 18, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 6, \"index\": 19, \"width\": 531, \"height\": 297}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-020.webp\", \"caption\": \"\", \"page\": 6, \"index\": 20, \"width\": 531, \"height\": 297}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-021.webp\", \"caption\": \"\", \"page\": 6, \"index\": 21, \"width\": 531, \"height\": 297}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-022.webp\", \"caption\": \"\", \"page\": 6, \"index\": 22, \"width\": 531, \"height\": 297}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-023.webp\", \"caption\": \"\", \"page\": 6, \"index\": 23, \"width\": 531, \"height\": 297}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-024.webp\", \"caption\": \"\", \"page\": 6, \"index\": 24, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-025.webp\", \"caption\": \"\", \"page\": 6, \"index\": 25, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-026.webp\", \"caption\": \"\", \"page\": 6, \"index\": 26, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-027.webp\", \"caption\": \"\", \"page\": 6, \"index\": 27, \"width\": 531, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-028.webp\", \"caption\": \"\", \"page\": 7, \"index\": 28, \"width\": 1263, \"height\": 298}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-029.webp\", \"caption\": \"\", \"page\": 7, \"index\": 29, \"width\": 674, \"height\": 562}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-030.webp\", \"caption\": \"\", \"page\": 7, \"index\": 30, \"width\": 1601, \"height\": 562}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-031.webp\", \"caption\": \"\", \"page\": 7, \"index\": 31, \"width\": 667, \"height\": 552}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-032.webp\", \"caption\": \"\", \"page\": 7, \"index\": 32, \"width\": 516, \"height\": 414}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-033.webp\", \"caption\": \"\", \"page\": 8, \"index\": 33, \"width\": 1500, \"height\": 1200}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-tang-rethinking-intermediate-representation-for-vlm-based-robot-manipulation-cvpr-2026-paper/fig-034.webp\", \"caption\": \"\", \"page\": 8, \"index\": 34, \"width\": 1169, \"height\": 680}]"
motivation: 将人类指令转化为可解动作的中间表示需在可理解性与泛化性之间权衡。
method: 借鉴上下文无关文法，将中间表示分解为词汇与语法构建SEAM，并用上下文学习做开放词汇分割定位部件。
result: 以简洁词汇与友好语法处理多样未见任务，实现精细部件定位。
conclusion: 为VLM驱动的机器人操作提供了更泛化的中间表示设计。
---

## Abstract
Vision-Language Model (VLM) is now an important component to enable robust robot manipulation. Yet, using it to translate human instructions into an action-resolvable intermediate representation often needs a tradeoff between VLM-comprehensibility and generalizability. Inspired by context-free grammar structure, we design the Semantic Assembly representation named SEAM, by decomposing the intermediate representation into vocabulary and grammar. Doing so leads us to a concise vocabulary of semantically-rich operations and a VLM-friendly grammar for handling diverse unseen tasks. Also, we design a novel open-vocabulary segmentation paradigm with an in-context learning strategy to precisely localize fine-grained object parts for manipulation (e.g., cup handle, teapot opening) effectively with the shortest inference time over all state-of-the-art parallel works. We then formulate new metrics for action-generalizability and VLM-comprehensibility to evaluate mainstream representations, demonstrating the strong performance of SEAM on both aspects. Extensive real-world experiments further manifest the SOTA performance of SEAM under varying settings and tasks.

---

## 论文详细总结（自动生成）

# 论文分析：Rethinking Intermediate Representation for VLM-based Robot Manipulation

## 1. 核心问题与整体含义

- **研究背景**：VLM 已成为通用机器人操作的重要组件，主流做法是让 VLM 将人类指令翻译为一种"中间表示"（intermediate representation），再由求解器据此解算机器人动作。这样做可避免为 VLA 模型准备海量动作标注数据。
- **核心矛盾（Trade-off）**：中间表示的设计存在两难。
  - **高层表示（High-level）**：使用预定义技能词（如 `grasp_center`、`cut`、`move_perpendicular`），VLM 易理解（高 VLM-comprehensibility），但过于僵化，遇到新任务需人工设计新词汇，泛化能力差（低 action-generalizability）。
  - **低层表示（Low-level）**：使用关键点、轴等基本图元（如 ReKep、OmniManip），动作泛化性强，但需要 VLM 生成极其复杂、脆弱的约束代码，可理解性差。
- **研究问题**：能否设计一种同时满足 **(i) 动作泛化性**与 **(ii) VLM 可理解性** 的中间表示？
- **整体含义**：论文主张从"上下文无关文法（CFG）"视角重新审视中间表示，将表示拆解为**词汇 + 语法**，从而在可读性与可扩展性之间取得平衡。这是首个对 VLM 机器人操作中间表示进行系统化分析并给出量化指标的研究。

## 2. 方法论

### 2.1 核心思想：SEAM（Semantic Assembly Representation）

- 将中间表示形式化为语言结构 $\tilde{R} = (V, G)$，其中 $V$ 为**词汇表**（语义丰富的操作原语），$G$ 为**语法**（规定词汇合法组合的规则）。
- 类比 CFG 四元组 $(V, \Sigma, R, S)$：SEAM 的 $V$ 对应非终结符/终结符/起始符的并集，$G$ 对应产生式规则 $R$，但所有符号都以人类可读、语义明确的方式呈现。
- 关键转变：把"代码生成"变成"语义引导的装配（assembly）过程"。

### 2.2 词汇与语法设计（表 1）

- **词汇 V（核心原语，约 11 个）**：`get_axis`、`get_centroid`、`get_height`、`move_cost`、`parallel_cost`、`perpendicular_cost`、`rotate_cost`、`orbit_cost`、`gripper_close`、`gripper_open` 等。
- **语法 G（带类型约束的组合规则）**：
  - `cost → cost + cost`
  - `get_axis(object) → vec`，`get_centroid(object) → pt`，`get_height(object) → cost`
  - `parallel_cost(vec, vec) → cost`，`move_cost(pt, pt) → cost`
  - `pt → pt ± pt`
- **六项设计原则**：VLM 可读性、适当抽象（隐藏底层实现如 PCA 求轴）、简洁性（词汇正交、最小化语义重叠）、可靠性（类型系统约束生成）、恰当极简主义（减少 VLM 学习负担）、可组合性（模块化可扩展）。
- **示例**：将"用夹持的刀切胡萝卜"翻译为
  ```
  perpendicular_cost(get_axis("carrot"), get_axis("knife blade"))
  + move_cost(get_centroid("knife"), get_centroid("knife blade"), offset=[0,0,0.1])
  ```

### 2.3 RAG 式少样本开放词汇分割

- **动机**：`get_centroid`、`get_axis` 等词汇需要精确定位细粒度物体部件（如茶壶开口、花瓶茎、杯口），现有 OV-Seg、Grounded SAM2、LISA 均难以准确分割部件。
- **数据库构建**：$D = \{(K_i, P_i)\}_{i=1}^{N}$，其中 $K_i$ 为描述部件的关键短语集合（如"cup opening / cup rim / cup edge"），$P_i = \{(I^S_j, M^S_j)\}_{j=1}^{n}$ 为支撑图像-掩码对。
- **检索**：用 **Levenshtein 距离**匹配查询描述 `desc` 与关键短语（对轻微词汇不一致鲁棒）。
- **分割**：采用少样本分割网络 **Mapper**，根据支撑掩码与查询特征的注意力相似度，将支撑掩码映射为查询掩码 $M_Q$。
- **特征提取**：Swin-B transformer。

### 2.4 轨迹生成

- SEAM 表示可直接 Python 执行，执行结果是一个数值化 cost，衡量点云 $P$ 与表示的匹配程度。
- 通过判断部件是否随夹爪移动，将点云分为运动部件 $P_m$ 与静止部件 $P_s$；因夹爪与 $P_m$ 刚性绑定，二者共享同一变换。
- 求解目标姿态 $R \in SO(3)$、$t \in \mathbb{R}^3$ 的最小化问题：
  $$\min_{R,t} \| P_s \cup (R R_0^{-1}(P_m - t_0) + t) \| + \alpha \|t - t_0\|^2 + \beta \| \text{euler}(R R_0^{-1}) \|_1$$
  其中后两项为正则项，分别惩罚过大的平移与旋转，$\alpha, \beta$ 为权重。

## 3. 实验设计

### 3.1 硬件与场景

- **机器人平台**：UR5 工业机械臂 + 夹爪。
- **视觉感知**：两台 Intel RealSense D435 深度相机置于工作空间两侧，双视角图像拼接后输入 Qwen-VL 检测无遮挡的最置信物体。
- **VLM**：Qwen3-VL-30B-22A，部署于 A100 GPU。

### 3.2 Benchmark（8 项真实任务）

- 涵盖刚性物体交互与铰接机构操作：将笔插入笔筒、回收电池、把杯/碗放到盘子、将盖子盖到茶壶、打开/关闭抽屉、按下红色按钮、打开罐子。
- 每任务重复 **10 次试验**，随机化物体配置以避免评估偏差；同时评估闭环与开环两种设置。

### 3.3 对比方法

- **VoxPoser**：LLM/VLM 构建 3D value map 合成轨迹。
- **CoPa**：部件级空间约束。
- **ReKep**：基于关系关键点约束 + 多层优化。
- **OmniManip**：以操作感知图元构建空间约束。
- 定量研究部分另对比 **Instruct2Act**（高层 API 表示）。

### 3.4 新提出的评估指标

- **Action-Generalizability (AG)**：$AG = 1 - |V| / T$，$|V|$ 为覆盖全部任务所需唯一词汇操作数，$T$ 为任务总数；值越高表示用越少词汇覆盖越多任务。
- **VLM-Comprehensibility (VC)**：$VC = N_{succ} / T$，VLM 能正确生成并成功执行的任务比例。
- 用 33 个随机生成的单臂、非触觉、无力反馈任务，由 Qwen3-VL 生成表示，DeepSeek 辅助评估表示能否合理完成任务。

## 4. 资源与算力

- **文中明确提到**：
  - 部署 **Qwen3-VL-30B-22A** 于 **A100 GPU** 作为 VLM。
  - 时间效率对比时，将所有方法部署于 **A6000 GPU**。
- **未明确说明**：
  - 未给出 GPU 数量、训练时长、总计算预算。
  - 该方法是推理型（VLM 直接生成表示 + 检索式少样本分割），基本不涉及大规模训练，但分割 matcher 的训练成本未披露。

## 5. 实验数量与充分性

- **真实机器人实验**：8 个任务 × 10 次试验 × 4 个对比方法（部分方法因故未跑全部任务），规模较大且覆盖刚体与铰接物体。
- **定量表示研究**：33 个随机任务 × 4 种表示方法，评估 AG 与 VC。
- **分割对比**：与 LISA、OV-Seg、Grounded SAM、AffordanceNet、RoboAfford 定性/定量比较；时间对比含 LISA、OV-seg、Grounded SAM。
- **消融分析**：分别分析 SEAM 与 RAG 分割两个关键组件的贡献。
- **充分性评价**：
  - 优点：真实机器人闭环实验 + 新指标量化分析 + 定性可视化，层次较完整；任务随机化降低偏差。
  - 局限：33 任务评估依赖 DeepSeek 自动判定而非真实/仿真执行，存在主观性与偏差风险；每任务仅 10 次试验，统计置信度有限；部分基线（如 ReKep 在部分任务）缺失数据，比较不完全对等。

## 6. 主要结论与发现

- **存在明确 trade-off**：现有 SOTA 表示要么过于高层（高 VC、低 AG，如 Instruct2Act），要么过于低层（低 VC、高 AG，如 ReKep、OmniManip）。
- **SEAM 同时兼顾两者**：在 AG 与 VC 两个指标上均取得最佳平衡。
- **真实任务性能**：SEAM 总成功率 **83.8%（闭环）/ 63.8%（开环）**，较 OmniManip 的 68.8%/52.5% 提升约 **15%**。
- **分割效率最优**：SEAM 推理耗时 **0.6 秒**，优于 LISA（0.9s）、OV-seg（10.2s）、Grounded SAM（0.88s）。
- **部件级定位优势**：在"盖茶壶盖"任务中能准确定位壶口边缘，而其他方法只能定位茶壶中心或内部点，导致对不准或压碎。
- **失败原因**：主要来自 VLM 自身空间理解不足（如方向错误）与感知不足（遮挡、关键部件未清晰捕获导致点云缺陷）。

## 7. 优点

- **理论视角新颖**：首次将 CFG 思想系统引入 VLM 机器人操作的中间表示设计，词汇/语法解耦的思路清晰且具启发意义。
- **平衡性设计出色**：通过语义丰富的最小词汇 + 类型约束语法，同时实现 VLM 友好与强泛化，避免了手工设计新技能的负担。
- **评估体系贡献**：提出 AG 与 VC 两个可量化指标，填补了中间表示缺乏客观评价标准的空白。
- **工程完整性**：从表示设计 → 开放词汇细粒度分割 → 轨迹优化 → 真实机器人验证，形成闭环 pipeline。
- **效率优势显著**：分割推理速度优于所有对比 SOTA。
- **诚实报告局限**：结论部分明确列出失败模式，学术态度严谨。

## 8. 不足与局限

- **空间推理依赖 VLM 固有能力**：方向判断错误等仍会导致失败，方法本身未提供空间推理的强约束机制。
- **感知鲁棒性受限**：遮挡或关键部件未被相机清晰捕获时，点云缺陷会传导至后续求解，双相机方案仅部分缓解。
- **定量评估的客观性风险**：33 任务的 VC/AG 评估依赖 DeepSeek 自动判定，而非真实或仿真环境执行，可能引入模型偏好偏差。
- **任务覆盖有限**：仅单臂、非触觉、无力反馈场景；未涉及双臂、接触丰富、可变形物体或长时序任务。
- **资源信息不透明**：未披露训练成本、GPU 数量、分割模块训练细节，复现门槛不明确。
- **基线对齐不完全**：部分基线在部分任务上缺测（如 ReKep 在多个任务显示"-"），跨方法比较的公平性有待进一步保证。
- **样本量**：每任务 10 次试验，统计显著性有限，缺少误差棒或置信区间报告。

（完）
