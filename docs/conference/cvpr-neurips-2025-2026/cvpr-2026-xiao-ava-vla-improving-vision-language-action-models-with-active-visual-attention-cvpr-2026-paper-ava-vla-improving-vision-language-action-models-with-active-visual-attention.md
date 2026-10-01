---
title: "AVA-VLA: Improving Vision-Language-Action models with Active Visual Attention"
title_zh: AVA-VLA：用主动视觉注意力改进视觉-语言-动作模型
authors: "Xiao, Lei, Li, Jifeng, Gao, Juntao, Ye, Feiyang, Jin, Yan, Qian, Jingjing, Zhang, Jing, Wu, Yong, Yu, Xiaoyuan"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Xiao_AVA-VLA_Improving_Vision-Language-Action_models_with_Active_Visual_Attention_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: VLA策略改进
tldr: 现有视觉-语言-动作模型多在每个时间步独立处理视觉观测，这种无历史设计将操作视为马尔可夫决策过程，与实际部分可观测的控制不符。本文从部分可观测马尔可夫决策过程出发重构VLA策略学习，提出AVA-VLA，用循环状态近似智能体对任务历史的信念，并构建主动视觉注意力机制。实验表明该方法能更好利用历史交互信息。这为VLA策略的历史推理提供了有效框架。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-xiao-ava-vla-improving-vision-language-action-models-with-active-visual-attention-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 800, \"height\": 1200}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-xiao-ava-vla-improving-vision-language-action-models-with-active-visual-attention-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 1816, \"height\": 1816}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-xiao-ava-vla-improving-vision-language-action-models-with-active-visual-attention-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 1816, \"height\": 1816}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-xiao-ava-vla-improving-vision-language-action-models-with-active-visual-attention-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 6674, \"height\": 1844}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-xiao-ava-vla-improving-vision-language-action-models-with-active-visual-attention-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 1889, \"height\": 566}]"
motivation: 多数VLA方法将视觉观测逐步独立处理，忽略了机器人控制固有的部分可观测性。
method: 从POMDP视角重构VLA策略学习，用循环状态近似信念并引入主动视觉注意力。
result: 在具身任务上验证了该方法能更好利用历史信息提升策略表现。
conclusion: 为VLA策略引入历史推理提供了有效框架。
---

## Abstract
Vision-Language-Action (VLA) models have shown remarkable progress in embodied tasks recently, but most methods process visual observations independently at each timestep. This history-agnostic design treats robot manipulation as a Markov Decision Process, even though real-world robotic control is inherently partially observable and requires reasoning over past interactions. To address this mismatch, we reformulate VLA policy learning from a Partially Observable Markov Decision Process perspective and propose AVA-VLA, a framework that conditions action generation on a recurrent state that serves as a neural approximation to the agent's belief over task history. Built on this recurrent state, we introduce Active Visual Attention (AVA), which dynamically reweights visual tokens in the current observation to focus on regions most relevant given both the instruction and execution history. Extensive experiments show that AVA-VLA achieves state-of-the-art performance on standard robotic benchmarks, including LIBERO and CALVIN, and transfers effectively to real-world dual-arm manipulation tasks. These results demonstrate the effectiveness of temporally grounded active visual processing for improving VLA performance in robotic sequential decision-making.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究动机**：现有 Vision-Language-Action（VLA）模型大多在每个时间步独立处理当前视觉观测，隐含地将机器人操作建模为**马尔可夫决策过程（MDP）**，即认为当前帧足以代表完整世界状态。
- **核心问题**：真实机器人控制本质上是**部分可观测**的，当前视觉帧只是环境状态的部分观测；忽略历史交互会导致模型无法抑制时间冗余信息，也难以根据过去动作聚焦关键区域，视觉处理因此偏“被动”。
- **整体含义**：论文从**部分可观测马尔可夫决策过程（POMDP）**视角重新形式化 VLA 策略学习，提出 AVA-VLA，用循环状态近似智能体对任务历史的“信念”，并据此动态调制当前视觉 token 的注意力，从而提升机器人顺序决策性能。

## 2. 方法论

- **核心思想**：
  - 将 VLA 策略从 \( \bar{A}_t \sim P_\theta(A_t \mid x_t) \) 改为 \( \bar{A}_t \sim P_\theta(A_t \mid x_t, b_{t-1}) \)，其中 \( b_{t-1} \) 是 POMDP 中的信念状态。
  - 由于真实信念状态不可直接计算，引入**循环状态 \( r_{t-1} \)** 作为其神经网络近似，来自上一时间步动作相关隐藏状态。
  - 基于该循环状态设计**主动视觉注意力（Active Visual Attention, AVA）**，动态重加权当前观测中的视觉 token。

- **关键公式与流程**：
  - 循环状态由上一时间步第 \( M \) 层隐藏状态经 MLP 得到：  
    \( r_{t-1} = B(h^{t-1}_M) \)。
  - 该循环状态还用于初始化当前动作 placeholder：\( p_t = r_{t-1} \)，以保留历史信息。
  - 前向过程可写为：  
    \( A_t = Q(M_{\text{parallel}}(z^t_I, V(x_t, r_{t-1}), z^t_S, r_{t-1})) \)，其中 \( V \) 为 AVA 模块。

- **AVA 模块细节**：
  - 使用模态特定 MLP 将视觉特征 \( z^t_I \) 和语言指令特征 \( z^t_S \) 投影到低维 \( d' \)。
  - 用 **FiLM** 以语言指令调制视觉特征：\( \hat{z}^t_I = F_\gamma(\bar{z}^t_S) \odot \bar{z}^t_I + F_\beta(\bar{z}^t_S) \)。
  - 以视觉 token 为 query，以循环状态为 key/value，进行 **Cross-Attention**，再接 **Self-Attention**。
  - 输出经 FFN、线性层和 Softmax，得到每个视觉 token 的增强/减弱 logits \( \rho_t \in \mathbb{R}^{L_I \times 2} \)。
  - 最终软权重 \( \omega_t = \rho_t \gamma \)，其中 \( \gamma \) 的两个分量分别表示增强和削弱分数。
  - 该软权重被用于构造软注意力矩阵 \( U_t \)，并调制 LLM 每一层的注意力分数，使视觉 token 根据指令和历史上下文被动态加权。

- **训练与推理**：
  - 训练采用**截断反向传播 Through Time**，展开长度 \( T=4 \)。
  - 动作预测损失为 MAE；同时加入对软权重均值的 L2 正则：\( \| \mu(\omega_t) - c \| \)，防止权重过于分散。
  - 总损失为预测损失与正则损失的加权和。
  - 推理时完全循环：新 episode 初始 \( r_{-1}=0 \)，每一步根据当前观测和上一循环状态预测动作 chunk，并提取新的循环状态。

## 3. 实验设计

- **仿真基准**：
  - **LIBERO**：包含 LIBERO-Spatial、LIBERO-Object、LIBERO-Goal、LIBERO-Long 四个 suite，共约 5,000 episodes、100 个任务，使用 Franka Emika Panda 机械臂。
  - **LIBERO+**：LIBERO 的鲁棒性扩展基准，包含 7 个扰动维度和 21 个子维度，结果放在附录 D。
  - **CALVIN**：语言条件长时程操作基准，采用 “ABC → D” 设置，即 A/B/C 环境训练、D 环境零样本泛化。

- **真实机器人实验**：
  - 使用真实双臂机器人平台，评估四个任务：Pick and Place、Sequenced Instruction Understanding、Flexible Object Folding、Dexterous Action。
  - 每个任务演示数据约 30 到 450 条。

- **对比方法**：
  - 包括 TraceVLA、WorldVLA、π0、π0-FAST、UnifiedVLA、OpenVLA-OFT、OpenVLA、SpatialVLA、CoT-VLA、NORA、PD-VLA、UniVLA、FLOWER、RIPT-VLA、VLA-Adapter、Seer 等。
  - 真实机器人实验主要对比 UniVLA 和 OpenVLA-OFT。
  - 基础模型采用 OpenVLA-OFT，视觉编码器为 DINOv2 + SigLIP，LLM backbone 为 LLaMA2-7B。

## 4. 资源与算力

- 论文明确提到所有实验在 **Nvidia A800 GPUs** 上进行。
- 但**未说明 GPU 的具体数量、训练总时长、显存占用或总计算量**。
- 也未给出不同实验的训练成本对比，因此算力可复现性信息有限。

## 5. 实验数量与充分性

- **实验组数量**：
  - LIBERO 表 1 包含两组设置：一个策略覆盖 4 个 suite，以及每个 suite 单独训练一个策略，对比约 18 个基线结果。
  - CALVIN 表 2 对比 8 个方法，报告 5 个连续任务成功率和平均完成长度。
  - 真实机器人实验覆盖 4 个任务，Pick and Place 评估 30 次，其他任务各 24 次。
  - 消融实验包括：3 种 backbone、AVA 模块与状态初始化的组合、6 种视觉 token 剪枝比例。
  - 另有 LIBERO+ 鲁棒性实验、定性可视化与视觉 token 缩减分析，主要放在附录或分析部分。

- **充分性评价**：
  - 覆盖仿真与真实任务、多 backbone、组件消融、token 剪枝，整体较充分。
  - 但真实机器人实验 trial 数相对有限，未报告多次运行的标准差或统计显著性。
  - 部分 baseline 结果来自原论文或已发表工作，而非在同一协议下全部重训，公平性可能受不同训练/评测细节影响。
  - LIBERO+ 仅在附录中，主文对鲁棒性讨论较少。

## 6. 主要结论与发现

- AVA-VLA 在 LIBERO 多任务设置中平均成功率 **98.0%**，单任务设置平均 **98.2%**，在 LIBERO-Long 上提升明显。
- 在 CALVIN ABC → D 上平均完成长度达到 **4.65**，五个连续任务成功率均优于基线。
- 在真实双臂机器人任务中，AVA-VLA 取得最高平均性能，验证了真实世界可迁移性。
- 消融表明：
  - 状态初始化与 AVA 模块各自都能提升性能，二者结合最佳。
  - 方法可跨不同 backbone 提升，包括未在机器人数据上预训练的模型。
  - AVA 软权重可用于视觉 token 剪枝，在剪除 50%–70% 视觉 token 后性能仍较稳健，甚至剪除 90% 后仍优于部分基线。

## 7. 优点

- **理论视角清晰**：从 POMDP 出发重新审视 VLA 的 MDP 假设，问题定位准确。
- **方法设计合理**：循环状态近似信念，并通过 AVA 模块将历史上下文注入视觉注意力，形成“主动视觉”机制。
- **组件互补**：状态初始化和 AVA 模块均有独立增益，组合后效果最佳。
- **实验较全面**：覆盖 LIBERO、CALVIN、真实机器人任务，并包含 backbone、消融和 token 剪枝分析。
- **实用性潜力**：软权重可自然用于视觉 token 剪枝，为后续效率优化提供接口。
- **跨 backbone 有效性**：在多种规模/预训练条件下均有提升，说明方法具有一定通用性。

## 8. 不足与局限

- **算力信息不完整**：仅说明使用 A800 GPU，未给出数量、训练时长、总计算量，复现成本不明确。
- **长时依赖建模有限**：训练采用截断 BPTT，展开长度仅 \( T=4 \)，可能限制对更长历史依赖的建模能力。
- **真实实验规模有限**：真实机器人任务 trial 数较少，未报告方差、置信区间或统计显著性。
- **基准公平性风险**：部分 baseline 结果引用自不同论文，训练和评测协议未必完全一致。
- **依赖基础模型**：方法建立在 OpenVLA-OFT 上，迁移到其他 VLA 架构时是否同样有效仍需更多验证。
- **效率优势非主要目标**：虽然 token 剪枝有潜力，但论文未系统分析实际推理加速、显存节省或实时部署开销。
- **复杂任务覆盖有限**：真实任务集中在抓放、折叠、堆叠和精细操作，对更复杂动态环境、多物体干扰或长时程任务覆盖仍有限。

（完）
