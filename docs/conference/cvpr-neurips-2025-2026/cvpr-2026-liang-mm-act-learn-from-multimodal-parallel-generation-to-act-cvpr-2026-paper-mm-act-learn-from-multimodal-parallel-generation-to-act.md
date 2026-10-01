---
title: "MM-ACT: Learn from Multimodal Parallel Generation to Act"
title_zh: MM-ACT：从多模态并行生成到动作
authors: "Liang, Haotian, Chen, Xinyi, Wang, Bin, Chen, Mingkang, Liu, Yitian, Zhang, Yuhao, Chen, Zanxin, Yang, Tianshuo, Chen, Yilun, Pang, Jiangmiao, Liu, Dong, Yang, Xiaokang, Mu, Yao, Shao, Wenqi, Luo, Ping"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Liang_MM-ACT_Learn_from_Multimodal_Parallel_Generation_to_Act_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 统一VLA机器人策略模型
tldr: 通用机器人策略既需要语义理解以进行任务规划，也需要通过预测能力与环境交互。本文提出MM-ACT，一个将文本、图像和动作整合到共享token空间并跨三种模态生成的统一视觉-语言-动作模型。该方法对文本和图像采用重掩码并行解码，对动作采用一步并行解码以提升效率，并提出上下文共享多模态学习统一训练范式。实验验证了跨模态学习对动作生成的增强作用。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 1019, \"height\": 1147}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 7, \"index\": 2, \"width\": 1243, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 7, \"index\": 3, \"width\": 1245, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 1242, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 7, \"index\": 5, \"width\": 1241, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 7, \"index\": 6, \"width\": 1247, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 7, \"index\": 7, \"width\": 1244, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 7, \"index\": 8, \"width\": 1247, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 7, \"index\": 9, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 7, \"index\": 10, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 7, \"index\": 11, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 7, \"index\": 12, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 7, \"index\": 13, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 7, \"index\": 14, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 7, \"index\": 15, \"width\": 1280, \"height\": 1280}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liang-mm-act-learn-from-multimodal-parallel-generation-to-act-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 7, \"index\": 16, \"width\": 2623, \"height\": 1475}]"
motivation: 通用机器人策略既需语义理解做任务规划，又需预测能力与环境交互。
method: 提出MM-ACT，将文本、图像与动作整合到共享token空间并进行多模态并行生成。
result: 采用重掩码与一步并行解码策略，通过跨模态学习增强动作生成。
conclusion: 为统一多模态VLA策略提供了新范式。
---

## Abstract
A generalist robotic policy needs both semantic understanding for task planning and the ability to interact with the environment through predictive capabilities. To tackle this, we present MM-ACT, a unified Vision-Language-Action (VLA) model that integrates text, image, and action in shared token space and performs generation across all three modalities. MM-ACT adopts a re-mask parallel decoding strategy for text and image generation, and employs a one-step parallel decoding strategy for action generation to improve efficiency. We introduce Context-Shared Multimodal Learning, a unified training paradigm that supervises generation in all three modalities from a shared context, enhancing action generation through cross-modal learning. Experiments were conducted on the LIBERO simulation and Franka real-robot setups as well as RoboTwin2.0 to assess in-domain and out-of-domain performances respectively. Our approach achieves a success rate of 96.3% on LIBERO, 72.0% across three tasks of real Franka, and 52.38% across eight bimanual tasks of RoboTwin2.0 with an additional gain of 9.25% from cross-modal learning. We release our codes, models and data at https://github.com/HHYHRHY/MM-ACT.

---

## 论文详细总结（自动生成）

# MM-ACT 论文总结

## 1. 核心问题与研究动机

- **背景**：构建通用机器人策略（generalist robotic policy）需要同时具备两种能力——用于任务规划的**高层语义理解**，以及通过与环境的交互来实现的**预测能力**。
- **现有 VLA 的两难**：
  - 基于大规模预训练 VLM 的 VLA（如 OpenVLA、π0 系列）擅长视觉-语义理解，但**缺乏对物理动力学的显式建模**，限制了时序动作生成。
  - 以视觉预测驱动的世界模型类方法（如 DreamVLA、CoT-VLA）具备动态预测能力，但**主要为预测目标训练，任务导向规划与指令理解能力弱**。
  - 近期统一 VLA 方法大多直接沿用统一理解-生成模型的范式（如 AR 文本 + 并行图像/动作，或全 AR），导致**注意力机制/训练流程复杂**或**推理速度慢**；且在 AR 预训练骨干上做扩散式动作微调，会带来**目标不一致（token 预测 vs 去噪）的优化错位**。
- **整体含义**：论文主张重新思考策略架构，让文本、图像、动作在同一离散 token 空间中以**统一的并行解码目标**生成，从而兼顾语义理解、未来预测与低延迟动作生成。

## 2. 方法论

### 2.1 核心思想
- **统一 token 空间**：用模态专用 tokenizer 将文本、图像、机器人本体状态/动作编码为同一序列中的离散 token，模型以带**双向注意力**的 8B Transformer 作为 mask token 预测器，对三种模态统一生成。
- **模态 token 控制生成目标**：上下文前加 `<modal>` token（`<|mm2a|>` 动作、`<|mmu|>` 文本规划、`<|t2i|>` 图像），决定本次生成的是动作、文本还是图像。

### 2.2 关键技术细节
- **Tokenizer 配置**：
  - 文本：LLaDA tokenizer。
  - 图像：Show-o 的预训练图像量化器，8192 码本；输入填充为方形后下采样到 256×256，编码为 256 token，输出解码回 256×256 图像。
  - 状态/动作：bin tokenizer（OpenVLA 风格），2048 个专用码本；连续标量归一化到 [-1,1] 后量化，输出再反量化回连续动作值。
- **上下文共享输入**：`C_modal = <modal> + shared_input`，shared_input 为多视图观测、任务指令、文本描述、（可选）机器人状态的交错 token 模板。文本块 256 token、图像块 256 token、动作块大小为 `N_act_block = d_action × N_chunk_size`（动作块大小固定为 8）。
- **统一掩码预测目标**：
  - 对每个模态块构造掩码序列，掩码概率 `p_mask = f_modal(t)`；条件分布按式(1)(2) 定义，各位置独立掩码。
  - 文本用**线性掩码调度**（沿用 LLaDA），图像与动作用**余弦调度**以对齐连续去噪的噪声调度。
  - 动作模态训练时直接令 `t = 1`，即从**全掩码序列**在单次前向中生成全部动作 token。
  - 损失为跨三模态掩码位置的统一交叉熵（式(3)），`λ_modal` 控制各模态权重。
- **并行解码策略**：
  - 文本与图像：**re-mask 多步并行解码**（低置信度重掩码，余弦噪声调度，参考 MAGVIT-v2）。
  - 动作：**一步并行解码**（one-step parallel decoding），单次前向输出整个动作块，实现低延迟（稳定 40Hz 动作频率）。
  - 文本限制在 256 token 单块内，不做半自回归。
- **两阶段训练（Context-Shared Multimodal Learning）**：
  - Stage 1：`λ_mm2a = 0`，仅训练文本与图像生成，直至损失较低。
  - Stage 2：以动作生成监督为主，`λ_mmu`、`λ_t2i` 调至约 0.05–0.1 以保持其他模态生成能力。
  - 同一共享上下文下，三模态前向过程在**同一梯度累积步内聚合损失**优化；部署时仅做一步动作生成。

## 3. 实验设计

- **Benchmark / 场景**：
  - **LIBERO 仿真**（Franka 单臂）：Spatial、Object、Goal、Long 四个子基准，各 10 任务、每任务 50 条遥操演示；关注 Long 子集的长期规划。
  - **RoboTwin 2.0 仿真**（Agilex Piper 双臂）：8 个代表性任务，在**域随机化 + 未见设置**（指令、环境、物体位置均未见）下评测，偏域外（out-of-domain）；每任务采集 500 条专家轨迹，约 70k 训练样本。
  - **Franka 真实机器人**：3 个任务（按按钮、小方块叠大方块、果蔬分类），每任务 100 条遥操演示、20 次评测试验。
- **对比方法（三大范式）**：
  - VLM-based VLA：OpenVLA、OpenVLA-OFT、π0、π0+FAST。
  - Visual Prediction VLA：CoT-VLA、TraceVLA、DreamVLA。
  - Unified VLA：UniVLA、WorldVLA。
- **消融/分析设置**：Vanilla（仅动作）、+Text、+Image、+Text&Image 四种训练配置，验证跨模态协同增益；并对比一步并行解码与 re-mask 策略的效率/效果权衡（详见附录 A.2）。

## 4. 资源与算力

- **论文未明确披露算力信息**：未提及所用 GPU 型号、数量、总训练时长或总算力开销。
- 仅给出的训练规模信息：batch size 128、动作块大小 8；LIBERO 每个子基准单独训练约 15k 步；RoboTwin 八任务多任务训练约 27k 步；Franka 每任务约 8k 步；基础权重为 8B 的 MMaDA。
- **结论**：算力与能耗细节缺失，无法评估其训练成本与可复现的资源门槛。

## 5. 实验数量与充分性

- **实验规模概览**：
  - 仿真：LIBERO 4 个子基准（约 40 任务）+ RoboTwin 8 任务，均含与 9 个基线方法的对比。
  - 真实机器人：3 个任务 × 20 次试验 × 3 个模型（含 π0、OpenVLA-OFT）。
  - 训练流程分析：4 组训练配置对比（仅动作 / +文本 / +图像 / +三模态），并在 LIBERO-Long 上验证文本规划带来的 +5.0% 增益。
  - 图像生成质量定性评估（RoboTwin 未见场景可视化），解码策略消融、机器人状态放置位置（文本 vs 图像上下文）等实验置于附录。
- **充分性与公平性评估**：
  - **优点**：覆盖仿真（域内 + 域外）与真实机器人，跨越三大类基线范式，跨模态训练做了较系统的对照，对比维度较全面。
  - **局限**：真实机器人任务仅 3 个、每任务 20 次试验，样本量偏小，统计显著性未报告；部分 RoboTwin 任务上 MM-ACT 明显低于基线（如 Bigbin 仅 13%，低于 π0 的 61%），论文未深入分析这类失败模式；消融主要集中在 RoboTwin 与 LIBERO-Long，未在其他子基准上系统重复；训练超参（学习率、优化器、掩码步数）与部分设置放在附录，正文透明度有限。

## 6. 主要结论与发现

- **LIBERO**：MM-ACT 平均成功率 96.3%（Vanilla 95.0%），优于 OpenVLA（+19.8%）、π0+FAST（+10.8%）、π0（+2.1%）、OpenVLA-OFT（+0.9%）、DreamVLA（+3.7%）、UniVLA（+0.8%）、WorldVLA（+14.5%）；加入文本任务规划后 Libero-Long 从 88.0% 提升至 93.0%（+5.0%）。
- **RoboTwin 2.0（域外）**：平均成功率 52.38%，超过 π0（48.13%，+4.25%）与 OpenVLA-OFT（23.13%，+29.25%）。
- **真实 Franka**：平均 72.0%，高于 π0（70.0%）与 OpenVLA-OFT（58.6%）。
- **跨模态学习增益**：仅动作 43.13% → +文本 46.5%（+3.37%）→ +图像 48.75%（+5.62%）→ +文本&图像 52.38%（+9.25%），验证三模态联合监督对动作生成的协同增强。
- **效率**：动作一步并行解码支持稳定 40Hz 推理；文本/图像采用 re-mask 多步解码以保证质量，二者在效果与效率间存在权衡。
- **图像生成**：生成的子目标图像能较好对齐真值并反映环境动态变化（含域随机化未见场景）。

## 7. 优点

- **架构统一且简洁**：三模态共享离散 token 空间、同一掩码预测目标与双向注意力，无需模态专用注意力或专用解码器，简化训练流程；避免了 AR 预训练与扩散微调之间的目标错位。
- **解码策略按模态差异化**：动作一步并行解码实现低延迟高频率控制，文本/图像用 re-mask 保质量，兼顾效率与生成效果。
- **训练范式设计巧妙**：Context-Shared Multimodal Learning 从同一上下文监督三种生成任务，用权重 `λ_modal` 和两阶段策略平衡模态，使任务规划、未来图像预测与动作生成互相促进（最高 +9.25%）。
- **评测覆盖较全面**：同时包含域内（LIBERO、Franka）与域外（RoboTwin 域随机化未见设置）、仿真与真实机器人，并对三大类 VLA 基线做了系统对比。
- **开源**：代码、模型与数据公开。

## 8. 不足与局限

- **算力信息缺失**：未报告 GPU 型号、数量与训练时长，训练成本与可复现性难以评估。
- **真实世界实验规模有限**：仅 3 个任务、每任务 20 次试验，缺乏统计显著性与更多样化的任务/物体/环境覆盖。
- **任务级性能不均衡**：在 RoboTwin 部分任务上显著落后于基线（如 Bigbin 13% vs π0 61%），论文未给出失败原因分析，泛化边界不清晰。
- **方法限制与假设**：
  - 动作块大小 `N_chunk_size` 训练与推理必须固定，灵活性与长时序适应性受限。
  - 文本生成限定 256 token 单块，对更长/更复杂规划可能不足。
  - 状态与动作使用 2048 码本的 bin tokenizer 量化，存在量化精度损失风险。
- **消融覆盖有限**：解码策略、状态上下文位置等消融主要在附录/部分设置上进行，正文对不同模态贡献的机制性分析偏浅（仅报告成功率）。
- **应用限制**：8B 模型规模在真实机器人端侧部署的实时性与成本仍是潜在瓶颈；40Hz 为报告值，未说明硬件配置。

（完）
