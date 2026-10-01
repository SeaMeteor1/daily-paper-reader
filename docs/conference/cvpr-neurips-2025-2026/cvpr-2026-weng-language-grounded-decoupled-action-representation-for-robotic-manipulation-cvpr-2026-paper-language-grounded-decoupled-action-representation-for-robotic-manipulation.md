---
title: Language-Grounded Decoupled Action Representation for Robotic Manipulation
title_zh: 面向机器人操作的语言接地解耦动作表示
authors: "Weng, Wuding, Wu, Tongshu, Chen, Liucheng, Xie, Siyu, Wang, Zheng, Xu, Xing, Song, Jingkuan, Shen, Heng Tao"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Weng_Language-Grounded_Decoupled_Action_Representation_for_Robotic_Manipulation_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 6.0
evidence: 面向机器人操作的语言接地动作表示
tldr: 该文针对机器人操作中高层视觉语言理解与底层动作控制之间异质性大、难以泛化到新任务的问题，提出语言接地解耦动作表示LaDA框架。方法以自然语言作为语义桥梁，将动作拆解为平移、旋转与夹爪控制三类可解释原子，并引入语义引导软标签增强对齐。实验显示其在新任务与语义相关任务上能生成更稳健准确的动作，为视觉-语言-动作的语义对齐提供了新途径。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 2544, \"height\": 1210}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 3, \"index\": 2, \"width\": 3831, \"height\": 1391}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 6, \"index\": 3, \"width\": 2629, \"height\": 1101}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 997, \"height\": 745}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 2230, \"height\": 935}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 8, \"index\": 6, \"width\": 1590, \"height\": 1504}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-weng-language-grounded-decoupled-action-representation-for-robotic-manipulation-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 8, \"index\": 7, \"width\": 1770, \"height\": 685}]"
motivation: 机器人操作中高层视觉语言理解与底层动作控制存在异质性，难以泛化到新任务。
method: 以自然语言为语义桥梁，将动作解耦为平移、旋转、夹爪三类可解释原子并做语义软标签对齐。
result: 在新型及语义相关任务上生成更稳健准确的动作。
conclusion: 为视觉语言与动作控制的语义对齐提供了可解释的表示方案。
---

## Abstract
The heterogeneity between high-level vision-language understanding and low-level action control remains a fundamental challenge in robotic manipulation. Although recent methods have advanced task-specific action alignment, they often struggle to generate robust and accurate actions for novel or semantically related tasks. To address this, we propose the Language-Grounded Decoupled Action Representation (LaDA) framework, which leverages natural language as a semantic bridge to connect perception and control. LaDA introduces a fine-grained intermediate layer of three interpretable action primitives--translation, rotation, and gripper control--providing explicit semantic structure for low-level actions. It further employs a semantic-guided soft-label contrastive learning objective to align similar action primitives across tasks, enhancing generalization and motion consistency. An adaptive weighting strategy, inspired by curriculum learning, dynamically balances contrastive and imitation objectives for stable and effective training. Extensive experiments on simulated benchmarks (LIBERO and MimicGen) and real-world demonstrations validate that LaDA achieves strong performance and generalizes effectively to unseen or related tasks.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **核心问题**：机器人操作中，高层视觉-语言理解与底层动作控制之间存在显著异质性，导致模型难以对新任务或语义相关任务生成稳健、准确的动作。
- **现有范式局限**：
  - **端到端 VLA**：将多模态输入直接映射到低层控制，感知与控制纠缠，可解释性差，难以复用共享运动结构。
  - **潜在动作学习**：将动作编码到隐空间，但通常由观测差分定义，缺少显式语义，跨任务迁移能力有限。
  - **语言条件策略**：引入语言作为中间监督或表示，但多使用粗粒度、离散 primitive，如“前进”“闭合夹爪”，缺少平移幅度、旋转轴/角度等细粒度运动参数。
- **整体含义**：论文提出 **LaDA**，以自然语言为语义桥梁，将连续 7-DoF 动作解耦为可解释、语言接地的动作 primitive，旨在同时实现语义理解与精确控制，并提升跨任务泛化与组合泛化能力。

## 2. 方法论

- **核心思想**：将 7-DoF 末端执行器动作分解为三个正交、可解释、语言接地的 motion primitives：
  - **平移 primitive**：如 “Move [dist] meters along [dir]”；
  - **旋转 primitive**：如 “Rotate [mag] degrees around [axis]”；
  - **夹爪 primitive**：离散命令 “Open” / “Close”。
- **动作分解与语义化**：
  - 定义投影 \(\Pi: a_t \mapsto p_t\)，将连续动作转为语言对齐的离散 bin。
  - 每个 primitive 具有自然语言模板，使低层动作获得显式语义监督。
- **语义引导软标签对比学习**：
  - 构建软标签相似度矩阵 \(S\)，融合平移、旋转、夹爪三部分匹配矩阵：
    \[
    S = \frac{w_t M_t + w_r M_r + w_g M_g}{w_t + w_r + w_g}
    \]
  - \(M_t, M_r, M_g\) 表示两个动作是否共享同一 primitive 属性；\(S_{ij}\) 表示动作 \(i,j\) 的细粒度语义相似度。
- **双路径软标签对比目标**：
  - 使用预训练 CLIP 编码视觉与语言，得到视觉 token \(v_i\) 和指令 token \(l_i\)。
  - 通过 FiLM 融合视觉与语言，再经 MLP adapter 得到统一动作嵌入：
    \[
    A_i = \mathrm{MLP}(\mathrm{FiLM}(v_i, l_i))
    \]
  - **Action–Action 对齐** \(L_a\)：按 \(S_{ij}\) 加权，使语义相关动作在嵌入空间靠近。
  - **Action–Primitive 对齐** \(L_m\)：将动作嵌入锚定到 tokenized primitive 描述 \(P_j\)，保持语言可解释性。
  - 两者均使用软标签 InfoNCE，总对比损失为：
    \[
    L_{CL} = L_a + \lambda L_m
    \]
- **自适应损失加权**：
  - 同时使用模仿损失 \(L_{IL}\) 预测离散平移、旋转、夹爪 primitive。
  - 基于移动平均 MA 动态平衡：
    \[
    w_{IL} = \frac{MA(L_{IL})}{MA(L_{IL}) + MA(L_{CL})},\quad
    w_{CL} = \frac{MA(L_{CL})}{MA(L_{IL}) + MA(L_{CL})}
    \]
  - 最终目标：
    \[
    L_{total} = w_{CL}L_{CL} + w_{IL}L_{IL}
    \]
- **微调与推理**：
  - 预训练后，用轻量 MLP action head 和 L1 轨迹回归损失微调，进行 7-DoF 动作预测。
  - 推理时直接根据 \((V_t, L_t)\) 输出连续动作，无需显式 primitive 标签。

## 3. 实验设计

- **预训练数据**：
  - 使用 **Open X-Embodiment (OXE)** 数据集，约 22 个机器人本体、超过 100 万条真实轨迹。
  - 采用约 **2250 万视觉帧** 的精选子集；每个低层动作为 7-DoF 向量：3D 平移、3D 旋转、二值夹爪。
  - 自动生成结构化语言描述，如 “move 0.5 meters forward, rotate 90 degrees around the z-axis, and close the gripper”。
- **仿真 benchmark**：
  - **LIBERO**：语言条件多任务操作 benchmark，包含四个套件：Spatial、Object、Goal、Long；每套件 10 个任务，每任务 50 个人类遥操作演示；报告 50 次随机试验平均成功率。
  - **MimicGen**：接触丰富操作 benchmark，评估 9 个任务，覆盖长时程装配与高精度操作，每任务约 1K 演示；每任务 50 次 rollout。
- **真实世界实验**：
  - 7-DoF **Franka Emika Panda**，静态第三人称 **RealSense D435i** 相机。
  - 任务：抓取方块并放入盒子；用 100 个人类演示微调。
- **对比方法**：
  - **LIBERO**：UniACT、LAPA、Diffusion Policy、Octo、MDT、OpenVLA、SpatialVLA、CoT-VLA、WorldVLA、Dita、ThinkAct、π-FAST、GR00T-N1.5、MolmoAct、FlowVLA、CLIP-RT，以及同 ViT-L/14 backbone 重实现的 CLIP-RT*。
  - **MimicGen**：OpenVLA、task-conditioned、subgoal-conditioned、motion-conditioned、subgoal self-reflection、Phoenix、CLIP-RT*。
- **泛化与消融**：
  - LIBERO-Goal 上评估 cross-task 泛化与 similar-task 泛化。
  - MimicGen 上比较多任务训练收益。
  - 消融：去掉软标签对比学习 SCL、去掉自适应加权 AW。
  - t-SNE 可视化动作嵌入。

## 4. 资源与算力

- **论文未明确报告**使用的 GPU 型号、数量、训练时长、总 GPU 小时或碳足迹。
- 文中仅提到：
  - 预训练数据规模约 **2250 万视觉帧**；
  - 模型参数量约 **0.6B**；
  - 使用 CLIP 编码器、FiLM、MLP adapter、MLP action head；
  - 实现细节和参数设置称见附录，但所给 PDF 提取内容未包含附录细节。
- 因此，无法从现有内容评估其训练成本、算力需求和可复现性。

## 5. 实验数量与充分性

- **实验组数概览**：
  - LIBERO：4 个任务套件，每套件 10 任务，每任务 50 次试验。
  - MimicGen：9 个任务，每任务约 1K 演示、50 次 rollout。
  - 泛化实验：LIBERO-Goal 下 cross-task 与 similar-task，4 种训练数据比例，每种 1000 rollouts、20 随机种子。
  - 消融：w/o SCL、w/o AW、完整 LaDA。
  - 真实世界：1 个 pick-and-place 任务，100 个演示。
  - 可视化：t-SNE 动作嵌入。
- **充分性**：
  - 覆盖两个主流仿真 benchmark、真实机器人、泛化评估、消融和可视化，整体较充分。
  - 消融验证了 SCL 与 AW 的互补作用。
  - 多任务训练对比与 t-SNE 提供了语义结构证据。
- **公平性与客观性**：
  - LIBERO 上所有模型在相同仿真和语言指令设置下评估；CLIP-RT* 使用与 LaDA 相同 ViT-L/14 backbone 重实现，增强可比性。
  - 但部分 baseline 结果来自已有工作或官方超参，训练预算、数据增强、模型规模不完全一致。
  - 主要表格未报告方差或统计显著性；真实世界试验次数未明确。
  - MimicGen 上 LaDA 平均最高，但并非所有任务都最优，例如 Threading D0 低于 Phoenix。

## 6. 主要结论与发现

- LaDA 在 **LIBERO** 上平均成功率
