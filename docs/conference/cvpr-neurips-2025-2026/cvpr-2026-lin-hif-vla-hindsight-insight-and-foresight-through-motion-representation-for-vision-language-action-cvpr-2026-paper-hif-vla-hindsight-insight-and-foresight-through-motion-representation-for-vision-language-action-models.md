---
title: "HiF-VLA: Hindsight, Insight and Foresight through Motion Representation for Vision-Language-Action Models"
title_zh: HiF-VLA：通过运动表征实现视觉-语言-动作模型的后见、洞察与预见
authors: "Lin, Minghui, Ding, Pengxiang, Wang, Shu, Zhuang, Zifeng, Liu, Yang, Tong, Xinyang, Song, Wenxuan, Lyu, Shangke, Huang, Siteng, Wang, Donglin"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Lin_HiF-VLA_Hindsight_Insight_and_Foresight_through_Motion_Representation_for_Vision-Language-Action_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 面向VLA模型的以运动为中心的世界模型
tldr: 多数VLA模型假设马尔可夫性，仅依赖当前观测，导致时间短视并损害长程任务连贯性。本文以运动作为更紧凑且信息丰富的时间上下文与世界动态表征，过滤静态像素噪声。HiF-VLA为VLA配备以运动为中心的世界模型，使智能体在生成动作时能推理未来演化。该工作提升了VLA在长程操作中的时间连贯性与动态推理能力，为VLA引入运动表示提供新视角。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 7, \"index\": 1, \"width\": 435, \"height\": 319}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 7, \"index\": 2, \"width\": 455, \"height\": 369}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 7, \"index\": 3, \"width\": 455, \"height\": 374}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 537, \"height\": 398}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 373, \"height\": 386}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 8, \"index\": 6, \"width\": 723, \"height\": 749}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 8, \"index\": 7, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 8, \"index\": 8, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 8, \"index\": 9, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 8, \"index\": 10, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 8, \"index\": 11, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 8, \"index\": 12, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 8, \"index\": 13, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 8, \"index\": 15, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 8, \"index\": 16, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 8, \"index\": 17, \"width\": 645, \"height\": 443}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-lin-hif-vla-hindsight-insight-and-foresight-through-motion-representation-for-vision-language-action-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 8, \"index\": 18, \"width\": 645, \"height\": 443}]"
motivation: 多数VLA模型假设马尔可夫性，仅依赖当前观测，导致时间短视并削弱长程任务连贯性。
method: 以运动作为紧凑的时间上下文与世界动态表征，为VLA配备以运动为中心的世界模型，推理未来演化。
result: 模型在长程操作中改善了时间连贯性并增强了动态推理能力。
conclusion: 运动表示驱动的世界模型为VLA长程操作提供有效增强。
---

## Abstract
Vision-Language-Action (VLA) models have recently enabled robotic manipulation by grounding visual and linguistic cues into actions. However, most VLAs assume the Markov property, relying only on the current observation and thus suffering from temporal myopia that degrades long-horizon coherence. In this work, we view motion as a more compact and informative representation of temporal context and world dynamics, capturing inter-state changes while filtering static pixel-level noise. From this perspective, HiF-VLA equips a motion-centric world model for the VLA, enabling agents to reason about temporal dynamics for future evolution during action generation. Building on this idea, we propose HiF-VLA (Hindsight, Insight, and Foresight for VLAs), a unified framework that leverages motion for bidirectional temporal reasoning. HiF-VLA encodes past dynamics through hindsight priors, anticipates future motion via foresight reasoning, and integrates both through a hindsight-modulated joint expert to enable a "think-while-acting" paradigm for long-horizon manipulation. As a result, HiF-VLA surpasses strong baselines on LIBERO-Long and CALVIN ABC-D benchmarks, while incurring negligible additional inference latency. Furthermore, HiF-VLA achieves substantial improvements in real-world long-horizon manipulation tasks, demonstrating its broad effectiveness in practical robotic settings.

---

## 论文详细总结（自动生成）

# HiF-VLA 论文中文结构化总结

## 一、核心问题与研究动机

- **背景**：Vision-Language-Action（VLA）模型通过将视觉与语言线索 grounding 到动作空间，已实现机器人操作能力。
- **核心问题**：多数 VLA 模型（如 OpenVLA、RT-2 等）隐含假设**马尔可夫性**，仅依赖当前观测预测动作，不显式建模时间依赖，导致**时间短视（temporal myopia）**——连续动作之间的依赖退化，轨迹碎片化，长程任务级连贯性下降。
- **现有方案的局限**：
  - **堆叠历史帧**（如 RoboVLMs、TraceVLA、Octo）：计算开销大、推理延迟高、像素级冗余严重，静态信息淹没任务相关的动态信息。
  - **预测未来像素级子目标**（如 CoT-VLA、Seer、UP-VLA）：易产生局部畸变与语义漂移，缺乏连续时间建模，且依赖逆动力学模型（IDM）推断动作，结构不够清晰。
- **核心主张**：历史更精确、更高效的表示不是原始视觉内容，而是**状态之间的运动（motion）**。运动是时间记忆与环境动态的直接、紧凑代理，能忠实捕获交互动态（物体移动、抽屉关闭等），同时丢弃冗余静态信息。
- **整体含义**：将运动作为连接**过去（hindsight）与未来（foresight）**的自然桥梁，为 VLA 配备以运动为中心的世界模型，实现“边思考边行动（think-while-acting）”的长程操作范式。

## 二、方法论

### 2.1 核心思想

HiF-VLA 是一个统一框架，通过**运动向量（Motion Vectors, MVs）** 作为结构化、低维的时间基元，实现双向时间推理：

- **Hindsight（后见）**：编码过去动态为紧凑的 hindsight 先验。
- **Insight（洞察）**：理解任务指令与当前观测。
- **Foresight（预见）**：预测未来运动与潜在动作 token。
- **融合**：通过 hindsight-modulated joint expert 将后见作为自上而下的约束，调制预见与动作流。

### 2.2 关键技术细节

**（1）Hindsight 先验获取**

- 采用 MPEG-4 / H.264 视频编码标准提取**运动向量（MVs）**，预测相邻帧间宏块位移，避免像素级冗余。
- 运动向量定义：`MV_{t-1:t}(x,y) = (x_t - x_{t-1}, y_t - y_{t-1})`，其中 `(x_t, y_t)` 与 `(x_{t-1}, y_{t-1})` 分别表示宏块在连续帧中的位置。
- 以当前观测 `o_t` 为关键帧，维护长度 `m` 的历史窗口，形成 GOP 单元：`GOP = [MV_{t-m:t-m+1}, ..., MV_{t-1:t}, o_t]`。
- MVs 遵循 MPEG-4 的 16×16 宏块布局，表示为张量 `h × (H//16) × (W//16) × 2`。
- 使用轻量级 **ViT-based hindsight encoder** + 浅层 3D 卷积，将 hindsight 运动编码为紧凑 token `M_h ∈ R^{K_h×d}`。

**（2）Foresight Reasoning with Insight**

- 不预测原始未来像素，而是以结构化 MVs 作为时空目标。
- 引入 `K_f` 个可学习的 **foresight query tokens** `{q_f^1, ..., q_f^{K_f}}` 和 `K_a` 个空 **action tokens** `{q_a^1, ..., q_a^{K_a}}`，与任务指令 `l`、当前观测 `o_t` 拼接后输入 VLM `F_θ`。
- 并行推理过程：`(M_f, A_f) = F_θ(o_t, l)`，得到 foresight motion tokens `M_f` 与 action latent tokens `A_f`。

**（3）Hindsight-Modulated Joint Expert**

- **关键设计**：hindsight 运动 token 不直接注入 VLM 输入（避免破坏视觉-语言预训练对齐），而是通过 **AdaLN（Adaptive Layer Normalization）** 作为条件调制联合专家的推理过程。
- 三种序列表示：hindsight motion tokens `M_h`（仅作条件输入）、foresight motion latent tokens `M_f`、action tokens `A_f`。
- foresight 与 action 形成两条并行流，通过 **cross-stream joint attention** 交互，同时保留独立 FFN 以确保互补且解耦的表示。
- hindsight tokens 经线性投影得到条件向量 `h_c`，注入每个联合专家模块：

```
AdaLN(z; h_c) = γ(h_c) · (z - μ(z)) / σ(z) + β(h_c)
```

其中 `z ∈ {M_f, A_f}`，`γ(h_c)` 和 `β(h_c)` 为调制参数。

- 联合注意力对 `M_f` 与 `A_f` 拼接后的序列进行**非因果自注意力**，Q、K、V 联合投影。
- 最终融合表示经各自 head 投影，生成未来运动 `m̃_{t:t+n}` 与动作 `ã_{t:t+n}`。

**（4）训练目标**

- 两个 L1 损失：

```
L_MV = (1/n) Σ_{j=1}^{n} |m_{t+j} - m̃_{t+j}|
L_A  = (1/n) Σ_{j=1}^{n} |a_{t+j} - ã_{t+j}|
```

- 总损失：`L_all = L_A + λ · L_MV`，其中 `λ = 0.01`。

**（5）输入表示**

- 沿用 OpenVLA-OFT：当前观测分别经 DINOv2 与 SigLIP 编码，得到混合视觉嵌入。
- 历史运动序列经时空卷积压缩、ViT 编码器聚合、投影到联合专家潜在空间。

**（6）推理过程**

- 形式化：`(ã_{t:t+n}, m̃_{t:t+n}) ~ P'_θ(a_{t:t+n}, m_{t:t+n} | o_t, l, m^his_{t-h:t})`
- 推理时运动解码为可选步骤，可根据下游任务需求省略。

## 三、实验设计

### 3.1 数据集与 Benchmark

| 基准 | 描述 |
|------|------|
| **LIBERO-Long** | 10 个多子目标操作任务，跨多样场景，评估长程任务成功率 |
| **CALVIN ABC-D** | 4 个室内环境（A-D），在 A-C 上训练，在未见过的 D 上评估连续任务泛化能力 |
| **真实世界** | AgileX Piper 机器人，RealSense D435 场景相机 + USB 腕部相机，3 个长程任务，每个 100 条演示 |

### 3.2 对比方法

- **LIBERO-Long**：OpenVLA、UniVLA、MemoryVLA、OpenVLA-OFT、Seer（scratch）、Seer
- **CALVIN ABC-D**：SuSIE、OpenVLA、CLOVER、VPP、π0、UniVLA、GR-1、Vidman、UP-VLA、OpenVLA-OFT、RoboVLMs、Seer
- **效率对比**：Baseline、+Subgoal、+Foresight (Ours)、+History frames、+Hindsight (Ours)、+Hindsight+Foresight (Ours)
- **真实世界**：OpenVLA-OFT vs HiF-VLA

### 3.3 评估设置

- 第三视角（primary camera）与多视角（primary + wrist camera）两种输入设置。
- 每个任务 500 次试验（LIBERO-Long）；真实世界每个任务 20 次试验。

## 四、资源与算力

- **GPU**：8 张 NVIDIA A100 GPU。
- **全局 batch size**：64。
- **训练步数**：LIBERO 150k steps，CALVIN 80k steps。
- **VLM 骨干**：Prismatic-7B，使用 OpenVLA 权重初始化（在 OXE 上预训练），其他模块随机初始化。
- **时间 chunk**：动作与 foresight 建模均为 `n = 8`；hindsight 窗口可变（默认 8）。
- **损失权重**：`λ = 0.01`。

> 论文未明确报告总训练时长（小时/天），也未提供具体能耗或成本估算。

## 五、实验数量与充分性

### 5.1 实验组数概览

| 实验类型 | 内容 |
|----------|------|
| 主实验 | LIBERO-Long（第三视角 + 多视角，共 2 组）+ CALVIN ABC-D（2 组） |
| 效率与冗余分析 | 6 种变体对比（Peak GPU Memory、Latency、Avg. SR） |
| 推理可扩展性 | 历史长度 4/8/16/32 下的延迟对比（2 条 baseline） |
| Hindsight 长度消融 | 第三视角 + 多视角，长度 4/8/16/32 |
| Hindsight 嵌入位置消融 | VLM 注入 vs Expert 条件调制（2 组） |
| 真实世界实验 | 3 个长程任务，每任务 100 演示、20 次试验 |

### 5.2 充分性与公平性评估

- **充分性**：覆盖模拟与真实、单视角与多视角、主实验与消融、效率与可扩展性，维度较全面。消融实验直接针对核心设计选择（hindsight 长度、嵌入位置），有说服力。
- **公平性**：
  - 主 baseline（OpenVLA-OFT）与 HiF-VLA 共享相同的预训练初始化。
  - 效率对比中，history 与 hindsight 长度均固定为 4，batch size 固定为 4，条件对齐。
  - 部分 baseline 结果标注为“*”表示使用官方开源代码复现，增强了可比性。
- **潜在不足**：CALVIN 和 LIBERO 均为仿真基准，真实世界实验仅 3 个任务，规模有限；未报告多次随机种子的方差或置信区间。

## 六、主要结论与发现

1. **LIBERO-Long**：
   - 第三视角：HiF-VLA 达到 **94.4%** 平均成功率，比 OpenVLA-OFT 基线提升 **3.4%**。
   - 多视角：达到 **96.4%**，持续优于所有对比方法。
   - 第三视角变体性能与多视角 baseline 相当，展现强时间推理能力。

2. **CALVIN ABC-D**：
   - 平均任务完成长度 **4.35**（第三视角 4.08），优于 OpenVLA-OFT（4.10）、Seer（4.28）、VPP（4.33）等。

3. **效率与冗余**：
   - Foresight head 仅增加 **0.13×** 延迟和 **0.03×** GPU 显存。
   - 密集多帧输入（History frames）延迟为 baseline 的 **3.15×**，且性能反而下降（90.4% vs 91.0%）。
   - HiF-VLA 统一整合 hindsight + foresight 后达到 **93.2%** 成功率。

4. **推理可扩展性**：
   - 多帧 baseline 延迟随历史长度近似线性增长；历史长度 8 时延迟为 vanilla VLA 的 **4.5×** 以上。
   - HiF-VLA 延迟随历史增长仅边际增加，展现优越的时间可扩展性。
   - 论文图 1 指出推理延迟降低 **58.3%** 和 **29.3%**。

5. **消融发现**：
   - Hindsight 长度最优值为 **8**（第三视角 94.4%，多视角 96.4%）。
   - Expert 条件调制优于 VLM 直接注入，说明运动信息可能干扰视觉-语言预训练对齐。

6. **真实世界**：
   - OpenVLA-OFT 在 Press-Buttons-Order 任务上仅 **17.4%** 成功率，HiF-VLA 显著提升。
   - HiF-VLA 能可靠检测细微状态变化（如按钮按下与未按下），展现广泛实际有效性。

## 七、优点

- **表示创新**：首次将视频编码中的运动向量（MVs）系统性地引入 VLA 作为时间上下文表示，兼顾紧凑性、表达力与计算效率。
- **双向时间推理**：统一 hindsight、insight、foresight 三个维度，形成运动中心的世界行动模型（World Action Model），结构清晰。
- **条件调制设计**：通过 AdaLN 将 hindsight 作为专家模块的条件输入而非 VLM 输入，避免破坏预训练视觉-语言对齐，消融实验验证其有效性。
- **并行推理**：foresight 与 action 双流并行、交叉注意力交互，实现“边思考边行动”。
- **效率优势显著**：相比帧堆叠方案，延迟与显存开销大幅降低，且性能不降反升。
- **实验覆盖较全面**：模拟 + 真实、单/多视角、主实验 + 多组消融 + 效率 + 可扩展性，论证链条完整。
- **公平对比**：与 baseline 共享预训练权重，效率对比条件对齐，部分 baseline 复现验证。

## 八、不足与局限

- **运动表示依赖估计精度**：MVs 依赖视频编码/光流估计的准确性，在高动态场景或噪声环境下可能敏感，论文作者也在结论中承认此局限。
- **未探索大规模预训练**：论文未利用互联网视频进行大规模预训练以增强运动理解与生成能力，作者将其列为未来工作。

八、不足与局限（续）

- **真实世界实验规模有限**：仅在 3 个长程任务上验证，每个任务 100 条演示、20 次试验，任务多样性与统计显著性仍有提升空间。
- **缺乏多次随机种子的方差报告**：论文未提供置信区间或标准差，难以全面评估性能稳定性与鲁棒性。
- **对视频编码标准的依赖**：MVs 提取基于 MPEG-4/H.264，在低光照、快速运动或严重遮挡场景下可能产生噪声，影响 hindsight 先验质量。
- **计算资源门槛较高**：8×A100 GPU 的训练配置可能限制学术机构复现与进一步扩展。
- **运动与动作预测的误差传播**：尽管采用并行双流设计，运动预测误差仍可能通过交叉注意力影响动作生成，其鲁棒性需进一步分析。
- **骨干网络依赖性**：方法依赖 Prismatic-7B 与 OpenVLA 权重初始化，迁移到其他 VLM 骨干时的泛化能力尚未验证。

九、总体评价

HiF-VLA 提出了一种以**运动向量**为中心的时间推理框架，巧妙地将视频编码中的运动信息引入 VLA，作为连接过去（hindsight）与未来（foresight）的桥梁。其核心贡献可概括为：

1. **表示创新**：用紧凑的 MVs 替代原始帧堆叠，显著降低计算冗余，同时保留交互动态，为 VLA 的时间建模提供了新范式。
2. **架构设计**：通过 AdaLN 条件调制将 hindsight 注入联合专家，避免破坏 VLM 预训练对齐，实现双向时间推理与“边思考边行动”。
3. **实验验证**：在 LIBERO-Long 与 CALVIN ABC-D 上达到 SOTA，真实世界任务中显著优于 OpenVLA-OFT，且效率优势明显。
4. **可扩展性**：推理延迟随历史长度增长缓慢，适合长程任务，为实际机器人部署提供了可行性。

总体而言，HiF-VLA 在时间表示、模型架构与实验验证上均有扎实贡献，为 VLA 的长期时间建模开辟了以运动为中心的新方向。未来可探索更丰富的运动表示、大规模互联网视频预训练以及多模态融合，进一步提升泛化能力与场景适应性。

（完）
