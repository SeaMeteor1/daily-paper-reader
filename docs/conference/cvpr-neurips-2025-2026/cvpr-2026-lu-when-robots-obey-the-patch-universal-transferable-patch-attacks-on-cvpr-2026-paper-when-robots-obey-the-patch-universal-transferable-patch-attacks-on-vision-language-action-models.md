---
title: "When Robots Obey the Patch: Universal Transferable Patch Attacks on Vision-Language-Action Models"
title_zh: 当机器人服从补丁：对视觉-语言-动作模型的通用可迁移补丁攻击
authors: "Lu, Hui, Yu, Yi, Yang, Yiming, Yi, Chenyu, Zhang, Qixin, Shen, Bingquan, Kot, Alex C., Jiang, Xudong"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Lu_When_Robots_Obey_the_Patch_Universal_Transferable_Patch_Attacks_on_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 4.0
evidence: 针对VLA模型的对抗攻击
tldr: 视觉-语言-动作模型对对抗攻击脆弱，但通用且可迁移的攻击仍研究不足，现有补丁多过拟合单一模型并在黑盒设定下失效。本文系统研究针对VLA机器人的通用可迁移对抗补丁，提出UPA-RFAS框架，在共享特征空间学习单一物理补丁并促进跨模型迁移。实验覆盖未知架构、微调变体与仿真到现实迁移。该工作揭示了VLA机器人部署中的安全威胁。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
motivation: VLA模型对对抗攻击脆弱，现有补丁多过拟合单一模型且黑盒下失效。
method: 提出UPA-RFAS框架，在共享特征空间学习单一物理补丁以促进跨模型迁移。
result: 在未知架构、微调变体和仿真到现实迁移下实现通用可迁移攻击。
conclusion: 揭示了VLA驱动的机器人面临的安全威胁。
---

## Abstract
Vision-Language-Action (VLA) models are vulnerable to adversarial attacks, yet universal and transferable attacks remain underexplored, as most existing patches overfit to a single model and fail in black-box settings. To address this gap, we present a systematic study of universal, transferable adversarial patches against VLA-driven robots under unknown architectures, finetuned variants, and sim-to-real shifts. We introduce UPA-RFAS (Universal Patch Attack via Robust Feature, Attention, and Semantics), a unified framework that learns a single physical patch in a shared feature space while promoting cross-model transfer. UPA-RFAS combines (i) a feature-space objective with an l_1 deviation prior and repulsive InfoNCE loss to induce transferable representation shifts, (ii) a robustness-augmented two-phase min-max procedure where an inner loop learns invisible sample-wise perturbations and an outer loop optimizes the universal patch against this hardened neighborhood, and (iii) two VLA-specific losses: Patch Attention Dominance to hijack text to vision attention and Patch Semantic Misalignment to induce image-text mismatch without labels. Experiments across diverse VLA models, manipulation suites, and physical executions show that UPA-RFAS consistently transfers across models, tasks, and viewpoints, exposing a practical patch-based attack surface and establishing a strong baseline for future defenses.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究动机**：视觉-语言-动作（VLA）模型已用于开放世界机器人操作、语言条件规划和跨本体迁移，但其多模态管线容易受到结构化视觉扰动攻击。现实机器人部署通常处于黑盒、未知架构、微调变体和仿真到现实迁移等条件。
- **核心问题**：现有 VLA 对抗补丁多针对单一模型、数据集或提示模板过拟合，迁移到未见架构或微调变体时效果显著下降，导致黑盒安全评估可能高估安全性、低估补丁威胁。
- **整体含义**：论文系统研究针对 VLA 机器人的**通用、可迁移物理补丁攻击**，提出 UPA-RFAS 框架，在共享特征空间学习单一物理补丁，揭示实际部署中基于补丁的攻击面，并为后续防御提供强基线。

## 2. 方法论：核心思想与关键技术

- **核心思想**：不直接在某个代理模型的输出端过拟合，而是在代理与目标模型共享的特征空间中制造稳定、可迁移的表示偏移；同时结合鲁棒增强、跨模态注意力和语义错位，使补丁在不同模型、任务、视角和仿真/现实条件下仍有效。
- **特征空间目标**：
  - 使用 **L1 特征偏差** 最大化代理侧特征变化，理论上通过线性对齐假设与 Proposition 1 说明目标侧位移有下界。
  - 使用 **排斥式 InfoNCE 损失** 将带补丁特征推离干净锚点，促使变化沿批次一致、跨模型共享的方向集中。
  - 总体训练目标为 `Jtr = L1 + φcon * Lcon`。
- **鲁棒增强的通用补丁攻击（RAUP）**：
  - 采用**两阶段 min-max** 优化。
  - **内层最小化**：对每个样本学习一个不可见、样本级扰动，通过 PGD 最小化特征攻击目标，相当于局部“对抗训练”，硬化代理模型。
  - **外层最大化**：固定内层扰动，在随机位置、旋转、倾斜等几何变换下优化单个通用物理补丁，使其在硬化邻域中仍能攻击。
- **VLA 专用损失**：
  - **Patch Attention Dominance（PAD）**：劫持动作相关文本查询到视觉的注意力，增加补丁视觉 token 的注意力增量，抑制非补丁 token 增量，并用 margin 保证补丁超过最强非补丁路由。
  - **Patch Semantic Misalignment（PSM）**：将补丁池化特征拉近一组跨模型稳定的动作/方向探针短语，同时推离当前完整指令嵌入，制造无标签的图像-文本语义错位。
- **算法流程**：
  - 对每个 mini-batch，先初始化样本级扰动，采样补丁变换，迭代 PGD 最小化 `Jin` 得到 `εω`。
  - 再固定 `εω`，采样变换，用 AdamW 最大化 `Jout = L1 + φcon Lcon + φPAD LPAD + φPSM LPSM`，更新并裁剪通用补丁 `ω` 到 `[0,1]`。
- **理论支撑**：
  - 通过 CCA 和线性回归探针发现代理与目标特征空间存在较强线性关系，`R² ≈ 0.654`，支持共享低维子空间假设。
  - Assumption 1 假设线性对齐且有界残差，Proposition 1 给出目标侧位移下界，Corollary 1 说明最大化 L1 偏差可诱导目标侧非平凡变化。

## 3. 实验设计：数据集、场景与对比方法

- **数据集/场景**：
  - **BridgeData V2**：真实世界机器人操作语料，24 个环境、13 类技能、60,096 条轨迹。
  - **LIBERO**：仿真基准，包含 Spatial、Object、Goal、Long 四类任务族；每套件 10 个任务，每任务 10 次独立试验，即每套件 100 次 rollout。
  - 同时评估**模拟设置**和**物理设置**。
- **代理模型与受害者模型**：
  - 代理模型：OpenVLA-7B（BridgeData V2）和 OpenVLA-7B-LIBERO-Long。
  - 受害者模型：OpenVLA-oft 的四个不同 LIBERO 任务套件微调变体、多套件模型 OpenVLA-oft-w，以及 π0（文中 OCR 显示为 ε0/ε 系列）等异质 VLA。
  - 严格黑盒迁移：不使用受害者权重、架构细节、微调数据或超参数。
- **对比基线**：
  - 采用 RoboticAttack 的 6 个目标/变体，包括 UMA、UADA、TMA 及不同 DoF 设置。
  - 按原始损失定义和评估协议复现/比较。
- **评估指标**：
  - 主要使用 LIBERO 中的任务成功率（Success Rate, SR）。
  - 攻击越强，SR 越低。

## 4. 资源与算力

- 提供的论文文本中**未明确说明**使用的 GPU 型号、数量、训练时长、显存消耗或总计算量。
- 文中仅提到实现细节见附录 B，代码已开源于 `https://github.com/yuyi-sd/UPA-RFAS`。
- 因此，无法从当前文本判断其训练与实验的算力规模。

## 5. 实验数量与充分性

- **主要实验**：
  - Table 1 展示从 OpenVLA-7B 迁移到 OpenVLA-oft-w、OpenVLA-oft 多个变体的模拟与物理结果。
  - 覆盖 Spatial、Object、Goal、Long 四类任务，每类 100 次 rollout，实验规模较大。
- **消融实验**：
  - Table 2 消融 RUPA、PAD、PSM、`Jtr`、`Lcon`、`L1` 等组件。
  - Table 3 消融文本探针措辞：联合动作+方向、仅动作、仅方向。
  - 附录中还包含白盒性能、迁移到 π0、更多参数消融等。
- **充分性评价**：
  - 覆盖多模型、多任务、模拟/物理、黑盒迁移和组件消融，整体较充分。
  - 公平性方面，采用严格黑盒协议，未使用受害者信息，基线按原协议比较，较客观。
  - 但物理实验规模、随机种子数量、统计显著性等未在正文中充分展开；补丁放置位置预先设定，可能偏理想化。

## 6. 主要结论与发现

- UPA-RFAS 能生成单一通用物理补丁，在未知架构、微调变体和仿真到现实条件下实现强黑盒迁移。
- 在 OpenVLA-7B 到 OpenVLA-oft-w 的模拟迁移中，干净策略平均成功率 98.25%，UPA-RFAS 降至 5.75%，下降超过 92 个百分点；基线仍保留 41.25%–69.25% 的平均成功率。
- 物理设置中，UPA-RFAS 也将成功率降至 40.25%，明显低于基线的 65.00%–91.25%。
- 消融显示：去掉 `Jtr` 后攻击显著失效，说明特征空间目标最关键；`Lcon` 比 `L1` 影响更大，表明特征变化方向比单纯幅度更重要。
- 联合动作与方向探针的 PSM 设计优于仅动作或仅方向探针。
- 补丁可视化显示，基线方法易生成与场景/夹爪相关的图案，而 UPA-RFAS 学习到更抽象、模型无关的补丁，避免对象模仿，增强跨模型迁移。

## 7. 优点

- **首次系统研究**：面向 VLA 机器人的通用、可迁移补丁攻击，填补黑盒迁移与仿真到现实评估空白。
- **方法设计有理论支撑**：用线性对齐假设、CCA 分析和下界命题解释特征空间迁移。
- **多目标联合优化**：结合特征空间偏移、注意力劫持和语义错位，兼顾表示、注意力和语义层面。
- **鲁棒增强优化**：内层样本级扰动模拟对抗训练，外层在几何随机化下优化通用补丁，提升黑盒迁移和物理鲁棒性。
- **实验覆盖较广**：多 VLA 模型、多任务套件、模拟与物理执行、多个消融维度。
- **开源代码**：便于复现和后续防御研究。

## 8. 不足与局限

- **算力信息缺失**：未报告 GPU 型号、数量、训练时长等，难以评估计算成本和可复现资源需求。
- **受害者架构覆盖有限**：主要围绕 OpenVLA 家族，π0 等异质模型在附录中，跨架构结论仍需更多验证。
- **物理攻击仍有残余成功率**：物理设置下成功率降至 40.25%，并非完全失效，实际威胁程度依赖场景。
- **补丁放置假设较强**：实验使用预定放置位置以避免遮挡，真实攻击中能否稳定放置、是否被察觉未充分讨论。
- **探针短语手工设计**：PSM 依赖动作/方向探针，跨任务和跨语言泛化能力可能受限。
- **防御评估缺失**：论文定位

- **防御评估缺失**：论文定位为攻击侧研究，重点在于证明通用物理补丁的迁移威胁与黑盒攻击面，尚未系统评估现有防御手段（如补丁检测、输入净化、对抗训练、随机平滑、注意力正则化、特征对齐约束等）对 UPA-RFAS 的抑制效果，因此对“攻击—防御”闭环的指导仍有限。
- **统计细节与可复现性不足**：正文虽给出成功率对比，但对随机种子数量、多次运行方差、置信区间和显著性检验披露不充分；物理实验的重复次数、失败模式分类和跨环境稳定性也缺少更细粒度报告。
- **真实部署条件仍偏理想化**：补丁放置位置经过预先设定以避免遮挡，真实场景中的动态视角、光照变化、运动模糊、相机标定误差、补丁材质与打印色差、遮挡和检测风险等未被充分建模，仿真到现实的域间隙仍可能削弱攻击。
- **跨本体与跨语言泛化待验证**：实验主要围绕 OpenVLA 家族展开，π0 等异质模型主要在附录中涉及；对于更多机器人本体、不同动作空间、多语言指令和更复杂长时程任务，通用性仍需进一步检验。
- **探针设计与任务依赖**：PSM 依赖动作/方向探针短语，虽然消融显示联合探针更优，但探针集合的手工设计可能引入任务先验，跨任务、跨语言和跨场景扩展时可能需要重新设计或自动生成。
- **伦理与安全双用途风险**：论文开源攻击代码与补丁生成流程，有助于安全研究复现，但也存在被滥用于真实机器人系统的风险；文中对负责任披露、访问限制和防御建议的讨论相对有限。
- **长时程与动态交互评估有限**：LIBERO-Long 等任务提供了一定长时程验证，但真实机器人中的闭环纠错、人类干预、动态障碍和多阶段任务恢复等情形仍未充分覆盖。

## 9. 总体评价与启示

- **总体定位**：该工作将 VLA 机器人安全从单模型、单任务对抗攻击推进到通用、可迁移、跨仿真与物理部署的补丁攻击，问题重要且切中实际黑盒评估盲区。
- **方法价值**：UPA-RFAS 将特征空间偏移、鲁棒增强、注意力劫持和语义错位结合，形成较系统的攻击框架；CCA 分析与下界命题为迁移性提供了可解释线索。
- **实验价值**：多任务套件、多微调变体、模拟与物理执行、组件消融和探针消融共同支撑了“单一补丁可强迁移”的主要结论，基线对比也较有说服力。
- **主要局限**：算力报告缺失、防御评估不足、统计细节有限、真实部署假设较强、跨架构覆盖仍偏窄，这些都会影响对其实际威胁边界和可复现成本的判断。
- **研究启示**：VLA 安全评估不应仅依赖单一代理模型或白盒设定；防御研究需关注共享特征空间、跨模态注意力路由和动作相关表示，而非只做像素级补丁检测。未来可构建统一的 VLA 攻防基准，纳入更多本体、真实动态环境和防御基线，以更准确衡量风险与鲁棒性。

（完）
