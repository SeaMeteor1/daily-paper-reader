---
title: "TeamHOI: Learning a Unified Policy for Cooperative Human-Object Interactions with Any Team Size"
title_zh: TeamHOI：学习任意团队规模下协作人-物交互的统一策略
authors: "Lionar, Stefan, Lee, Gim Hee"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Lionar_TeamHOI_Learning_a_Unified_Policy_for_Cooperative_Human-Object_Interactions_with_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 4.0
evidence: 面向可变团队规模的单一统一去中心化策略
tldr: 物理仿真的人形控制已能实现高质量单智能体行为，但扩展到协作式人-物交互仍面临团队规模变化与数据稀缺的挑战。本文提出TeamHOI框架，用单一去中心化策略处理任意数量智能体的协作，每个智能体基于局部观测并通过带队友令牌的Transformer策略网络关注同伴，同时引入掩码对抗运动先验保证运动真实感。实验表明其能在可变团队规模下实现可扩展协作。该工作为多智能体统一策略学习提供了可扩展方案。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 1, \"index\": 7, \"width\": 1024, \"height\": 1024}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 1, \"index\": 8, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 1, \"index\": 9, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 1, \"index\": 10, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 1, \"index\": 11, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 4, \"index\": 12, \"width\": 960, \"height\": 320}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 7, \"index\": 13, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 7, \"index\": 14, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 7, \"index\": 15, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 7, \"index\": 16, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 7, \"index\": 17, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 7, \"index\": 18, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 7, \"index\": 19, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-020.webp\", \"caption\": \"\", \"page\": 7, \"index\": 20, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-021.webp\", \"caption\": \"\", \"page\": 8, \"index\": 21, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-022.webp\", \"caption\": \"\", \"page\": 8, \"index\": 22, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-023.webp\", \"caption\": \"\", \"page\": 8, \"index\": 23, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-024.webp\", \"caption\": \"\", \"page\": 8, \"index\": 24, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-025.webp\", \"caption\": \"\", \"page\": 8, \"index\": 25, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-026.webp\", \"caption\": \"\", \"page\": 8, \"index\": 26, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-027.webp\", \"caption\": \"\", \"page\": 8, \"index\": 27, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-028.webp\", \"caption\": \"\", \"page\": 8, \"index\": 28, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-029.webp\", \"caption\": \"\", \"page\": 8, \"index\": 29, \"width\": 360, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lionar-teamhoi-learning-a-unified-policy-for-cooperative-human-object-interactions-with-cvpr-2026-paper/fig-030.webp\", \"caption\": \"\", \"page\": 8, \"index\": 30, \"width\": 360, \"height\": 360}]"
motivation: 将物理仿真人形控制扩展到协作人-物交互仍具挑战，面临团队规模变化与数据稀缺。
method: 提出单一去中心化策略，通过带队友令牌的Transformer策略网络与掩码对抗运动先验支持任意团队规模协作。
result: 实现可变团队规模下可扩展且逼真的协作人-物交互。
conclusion: 为多智能体统一策略学习提供了可扩展方案。
---

## Abstract
Physics-based humanoid control has achieved remarkable progress in enabling realistic and high-performing single-agent behaviors, yet extending these capabilities to cooperative human-object interaction (HOI) remains challenging. We present TeamHOI, a framework that enables a single decentralized policy to handle cooperative HOIs across any number of cooperating agents. Each agent operates using local observations while attending to other teammates through a Transformer-based policy network with teammate tokens, allowing scalable coordination across variable team sizes. To enforce motion realism while addressing the scarcity of cooperative HOI data, we further introduce a masked Adversarial Motion Prior (AMP) strategy that uses single-human reference motions while masking object-interacting body parts during training. The masked regions are then guided through task rewards to produce diverse and physically plausible cooperative behaviors. We evaluate TeamHOI on a challenging cooperative carrying task involving two to eight humanoid agents and varied object geometries. Finally, to promote stable carrying, we design a team-size- and shape-agnostic formation reward. TeamHOI achieves high success rates and demonstrates coherent cooperation across diverse configurations with a single policy.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：基于物理仿真的人形控制已在单智能体场景中取得显著进展，能实现行走、抓取、操作物体等逼真行为；但将这类能力扩展到**协作式人-物交互（Cooperative HOI）**仍很困难。
- **核心问题**：
  - 现有多数方法使用固定输入维度的 MLP 策略，导致策略只能适配**固定团队规模**，无法泛化到任意数量的合作智能体。
  - 部分方法省略显式智能体间通信，仅靠共享物体动力学间接协调，难以模拟真实人类协作中持续感知队友并调整配合的行为。
  - 运动先验（AMP）通常依赖参考动作数据，而**多人类协作 HOI 参考数据稀缺**，只能使用单人类参考动作，限制了可涌现的协作行为多样性。
- **整体含义**：论文提出 **TeamHOI**，目标是训练一个**单一、去中心化、共享参数**的策略，使其在任意团队规模、不同物体几何形状下都能完成协作 HOI。该工作为可扩展的物理仿真多智能体控制、虚拟人多角色动画和机器人协作提供了统一策略学习方案。

## 2. 方法论

### 2.1 核心思想
- 每个智能体独立基于**局部观测**行动，但共享同一个策略网络参数。
- 通过 **Transformer 策略网络 + 队友令牌（teammate tokens）** 实现对其他智能体状态的关注，从而支持可变团队规模。
- 训练时并行实例化不同团队规模的环境，让同一策略接触多种协作配置，无需重新训练或微调即可适配不同团队规模。

### 2.2 策略网络与训练
- 观测 \(o_t=(s_t,g_t)\)，包含自身本体状态、目标状态、物体中心、候选接触点、手-物最近点、目标物体位置以及队友线索。
- 观测被分别编码为 token：可学习嵌入 \(e\)、本体 token、目标 token、物体 token，以及数量可变的队友 token。
- Transformer 由多层**交替的自注意力与交叉注意力**组成：
  - 自注意力处理观察者自身 token；
  - 交叉注意力让观察者 token 关注队友 token，且对较大团队规模仍较高效。
- 更新后的嵌入 \(e\) 经动作头输出目标关节旋转，由 PD 控制器执行。
- 使用 **PPO** 优化策略；不同团队规模环境并行训练，并**按团队规模分别归一化 PPO 优势**，以稳定混合团队配置下的训练。

### 2.3 Masked AMP
- 传统 AMP 使用判别器区分策略生成的状态转移与参考动作，提供风格奖励，但单人类参考动作会限制协作行为多样性。
- 论文引入**掩码 AMP**：
  - 训练两个判别器：\(D_{\text{full}}\) 评估全身参考动作；\(D_{\text{mask}}\) 排除与物体直接交互的身体部位（如手、前臂）。
  - 当智能体与物体交互时，使用掩码判别器的风格奖励；非交互时使用全身判别器的风格奖励。
  - 混合风格奖励为：
    \[
    r_t^{\text{style}}=\sigma(\alpha_t)r_t^{\text{mask}}+(1-\sigma(\alpha_t))r_t^{\text{full}}
    \]
    其中 \(\alpha_t\) 是连续交互指标（如智能体-物体距离），\(\sigma\) 为 sigmoid。
- 掩码区域不再被参考动作强约束，而是通过**任务奖励**引导学习多样且物理合理的物体交互行为。

### 2.4 协作搬运任务与队形奖励
- 测试任务：2–8 个人形智能体协作搬运不同形状（方形、矩形、圆形）的桌子，包括接近、接触、抬起、运输和放下等阶段。
- 与 CooHOI 不同，论文不提供 oracle 的每智能体手部目标位置，智能体需自行推断合适接触点并形成稳定队形。
- **角度分布奖励 \(r_{\text{ang}}\)**：鼓励智能体围绕桌子均匀分布，理想角间距为 \(2\pi/m\)。
- **主轴覆盖奖励 \(r_{\text{cov}}\)**：将智能体根位置投影到物体边缘，构建支撑多边形，测量其沿物体主轴对中心的支持覆盖程度，鼓励沿物体自然旋转稳定轴形成支撑。
- 最终队形奖励：
  \[
  r_{\text{form}}=0.25r_{\text{ang}}+0.75r_{\text{cov}}
  \]
- 整体任务奖励还包括走向物体、接触、抬起、运输、放下等组件。

## 3. 实验设计

- **数据集与参考动作**：
  - 使用 **AMASS** 数据集。
  - 采用 ACCAD 子集的 9 个行走动作及其时间反转版本用于后退行走；CMU 子集的 3 个侧向行走动作；ACCAD 的 3 个拾取动作，截断后反转生成抬起动作。
- **仿真场景**：
  - MuJoCo 人形模型，简化球状手、无手指。
  - 设计三种 URDF 桌子：方形 \(1.60m\times1.60m\)、矩形 \(2.00m\times1.20m\)、圆形直径 \(2.00m\)，质量 50–70 kg。
  - 智能体随机初始化在半径 8 m 圆上，目标位置距桌子中心 3–10 m，每回合 600 个仿真时间步。
- **Benchmark 与对比方法**：
  - 主任务为协作搬运，评估团队规模 2、4、8。
  - 对比 **CooHOI\***：作者大幅改编的 CooHOI 框架，加入 masked AMP 和专门奖励，并训练 CooHOI*-2、CooHOI*-4、CooHOI*-8 三个固定团队规模变体。
  - CooHOI* 使用手动选择、沿主轴最大覆盖的固定接触点，不强制队形奖励；TeamHOI 则需自主学习协作队形。
- **评价指标**：
  - 成功率 SR；
  - 最终桌子中心到目标的距离 \(d\)；
  - 协作时间比例 \(t_{\text{coop}}\)：所有智能体保持接触的时间占比；
  - 平均绝对 jerk \(|J|\)：运输平滑度，越低越好。
- **额外设置**：重载设置（桌子重量 ×5），并在补充材料中报告对未见设置的鲁棒性和 16 智能体零样本泛化。

## 4. 资源与算力

- 论文正文**未明确说明**使用的 GPU 型号、数量、训练时长、总计算量或具体训练资源。
- 只提供了训练相关细节，如并行实例化不同团队规模环境、PPO 优化、按团队规模归一化优势、每项评估平均 10,000 个仿真回合。
- 因此无法从给定文本判断其算力规模与训练成本。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 主对比：2、4、8 智能体三种团队规模，对比 CooHOI*-2/4/8 与 TeamHOI；
  - 重载实验：5× 桌子重量下评估 4、8 智能体；
  - 消融实验：masked AMP 消融、formation reward 消融；
  - 补充材料：鲁棒性、16 智能体零样本泛化等。
- **充分性**：
  - 在单一协作搬运任务上，实验覆盖了不同团队规模、不同桌形、重载和关键组件消融，主结果平均 10,000 回合，统计量较充分。
  - 但任务类型较单一，主要集中在搬桌子；对更多协作 HOI 任务、复杂地形、非规则物体、真实机器人部署等覆盖有限。
- **公平性**：
  - CooHOI* 经过作者大幅改编，且使用 oracle 固定接触点、无需学习队形，而 TeamHOI 需自主学习队形。这种设置对 CooHOI* 在接触点分配上更有利，但 CooHOI* 缺少统一策略和可变团队规模能力。
  - 由于 baseline 是重实现版本，不能完全等同于原始 CooHOI 的官方性能，比较存在一定偏差风险。
  - 个别指标上 TeamHOI 并非全面最优，例如 2 智能体时 jerk 为 51.0，略高于 CooHOI*-2 的 48.3，但整体成功率和协作质量明显更优。

## 6. 主要结论与发现

- TeamHOI 能用**单一统一策略**在 2–8 个智能体、不同桌形下实现高成功率协作搬运。
- 主结果中，TeamHOI 在 2A/4A/8A 下成功率分别为 99.1%、99.2%、97.5%，协作时间比例高，运输较平滑。
- CooHOI* 基线严重依赖训练时的团队规模：CooHOI*-2 仅适合 2 智能体，CooHOI*-4 扩展到 8 智能体时性能急剧下降，CooHOI*-8 自身设置下也协调困难。
- 重载 5× 设置下，只有 TeamHOI 在 8 智能体时表现出有效协作，成功率约 81.1%，说明统一策略具备较强的可扩展协作能力。
- 消融表明：
  - masked AMP 显著提升抬起阶段成功率和任务奖励，允许手-物交互通过任务奖励学习，而非被单人类全身参考动作过度约束；
  - 主轴覆盖奖励促使智能体沿物体主轴形成稳定支撑，产生更自然的对称步态，避免过度旋转和斜向不自然步态。
- 定性结果显示，TeamHOI 能形成全局一致的抬升、稳定和运输行为，而基线常出现竞争、失去接触或冲突力。

## 7. 优点

- **统一且可扩展**：单一去中心化策略支持任意团队规模，无需为每个团队规模单独训练。
- **通信机制合理**：Transformer 队友令牌显式建模智能体间关系，比仅依赖共享物体动力学的隐式通信更符合真实协作。
- **数据稀缺下的创新**：Masked AMP 利用单人类参考动作，通过掩码交互部位并借助任务奖励扩展协作行为多样性。
- **队形奖励设计通用**：角度分布 + 主轴覆盖奖励对团队规模和物体形状不敏感，能引导稳定搬运队形。
- **实验指标全面**：同时评估成功率、目标距离、协作时间比例和运动平滑度，较全面反映协作质量。
- **零样本泛化
