---
title: "OTTER: A Vision-Language-Action Model with Text-Aware Visual Feature Extraction"
title_zh: OTTER：一种具有文本感知视觉特征提取的视觉-语言-动作模型
authors: "Huang Huang, Fangchen Liu, Letian Fu, Tingfan Wu, Mustafa Mukadam, Jitendra Malik, Ken Goldberg, Pieter Abbeel"
date: 2025-05-01
pdf: "https://raw.githubusercontent.com/mlresearch/v267/main/assets/huang25u/huang25u.pdf"
tags: ["query:x-embodiment"]
score: 8.0
evidence: 视觉语言动作模型根据视觉观察和语言指令预测机器人动作
tldr: 现有视觉语言动作模型在微调视觉语言模型时往往破坏预训练语义对齐，且独立输入视觉与语言特征会削弱指令跟随能力。OTTER提出文本感知的视觉特征提取架构，仅选择与语言指令语义对齐的任务相关视觉特征送入策略Transformer，并保持预训练编码器冻结。该设计在机器人操作任务上提升了动作预测的准确性与泛化性，为构建高效VLA模型提供了新思路。
source: ICML-2025-Accepted
selection_source: topic_research
id: openreview-icml-2025-uhf0km7r5m
canonical_id: "work:c5b19d70c465ea28a8edc43e"
publication_date: 2025-10-06
publication_date_precision: day
publication_date_source: "https://raw.githubusercontent.com/mlresearch/v267/gh-pages/_config.yml"
publication_date_kind: proceedings
official_pdf_url: "https://raw.githubusercontent.com/mlresearch/v267/main/assets/huang25u/huang25u.pdf"
official_link: "https://proceedings.mlr.press/v267/huang25u.html"
conference_acceptance_status: accepted
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 2752, \"height\": 2134}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 1982, \"height\": 1632}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 1684, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-004.webp\", \"caption\": \"\", \"page\": 5, \"index\": 4, \"width\": 3192, \"height\": 1182}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-005.webp\", \"caption\": \"\", \"page\": 14, \"index\": 5, \"width\": 3432, \"height\": 1996}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-006.webp\", \"caption\": \"\", \"page\": 15, \"index\": 6, \"width\": 4088, \"height\": 1130}]"
motivation: 现有VLA模型微调视觉语言模型会破坏预训练语义对齐，且视觉与语言特征独立输入策略导致指令跟随能力下降。
method: 提出文本感知视觉特征提取架构，选择性抽取与语言指令语义对齐的任务相关视觉特征，并冻结预训练视觉语言编码器。
result: 在机器人操作任务中提升动作预测准确性，同时保持预训练视觉语言语义对齐。
conclusion: 表明显式利用预训练视觉语言对齐可构建更高效的视觉语言动作模型。
---

## 摘要
视觉-语言-动作（VLA）模型旨在基于视觉观察和语言指令预测机器人动作。现有方法需要对预训练的视觉-语言模型（VLM）进行微调，因为视觉和语言特征被独立地输入下游策略，从而降低了预训练的语义对齐。我们提出 OTTER，一种新颖的 VLA 架构，通过显式的文本感知视觉特征提取来利用这些已有对齐。OTTER 不处理所有视觉特征，而是选择性地提取并仅将与语言指令语义对齐的任务相关视觉特征传递给策略 Transformer。这使 OTTER 能够保持预训练的视觉-语言编码器冻结。因此，OTTER 保留并利用了从大规模预训练中学到的丰富语义理解，从而实现强大的零样本泛化能力。在仿真和真实世界实验中，OTTER 显著优于现有 VLA 模型，展示出对新颖物体和环境的强大零样本泛化能力。视频、代码、检查点和数据集：https://ottervla.github.io/。

## Abstract
Vision-Language-Action (VLA) models aim to predict robotic actions based on visual observations and language instructions. Existing approaches require fine-tuning pre-trained vision-language models (VLMs) as visual and language features are independently fed into downstream policies, degrading the pre-trained semantic alignments. We propose OTTER, a novel VLA architecture that leverages these existing alignments through explicit, text-aware visual feature extraction. Instead of processing all visual features, OTTER selectively extracts and passes only task-relevant visual features that are semantically aligned with the language instruction to the policy transformer. This allows OTTER to keep the pre-trained vision-language encoders frozen. Thereby, OTTER preserves and utilizes the rich semantic understanding learned from large-scale pre-training, enabling strong zero-shot generalization capabilities. In simulation and real-world experiments, OTTER significantly outperforms existing VLA models, demonstrating strong zero-shot generalization to novel objects and environments. Video, code, checkpoints, and dataset: https://ottervla.github.io/.

---

## 论文详细总结（自动生成）

# OTTER 论文结构化总结

## 一、核心问题与研究动机

- **背景**：视觉-语言-动作（VLA）模型以多视角图像、语言指令和机器人本体状态为输入，输出动作。主流做法（Octo、OpenVLA、RT-2 等）将视觉与语言特征**分别独立编码**后送入策略 Transformer，并往往需要在机器人数据上**微调预训练 VLM**。
- **核心问题**：
  - 机器人数据集的语义多样性远低于大规模图文数据（如 LAION、WIT-400M），在此类数据上微调 CLIP 等视觉编码器容易**过拟合**，破坏预训练阶段学到的视觉-语言语义对齐，导致对未见物体/环境的泛化性能明显下降。
  - 视觉与语言特征独立输入策略网络，迫使策略自行学习跨模态关联与精确控制，在小规模机器人数据上尤其困难。
- **研究动机**：CLIP/SigLIP 本身已具备强视觉-语言对齐与零样本能力（如开放词汇分割）。因此论文提出：**与其通过微调削弱这种对齐，不如显式提取并利用它**。
- **整体含义**：OTTER 通过“文本感知的视觉特征提取”将任务规划（选出与指令相关的视觉区域）与动作规划（策略网络预测动作）解耦，并**全程冻结预训练视觉-语言编码器**，从而保留大规模预训练带来的语义理解与零样本泛化能力。

## 二、方法论

### 核心思想
- 不把所有视觉 token 送入策略，而是先用语言指令作为查询，从冻结 CLIP 的视觉特征中**检索/加权组合出与每个文本 token 语义对齐的视觉 patch 特征**，再与文本特征、本体感受特征拼接，输入轻量因果 Transformer 预测动作。
- 整个 CLIP **完全冻结**，唯一可学习的是温度参数 τ；跨模态融合以**无参数**的余弦相似度 + softmax 完成。

### 关键技术细节
- **视觉特征来源**：受 ClearCLIP 启发，取 CLIP ViT 最后一层自注意力的输出 `X_attn`（而非含残差与 FFN 的 `X_out`），因其语义更干净、与文本对齐更好（附录 C 给出注意力可视化与线性化推导）。
- **特征归一化**：
  - 文本：`f̂_l = LN_final(f_l)·w_l`，再做 L2 归一化；
  - 视觉：`f̂_v = LN_post(X_attn)·w_v`，再做 L2 归一化；
  - `w_l, w_v` 为 CLIP 原有的模态投影矩阵。
- **温度加权注意力（核心公式）**：
  `f_vl = softmax(f̂_l · f̂_vᵀ / τ) · (f̂_v + PE)`
  - softmax 沿 patch 维度进行，得到每个文本 token 在所有空间位置上的语义相似度分布；
  - 输出 `f_vl ∈ R^{m×d}` 为 m 个文本感知视觉 token，每行是视觉 patch 的加权组合；
  - `PE` 为二维 sin-cos 位置编码，向策略提供空间位置信息；
  - τ 可学习并裁剪在 (0, 100]，小 τ 使选择更尖锐、大 τ 更平滑；**CLIP 其余部分全部冻结**。

### 模型架构与流程
1. **特征压缩**：对每个相机的 `f_vl` 用可学习 cross-attention pooling（4 个 query、8 头、2 个注意力块）压缩为单 token `f'_vl`；对文本特征 `f_l` 另做一次 pooling 得到 `f'_l`。
2. **本体感受编码**：10 维本体状态（末端平移 xyz、6DoF 旋转向量、夹爪开合）经 FFN 得到 `f_e`。
3. **策略输入**：将 `f'_l`、`f'_vl`、`f_e` 沿通道拼接为单 token `f_t`。
4. **策略网络与动作头**：4 层、8 头、512 维因果 Transformer，上下文长度 T=12；每个时间步经 FFN 预测未来 12 步动作。
5. **动作参数化**：预测相对当前末端位姿的 delta 变换（平移 + 6DoF 旋转向量）加绝对夹爪位置，共 10 维；执行时采用时间集成（temporal ensembling）与滚动时域控制，动作 horizon 取 8。
6. **效率**：推理时缓存 CLIP 特征，ViT-L/14 版本可在单张 3090Ti 上以 50Hz 运行，支持实时控制。

## 三、实验设计

### 仿真环境
- **Benchmark**：LIBERO，使用 LIBERO-Spatial、LIBERO-Object、LIBERO-Goal（共 30 个分布内任务）及 LIBERO-90。
- **未见任务**：基于 LIBERO-90 的 10 个原始任务，通过修改语言指令与目标物体类型/颜色构造 10 个新任务（遵循 LIBERO 的 bddl 与初始化约定）。
- 每个任务 50 条演示、50 次试验。

### 真实机器人环境
- **平台**：Franka 机械臂，人类遥操作采集。
- **数据集**：
  - DS-PnP：10 个 pick-and-place 任务，每任务 50–80 条演示，共 **724 条**；
  - DS-ALL：覆盖 pick-and-place、poking、pouring、开关抽屉四类原语，共 **1,185 条**演示。
- **评测设置**：19 个分布内训练任务 + 15 个分布外未见任务；每任务 10 次试验，随机化目标位置并加入 2–3 个干扰物；pick-and-place 采用 0/0.5/1 分级评分，其余原语二值评分；除 OpenVLA（60 秒）外每 trial 限时 30 秒。

### 对比方法
- **Octo**：从头在 OXE 上训练的 Transformer 策略（使用 octo-small-1.5 checkpoint 并微调）。
- **OpenVLA**：微调 Prismatic-7B VLM，并加入 16 步 action chunking。
- **π0-Fast-Droid**：PaliGemma + FAST 动作分词器，在 Droid 上微调；另设 Finetuned π0-Fast-Droid（在 DS-ALL 上微调）。
- **DFP-OTTER**：直接特征传递变体（文本、视觉分别 pooling 后拼接），用于隔离“文本感知提取”的贡献。
- **OTTER 系列**：OTTER（从头训练）、OTTER-OXE（OXE 预训练后微调）、OTTER-L / OTTER-OXE-L（更大更宽版本）。
- **消融**：w.o. `f_e`、w.o. `f'_l`、w.o. CLIP vision（小 ViT 从头训练）、Finetune CLIP、DFP-OTTER (CLS)、OTTER (xattn)（用标准 cross-attention 替代文本感知提取）。
- **规模缩放**：ViT-B/32 → ViT-B/16 → ViT-L/14。

## 四、资源与算力

- **训练**：所有模型在 **4 张 NVIDIA A100 80GB GPU** 上训练；AdamW、cosine 衰减、warmup 2000 步、学习率 3e-4、batch size 64、总梯度步数 40,000（部分设置 60,000）。
- **推理**：缓存 CLIP 特征后，ViT-L/14 版本可在**单张 NVIDIA 3090Ti 上达到 50Hz**。
- **模型规模**：OTTER 约 11.8M 参数，大版本约 25.5M 参数。
- **未明确说明**：论文未给出具体训练总时长（小时/GPU·天）与能耗信息。

## 五、实验数量与充分性

- **实验组数概览**：
  - 真实单原语（pick-and-place）：100 个分布内 trial + 70 个未见 trial，对比 9 个方法/变体；
  - 真实多原语：4 类原语、150 个未见 trial，对比 7 个方法/变体；
  - 仿真 LIBERO：30 个分布内任务 + 10 个未见任务，各 50 trial，对比 4 个方法；
  - 消融：真实 4 组 + 仿真 3 组 + 附录 2 组（CLS token、标准 cross-attention）；
  - 缩放实验：3 个 CLIP 规模。
- **充分性评价**：
  - **较充分**：覆盖仿真与真实、单/多原语、分布内/分布外、多类消融与规模缩放，且对“冻结 vs 微调”“文本感知 vs 直接传递”做了针对性对照，能较好支撑核心论点。
  - **客观性/公平性存在一定张力**：
    - 仿真中 Octo 与 OpenVLA 的数字直接引自 OpenVLA 论文，虽按相同数据处理流程，但训练细节与调参未必完全对等；DFP-OTTER 从头训练而 Octo/OpenVLA 使用 OXE 预训练，比较不完全对等（作者亦有说明）。
    - 真实实验中每个任务仅 10 次试验，随机性较大，标准差以标准误报告。
    - π0-Fast-Droid 主要直接评测（未在本文数据上微调），仅补充了微调版本，跨设置比较需谨慎。
    - OTTER 受益于 CLIP 大规模预训练，而 Octo 无预训练 VLM，比较反映的是“是否利用预训练对齐”的整体差异，而非单一架构因素。

## 六、主要结论与发现

- **真实单原语**：OTTER 在训练任务 68%、未见任务 62%；OTTER-OXE 达 72%/73%；显著优于 Octo（15%/12%）、OpenVLA（30%/9%）、DFP-OTTER（29%/4%）、Finetune CLIP（26%/15%）。π0-Fast-Droid 在未见 pick-and-place 上达 61%，但在其他原语上失效。
- **真实多原语零样本泛化**：OTTER 平均 67%，OTTER-OXE-L 达 77%；基线最高仅 35%（Finetuned π0-Fast-Droid），Octo/OpenVLA 在多类原语上接近 0%。
- **仿真 LIBERO**：分布内平均 84%（与 OpenVLA 的 84% 相当），未见任务 61%，明显高于 OpenVLA（48%）、DFP-OTTER（45%）、Octo（26%）。
- **消融结论**：
  - 去掉本体感受 `f_e` 性能大幅下降（真实训练 -28%、未见 -33%），说明物理 grounding 关键；
  - 去掉文本 token `f'_l` 下降约 10%，说明其提供互补信息；
  - 用从头训练的 ViT 替代冻结 CLIP，性能下降超过 50%，接近 Octo 水平；
  - 微调 CLIP 会过拟合前景/背景分离、丧失零样本目标定位能力，训练与未见任务差距拉大；
  - DFP-OTTER、DFP-OTTER (CLS)、OTTER (xattn) 均无法泛化到未见任务（2%–6%），证明“文本感知提取 + 冻结编码器”两者缺一不可。
- **可扩展性**：CLIP 从 ViT-B/32 提升到 ViT-L/14，训练任务 +27.5%、未见任务 +39.3%；更大策略网络（OTTER-L）与 OXE 预训练均进一步提升性能，说明性能可沿“编码器规模、策略容量、机器人数据规模”三条轴扩展。

## 七、优点

- **思路简洁且有效**：用无参数的余弦相似度 + softmax 完成跨模态选择，仅学习温度 τ，避免破坏预训练对齐，参数效率高。
- **显式解耦任务规划与动作规划**：语言引导的视觉特征选择把“看哪里”与“怎么动”分离，降低小数据下策略学习跨模态关联的难度。
- **强零样本泛化证据**：在真实多原语未见任务上大幅领先（67–77% vs 基线 ≤35%），并给出训练/未见性能差距小的证据。
- **消融设计针对性强**：分别隔离“冻结 vs 微调”“文本感知 vs 直接传递”“有无 CLIP”“有无本体/文本 token”，结论清晰。
- **可扩展性与实用性**：验证 CLIP 规模、策略容量、机器人数据规模三条扩展轴；缓存特征后 50Hz 实时推理，具备实际部署价值。
- **分析深入**：附录提供注意力可视化与线性化推导，解释为何用 `X_attn` 而非 `X_out`，为设计选择提供机理支撑。

## 八、不足与局限

- **形态与动作空间受限**：仅支持可由 SE(3) 变换参数化的单臂末端控制，难以扩展到多指灵巧手等复杂形态。
- **任务时长与场景复杂度有限**：未系统探索长时程任务与高度复杂场景；真实任务多为短程原语组合。
- **数据规模与试验次数偏小**：真实数据仅千余条演示，每任务 10 次试验，统计功效有限；未见任务的构造方式（换物体/换颜色/换位置）相对受控，与开放世界的分布偏移仍有差距。
- **对 CLIP 对齐质量的依赖**：若目标物体在 CLIP 语义空间中区分度低（如仿真中不真实物体），文本感知特征可能高亮错误或多个物体，需依赖 `f'_l` 补偿；对细粒度、相似物体场景的鲁棒性未充分验证。
- **比较公平性风险**：仿真基线数字引自其他论文；Octo/OpenVLA 与 OTTER 在预训练资源上不对等；π0-Fast-Droid 主要为跨设置直接评测；DFP-OTTER 从头训练，与 OTTER-OXE 的可比性受限。
- **计算开销**：每个相机、每个文本 token 都需计算相似度并做加权组合，文本较长或多相机时开销上升；虽可缓存 CLIP 特征，但缓存策略对动态场景的适用性未讨论。
- **未报告训练时长与能耗**，不利于复现与成本评估。

（完）
