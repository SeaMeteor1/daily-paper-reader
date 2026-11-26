---
title: Universal Actions for Enhanced Embodied Foundation Models
title_zh: 用于增强具身基础模型的通用动作
authors: "Zheng, Jinliang, Li, Jianxiong, Liu, Dongxiu, Zheng, Yinan, Wang, Zhihao, Ou, Zhonghong, Liu, Yu, Liu, Jingjing, Zhang, Ya-Qin, Zhan, Xianyuan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zheng_Universal_Actions_for_Enhanced_Embodied_Foundation_Models_CVPR_2025_paper.pdf"
tags: ["query:x-embodiment"]
score: 10.0
evidence: 通用动作空间对齐不同具身的动作空间
tldr: 现有具身数据因不同机器人物理形态与控制接口导致动作空间高度异构，难以直接训练具身基础模型。本文提出UniAct框架，在通用动作空间中学习能捕捉不同机器人共享结构特征的通用动作，从而统一异构动作表示。实验表明该方法可有效利用跨具身数据提升基础模型性能，为跨具身学习提供了可复用的动作抽象方案。
source: CVPR-2025-Accepted
selection_source: topic_research
id: cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper
canonical_id: "work:934086881b2bfac8e6db694c"
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
conference_acceptance_status: accepted
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 333, \"height\": 377}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 6, \"index\": 2, \"width\": 1826, \"height\": 282}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 6, \"index\": 3, \"width\": 1961, \"height\": 270}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 2002, \"height\": 416}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 1960, \"height\": 709}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 8, \"index\": 6, \"width\": 1959, \"height\": 615}]"
motivation: 不同机器人动作空间因物理形态与控制接口差异而高度异构，阻碍跨具身基础模型训练。
method: 提出UniAct框架，学习捕捉不同机器人共享结构特征的通用动作空间以统一表示。
result: 实验表明通用动作能有效利用跨具身异构数据并提升具身基础模型表现。
conclusion: 通用动作空间为跨具身数据训练提供了可行的动作抽象方案。
---

## 摘要
在多样化、互联网规模数据上进行训练是近期大型基础模型成功的关键因素。然而，将同样的方法用于构建具身智能体时却遇到了明显困难。尽管已有许多众包具身数据集，但由于不同机器人具有不同的物理形态和控制接口，其动作空间往往呈现出显著的异质性，这给利用跨具身数据开发具身基础模型带来了重大挑战。本文提出 UniAct，一种在通用动作空间中运行的新型具身基础模型框架。我们学习到的通用动作通过利用不同机器人共享的结构特征来捕捉其通用行为，并通过消除众所周知的异质性问题，增强跨域数据利用和跨具身泛化能力。此外，只需加入特定具身细节，通用动作即可高效转换回异质的可执行命令，从而使快速适应新机器人变得简单直接。我们的 0.5B 规模 UniAct 实例在多种真实世界和仿真机器人上的广泛评估中，优于参数量大 14 倍的 SOTA 具身基础模型，展现出卓越的跨具身控制和适应能力，凸显了采用通用动作的关键优势。

## Abstract
Training on diverse, internet-scale data is a key factor in the success of recent large foundation models. Yet, using the same recipe for building embodied agents has faced noticeable difficulties. Despite the availability of many crowd-sourced embodied datasets, their action spaces often exhibit significant heterogeneity due to distinct physical embodiment and control interfaces for different robots, causing substantial challenges in developing embodied foundation models using cross-embodiment data. In this paper, we introduce UniAct, a new embodied foundation modeling framework operating in the Universal Action Space. Our learned universal actions capture the generic behaviors across diverse robots by exploiting their shared structural features, and enable enhanced cross-domain data utilization and cross-embodiment generalizations by eliminating the notorious heterogeneity. Moreover, the universal actions can be efficiently translated back to heterogeneous actionable commands by simply adding embodiment-specific details, from which fast adaptation to new robots becomes simple and straightforward. Our 0.5B instantiation of UniAct outperforms 14X larger SOTA embodied foundation models in extensive evaluations on various real-world and simulation robots, showcasing exceptional cross-embodiment control and adaptation capability, highlighting the crucial benefit of adopting universal actions.

---

## 论文详细总结（自动生成）

# UniAct 论文中文总结

## 1. 核心问题与研究动机

- **背景**：大语言模型与视觉语言模型的成功高度依赖互联网规模的多源数据；但将同样范式迁移到具身智能体时遇到根本障碍——**动作空间的异质性**。
- **异质性的三个来源**：
  - 不同物理形态（自由度不同、机械臂/四足/车辆）拥有完全不同的动作空间；
  - 不同控制接口（末端执行器位置/速度、关节位置/力矩）使动作指令的物理含义根本不同；
  - 同一平台不同人类操作者带来的行为多模态性进一步加剧差异。
- **后果**：跨机器人、跨机构采集的动作数据落在彼此基本不相交的流形上，难以共享，阻碍通用具身基础模型的训练。
- **现有方案的不足**：
  - RT-X、Octo、OpenVLA 等强行把不同动作空间视为等价，统一离散化/归一化，导致"相似编码代表完全不同物理含义"的冲突空间；
  - CrossFormer、RDT、π0 等朴素聚合所有动作空间，依赖大量人工工程，且未挖掘不同具身之间的共享结构；
  - LAPA、IGOR、LAPO 等从视频帧间变化推断隐动作，会混入与动作无因果关系的视觉变化（如新物体出现），且受观测间隔影响，语义不统一。
- **整体含义**：论文主张放弃在异质动作空间上直接建模，转而构建一个**通用动作空间（Universal Action Space）**，让不同机器人共享"原子行为"表示，从而提升跨域数据利用率与跨具身泛化能力。

## 2. 方法论（UniAct 框架）

- **核心思想**：不同机器人执行"向前移动"等语义行为时控制信号各异，但行为本身共享；若把这些通用原子行为编码为离散码本，即可作为跨具身的信息瓶颈与技能库。
- **通用动作空间**：
  - 建模为向量量化码本 \(U=(u_1,\dots,u_N)\)，每个 \(u_i\in\mathbb{R}^D\) 表示一个通用原子行为；
  - 实例化规模 \(U\in\mathbb{R}^{256\times128}\)（256 个码、128 维）。
- **通用动作提取器（Universal Action Extractor）**：
  - 以预训练 VLM（LLaVA-OneVision-0.5B）为骨干，输入观测 \(o\) 与语言目标 \(g\)，输出选择各通用动作的概率 \(p(u|o,g)\)；
  - 目标是取 \(u^*=\arg\max_{u\in U} p(u|o,g)\)，即推断"最有助于完成任务"的原子行为，而非仅解释观测变化；
  - 由于 argmax 不可微，训练时用 **Gumbel-Softmax** 重参数化：\(u^*=\sum_i w_i u_i\)，其中 \(w_i=\mathrm{softmax}((\log p(u_i|o,g)+\epsilon_i)/\tau)\)，\(\epsilon_i\) 为 Gumbel 噪声，温度 \(\tau\) 随训练逐步衰减以兼顾探索与收敛；
  - 该离散瓶颈强制不同机器人共用同一码本，是跨域泛化的关键。
- **异构解码（Heterogeneous Decoding）**：
  - 为每个训练域配备一个轻量 MLP 头 \(h_k\)，输入通用动作 \(u^*\) 与共享视觉骨干提取的观测特征 \(o\)，输出该具身的控制信号 \(\hat a^{(k)}=h_k(u^*,o)\)；
  - 头部刻意保持轻量，避免过拟合目标域，使大部分学习发生在通用动作层面。
- **训练流程**：
  - 在 \(K\) 个异质数据集上做行为克隆，目标为 \(\min_{U,\theta}\sum_k \mathbb{E}\,L_k(\hat a^{(k)},a^{(k)})\)；
  - \(L_k\) 可按数据特性选择交叉熵、MSE、Huber 或扩散损失；
  - 码本与提取器每步全局更新，各解码头仅用本域采样批次更新，类似元学习中的"共享参数 + 任务特定组件"。
- **部署与适配**：新机器人只需冻结码本与提取器、新增一个轻量头并少量演示即可快速适配。

## 3. 实验设计

- **训练数据**：约 100 万条演示、覆盖 **28 种具身**，整合 Open-X Embodiment、LIBERO、DROID，统一为第三人称视觉 + 语言指令，但**保留动作异质性**（不做统一清洗）。
- **评测平台与 Benchmark**：
  - **真实 WidowX 机器人**：19 个任务、每任务 10 次试验（共 190 rollouts），覆盖视觉、运动、物理、语义、语言 grounding 五类泛化；
  - **仿真 LIBERO**：5 个 suite（Spatial / Object / Goal / Long / 90）共 130 个任务，每任务 20 次试验；
  - **新具身快速适配**：未见过的真实 AIRBOT，4 种控制接口（相对/绝对 EEF 位置、相对/绝对关节位置），100 条演示；任务为"小方块叠小长方体"，分 easy/hard（含杂物干扰）两版；
  - **新解码头适配**：双臂 AIRBOT + ACT 头，4 个任务、每任务 250 条演示；另在 LIBERO 上用 ACT 头进一步微调。
- **对比基线**：
  - Octo（0.1B）、CrossFormer（0.1B）；
  - OpenVLA（7B，自回归离散动作）；
  - LAPA（7B，基于视频帧间变化构建隐动作，需额外用动作标签微调）；
  - 基线训练数据经过清洗（绝对 EEF 转相对、去除关节位置动作），UniAct 则直接用原始异质数据。

## 4. 资源与算力

- 论文明确说明：UniAct-0.5B 的训练在 **64 张 A100 GPU** 上使用 **DeepSpeed** 进行，历时约 **10 天**，数据规模为 100 万条演示、28 种具身。
- 基线模型的训练算力未在正文中详细列出；LAPA 在 WidowX 适配时约 2K 梯度步的全量微调。整体而言，本文对自身训练资源披露较清楚，但对基线复现成本披露有限。

## 5. 实验数量与充分性

- **实验组数概览**：
  - 主实验 2 组（WidowX 真实 19 任务、LIBERO 仿真 130 任务）；
  - 快速适配 2 组（AIRBOT 四接口、双臂 AIRBOT + ACT 头）；
  - 机制分析 3 组（256 个通用动作的人工解码一致性检查、直接用通用动作 ID 手动控制机器人、跨域动作利用分布的 JS 散度统计）。
- **充分性**：
  - 覆盖真实与仿真、单臂与新机器人、多种控制接口、多类泛化维度，规模在同类工作中较为可观；WidowX 每任务 10 次、LIBERO 每任务 20 次试验，统计上具备一定可靠性。
  - 但正文**未见系统性消融实验**（如码本大小 256、维度 128、温度衰减策略、解码头复杂度、是否使用语言目标等关键设计的影响），相关细节推至附录，削弱了对各组件贡献的量化归因。
- **公平性**：
  - 优点：LIBERO 上 UniAct 与基线在任务、数据量、图像质量上对齐；基线在 WidowX 与 AIRBOT 上均做了充分微调（如 OpenVLA 达到约 95% 预测精度）；UniAct 参数量远小（0.5B vs 7B），比较方向对其不利却仍胜出，结论较有说服力。
  - 需注意：UniAct 使用保留异质性的原始数据，而基线使用清洗后数据，二者训练数据并非完全一致；LAPA 需额外微调才能输出动作；快速适配实验中 UniAct 仅需训练新头（约 4M 参数，占 0.8%），而基线需大幅微调，适配成本对比虽体现优势，但也意味着"可训练参数预算"并不对等。整体公平性基本合理，但并非严格受控对比。

## 6. 主要结论与发现

- **性能**：0.5B 的 UniAct 在 WidowX 的视觉、运动、物理泛化上超过 14 倍大的 OpenVLA-7B 与 LAPA-7B；在语义泛化与语言 grounding 上与 7B 模型相当；在 LIBERO 全部 5 个 suite 上均优于基线。
- **通用动作的有效性**：人工检查全部 256 个通用动作，至少 **40%** 在不同机器人上解码出**完全一致**的语义行为，即使存在视角差异与仿真到现实的巨大鸿沟。
- **可直接操控**：无需机器人运动学知识，仅通过选择通用动作 ID 序列即可手动控制机器人完成抓取放置等任务，说明通用动作具有语义可解释性，并可作为"动作 tokenizer"支撑未来在离散空间中的规划。
- **统计证据**：同一任务在不同机器人上的通用动作利用分布 JS 散度较低（0.34/0.44），不同任务间则较高（0.58–0.60），表明提取器确实聚焦任务进展而非具身细节。
- **高效适配**：冻结码本与提取器、仅新增轻量头即可适配新机器人、新控制接口与新解码器（ACT），微调参数占比仅 0.8%，显著低于 OpenVLA（1.4%）与 Octo（2%）。

## 7. 优点

- **问题定位准确**：抓住"动作异质性"这一跨具身学习的核心瓶颈，而非仅处理视觉域差异，动机清晰且有说服力。
- **表示设计巧妙**：用离散 VQ 码本 + 语言目标监督构建通用动作，既形成信息瓶颈强制共享结构，又避免纯视觉隐动作混入无关变化；Gumbel-Softmax 使离散选择端到端可训练。
- **架构解耦良好**：共享 VLM 提取器 + 轻量域特定头，实现"通用行为共享、具身细节分离"，天然支持新具身/新控制器的即插即用式扩展。
- **参数效率突出**：0.5B 模型在多项任务上超越 7B 基线，适配仅需 0.8% 参数，工程与实用价值高。
- **可解释性与可控性**：通用动作可人工检视、可直接手动编排控制机器人，为后续"在动作 token 空间做规划"提供了直观基础。
- **实验维度丰富**：真实 + 仿真、单臂 + 新平台、多控制接口、多泛化轴，并有机制层面的定量分析（一致性比例、JS 散度），论证链条较完整。

## 8. 不足与局限

- **规模与覆盖面有限**（作者自述）：仅 0.5B 实例，评测以单臂平台为主，尚未扩展到双臂、自动驾驶等更广具身；训练虽含 28 种具身，但主评测仅集中在 WidowX、Franka/LIBERO 与 AIRBOT。
- **通用动作空间质量仍有提升空间**：仅约 40% 的动作在跨具身上表现完全一致，说明码本中仍有相当比例未被充分共享或语义不稳定；码本利用率、坍缩风险等未做深入分析。
- **缺少系统性消融**：码本大小/维度、温度调度、语言目标的作用、解码头容量、损失函数选择等关键设计未在正文中量化对比，组件贡献难以归因。
- **对比并非严格受控**：UniAct 与基线所用训练数据（是否清洗）不一致；LAPA 需额外微调；快速适配时各方法的可训练参数预算不对等，虽总体不影响"UniAct 更优"的结论，但细粒度比较需谨慎解读。
- **适配实验规模偏小**：AIRBOT 每接口仅 100 条演示，双臂任务每任务 250 条，任务种类少（4 个），对新具身泛化能力的统计稳健性有限。
- **训练成本较高**：64×A100 训练 10 天，复现门槛高；论文未报告推理延迟、实时控制频率等部署关键指标。
- **潜在偏差风险**：JS 散度分析仅涉及 2 个任务 × 2 个域，样本量小；人工检查 256 个动作的一致性判断存在主观性，缺乏多人标注或量化协议说明。
- **应用限制**：方法依赖较高质量的观测与语言指令，对无语言标注数据、纯视频数据的适用性未验证；对长时序、多阶段复杂任务的规划能力尚待检验。

（完）
