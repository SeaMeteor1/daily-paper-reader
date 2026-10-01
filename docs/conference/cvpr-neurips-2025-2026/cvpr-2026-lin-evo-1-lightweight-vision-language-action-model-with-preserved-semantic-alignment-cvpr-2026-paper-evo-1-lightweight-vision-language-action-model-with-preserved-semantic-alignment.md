---
title: "Evo-1: Lightweight Vision-Language-Action Model with Preserved Semantic Alignment"
title_zh: Evo-1：保持语义对齐的轻量级视觉-语言-动作模型
authors: "Lin, Tao, Zhong, Yilei, Du, Yuxin, Zhang, Jingjing, Liu, Jiting, Chen, Yinxinyu, Gu, Encheng, Liu, Ziyan, Cai, Hongyi, Zou, Yanwen, Zou, Lixing, Zhou, Zhaoye, Li, Gen, Zhao, Bo"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Lin_Evo-1_Lightweight_Vision-Language-Action_Model_with_Preserved_Semantic_Alignment_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 提出统一的轻量级视觉-语言-动作模型用于机器人多模态控制
tldr: 现有视觉-语言-动作模型参数量庞大，依赖大规模机器人数据预训练，训练成本高且难以实时部署，同时训练范式常损害视觉-语言骨干的感知表征，导致过拟合与泛化差。本文提出 Evo-1，一种轻量级 VLA 模型，在降低计算量、提升部署效率的同时保持语义对齐。该工作面向机器人学习任务，为高效可部署的多模态感知与控制一体化模型提供了新方案，具有推动 VLA 实际落地的意义。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 3, \"index\": 1, \"width\": 10002, \"height\": 4446}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 4, \"index\": 4, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 4, \"index\": 5, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 4, \"index\": 6, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 4, \"index\": 7, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 6, \"index\": 8, \"width\": 3618, \"height\": 3096}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 6, \"index\": 9, \"width\": 3846, \"height\": 1902}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 7, \"index\": 10, \"width\": 2856, \"height\": 678}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 8, \"index\": 11, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 8, \"index\": 12, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 8, \"index\": 13, \"width\": 448, \"height\": 448}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 2142, \"height\": 1686}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 8, \"index\": 15, \"width\": 2142, \"height\": 1686}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 8, \"index\": 16, \"width\": 2142, \"height\": 1602}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 8, \"index\": 17, \"width\": 2136, \"height\": 1506}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 8, \"index\": 18, \"width\": 1746, \"height\": 2508}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-evo-1-lightweight-vision-language-action-model-with-preserved-semantic-alignment-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 8, \"index\": 19, \"width\": 2526, \"height\": 1860}]"
motivation: 现有 VLA 模型参数庞大、依赖大规模预训练且易过拟合，训练成本高、难以实时部署。
method: 提出轻量级 VLA 模型 Evo-1，在降低计算量的同时保持视觉-语言骨干的语义对齐。
result: 模型在减少计算开销、提升部署效率的同时维持了较强的感知与泛化性能。
conclusion: 该工作为机器人学习提供了高效可部署的视觉-语言-动作一体化模型框架。
---

## Abstract
Vision-Language-Action (VLA) models have emerged as a powerful framework that unifies perception, language, and control, enabling robots to perform diverse tasks through multimodal understanding. However, current VLA models typically contain massive parameters and rely heavily on large-scale robot data pretraining, leading to high computational costs during training, as well as limited deployability for real-time inference.Moreover, most training paradigms often degrade the perceptual representations of the Vision-Language backbone, resulting in overfitting and poor generalization to downstream tasks.In this work, we present Evo-1, a lightweight VLA model that reduces computation and improves deployment efficiency, while maintaining strong performance without pretraining on robot data. Evo-1 builds on a native multimodal Vision-Language model (VLM), incorporating a novel cross-modulated diffusion transformer along with an optimized integration module, together forming an effective architecture.We further introduce a two-stage training paradigm that progressively aligns action with perception, preserving the representations of the VLM.Notably, with only 0.77 billion parameters, Evo-1 achieves state-of-the-art results on the Meta-World and RoboTwin suite, surpassing the previous best models by 12.4% and 6.9%, respectively, and also attains a competitive result of 94.8% on LIBERO.In real-world evaluations, Evo-1 attains a 78% success rate with high inference frequency and low memory overhead, outperforming all baseline methods.We release code, data, and model weights to facilitate future research on lightweight and efficient VLA models.

---

## 论文详细总结（自动生成）

# Evo-1 论文深度总结

## 一、核心问题与整体含义（研究动机与背景）

- **VLA 模型的价值**：视觉-语言-动作（VLA）模型统一了感知、语言与控制，使机器人能够依据自然语言指令和视觉观测执行多样化操作任务，具备跨环境与跨本体的泛化潜力。
- **现存四大痛点**：
  - **参数量巨大**：现有 VLA 模型通常达数十亿参数，训练与推理的 GPU 显存和算力开销极高。
  - **实时性差**：大计算量导致控制频率低，难以满足交互式机器人任务的实时响应需求。
  - **表征退化**：端到端训练范式常破坏视觉-语言骨干的语义表征空间，引发过拟合与下游泛化能力下降。
  - **依赖大规模机器人数据预训练**：多数模型依赖 OXE、DROID 等长时、昂贵、劳动密集的数据集预训练。
- **整体含义**：论文提出 **Evo-1**，旨在探索一条"轻量、低成本、无需机器人数据预训练"的 VLA 路线，在保留 VLM 语义对齐能力的同时实现高性能实时部署，推动 VLA 从实验室走向实际落地。

## 二、方法论

### 2.1 核心思想
- 采用**模块化轻量架构**：原生多模态 VLM 骨干 + 跨调制扩散 Transformer（动作专家）+ 优化集成模块。
- 通过**两阶段训练**渐进对齐动作与感知，避免直接端到端训练破坏预训练语义空间。

### 2.2 关键技术细节

- **视觉-语言骨干（InternVL3-1B）**：
  - 视觉编码器为 **InternViT-300M**（由 InternViT-6B 蒸馏而来）；输入 RGB 观测统一缩放至 448×448，并经 pixel-unshuffle 下采样将视觉 token 数减少 4×。
  - 语言分支为 **Qwen2.5-0.5B**，仅保留前 **14 层**（经验上中间层具有更强的跨模态对齐能力）。
  - 采用原生多模态预训练范式，避免"事后对齐"带来的语义割裂。
  - 融合表征记为：`z_t = f_VLM({I_i^t}, L^t)`。

- **跨调制扩散 Transformer（动作专家）**：
  - 基于 **Flow Matching** 的 DiT，**仅使用堆叠的交叉注意力层**（区别于 π0、SmolVLA 的自注意力+交叉注意力交替结构）。
  - 噪声插值构造：`A_τ^t = τ·A_t + (1-τ)·ε`，τ 采样自 Beta 分布并截断至 [0.02, 0.98] 以保证数值稳定。
  - 训练目标（学习时间条件速度场）：
    `L_τ(θ) = E[ || v_θ(A_τ^t, z_t, s_t) − u(A_τ^t | A_t) ||² ]`
  - 推理时输出未来 H 步动作块：`Â_t = f_AE(z_t, s_t, A_τ^t)`。

- **集成模块**：
  - 采用**交叉注意力**结构，将第 14 层融合表征 `z_t` 与机器人本体状态 `s_t` **直接拼接**（而非投影到共享空间），作为动作专家各层的 key-value 输入，查询为噪声动作 `A_τ^t`。
  - 拼接方式旨在**完整保留感知嵌入与本体状态信息**，避免投影造成的信息损失。

- **两阶段训练范式**：
  - **阶段 1（动作专家对齐）**：冻结整个 VLM 骨干，仅训练动作专家与集成模块，使随机初始化的动作专家逐步对齐多模态嵌入空间，避免噪声梯度回传污染预训练骨干。
  - **阶段 2（全量微调）**：解冻 VLM 骨干，全架构联合微调，实现更深度的感知-控制融合。
  - 整体映射：`a_t = f_Evo-1({I_i^t}, L^t, s_t; θ)`。

## 三、实验设计

### 3.1 仿真基准
- **Meta-World**：每任务 50 条演示，每任务 10 次试验，5 次独立运行取平均；按 easy/medium/hard/very hard 四档难度评估。
- **LIBERO**：40 个任务，分 spatial / object / goal / long 四类，每任务 10 次试验，5 次独立运行。
- **RoboTwin（双臂操作）**：选取 Click Alarmclock、Dump Bin Bigbin、Place Bread Basket、Place Can Basket 四个任务；每任务 50 条演示、100 次评估试验、两档难度。

### 3.2 真实世界实验
- 硬件：**6-DoF xArm6 机械臂 + 平行夹爪**。
- 四个任务：Pick and Place Can、Pour Foam from Cup、Hand Delivery、Can Stacking。
- 每任务采集 **100 条遥操作演示**；每任务 20 次试验，物体配置多变。

### 3.3 泛化实验
- 基于真实世界 Pick and Place Can 任务，设置四类分布外扰动：未见干扰物、背景颜色变化、目标位置偏移（10/20/30 mm）、目标高度变化（10/20/30 mm），每种条件 20 次试验。

### 3.4 消融实验
- **集成模块设计**：对比 Module A（中层交叉注意力，最终采用）、Module B（交叉-自注意力交错）、Module C（逐层交叉注意力）、Module D（联合 key-value 交叉注意力），在 LIBERO-Long 上评估。
- **训练范式**：两阶段 vs 单阶段联合训练，在 Meta-World 上对比，并可视化注意力图。
- **语义保持验证**：对比 Evo-1（InternVL3-1B）与 OpenVLA（Prismatic-7B）训练后的图文注意力图。

### 3.5 对比方法
- 仿真：Diffusion Policy、TinyVLA-H、π0、SmolVLA、OpenVLA、CoT-VLA、π0-FAST、GR00T N1、ACT、RDT。
- 真实世界：SmolVLA、OpenVLA-OFT、π0、OpenVLA。

## 四、资源与算力

- **明确提到的信息**：推理效率分析在 **RTX 4090D GPU** 上进行（单卡），报告了显存占用与推理频率（Evo-1：2.3 GB / 16.4 Hz）。
- **未明确说明的信息**：
  - 训练所用的 GPU 型号、数量、总卡时/训练时长均**未在文中给出**。
  - 仿真与真实世界实验的训练算力预算、训练步数/epoch 等细节也**未披露**。
- 这一缺失使得"低成本训练"的核心主张缺乏直接的算力数据支撑（虽通过 0.77B 参数规模间接体现）。

## 五、实验数量与充分性

- **实验组数概览**：
  - 3 个仿真基准（Meta-World 四档难度、LIBERO 四类任务、RoboTwin 四任务×两档难度）。
  - 1 组真实世界实验（4 任务 × 20 试次）。
  - 1 组泛化实验（4 类扰动、共 7 个条件 × 20 试次）。
  - 2 组消融（集成模块 4 变体；训练范式 2 对比）。
  - 1 组注意力可视化对比（与 OpenVLA/Prismatic-7B）。
- **充分性评价**：
  - **覆盖较广**：涵盖单臂/双臂、仿真/真实、性能/效率/泛化/消融，维度较为完整。
  - **客观性较好**：仿真基准采用标准协议，基线结果取自原论文或官方复现，声称公平对比。
  - **统计可靠性**：仿真采用 5 次独立运行平均，真实世界每任务 20 试次，泛化每条件 20 试次，样本量尚可。
  - **潜在不足**：真实世界任务数量（4 个）与试次规模有限；消融仅在 LIBERO-Long 或 Meta-World 单基准上验证，未做跨基准交叉验证；未报告多次随机种子的方差/置信区间。

## 六、主要结论与发现

- **仿真性能**：
  - Meta-World 平均成功率 **80.6%**，超越此前最佳 SmolVLA（68.2%）**12.4 个百分点**，并在四档难度上全面领先。
  - RoboTwin 平均成功率 **37.8%**，超越此前最佳 π0（30.9%）**6.9 个百分点**，在 Click Alarmclock 上表现尤为突出（77.0/58.0）。
  - LIBERO 平均 **94.8%**，超过 π0（94.2%）与 SmolVLA（88.8%），长任务（92.3%）鲁棒性显著。
- **真实世界性能**：平均成功率 **78%**，优于 SmolVLA（50%）、OpenVLA-OFT（55%）与 π0（73%），且参数量仅为 π0 的约 1/4。
- **推理效率**：仅 0.77B 参数，显存 **2.3 GB**，推理频率 **16.4 Hz**，在效率-性能权衡上最优。
- **泛化能力**：在未见干扰物、背景变化、位置/高度偏移下均优于 SmolVLA（如基础场景 95% vs 75%）。
- **语义保持**：两阶段训练后注意力图保持清晰、语义一致；单阶段训练则出现语义漂移与注意力分散，验证了训练范式的有效性。
- **核心结论**：轻量架构 + 两阶段训练可在**无需机器人数据预训练**的前提下，同时实现 SOTA 性能、高推理频率与强泛化。

## 七、优点（亮点）

- **架构轻量高效**：0.77B 参数、2.3 GB 显存、16.4 Hz 推理频率，可在消费级 GPU 上实时部署。
- **无需机器人数据预训练**：摆脱对 OXE/DROID 等大规模昂贵数据集的依赖，显著降低数据采集成本。
- **语义保持的训练设计**：两阶段范式（先冻结 VLM 对齐动作专家，再全量微调）有效防止表征退化，兼顾泛化与适配。
- **集成模块设计简洁有效**：直接拼接而非投影，避免信息损失；消融实验证明其优于交错/逐层/联合等多种替代方案。
- **动作专家结构创新**：仅用交叉注意力堆叠的 DiT，简化结构的同时提升时序推理效率。
- **实验覆盖较全面**：仿真三基准 + 真实世界 + 泛化扰动 + 双组消融 + 注意力可视化，多维度验证方法有效性。
- **开源贡献**：发布代码、数据与模型权重，促进轻量 VLA 研究。

## 八、不足与局限

- **算力信息缺失**：未报告训练 GPU 型号/数量/时长，"低成本训练"主张缺乏直接算力证据。
- **真实世界任务偏简单**：四个任务均为抓取-放置/倾倒/递送/堆叠等相对短时程操作，未涉及长时程、多阶段或复杂接触操作。
- **双臂任务绝对性能仍偏低**：RoboTwin 平均仅 37.8%，hard 难度部分任务接近 0–3%，说明复杂双臂操作仍是瓶颈。
- **泛化实验范围有限**：仅在单一真实任务（Pick and Place Can）上验证，且扰动类型限于视觉背景、位置、高度与干扰物，未涉及新本体、新指令语义或动态环境。
- **消融验证基准单一**：集成模块消融仅在 LIBERO-Long 上进行，训练范式消融仅在 Meta-World 上进行，跨基准一致性有待进一步验证。
- **统计报告不完整**：未提供方差、置信区间或显著性检验，部分提升（如 LIBERO 上 94.8% vs 94.2%）幅度较小。
- **基线对比口径差异**：部分基线结果引自原论文，训练数据规模、预训练策略、评测协议可能存在差异，绝对公平性存疑。
- **应用限制**：方法依赖 InternVL3-1B 与 Qwen2.5-0.5B 的预训练权重，跨本体/跨任务迁移的通用性尚待更大规模验证。

（完）
