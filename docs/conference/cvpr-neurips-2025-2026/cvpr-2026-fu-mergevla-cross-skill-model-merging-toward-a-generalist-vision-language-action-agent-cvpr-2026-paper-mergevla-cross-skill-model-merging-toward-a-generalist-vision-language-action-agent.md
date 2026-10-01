---
title: "MergeVLA: Cross-Skill Model Merging Toward a Generalist Vision-Language-Action Agent"
title_zh: MergeVLA：面向通用视觉-语言-动作智能体的跨技能模型合并
authors: "Fu, Yuxia, Zhang, Zhizhen, Zhang, Yuqi, Wang, Zijian, Huang, Zi, Luo, Yadan"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Fu_MergeVLA_Cross-Skill_Model_Merging_Toward_a_Generalist_Vision-Language-Action_Agent_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 跨技能合并VLA专家构建通用智能体
tldr: 该文针对视觉-语言-动作模型难以在单一模型中掌握多技能、直接合并不同任务专家成功率近乎为零的问题，提出MergeVLA跨技能模型合并方法。作者通过分解微调过程中的可学习参数，识别出LoRA适配器方向发散等导致模型不可合并的关键根源，并据此设计合并策略。实验表明该方法能在多技能设置下构建通用VLA智能体，为单一模型承载多种机器人能力提供了新思路。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fu-mergevla-cross-skill-model-merging-toward-a-generalist-vision-language-action-agent-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 3, \"index\": 1, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fu-mergevla-cross-skill-model-merging-toward-a-generalist-vision-language-action-agent-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 3, \"index\": 2, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fu-mergevla-cross-skill-model-merging-toward-a-generalist-vision-language-action-agent-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 3, \"index\": 3, \"width\": 512, \"height\": 512}]"
motivation: 现有VLA模型仅擅长单一本体或任务族，直接合并多任务专家会导致成功率几乎为零。
method: 通过分解微调可学习参数定位不可合并根源，提出跨技能模型合并策略构建通用VLA。
result: 识别出LoRA适配器发散等原因，合并后可在多技能场景取得有效性能。
conclusion: 为单一VLA模型掌握多技能、走向通用机器人智能体提供了方法基础。
---

## Abstract
Recent Vision-Language-Action (VLA) models reformulate vision-language models by tuning them with millions of robotic demonstrations. While they perform well when fine-tuned for a single embodiment or task family, extending them to multi-skill settings remains challenging: directly merging VLA experts trained on different tasks results in near-zero success rates. This raises a fundamental question: what prevents VLAs from mastering multiple skills within one model? With an empirical decomposition of learnable parameters during VLA fine-tuning, we identify two key sources of non-mergeability:(1) Finetuning drives LoRA adapters in the VLM backbone toward divergent, task-specific directions beyond the capacity of existing merging methods to unify.(2) Action experts develop inter-block dependencies through self-attention feedback, causing task information to spread across layers and preventing modular recombination.To address these challenges, we present MergeVLA, a merging-oriented VLA architecture that preserves mergeability by design.MergeVLA introduces sparsely activated LoRA adapters via task masks to retain consistent parameters and reduce irreconcilable conflicts in the VLM.Its action expert replaces self-attention with cross-attention-only blocks to keep specialization localized and composable.When the task is unknown, it uses a test-time task router to adaptively select the appropriate task mask and expert head from the initial observation, enabling unsupervised task inference.Across LIBERO, LIBERO-Plus, RoboTwin, and multi-task experiments on the real SO101 robotic arm, MergeVLA achieves performance comparable to or even exceeding individually finetuned experts, demonstrating robust generalization across tasks, embodiments, and environments. Project page: https://mergevla.github.io/

---

## 论文详细总结（自动生成）

# MergeVLA 论文中文总结

## 1. 核心问题与研究背景

- **背景**：视觉-语言-动作（VLA）模型通过在数百万机器人演示数据上微调视觉-语言模型（VLM），使机器人智能体能够执行复杂操作任务。这类模型在**单一任务**或**单一本体（embodiment）** 设置下表现优异，但真实世界的通用智能体需要支持多技能、多本体、多环境。
- **核心问题**：如何将多个独立微调的 VLA 专家模型整合为一个统一策略？作者尝试将大语言模型/视觉模型领域成熟的**模型合并（model merging）** 技术直接迁移到 VLA 上，却发现合并后的模型成功率**几乎为零**。
- **根本追问**：是什么阻碍了 VLA 在单一模型中掌握多种技能？
- **关键发现**：通过对 VLA 微调过程中可学习参数的经验性分解，作者识别出两个导致"不可合并"的根源：
  1. **LoRA 适配器方向发散**：微调使 VLM 骨干中的 LoRA 更新朝高度任务特定的方向偏移，直接平均或符号解析合并会激活无关甚至矛盾的参数，破坏共享的视觉-语言子空间。
  2. **动作专家的架构不兼容**：从零训练的动作解码器通过**自注意力反馈**在层间累积任务特定依赖，导致深层块参数距离爆炸，任务信息在层间扩散，无法模块化重组。
- **整体含义**：模型合并不仅是 VLA 可行的技术路径，更可成为通向**通用具身智能体**的可扩展方案。

## 2. 方法论：MergeVLA

### 2.1 核心思想

设计一种**"为合并而生"（mergeability by design）** 的 VLA 架构，使各技能模块在结构上保持可组合性，从而支持主流模型合并方法。

### 2.2 关键技术细节

**(1) 任务冲突问题（Q1）：基于任务掩码的稀疏 LoRA 激活**

- 设预训练权重为 Θ₀，任务 m 微调后权重为 Θₘ，任务向量 τₘ = Θₘ − Θ₀。
- 传统合并构造单一全局更新：τ_merge = α·R({τₘ})，Θ_merge = Θ₀ + τ_merge。
- MergeVLA 改为任务特定二值掩码：**Θ⁽ᵐ⁾_merge = Θ₀ + Sₘ ⊙ τ_merge**。
- 掩码构造采用参数级一致性检验：当某参数的 τₘ 既显著又主导于与 τ_merge 的缩放残差差时保留，即 **Sₘ = I[ |τₘ| > λ·|τ_merge − τₘ| ]**，λ 为掩码比例（容忍度）。
- 分析显示：合并 4 个任务时，"自私参数"（仅被单一任务保留）比例已超 **75%**，说明任务特异性极强，掩码机制至关重要。

**(2) 动作专家架构重设计（Q2）**

针对 VLA-Adapter 的动作专家（含自注意力 + 双交叉注意力 + FFN + tanh 门控）做两项改造：
- **移除自注意力层**：仅保留交叉注意力，迫使专家依赖稳健、共享的 VLM 特征。
- **替换门控函数**：将 tanh 门控改为 **sigmoid 门控**，确保 VLM 信息始终被保留与平衡，避免专家依赖自身从零训练的任务特定参数。
- 仅此两项改动即在 OOD 的 LIBERO-Plus 上提升 **13.4%** 成功率。

**(3) 专业化层次合并**

- 由于动作专家从零训练，无共享初始化，无法使用任务向量法，改用**简单权重平均**。
- 浅层块平均效果良好，但深层块参数差异剧增，称为**专家头（expert head, H_{l→L}）**，通常仅最后一层 L。
- 策略：**专家头不合并**，每个任务保留自己的专家头。

**(4) 测试时任务路由（Q3）**

- 当推理时任务身份未知，需从初始观测动态推断任务。
- 对合并后的 LoRA 参数应用各任务掩码，得到 M 个 VLM 变体，生成隐藏状态。
- 对动作专家第 l 层两条交叉注意力路径的**值投影矩阵 V** 做 SVD，保留前 kᵣ 个右奇异向量构成主导内容子空间 P_T、P_A。
- 用隐藏状态在子空间上的投影范数衡量激活强度：r_T,m = ‖P_T·h_A,m‖₂，r_A,m = ‖P_A·h_T,m‖₂。
- 组合分数 r = ½(r_T + r_A)，softmax 得到路由概率，取 argmax 选定任务掩码与专家头。
- **无需额外训练或监督**，仅用 t=0 初始观测一次路由即可，之后固定。

## 3. 实验设计

### 3.1 数据集与场景

| 基准 | 内容 |
|------|------|
| **LIBERO** | 四个任务套件：Spatial、Object、Goal、Long，评估多技能能力 |
| **LIBERO-Plus** | 含 7 种扰动（背景纹理、相机视角、语言指令、光照、物体布局、机器人状态、传感器噪声），共 10,030 个任务，评估 OOD 鲁棒性 |
| **RoboTwin 2.0** | 双臂跨本体基准，选 3 种本体（Aloha-Agilex、ARX-X5、Piper）和 4 个任务 |
| **真实实验** | SO101 机械臂多任务实验（详见附录） |

### 3.2 对比方法

- **单任务微调基线**：OpenVLA、π0、VLA-Adapter、MergeVLA
- **合并基线**：TA（Task Arithmetic）、TIES、WUDI、EMR、TSV、KnOTS
- **消融对比**：掩码比例 λ（0.2–0.9）、路由子空间选择（仅 K / K&V / 仅 V）

## 4. 资源与算力

- **论文正文未明确说明**所使用的 GPU 型号、数量及训练时长。
- 仅提及 MergeVLA 是**轻量级**模型：基于 VLA-Adapter 的 0.68B 参数，四任务评估总参数 0.68B×4；相比 OpenVLA 的 7B×4 显著更小。
- 计算开销方面提到：任务路由机制需维护 M 个任务掩码与对应动作头，但**额外计算与参数开销极小**。
- **建议**：读者若需复现，应参考项目主页（https://mergevla.github.io/）或原文附录获取算力细节。

## 5. 实验数量与充分性

### 5.1 实验组数概览

- **LIBERO**：4 个任务套件 × 多组合并方法对比（TA、TIES、WUDI、EMR、TSV、KnOTS 等），含单任务与合并两大设置。
- **LIBERO-Plus**：7 种扰动 × 4 个任务套件，单任务与合并两种设置。
- **RoboTwin**：两种设定（A：跨本体单任务；B：跨本体跨任务）× 3 种本体 × 3 任务，每组合 50 条演示轨迹、50 次试验。
- **真实世界**：SO101 机械臂多任务实验。
- **消融实验**：λ 敏感性分析（4 任务 × 8 个 λ 值）、路由子空间对比（3 种配置）。

### 5.2 充分性与公平性评估

- **优点**：
  - 覆盖仿真到真实、单任务到多任务、同本体到跨本体，维度较全。
  - 与多种主流合并方法（TA、TIES、WUDI、EMR、TSV、KnOTS）横向对比，参照充分。
  - 单任务微调结果作为上界参考（灰色高亮行），便于衡量合并性能损失。
- **局限**：
  - 真实世界实验在正文中仅给出平均成功率（90.0%），细节置于附录，正文可验证性有限。
  - RoboTwin 每组合仅 50 条演示轨迹，样本量相对偏小。
  - 未报告多次运行的方差或置信区间，统计显著性未知。

## 6. 主要结论与发现

- **性能结果**：
  - LIBERO 混合任务评估：**90.2%**（TIES 合并），仅比单任务微调低 6.5%。
  - LIBERO-Plus：**62.5%**，超过 OpenVLA（16.3%）、π0（56.3%）和 VLA-Adapter（59.0%）的单任务微调结果。
  - RoboTwin 跨本体跨任务：**70.7%**（TIES + H(L−2)→L 路由）。
  - 真实 SO101 机械臂：**90.0%**。
- **核心发现**：
  1. 直接对 VLA 专家做标准模型合并会**完全崩溃（0% 成功率）**。
  2. 仅解决 LoRA 干扰（加掩码）**仍不够**，动作专家架构本身是不兼容根源。
  3. 架构改造（去自注意力 + sigmoid 门控）带来 **13.4%** 的 OOD 鲁棒性提升。
  4. 值（V）子空间比键（K）子空间更适合任务路由，仅用 K 时部分任务完全失败。
  5. 掩码比例 λ 在 0.6–0.9 时成功率超 70%，适度稀疏性可平衡任务特定与合并向量。

## 7. 优点

- **问题洞察深刻**：通过参数分解系统性地定位 VLA 不可合并的两大根源，而非简单套用现有合并方法。
- **架构与合并协同设计**：不是事后合并，而是"为合并而设计"架构，思路新颖。
- **训练-free 任务路由**：基于值投影子空间的任务推断无需额外训练或监督，实用性强。
- **轻量高效**：0.68B 参数即可承载多技能，远小于 OpenVLA 7B，利于实际部署。
- **鲁棒性突出**：在视觉与语言分布偏移下仍保持高性能，甚至超越单任务微调基线。
- **跨本体验证**：RoboTwin 实验证明方法可扩展到不同机械臂硬件。

## 8. 不足与局限

- **算力信息缺失**：未报告 GPU 型号、数量与训练时长，复现成本不透明。
- **专家头需保留多份**：每个任务保留独立专家头，随任务数增长参数与存储开销线性增加，未讨论大规模任务下的可扩展性。
- **真实实验细节不足**：正文仅给出平均成功率，具体任务设置、失败案例分析缺失。
- **任务路由依赖初始观测**：若初始观测信息不足或任务在过程中切换，路由可能失效；未讨论动态任务场景。
- **基准覆盖有限**：RoboTwin 仅选 3 本体 4 任务，LIBERO-Plus 虽任务多但基于同一仿真平台，真实世界多样性验证仍显不足。
- **未验证更大 VLM 骨干**：作者在结论中自认"更大 VLM 骨干是否仍兼容本框架"为未来工作，说明当前结论的普适性有待检验。
- **潜在偏差风险**：合并方法（如 TIES、WUDI）超参数选择可能影响结果公平性，文中未详述调参过程。

（完）
