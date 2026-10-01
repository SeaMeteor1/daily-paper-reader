---
title: "LIBERO-Plus: A Progressive Robustness Benchmark for Visual-Language-Action Models"
title_zh: LIBERO-Plus：面向视觉-语言-动作模型的渐进式鲁棒性基准
authors: "Fei, Senyu, Wang, Siyin, Shi, Junhao, Dai, Zihao, Cai, Jikun, Qian, Pengfang, Ji, Li, He, Xinzhe, Zhang, Shiduo, Fei, Zhaoye, Fu, Jinlan, Gong, Jingjing, Qiu, Xipeng"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Fei_LIBERO-Plus_A_Progressive_Robustness_Benchmark_for_Visual-Language-Action_Models_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 7.0
evidence: 面向视觉-语言-动作模型的基准
tldr: "视觉-语言-动作模型在操作基准上报告超95%成功率，但这些结果可能掩盖鲁棒性缺陷。现有仿真鲁棒性评测扰动覆盖窄、依赖人工设计且分析粗糙。本文提出LIBERO-Plus，在物体布局、相机视角、机器人初始状态、语言指令、光照、背景纹理与传感器噪声七个维度施加受控扰动，实现自动、细粒度评测。对十个先进模型的系统分析揭示出一致的失败模式。"
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 1236, \"height\": 464}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 1236, \"height\": 465}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 1193, \"height\": 465}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 2, \"index\": 4, \"width\": 876, \"height\": 226}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 2, \"index\": 5, \"width\": 1214, \"height\": 465}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 2, \"index\": 6, \"width\": 1201, \"height\": 465}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-fei-libero-plus-a-progressive-robustness-benchmark-for-visual-language-action-models-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 3, \"index\": 7, \"width\": 2750, \"height\": 2745}]"
motivation: VLA模型的高成功率可能掩盖鲁棒性缺陷，现有鲁棒性评测覆盖窄且分析粗糙。
method: 提出跨七个维度受控扰动的自动细粒度评测框架，覆盖布局、视角、指令与噪声等。
result: 系统评测十个先进模型，揭示出稳定一致的失败模式与薄弱环节。
conclusion: 该基准为VLA模型的鲁棒性评估提供了更全面可靠的诊断工具。
---

## Abstract
Visual-Language-Action (VLA) models report impressive success rates exceeding 95% on robotic manipulation benchmarks, yet these results may mask fundamental weaknesses in robustness. Current simulation-based robustness evaluations suffer from narrow perturbation coverage, manual design constraints, and coarse-grained analysis that fails to reveal when and how models fail. To address this gap, we propose LIBERO-Plus, a comprehensive, automatic, and fine-grained evaluation framework with controlled perturbations across seven dimensions: object layouts, camera viewpoints, robot initial states, language instructions, lighting conditions, background textures, and sensor noise. Our systematic analysis of ten state-of-the-art models reveals consistent brittleness beneath apparent competence, with performance dropping from 95% to below 30% under modest perturbations. Our findings challenge the assumption that high benchmark scores equate to true competency and highlight the need for evaluation practices that assess reliability under realistic variation.

---

## 论文详细总结（自动生成）

# LIBERO-Plus 论文中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：视觉-语言-动作（VLA）模型在 LIBERO 等仿真操作基准上报告了超过 95%–99% 的成功率，看似操作任务已接近“解决”。
- **核心矛盾**：真实部署中，模型面对光照变化、相机视角偏移、语言表述差异等环境扰动时表现急剧下降，高基准分数可能掩盖了鲁棒性缺陷。
- **现有评测的三大不足**：
  - **扰动覆盖窄**：多数工作只针对单一或少数扰动轴（如物体变化、光照、指令改写）。
  - **依赖人工设计**：扰动由人工构造，限制可扩展性与可复现性。
  - **分析粗糙**：仅报告聚合成功率，无法揭示模型“在何种条件下、以何种方式失败”。
- **整体含义**：论文主张高基准分数不等于真实能力，呼吁建立能评估真实变化下可靠性的评测实践。

## 2. 方法论：核心思想与关键技术细节

- **核心思想**：在 LIBERO 基础上构建 **LIBERO-Plus**，实现**全面（Comprehensive）、自动（Automatic）、细粒度（Fine-grained）**的渐进式鲁棒性评测。
- **七大扰动维度（21 个子维度）**：
  1. **物体布局**：引入干扰物体、目标物体空间位移与位姿变化。
  2. **相机视角**：相机位姿、朝向与视场角修改。
  3. **机器人初始状态**：机械臂起始位姿变化。
  4. **语言指令**：语义改写、语言复杂度提升、常识改写。
  5. **光照条件**：强度、方向、颜色变化。
  6. **背景纹理**：表面材质与纹理替换。
  7. **传感器噪声**：抖动、高斯模糊等光度畸变。
- **自动化生成**：所有扰动由参数化方法自动生成，可同时构造训练与测试数据集，覆盖 **10,030 个任务实例 / 超过 56K 鲁棒性场景**，保证可复现。
- **渐进式难度分层（L1–L5）**：基于四个代表性 VLA 模型的实证表现，将任务划分为 5 个难度等级，形成渐进式评估框架。
- **组合泛化差距的统计定义（第 7 节）**：
  - 定义扰动指示变量 $D_i, D_j \in \{0,1\}$ 与成功指示变量 $Y$。
  - 以成功条件下的联合概率与边缘概率之差定义**组合性差距** $\Delta_{ij} = \text{Cov}(D_i, D_j \mid Y=1)$。
  - $\Delta_{ij}>0$ 表示两扰动可协同处理；$\Delta_{ij}<0$ 表示组合带来额外困难；$\Delta_{ij}=0$ 表示独立。
- **诊断性消融设计**：
  - **空白指令实验**（完全移除语言输入）检验语言模态是否被真正使用。
  - **目标替换实验**（替换指令与任务目标物体）检验跨物体指令遵循能力。
  - **全黑 / 仅第三人称黑屏**消融，定位视觉依赖来源与腕部相机作用。

## 3. 实验设计：基准、场景与对比方法

- **基准与场景**：基于 **LIBERO** 的四个任务套件（Spatial、Object、Goal、Long），扩展出 7 维扰动、21 子维度、10,030 个任务实例。
- **对比方法（10 个代表性 VLA 模型）**：
  - OpenVLA 及其变体：OpenVLA、OpenVLA-OFT、OpenVLA-OFT_w（仅第三人称视角）、OpenVLA-OFT_m（在全部 4 个套件混合微调）。
  - π0、π0-fast、Nora、WorldVLA、UniVLA、RIPT-VLA。
  - 涵盖自回归、扩散、世界模型、强化学习等多种训练范式。
- **附加实验**：
  - 组合泛化实验：6 个扰动维度（排除语言）的两两组合，共 **30K 次独立重复实验**，每种组合 2000 次，并使用卡方检验验证显著性。
  - 训练增强实验：基于自动化管线构建 **超过 20,000 条成功轨迹**，从官方 OpenVLA-OFT 权重出发进行混合微调。

## 4. 资源与算力

- **论文正文未明确说明所使用的 GPU 型号、数量或训练时长**。
- 仅在致谢中提及国家自然科学基金资助（No. 62521004），未提供算力细节。
- 训练增强实验提到使用 20,000+ 成功轨迹进行混合微调，但未披露具体硬件配置与训练时间。

## 5. 实验数量与充分性

- **实验规模**：
  - 10 个模型 × 7 个扰动维度 × 5 个难度等级的完整评测矩阵。
  - 组合泛化实验：6 维两两组合共 30K 次试验（每组合 2000 次），统计严谨。
  - 语言相关消融：空白指令、目标替换，覆盖 4 个 LIBERO 套件。
  - 光照消融：原光照、光照扰动、仅第三人称黑屏、全黑四组对照。
  - 训练增强对比：与全部基线模型在 7 类扰动上的横向对比。
- **充分性评估**：
  - **优点**：扰动维度覆盖全面，难度分层细粒度强，统计检验增强了组合泛化结论的可信度。
  - **客观性**：模型选择覆盖多种架构与训练范式，对比相对公平；扰动为参数化自动生成，减少人工偏差。
  - **潜在不足**：组合泛化与语言消融主要集中在 OpenVLA-OFT 上，其他模型覆盖有限，结论的普适性需进一步验证。

## 6. 主要结论与发现

- **Finding 1**：当前 VLA 模型对扰动整体极其脆弱，性能可从 95% 骤降至 30% 以下。
- **Finding 2**：鲁棒性因扰动类型差异显著——对**相机视角**和**机器人初始状态**最脆弱，对光照与背景相对耐受。
- **Finding 3**：语言扰动影响意外地小（平均下降约 25.3 分），但并非源于语言泛化能力强。
- **Finding 4**：鲁棒性由架构与训练范式决定——带第一人称腕部相机的模型（如 OpenVLA-OFT）泛化更好；强调数据多样性与协同训练的策略（如 π0、π0-fast）更鲁棒。
- **Finding 5**：模型存在**位置偏置**而非真正的物体语义理解——能忽略干扰物，但目标物体位移后性能大幅下降。
- **Finding 6**：**腕部相机**提供光照不变性几何线索，是光照鲁棒性的关键；仅依赖第三人称的模型（OpenVLA、Nora、WorldVLA）在光照扰动下常掉 60 分以上。
- **Finding 7**：VLA 模型缺乏**跨物体指令遵循泛化**能力，目标替换后成功率几乎归零。
- **Finding 8**：模型更依赖**固定的视觉-动作映射**而非语言信号，即使指令改变仍执行原目标动作。
- **Finding 9**：泛化**本质不可分解**——组合性差距持续为负，说明扰动间存在耦合效应，模型缺乏高阶依赖建模能力。
- **训练增强结论**：使用自动化生成的泛化数据集微调后，整体成功率提升至 79.6%，相机视角鲁棒性提升至 92.8%（超出次优模型 37.2 个百分点）。

## 7. 优点

- **全面性**：7 大维度、21 子维度、10,030 个任务实例，远超现有基准的扰动覆盖范围。
- **自动化与可复现**：参数化自动生成扰动，可大规模构造训练与测试数据，摆脱人工设计约束。
- **细粒度分析**：L1–L5 渐进式难度分层，能精确定位模型失败的条件与程度。
- **诊断深入**：通过空白指令、目标替换、全黑/第三人称黑屏等消融，揭示了“忽略语言”“位置记忆”“腕部相机关键作用”等深层机制。
- **统计严谨**：组合泛化采用条件概率与协方差定义，配合卡方检验，方法论规范。
- **实用价值**：验证了基于该管线增强训练数据可显著提升鲁棒性，形成“评测—诊断—改进”的闭环。

## 8. 不足与局限

- **算力信息缺失**：未报告 GPU 型号、数量与训练时长，影响复现与成本评估。
- **真实世界验证不足**：所有实验均在仿真环境（LIBERO）中进行，未涉及真实机器人部署，仿真到现实的迁移性未知。
- **模型覆盖不均衡**：组合泛化实验（30K 次）与语言消融主要基于 OpenVLA-OFT，其他模型的深度诊断有限。
- **难度分层偏差风险**：L1–L5 分层依赖 4 个模型的实证表现，可能引入特定模型偏好或循环论证风险。
- **语言结论的普适性**：“模型忽略语言”的结论虽有多组证据，但可能因模型/任务而异，需更广泛验证。
- **扰动维度仍有边界**：如接触动力学、物体材质物理属性、多物体交互等维度未纳入；传感器噪声仅涉及光度畸变。
- **统计定义的前提**：组合性差距的协方差定义假设扰动以二值形式存在，对连续或多级扰动的推广需进一步讨论。

（完）
