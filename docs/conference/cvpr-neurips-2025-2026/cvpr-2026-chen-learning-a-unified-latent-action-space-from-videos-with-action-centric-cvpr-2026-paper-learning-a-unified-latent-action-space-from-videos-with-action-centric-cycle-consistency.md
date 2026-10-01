---
title: Learning a Unified Latent Action Space from Videos with Action-centric Cycle Consistency
title_zh: 基于动作中心循环一致性从视频学习统一的潜在动作空间
authors: "Chen, Guangyan, Shao, Qi, Cui, Te, Zhou, Zichen, Mao, Weixin, Yang, Luojie, Wang, Meiling, Yang, Yi, Chen, Hua, Yue, Yufeng"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Chen_Learning_a_Unified_Latent_Action_Space_from_Videos_with_Action-centric_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 从视频学习跨具身共享的统一潜在动作空间
tldr: 视频数据可缓解动作标注稀缺问题，但现有潜在动作分词器因相邻帧的唯一配对而缺乏对转移动态的深入理解，且为不同具身分配独立潜在动作子集，难以泛化。本文提出动作中心循环一致性方法，从视频中学习统一的潜在动作空间，使潜在动作语义一致并可跨具身共享。实验表明该方法提升了策略训练的效果与跨具身迁移能力。该工作为利用海量视频进行机器人策略学习提供了统一表示基础。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-chen-learning-a-unified-latent-action-space-from-videos-with-action-centric-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 1965, \"height\": 561}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-chen-learning-a-unified-latent-action-space-from-videos-with-action-centric-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 1902, \"height\": 775}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-chen-learning-a-unified-latent-action-space-from-videos-with-action-centric-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 7, \"index\": 3, \"width\": 914, \"height\": 397}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-chen-learning-a-unified-latent-action-space-from-videos-with-action-centric-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 522, \"height\": 476}]"
motivation: 视频潜在动作学习因相邻帧唯一配对而难以捕获真实转移动态，且跨具身难以共享。
method: 提出动作中心循环一致性，从视频学习统一潜在动作空间，使潜在动作跨具身共享。
result: 学习到语义一致且可跨具身复用的潜在动作，提升策略训练效果。
conclusion: 为利用视频数据进行跨具身机器人策略学习提供了统一表示。
---

## Abstract
Video data provides a rich source beyond expensive action-labeled data for advancing robot learning. Recent approaches have demonstrated promising potential in leveraging video data by learning latent actions for policy training. The latent action tokenizer encodes latent actions between successive video frames, and the tokenizer is trained to reconstruct future frames using current frames and the encoded latent actions. However, the unique pairing of successive frames permits future frame reconstruction with little understanding of transition dynamics, hindering the learning of semantically consistent latent actions. Moreover, the tokenizer typically allocates distinct latent action subsets to individual embodiments to accommodate heterogeneous morphologies, constraining knowledge transfer. To overcome such limitations, we propose the action-centric cycle consistency, aiming to establish a unified latent action space. Our method samples latent actions from the latent action space and decodes them with video frames to generate diverse subsequent frames, then enforces cycle consistency by predicting the sampled actions from both original and generated frames. Our concise method creates a challenging task that learns corresponding latent actions from current frames and diverse generated future frames, compelling the tokenizer to develop semantically consistent action representations. Additionally, sampled latent actions can be applied to video frames from distinct embodiments, facilitating the alignment of latent actions across embodiments. Experiments demonstrate that our approach achieves a 20.1% improvement over OpenVLA on the LIBERO benchmark and increases the average length from 3.27 to 3.93 on the CALVIN benchmark. In real-world experiments, our method maintains strong performance with a 44% improvement.

---

## 论文详细总结（自动生成）

# 论文总结：Learning a Unified Latent Action Space from Videos with Action-centric Cycle Consistency

## 1. 核心问题与整体含义

- **研究背景**：机器人模仿学习依赖昂贵的动作标注数据，而互联网视频提供了海量、廉价的行为与物理动态信息。近期工作（Genie、LAPA、Moto、UniVLA 等）尝试从视频中学习**潜在动作（latent action）**，用于策略预训练，从而减少对动作标签的依赖。
- **核心问题**：
  - **语义一致性不足**：现有潜在动作分词器（tokenizer）以“相邻帧唯一配对”的方式训练——用当前帧和编码出的潜在动作重建下一帧。由于未来帧是唯一确定的，模型可以在几乎不理解真实转移动态的情况下完成重建，导致学到的潜在动作语义一致性差。作者通过 pilot study 展示，将参考视频帧编码的潜在动作应用到当前帧时，Genie 生成的帧运动与参考视频明显发散。
  - **跨具身不统一**：为适配异构机器人形态，分词器通常为不同具身分配潜在动作空间的不同子集，造成表示空间碎片化，限制知识迁移。
- **整体含义**：论文提出 **CycleMimic** 框架，通过**动作中心循环一致性（Action-Centric Cycle Consistency, AC3）** 建立统一潜在动作空间，使潜在动作既语义一致又可跨具身共享，为仅利用视频数据进行 VLA 预训练提供统一表示基础。

## 2. 方法论

### 2.1 核心思想
- 不再依赖“当前帧→固定未来帧”的唯一配对，而是**从潜在动作空间中采样潜在动作**，与视频帧解码生成多样化的后续帧；再强制循环一致性：从原始帧和生成帧中预测出被采样的潜在动作。
- 该任务更难，迫使分词器学习语义一致的潜在动作表示。
- 跨具身时，将具身 $E_i$ 采样得到的潜在动作应用到具身 $E_j$ 的视频帧上，再要求预测回原动作，从而对齐不同具身的潜在动作空间。

### 2.2 潜在动作分词（Latent Action Tokenization）
- **编码器 E**：用 DINOv2 提取当前帧 $o_t$ 和未来帧 $o_{t+H}$ 的图像嵌入，拼接可学习潜在动作 token，经时空 Transformer（交错空间/时间自注意力）聚合转移动态，输出潜在动作 token $z^q_t \in \mathbb{R}^{l_z \times c_z}$。
- **量化**：采用 VQ-VAE 目标，将 $z^e_t$ 量化为从大小为 $K$ 的码本中选择的 $l_z$ 个离散 token。
- **解码器 D**：空间 Transformer，以当前帧 $o_t$ 和量化动作 $z^q_t$ 重建未来帧 $\hat{o}_{t+H}$。
- 公式：$z^q_t = E(o_t, o_{t+H})$，$\hat{o}_{t+H} = D(o_t, z^q_t)$。

### 2.3 动作中心循环一致性（AC3）
- 从**潜在动作缓冲区 Z** 中均匀采样潜在动作 $z^q_s$，与数据集视频帧 $o_c$ 解码生成后续帧 $\hat{o}_g = D(o_c, z^q_s)$。
- 将原始帧 $o_c$ 与生成帧 $\hat{o}_g$ 同时送入编码器，要求恢复出原采样动作：$\hat{z}^q_s = E(o_c, \hat{o}_g)$。
- 为支持梯度传播，使用量化前的嵌入 $\hat{z}^e_s$ 与码本向量 $e_k$ 的距离作为相似度，以采样动作的码本索引为监督信号，采用交叉熵损失：
  $$L_C = -\sum_{k=1}^{K} y_k \log \frac{\exp(-d(\hat{z}^e_s, e_k)/\tau)}{\sum_{j=1}^{K}\exp(-d(\hat{z}^e_s, e_j)/\tau)}$$
  其中 $y_k$ 为 one-hot 目标，$\tau$ 为温度，$d$ 为 L2 距离。
- **跨具身扩展**：从 $E_i$ 采样动作、应用到 $E_j$ 帧，循环一致性强制 $\hat{z}^q_s \approx z^q_s$，实现跨具身统一。

### 2.4 局部-全局判别器（Local-Global Discriminator）
- **目的**：解决解码器生成帧与数据集帧的分布不匹配，并防止解码器通过生成帧把潜在动作信息“泄漏”给编码器（造成表面循环一致但实质错误）。
- **结构**：输入图像帧，经空间 Transformer 提取 patch 特征，再分别通过 MLP 得到局部 patch logits，以及经卷积+全局池化得到全局 logits。
- **损失**：对局部和全局均施加对抗损失，判别器最大化区分数据集帧与生成帧，解码器则最大化让生成帧被判别为数据集分布：
  $$L^{GAN}_{\Psi} = -\log(\Psi(o)) - (1-\log(\Psi(D(o,z)))), \quad L^{GAN}_{D} = 1-\log(\Psi(D(o,z)))$$

### 2.5 潜在动作缓冲区（Latent Action Buffer）
- 潜在动作空间在优化中动态变化，无法预设采样空间；若仅从当前 batch 采样，分词器可能压缩空间以降低循环一致性难度。
- 方案：累积**前 B 个 batch** 编码的潜在动作构成缓冲区 Z，近似潜在动作空间并防止坍缩。

### 2.6 策略预训练与动作微调
- **预训练**：以 Prismatic-7B VLM 为基础（SigLip + DINOv2 融合视觉编码器 + LLaMA-2），扩充词表加入 $K$ 个潜在动作 token $\{LACT_1,\dots,LACT_K\}$。策略 $\pi_\phi$ 以观测 $o_t$、语言指令 $\ell$、潜在动作前缀 $z^q_{<i}$ 为条件，最小化下一潜在动作负对数似然：
  $$L_\pi = \mathbb{E}\left[-\sum_{i=1}^{N}\log \pi_\phi(\hat{z}^q_i = z^q_i \mid o_t, \ell, z^q_{<i})\right], \quad N=4$$
- **微调**：在预训练策略上追加动作查询 token ACT 和动作解码器，通过注意力聚合 VLM 最后一层视觉/动作嵌入，经 MLP 映射为连续动作（delta 末端执行器运动）。动作解码器全参数训练，VLM 使用 LoRA 微调，联合优化潜在动作预测损失与 L1 动作回归损失。

## 3. 实验设计

### 3.1 数据集与 Benchmark
- **LIBERO**：130 个语言条件操作任务，四个 suite（Spatial、Object、Goal、Long）。预训练配置分两种：仅用 Bridge 数据集、或用全量数据集。
- **CALVIN**：语言条件长时序操作，34 个任务、4 个环境；采用 ABC→D 未见场景泛化设置。
- **SimplerEnv**：WidowX + Bridge 设置，4 个任务（放勺子、放胡萝卜、堆绿黄方块、放茄子），每任务 24 次试验，评估抓取与任务成功率。
- **真实世界**：Franka Emika 机械臂 + OpenTeach 遥操作，ORBBEC Femto Bolt 静态相机；每任务 30 条动作标注轨迹，9 个任务（开抽屉、堆方块、开烤箱、放水果、按按钮、扫桌、插盒、推盒、折布），10 次随机位姿评估。

### 3.2 对比方法
- LIBERO：LAPA、Octo、MDT、OpenVLA、UniVLA、Ours w/ Genie（同架构同训练策略但用 Genie 学潜在动作）。
- CALVIN：Moto、GR-1、Dita、CLOVER、OpenVLA、UniVLA、Ours w/ Genie。
- 真实世界：OpenVLA、UniVLA、Ours w/ Genie。
- SimplerEnv：与 Genie 基线对比。

### 3.3 消融实验
- 潜在动作缓冲区 batch 累积数量（1、4、16）。
- 判别器架构（无判别器、局部判别器、局部-全局判别器）。
- 判别器深度（8、12、16 层）。
- 动作解码方式（离散动作、潜在动作解码、动作 token 解码）。

## 4. 资源与算力

- **论文正文未明确提及** GPU 型号、数量、训练时长、总计算量等具体算力信息。
- 仅能从方法描述中推测：基础模型为 Prismatic-7B VLM，训练涉及 DINOv2、SigLip、LLaMA-2，且包含判别器与分词器训练，但无具体硬件配置与耗时披露。
- 因此无法评估其训练成本与可复现性所需算力门槛。

## 5. 实验数量与充分性

- **实验数量**：
  - 三大仿真 benchmark（LIBERO 4 个 suite、CALVIN ABC→D、SimplerEnv 4 任务）。
  - 一组真实世界实验（9 个任务，每任务 30 条轨迹）。
  - 四组消融实验，每组含 3–4 种配置，共约 14 个消融变体。
- **充分性**：覆盖仿真与真实、短程与长程、单具身与跨具身，且包含对关键设计（缓冲区、判别器、解码方式）的逐项消融，整体较为充分。
- **客观性与公平性**：
  - 与 **Ours w/ Genie** 采用相同网络架构和训练策略，仅替换潜在动作学习方式，对比公平，能直接验证 AC3 的增益。
  - 与 OpenVLA、UniVLA、Octo 等对比时，这些基线预训练数据规模远大于本文 Bridge-only 设置，本文仍取得更优结果，说明方法有效性；但预训练数据、模型规模、训练细节不完全一致，严格意义上并非完全受控对比。
  - 真实世界实验每任务仅 30 条轨迹、10 次评估，统计波动可能较大，成功标准由人工评估，存在主观性风险。

## 6. 主要结论与发现

- AC3 能有效学习**语义一致**的潜在动作，并建立**跨具身统一**的潜在动作空间。
- **LIBERO**：全量预训练平均成功率 **96.6%**，仅 Bridge 预训练达 **95.4%**；相比 OpenVLA 提升 **20.1%**，且优于 UniVLA、Octo、MDT、LAPA 等。
- **CALVIN**：平均连续完成任务数从 OpenVLA 的 **3.27** 提升至 **3.93**，优于 UniVLA（3.80）、Dita（3.61）、CLOVER（3.53）、Moto（3.10）。
- **SimplerEnv**：抓取与任务成功率均显著优于 Genie 基线。
- **真实世界**：平均成功率 **0.88**，相比 OpenVLA 的 0.44 有 **44 个百分点**的提升；优于 UniVLA（0.77）和 Ours w/ Genie（0.68）。
- **消融结论**：
  - 缓冲区累积 4 个 batch 最佳；过少导致潜在空间坍缩，过多引入陈旧动作造成空间污染。
  - 局部-全局判别器优于无判别器或仅局部判别器，能同时缓解信息泄漏与分布错配。
  - 判别器深度 12 层（与编码器匹配）最佳；过浅容量不足，过深计算成本高。
  - 动作 token 解码优于离散动作解码和直接潜在动作解码，避免潜在动作 token 同时承担回归与预测双重约束。

## 7. 优点

- **方法简洁而有效**：核心仅是在“采样动作→解码生成→再编码预测”的循环中施加一致性约束，却显著提升潜在动作的语义一致性和跨具身可迁移性。
- **针对性强**：准确指出“唯一配对导致重建任务过于简单”这一根本缺陷，并用采样+循环一致性构造更难的自监督任务。
- **工程细节完备**：
  - 局部-全局判别器同时解决分布错配与信息泄漏两个隐患。
  - 潜在动作缓冲区防止空间坍缩与污染，设计朴素但有效。
- **跨具身统一**：通过跨具身采样与循环一致性直接对齐不同具身的潜在动作，而非简单共享码本。
- **实验覆盖广**：仿真（LIBERO、CALVIN、SimplerEnv）+ 真实世界，且包含同架构 Genie 对照，验证充分。
- **性能提升显著**：在仅用 Bridge 数据的情况下超过大规模预训练基线，真实世界提升尤为突出。

## 8. 不足与局限

- **算力信息缺失**：未报告 GPU 型号、数量、训练时长，难以评估训练成本与可复现性。
- **真实世界评估规模有限**：每任务仅 30 条轨迹、10 次随机评估，样本量小，成功标准人工判定，统计置信度与客观性有限。
- **超参数敏感性**：缓冲区 batch 数、判别器深度等对性能影响明显（如 batch=1 或 16 均下降），需要调参，泛化到新场景的鲁棒性未充分验证。
- **跨具身验证范围有限**：论文提及跨具身学习，但实验主要在固定机器人（LIBERO/CALVIN/Franka）上评估，未展示大量异构具身之间的直接迁移效果。
- **判别器额外开销**：引入局部-全局判别器增加训练复杂度与计算量，论文未量化其开销。
- **基线对比不完全受控**：与 OpenVLA、UniVLA 等的数据规模、模型规模、训练流程不同，性能差异不能完全归因于潜在动作学习方式；虽然 Bridge-only 结果有说服力，但仍需谨慎解读。
- **依赖预训练视觉特征**：编码器基于 DINOv2，策略基于 Prismatic-7B，方法效果可能受这些基础模型能力影响，未做消融。
- **潜在动作空间
