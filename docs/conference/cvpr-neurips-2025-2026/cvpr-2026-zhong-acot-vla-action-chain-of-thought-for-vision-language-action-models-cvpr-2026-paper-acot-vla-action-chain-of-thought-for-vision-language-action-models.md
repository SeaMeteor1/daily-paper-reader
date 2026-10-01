---
title: "ACoT-VLA: Action Chain-of-Thought for Vision-Language-Action Models"
title_zh: ACoT-VLA：面向视觉-语言-动作模型的动作思维链
authors: "Zhong, Linqing, Liu, Yi, Wei, Yifei, Xiong, Ziyu, Liu, Si, Ren, Guanghui"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Zhong_ACoT-VLA_Action_Chain-of-Thought_for_Vision-Language-Action_Models_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 在动作空间中直接推理的VLA机器人策略
tldr: 视觉-语言-动作模型已成为通用机器人策略，但现有方法多依赖子任务预测或目标图像合成等间接中间推理，难以传达精确动作执行所需的细粒度信息。本文提出动作思维链ACoT，主张最有效的推理应直接在动作空间中进行，从而引导动作生成。实验表明该范式在多样化操作任务上提升了精确执行能力。该工作为VLA模型的推理设计提供了新方向。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 8, \"index\": 2, \"width\": 3300, \"height\": 1800}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 8, \"index\": 3, \"width\": 1371, \"height\": 1068}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 8, \"index\": 4, \"width\": 1378, \"height\": 1091}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 1340, \"height\": 1072}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 8, \"index\": 6, \"width\": 1408, \"height\": 1105}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 8, \"index\": 7, \"width\": 1378, \"height\": 1107}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 8, \"index\": 8, \"width\": 1343, \"height\": 1090}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 8, \"index\": 9, \"width\": 1367, \"height\": 1084}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 8, \"index\": 10, \"width\": 1383, \"height\": 1108}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 8, \"index\": 11, \"width\": 1348, \"height\": 1114}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 8, \"index\": 12, \"width\": 1376, \"height\": 1119}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 8, \"index\": 13, \"width\": 1288, \"height\": 1110}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-zhong-acot-vla-action-chain-of-thought-for-vision-language-action-models-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 1350, \"height\": 1075}]"
motivation: 现有VLA的中间推理多为间接形式，难以传递精确动作所需的细粒度信息。
method: 提出动作思维链ACoT，让推理直接在动作空间中进行以引导动作生成。
result: 在多样化操作任务上提升精确动作执行能力。
conclusion: 表明在动作空间直接推理是VLA的有效范式。
---

## Abstract
Vision-Language-Action models have emerged as essential generalist robot policies for diverse manipulation tasks, conventionally relying on directly translating multimodal inputs into actions via Vision-Language Model embeddings. Recent advancements have introduced explicit intermediary reasoning--such as sub-task prediction (language) or goal image synthesis (vision)--to guide action generation. However, these intermediate reasoning are often indirect and inherently limited in their capacity to convey the full, granular information required for precise action execution. Instead, we posit that the most effective form of reasoning is one that deliberates directly in the action space. We introduce Action Chain-of-Thought (ACoT), a paradigm where the reasoning process itself is formulated as a structured sequence of coarse action intents that guide the final policy. In this paper, we propose ACoT-VLA, a novel architecture that materializes the ACoT paradigm. Specifically, we introduce two complementary components: an Explicit Action Reasoner (EAR) and Implicit Action Reasoner (IAR). The former proposes coarse reference trajectories as explicit action-level reasoning steps, while the latter extracts latent action priors from internal representations of multimodal input, co-forming an ACoT that conditions the downstream action head to enable grounded policy learning. Extensive experiments in real-world and simulation environments demonstrate the superiority of our proposed method. Code is available at: https://github.com/AgibotTech/ACoT-VLA.

---

## 论文详细总结（自动生成）

# ACoT-VLA 论文结构化总结

## 1. 核心问题与整体含义

- **研究背景**：视觉-语言-动作（VLA）模型已成为通用机器人策略的主流方案，其常规做法是通过预训练 VLM 将视觉与语言输入编码为隐表示，再直接解码为动作序列。
- **现有中间推理的局限**：
  - **语言 CoT**（如子任务预测）：以语义 token 形式提供推理，但过于抽象，难以承载精确执行所需的细粒度运动信息。
  - **视觉 CoT / 世界模型**（如目标图像合成、未来帧预测）：以自然视觉表征提供引导，但与底层动作空间仍存在异质性。
  - 二者共同问题是**语义-运动学鸿沟**（semantic-kinematic gap）：VLM 主干的知识源自 web 规模的语义对齐与问答预训练，其表征优化目标是语言理解而非物理动力学，因此对动作生成只能提供间接、次优的引导。
- **核心主张**：最有效的"推理"应当**直接在动作空间中进行**——把思维过程定义为结构化、运动学上可执行的粗粒度动作意图序列，而非语言 token 或视觉子目标。这一思路类比于从物理演示中学习，可为策略提供同质的运动线索。
- **整体含义**：作者提出 **Action Chain-of-Thought (ACoT)** 新范式，并实现为 **ACoT-VLA** 架构，试图在高层意图与底层电机控制之间建立直接、信息丰富的通道。

## 2. 方法论

### 2.1 问题形式化
- 通用机器人策略 $\pi_\theta$ 在语言指令 $l$ 与当前观测 $o_t$ 下预测动作序列 $a_{t:t+H-1}$。
- 已有工作引入引导信号 $g \in \{g_{lang}, g_{vis}\}$，本文扩展为 $g \in \{g_{lang}, g_{vis}, g_{action}\}$，并将动作引导进一步分解为：
  - **显式引导** $g^{ex}_{action}$：参考动作序列形式的直接先验。
  - **隐式引导** $g^{im}_{action}$：从语言、视觉上下文中隐含的动作分布先验。

### 2.2 显式动作推理器（EAR）
- 实例化为一个**轻量级 Transformer**（N=18 层），类比生成模型中的 self-conditioning。
- 输入含噪动作序列 $\tilde{a}_{t:t+H_{ref}-1}$，嵌入为初始隐表示 $h^{ref}_0$。
- 每层执行：自注意力（捕获动作序列时序依赖）+ 与对应 VLM 层 KV Cache 的交叉注意力（注入多模态上下文），再经 FFN 残差更新。
- 通过 **flow matching** 训练，输出去噪后的参考动作序列 $a^{ref}_{t:t+H_{ref}-1}$，再经 MLP 投影得到显式动作嵌入 $Z_{ex}$。

### 2.3 隐式动作推理器（IAR）
- 直接作用于 VLM 的 KV Cache，提取隐含在视觉-语言表征中的动作线索（如视觉可供性、动作相关语义）。
- 对每个 VLM 层 $i$，初始化可学习矩阵 $Q_i \in \mathbb{R}^{M \times d}$；先将 KV 对**下采样**到低维空间（$d'=128 \ll d$）以缓解冗余、提升效率。
- 对下采样后的 $Q'_i, K'_i, V'_i$ 做交叉注意力，再经平均池化与 MLP 投影，得到该层的隐式动作特征 $z^{im}_i$；跨层聚合后得到 $Z_{im}$。

### 2.4 动作引导预测（AGP）
- 将含噪动作段 $\tilde{a}_{t:t+H-1}$ 编码为 **action query** $Q_{action}$（而非直接送入动作头）。
- 执行**双重交叉注意力**：分别与 $Z_{ex}$、$Z_{im}$ 交互，得到 $S_{ex}$ 与 $S_{im}$——前者提供运动学线索，后者捕获潜在动作倾向。
- 拼接 $[S_{ex}; S_{im}]$ 后经自注意力融合块整合为统一表示 $\bar{h}$，送入动作头 $\pi^{head}_\theta$ 预测最终动作序列。

### 2.5 训练目标与稳定性设计
- **总损失**：$\mathcal{L}_{total} = \lambda_1 \mathcal{L}_{\pi^{ref}_\theta} + \lambda_2 \mathcal{L}_{\pi^{head}_\theta}$，两项均为 flow-matching MSE，$\lambda_1=\lambda_2=0.5$。
- **Teacher Forcing 稳定化**：训练时 $Z_{ex}$ 直接由 ground-truth 参考轨迹计算，避免 $\pi^{ref}_\theta$ 输出不稳定对动作头造成干扰；推理时切换为完全 self-conditioned 模式，由 $\pi^{ref}_\theta$ 自主生成参考动作。

## 3. 实验设计

### 3.1 数据集与场景
- **仿真基准**（均严格使用官方训练划分，不引入额外数据）：
  - **LIBERO**：4 个任务套件（Spatial / Object / Goal / Long），每套 10 个任务、每任务 50 条人类遥操作演示；每任务评测 50 次，共 2000 次 rollout。
  - **LIBERO-Plus**：引入 7 个扰动维度（相机视角、机器人初始状态、语言变化、光照、背景纹理、传感器噪声、物体布局），共 10,030 个评测回合；分 Zero-Shot Transfer 与 Supervised Fine-Tuning 两种协议。
  - **VLABench**：基于 ManiSkill3，5 条公开赛道（分布内、跨类别、常识推理、语义指令、未见纹理），指标为 Intention Score (IS) 与 Progress Score (PS)。
- **真实世界**：AgiBot G1 机器人上三个任务——"Wipe Stain"（接触密集操作）、"Pour Water"（精细物体操作）、"Open-set Pick"（指令跟随）；另在 AgileX 平台上做 "Open-set Pick" 以验证跨本体适应性。

### 3.2 对比方法
- 覆盖三类引导范式：
  - **视觉引导**：CoT-VLA、WorldVLA、DreamVLA、UniVLA、F1、GE-Act。
  - **语言引导**：TraceVLA、OpenVLA、UniAct、SpatialVLA、ThinkAct、π0-FAST、FPC-VLA、SmolVLA、GR00T-N1、π0、GO-1、DD-VLA、MemoryVLA、π0.5、OpenVLA-OFT、VLA-Adapter。
  - **无引导基线**：Diffusion Policy、Octo。
- 自身以 π0.5 为 baseline，并设置 frozen LLM 主干（†）与全量训练两种版本。

## 4. 资源与算力

- **训练**：单节点 **8 × NVIDIA H100 GPU**，bfloat16 精度。
- **推理**：单张 **NVIDIA RTX 4090**。
- **训练配置**：余弦衰减学习率，10K 步 warm-up，峰值 5e-5；AdamW，梯度裁剪 1.0；EMA 衰减率 0.999。
- **未明确说明**：论文**未报告具体训练时长、总 GPU 小时数、迭代步数（部分实验提到 60K 步）或能耗开销**。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 3 个仿真基准（LIBERO、LIBERO-Plus、VLABench）上的横向对比。
  - 1 组真实世界实验（3 个任务 + 1 个跨本体任务）。
  - 3 组消融实验：
    - **模块消融**（Table 4）：Baseline / +EAR / +IAR / +EAR+IAR。
    - **参考动作参数消融**（Table 5）：不同 action shift 与 action horizon 组合。
    - **KV-cache 交互策略消融**（Table 6）：Query / Attention Pooling / Downsample 三种策略。
- **充分性评价**：
  - **优点**：覆盖 3 个仿真基准 + 真实世界 + 跨本体，扰动维度丰富（LIBERO-Plus 10,030 回合统计上较可靠）；消融维度较完整，验证了 EAR、IAR 的独立与互补贡献。
  - **可商榷之处**：真实世界仅 3 个任务、跨本体仅 1 个任务，规模有限；未与所有最新方法在同一训练步数下严格对齐（VLABench 统一 60K 步，但 LIBERO 系列未明确）；部分对比方法使用官方 checkpoint 复现（*），可能存在复现偏差风险；论文提到更多消融在其他 benchmark 上，放在补充材料中，正文呈现有限。

## 6. 主要结论与发现

- **LIBERO**：平均成功率 98.5%（†版本 98.5%），超越 π0.5 的 96.9%，绝对提升 1.6%；在 Long 套件上提升显著（96.0% vs 92.4%），说明动作空间推理对长时程、需严格误差控制的任务尤其有效。
- **LIBERO-Plus**：
  - Zero-Shot 平均 86.6%，优于 π0.5 的 85.7%，在机器人初始状态扰动（+3.2%）与语言变化（+4.2%）上鲁棒性突出。
  - Supervised Fine-Tuning 平均 88.0%，为所有方法最优。
- **VLABench**：IS 63.5%、PS 47.4% 均为最佳；未见纹理赛道提升显著（IS +12.6%、PS +7.2%）。
- **真实世界**：平均成功率 66.7%，高于 π0.5 的 61.0% 与 π0 的 33.8%；AgiBot G1 与 AgileX 上表现一致，说明跨本体适应性。
- **消融结论**：
  - EAR 引入后平均从 96.9% → 98.3%，说明显式动作参考序列提供了强归纳偏置，降低观测到动作映射的歧义。
  - IAR 单独引入后 96.9% → 98.1%，说明 VLM 隐表示中蕴含可用的动作分布先验。
  - 两者结合达 98.5%，证实显式与隐式引导互补。
  - 参考动作参数方面：较短 horizon 配合适度 shift 增益更强。
  - KV-cache 交互方面：**Downsample 策略最优**，说明 VLM 特征对动作预测存在冗余，需设计合适的交互机制。

## 7. 优点

- **范式创新**：首次将 CoT 的"思维"从语言/视觉空间迁移到动作空间，直接针对语义-运动学鸿沟这一根本问题，动机清晰且逻辑自洽。
- **显隐互补设计**：EAR 提供运动学可执行的粗粒度轨迹，IAR 从 VLM 内部表征中挖掘隐含动作先验，两者从不同层面覆盖动作引导，且消融证明互补有效。
- **工程细节扎实**：
  - IAR 的下采样设计兼顾信息提取与计算效率，并指出 VLM 特征冗余。
  - Teacher Forcing 稳定化策略巧妙解耦了参考动作推理器与动作头的训练干扰。
  - 以 π0.5 为基座，验证了方法在强 baseline 之上的增量价值。
- **实验维度较全面**：仿真三基准 + 真实世界 + 跨本体 + 多维扰动，并区分 zero-shot 与 fine-tuning 协议，结论可信度较高。
- **可复现性**：代码已开源（https://github.com/AgibotTech/ACoT-VLA）。

## 8. 不足与局限

- **算力与训练细节不透明**：仅报告 GPU 型号与数量，未给出训练时长、总迭代数、数据规模与能耗，复现成本难以评估。
- **真实世界实验规模有限**：仅 3 个任务 + 1 个跨本体任务，任务多样性不足以支撑"通用策略"的强结论；样本量与统计显著性未详细说明。
- **对比公平性存在潜在偏差**：部分方法使用官方 checkpoint 复现（*标注），训练步数、数据配比、调参程度未必完全对齐；LIBERO 系列未明确统一训练步数。
- **方法本身的额外开销**：EAR 需 18 层 Transformer 与额外的 flow matching 训练目标，IAR 需跨层 KV-cache 交互，推理时 self-conditioned 生成参考动作会带来额外延迟，论文未报告推理时延与吞吐对比。
- **训练-推理不一致风险**：训练时用 ground-truth 参考轨迹计算 $Z_{ex}$，推理时用模型自生成参考动作，二者分布差异可能带来性能下降（teacher forcing gap），论文未量化该差距。
- **引导信号的依赖假设**：IAR 依赖 VLM 隐表示中确实蕴含动作先验，若基座 VLM 未在动作相关数据上充分训练，该假设可能不成立；论文未做跨基座 VLM 的鲁棒性验证。
- **性能增益的边际性**：在 LIBERO 等部分基准上相对 π0.5 的提升幅度较小（如 Spatial 99.4% vs 98.8%），接近饱和，可能受评测上限影响，难以充分体现方法优势。
- **应用限制**：方法依赖 VLM KV Cache 与 flow matching 框架，迁移到不同架构（如离散动作 token 的自回归 VLA）的可行性未讨论。

（完）
