# x-embodiment · 入门导读

<div class="dpr-topic-result-actions"><button type="button" class="arxiv-tool-btn" data-topic-copy="docs/20251126-20261125-starter-x-embodiment/papers.md">复制完整清单</button> <a class="arxiv-tool-btn" href="docs/20251126-20261125-starter-x-embodiment/papers.md" download data-no-router>下载 Markdown 清单</a></div>

- **研究方向**：机器人与AI：跨具身智能
- **覆盖范围**：arXiv 2025-11-26 ~ 2026-11-25；顶会近 24 个月（2024-11-26 ~ 2026-11-25）
- **精选论文**：共 50 篇（精读 50 篇 · 速读 0 篇）

> 说明：导读基于窗口内精选论文的标题、摘要与速览整理，不代表完整领域史，关键结论请结合原文核验。

## 方向概览

跨具身智能的核心问题是：如何利用来自不同机器人（乃至人类）的异构数据，训练出能泛化到新形态、新动作空间的单一策略。当前技术脉络大致分为三条：一是设计共享动作表示（通用动作空间、潜在动作、行为对齐表示）以消除动作空间异构性；二是将形态/运动学信息显式注入策略（运动学图、拓扑注意力、形态条件分词器），使策略感知自身身体；三是以视觉-语言-动作基础模型为骨架，通过大规模多具身预训练与对齐实现零样本或少样本迁移。关键挑战在于：共享表示可能丢失形态相关的行为差异，形态条件化又面临数据规模与泛化权衡，且零样本迁移的评测协议尚不统一。

**核心代表论文：**

- [Universal Actions for Enhanced Embodied Foundation Models](/conference/cvpr-2025/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper-universal-actions-for-enhanced-embodied-foundation-models)（`CVPR25` · 10.0分） — 用于增强具身基础模型的通用动作
- [Embedding Morphology into Transformers for Cross-Robot Policy Learning](/20251126-20261125-starter-x-embodiment/2603.00182v1-embedding-morphology-into-transformers-for-cross-robot-policy-learning)（`Arxiv2603` · 10.0分） — 将形态嵌入Transformer以实现跨机器人策略学习
- [LAP: Language-Action Pre-Training Enables Zero-shot Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2602.10556v2-lap-language-action-pre-training-enables-zero-shot-cross-embodiment-transfer)（`Arxiv2602` · 10.0分） — LAP：语言-动作预训练实现零样本跨具身迁移
- [ZETA: A Controlled Study of Zero-Shot Cross-Embodiment VLA Transfer for Tabletop Manipulation](/20251126-20261125-starter-x-embodiment/2609.02546v2-zeta-a-controlled-study-of-zero-shot-cross-embodiment-vla-transfer-for-tabletop-manipulation)（`Arxiv2609` · 10.0分） — ZETA：面向桌面操作的零样本跨具身 VLA 迁移的受控研究
- [Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization](/20251126-20261125-starter-x-embodiment/2601.12993v1-being-h05-scaling-human-centric-robot-learning-for-cross-embodiment-generalization)（`Arxiv2601` · 10.0分） — Being-H0.5：规模化以人为中心的机器人学习以实现跨具身泛化

## 1. 共享动作空间与潜在动作表示

这一路线假设跨具身迁移的关键障碍是动作空间异构，因此构造一个与具身无关的中间动作表示，再通过重定向或解码器映射回各机器人。UniAct 学习通用动作空间以捕捉不同机器人的共享结构特征；OPFA 用几何感知潜动作空间加统一潜重定向解码器支持任意自由度末端执行器联合训练；UHAS 以标准球面几何形变表示手部动作并级联逆运动学映射到各灵巧手；CIALLO 则将动作、视觉变化与语言对齐到短时行为意图空间，把具身校准与任务学习分离。这些工作的核心差异在于共享表示刻画的是“动作结构”还是“行为意图”：前者适合运动学相近的平台，后者更利于跨异构接口复用，但都可能牺牲形态特异的精细控制。

**相关论文：**

- [Universal Actions for Enhanced Embodied Foundation Models](/conference/cvpr-2025/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper-universal-actions-for-enhanced-embodied-foundation-models)（`CVPR25` · 10.0分） — 用于增强具身基础模型的通用动作
- [One-Policy-Fits-All: Geometry-Aware Action Latents for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2603.14522v1-one-policy-fits-all-geometry-aware-action-latents-for-cross-embodiment-manipulation)（`Arxiv2603` · 10.0分） — 一策通用：面向跨具身操作的几何感知动作潜变量
- [Cross-Embodiment Robot Manipulation via a Unified Hand Action Space](/20251126-20261125-starter-x-embodiment/2607.03570v1-cross-embodiment-robot-manipulation-via-a-unified-hand-action-space)（`Arxiv2607` · 9.0分） — 基于统一手部动作空间的跨具身机器人操作
- [CIALLO: Learning Shared Intent Representations for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2611.13732v1-ciallo-learning-shared-intent-representations-for-cross-embodiment-manipulation)（`Arxiv2611` · 10.0分） — CIALLO：学习用于跨具身操作的共享意图表示

## 2. 形态条件化与运动学感知策略

与追求完全共享表示不同，这一路线让策略显式感知目标机器人的运动学结构，从而在统一策略内生成具身特异的动作。OmniAct 以运动学图为条件、用流匹配预测各关节相对运动，支持不同自由度与构型；RoboMorpher 的动作分词器同时重建关节角与连杆位姿，把控制坐标与其空间效应关联；形态嵌入 Transformer 通过关节级运动学 token、拓扑感知注意力偏置与关节属性条件注入形态；SAT 将动作块重构为变长无序的关节轨迹序列，使 Transformer 原生处理异构关节数。该路线能保留形态差异带来的行为特化，但依赖可靠的运动学描述，且对未见形态的泛化仍需大规模形态数据支撑。

**相关论文：**

- [OmniAct: One Policy, One Million Embodiments](/20251126-20261125-starter-x-embodiment/2611.33158v2-omniact-one-policy-one-million-embodiments)（`Arxiv2611` · 10.0分） — OmniAct：一个策略，一百万种具身形态
- [RoboMorpher: Scaling Robot Morphology Representations for Cross-Embodiment Action Prediction](/20251126-20261125-starter-x-embodiment/2611.24816v1-robomorpher-scaling-robot-morphology-representations-for-cross-embodiment-action-prediction)（`Arxiv2611` · 9.0分） — RoboMorpher：规模化机器人形态表征以用于跨具身动作预测
- [Embedding Morphology into Transformers for Cross-Robot Policy Learning](/20251126-20261125-starter-x-embodiment/2603.00182v1-embedding-morphology-into-transformers-for-cross-robot-policy-learning)（`Arxiv2603` · 10.0分） — 将形态嵌入Transformer以实现跨机器人策略学习
- [Structural Action Transformer for 3D Dexterous Manipulation](/20251126-20261125-starter-x-embodiment/2603.03960v1-structural-action-transformer-for-3d-dexterous-manipulation)（`Arxiv2603` · 9.0分） — 用于三维灵巧操作的结构化动作Transformer

## 3. 视觉-语言-动作基础模型的跨具身预训练

以 VLA 模型为骨架、用多具身数据做大规模预训练，是当前最主流的通用策略路线。LAP 将底层动作直接用自然语言表示，使动作监督与 VLM 的输入输出分布对齐，实现无需具身微调的零样本迁移；Being-H0.5 以人类交互为“母语”，构建统一动作空间与混合专家架构；DyPES-VLA 用未来预测学习共享动力学先验，再以具身特定 MoE 动作头在各原生动作空间输出；MR0 采用离散动作词元预训练、流匹配跨具身中训练与真实后训练的三阶段配方。这些工作的分歧在于动作接口的选择（语言、离散词元、连续流匹配）与共享/特异的切分方式，其共同挑战是预训练数据中具身多样性与目标具身覆盖之间的权衡。

**相关论文：**

- [LAP: Language-Action Pre-Training Enables Zero-shot Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2602.10556v2-lap-language-action-pre-training-enables-zero-shot-cross-embodiment-transfer)（`Arxiv2602` · 10.0分） — LAP：语言-动作预训练实现零样本跨具身迁移
- [Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization](/20251126-20261125-starter-x-embodiment/2601.12993v1-being-h05-scaling-human-centric-robot-learning-for-cross-embodiment-generalization)（`Arxiv2601` · 10.0分） — Being-H0.5：规模化以人为中心的机器人学习以实现跨具身泛化
- [DyPES-VLA: Learning Shared Dynamics Priors and Embodiment-Specific Control for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2608.06374v1-dypes-vla-learning-shared-dynamics-priors-and-embodiment-specific-control-for-cross-embodiment-manipulation)（`Arxiv2608` · 10.0分） — DyPES-VLA：学习共享动力学先验与具身特定控制以实现跨具身操作
- [Meituan-Robotics-0: A Vision-Language-Action Foundation Model for Desktop Manipulation](/20251126-20261125-starter-x-embodiment/2611.08577v3-meituan-robotics-0-a-vision-language-action-foundation-model-for-desktop-manipulation)（`Arxiv2611` · 9.0分） — Meituan-Robotics-0：面向桌面操作的视觉-语言-动作基础模型

## 4. 行为对齐与人类数据利用

人类视频与示教是可扩展的数据来源，但具身、视角与动作空间的鸿沟使其难以直接使用。行为对齐路线通过建立跨具身的语义或行为对应来复用这些数据：BATCH 用循环一致性学习时序表征并做人类到机器人的风格迁移；行为对齐表示研究比较了包围框、语言动作与末端轨迹等表示，发现末端执行器轨迹对迁移尤其有效；LACE 利用共享身体部位对应在潜空间对齐人与机器人视觉表示；Demo-JEPA 则把演示视为未来目标而非动作序列，让目标机器人通过自身动力学规划实现。该路线的核心思想是“对齐意图而非复制动作”，适合人类数据丰富但目标机器人示教稀缺的场景，但对细粒度接触与力交互的迁移仍有限。

**相关论文：**

- [BATCH: Behavior Alignment for Cross-Embodiment Learning from Humans](/20251126-20261125-starter-x-embodiment/2611.10148v1-batch-behavior-alignment-for-cross-embodiment-learning-from-humans)（`Arxiv2611` · 9.0分） — BATCH：面向人类数据的跨具身学习中的行为对齐
- [Cross-Embodiment Transfer via Behavior-Aligned Representations](/20251126-20261125-starter-x-embodiment/2607.27549v1-cross-embodiment-transfer-via-behavior-aligned-representations)（`Arxiv2607` · 9.0分） — 通过行为对齐表征实现跨具身迁移
- [LACE: Latent Visual Representation for Cross-Embodiment Learning](/20251126-20261125-starter-x-embodiment/2605.16743v1-lace-latent-visual-representation-for-cross-embodiment-learning)（`Arxiv2605` · 9.0分） — LACE：面向跨具身学习的潜在视觉表征
- [Demo-JEPA: Joint-Embedding Predictive Architecture for One-shot Cross-Embodiment Imitation](/20251126-20261125-starter-x-embodiment/2605.20811v1-demo-jepa-joint-embedding-predictive-architecture-for-one-shot-cross-embodiment-imitation)（`Arxiv2605` · 9.0分） — Demo-JEPA：用于单样本跨具身模仿的联合嵌入预测架构

## 5. 世界模型与动力学先验

另一类方法不直接对齐动作，而是学习跨具身共享的时空动力学或世界模型，再据此生成或筛选动作。CoAWM 构建共享隐函数空间，把不同具身与采样频率的轨迹纳入统一表示；LPS 用跨具身光流预训练图像世界模型，再在目标具身上于潜空间搜索接近微调数据的动作计划；TraceGen 在紧凑 3D 轨迹空间中预测未来运动，从跨具身视频中学习；CLAP 以末端位姿、语言与潜在动作调和异构动作空间，训练跨具身动作条件视频模型。该路线的优势是能利用无动作标注的视频，且与策略解耦、可即插即用；局限在于世界模型的物理保真度与推理成本，以及潜空间搜索对长时程任务的扩展性。

**相关论文：**

- [Continuous-Action World Models: Learning Cross-Embodiment Spatiotemporal Dynamics Priors](/20251126-20261125-starter-x-embodiment/2610.40401v1-continuous-action-world-models-learning-cross-embodiment-spatiotemporal-dynamics-priors)（`Arxiv2610` · 9.0分） — 连续动作世界模型：学习跨具身时空动力学先验
- [Latent Policy Steering: An Efficient and Flexible Framework for Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2609.22521v1-latent-policy-steering-an-efficient-and-flexible-framework-for-cross-embodiment-transfer)（`Arxiv2609` · 9.0分） — 潜在策略引导：一种高效且灵活的跨具身迁移框架
- [TraceGen: World Modeling in 3D Trace Space Enables Learning from Cross-Embodiment Videos](/20251126-20261125-starter-x-embodiment/2511.21690v1-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cross-embodiment-videos)（`Arxiv2511` · 9.0分） — TraceGen：在三维轨迹空间中进行世界建模，实现从跨具身视频中学习
- [CLAP: Cross-Embodiment Video World Models are Zero-Shot Physical Simulators](/20251126-20261125-starter-x-embodiment/2608.27406v1-clap-cross-embodiment-video-world-models-are-zero-shot-physical-simulators)（`Arxiv2608` · 8.0分） — CLAP：跨具身视频世界模型是零样本物理模拟器

## 6. 评测协议、迁移边界与安全

随着方法激增，如何公平评估跨具身迁移成为独立问题。ZETA 区分严格零样本与预训练暴露式零样本，并构建覆盖 14 个留出具身的受控桌面基准，量化了末端表示、具身多样性与少量目标数据的影响；跨具身离线强化学习研究在 16 种运动平台上揭示次优数据与机器人种类增加会引发形态间梯度冲突，并提出按形态相似度分组更新；CrossSafe 将安全约束的推理与执行分离，用形态感知潜空间做 Hamilton-Jacobi 可达性分析以实现跨具身安全过滤；跨具身智能立场文章则主张以具身多样性作为扩展轴、发现可随经验增长迁移的表征。这些工作提醒：共享表示与形态条件化各有适用边界，评测需解耦具身变化与其他因素，安全与数据冲突是落地前必须处理的约束。

**相关论文：**

- [ZETA: A Controlled Study of Zero-Shot Cross-Embodiment VLA Transfer for Tabletop Manipulation](/20251126-20261125-starter-x-embodiment/2609.02546v2-zeta-a-controlled-study-of-zero-shot-cross-embodiment-vla-transfer-for-tabletop-manipulation)（`Arxiv2609` · 10.0分） — ZETA：面向桌面操作的零样本跨具身 VLA 迁移的受控研究
- [Cross-Embodiment Offline Reinforcement Learning for Heterogeneous Robot Datasets](/20251126-20261125-starter-x-embodiment/2602.18025v1-cross-embodiment-offline-reinforcement-learning-for-heterogeneous-robot-datasets)（`Arxiv2602` · 9.0分） — 面向异构机器人数据集的跨具身离线强化学习
- [CrossSafe: Towards Cross-Embodiment Latent Safety Filters](/20251126-20261125-starter-x-embodiment/2609.28984v2-crosssafe-towards-cross-embodiment-latent-safety-filters)（`Arxiv2609` · 8.0分） — CrossSafe：面向跨具身潜空间安全过滤器
- [Intelligence Across Embodiments](/20251126-20261125-starter-x-embodiment/2609.27095v1-intelligence-across-embodiments)（`Arxiv2609` · 9.0分） — 跨具身形态的智能

## 建议阅读路线

按「入门 → 进阶 → 专题」由浅入深编排，点击标题可直接进入站内精读/速读页。

### 第一阶段 · 入门必读

1. [Intelligence Across Embodiments](/20251126-20261125-starter-x-embodiment/2609.27095v1-intelligence-across-embodiments)（跨具身形态的智能）
   - **推荐理由**：先读这篇立场文章，建立跨具身学习的整体问题框架：工程化对齐的短期收益与长期局限、具身多样性作为扩展轴的含义。
   - **信息与链接**：`Arxiv2609` · 2026-09-22 · 评分 9.0 · [原文](https://arxiv.org/pdf/2609.27095v1)

2. [ZETA: A Controlled Study of Zero-Shot Cross-Embodiment VLA Transfer for Tabletop Manipulation](/20251126-20261125-starter-x-embodiment/2609.02546v2-zeta-a-controlled-study-of-zero-shot-cross-embodiment-vla-transfer-for-tabletop-manipulation)（ZETA：面向桌面操作的零样本跨具身 VLA 迁移的受控研究）
   - **推荐理由**：在进入具体方法前，先理解零样本迁移的定义分歧与受控评测逻辑，避免后续混淆不同论文的“零样本”口径。
   - **信息与链接**：`Arxiv2609` · 2026-09-02 · 评分 10.0 · [原文](https://arxiv.org/pdf/2609.02546v1) / [原文](https://arxiv.org/pdf/2609.02546v2)

3. [Universal Actions for Enhanced Embodied Foundation Models](/conference/cvpr-2025/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper-universal-actions-for-enhanced-embodied-foundation-models)（用于增强具身基础模型的通用动作）
   - **推荐理由**：UniAct 是共享通用动作空间的代表性工作，读它可掌握“消除动作异构性”这一最直观的技术切入点。
   - **信息与链接**：`CVPR25` · 2025 · 评分 10.0 · [原文](https://openaccess.thecvf.com/content/CVPR2025/html/Zheng_Universal_Actions_for_Enhanced_Embodied_Foundation_Models_CVPR_2025_paper.html)

4. [Embedding Morphology into Transformers for Cross-Robot Policy Learning](/20251126-20261125-starter-x-embodiment/2603.00182v1-embedding-morphology-into-transformers-for-cross-robot-policy-learning)（将形态嵌入Transformer以实现跨机器人策略学习）
   - **推荐理由**：形态嵌入 Transformer 展示了另一条互补思路：不消除差异而是把运动学结构注入策略，适合与 UniAct 对照阅读。
   - **信息与链接**：`Arxiv2603` · 2026-02-26 · 评分 10.0 · [PDF](https://arxiv.org/pdf/2603.00182v1)

### 第二阶段 · 进阶精读

5. [One-Policy-Fits-All: Geometry-Aware Action Latents for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2603.14522v1-one-policy-fits-all-geometry-aware-action-latents-for-cross-embodiment-manipulation)（一策通用：面向跨具身操作的几何感知动作潜变量）
   - **推荐理由**：OPFA 把几何感知潜动作与统一重定向解码器结合，是共享动作空间路线的进阶版，可看到多末端执行器联合训练的完整设计。
   - **信息与链接**：`Arxiv2603` · 2026-03-15 · 评分 10.0 · [PDF](https://arxiv.org/pdf/2603.14522v1)

6. [OmniAct: One Policy, One Million Embodiments](/20251126-20261125-starter-x-embodiment/2611.33158v2-omniact-one-policy-one-million-embodiments)（OmniAct：一个策略，一百万种具身形态）
   - **推荐理由**：OmniAct 以运动学图为条件并用流匹配预测关节运动，代表形态条件化路线的前沿，读后可理解“具身特异行为”如何被生成。
   - **信息与链接**：`Arxiv2611` · 2026-11-24 · 评分 10.0 · [原文](https://arxiv.org/pdf/2611.33158v1) / [原文](https://arxiv.org/pdf/2611.33158v2)

7. [RoboMorpher: Scaling Robot Morphology Representations for Cross-Embodiment Action Prediction](/20251126-20261125-starter-x-embodiment/2611.24816v1-robomorpher-scaling-robot-morphology-representations-for-cross-embodiment-action-prediction)（RoboMorpher：规模化机器人形态表征以用于跨具身动作预测）
   - **推荐理由**：RoboMorpher 指出仅从关节值学习表征存在根本歧义，并给出关节角加连杆位姿的监督方案，是对形态条件化的重要深化。
   - **信息与链接**：`Arxiv2611` · 2026-11-18 · 评分 9.0 · [原文](https://arxiv.org/pdf/2611.24816v1)

8. [LAP: Language-Action Pre-Training Enables Zero-shot Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2602.10556v2-lap-language-action-pre-training-enables-zero-shot-cross-embodiment-transfer)（LAP：语言-动作预训练实现零样本跨具身迁移）
   - **推荐理由**：LAP 用自然语言表示动作实现零样本跨具身迁移，是 VLA 路线中配方最简洁的一篇，适合作为进入 VLA 预训练的入口。
   - **信息与链接**：`Arxiv2602` · 2026-02-11 · 评分 10.0 · [PDF](https://arxiv.org/pdf/2602.10556v2)

9. [Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization](/20251126-20261125-starter-x-embodiment/2601.12993v1-being-h05-scaling-human-centric-robot-learning-for-cross-embodiment-generalization)（Being-H0.5：规模化以人为中心的机器人学习以实现跨具身泛化）
   - **推荐理由**：Being-H0.5 展示了以人为中心的大规模数据配方与统一动作空间加混合专家的完整架构，是 VLA 跨具身预训练的规模化范例。
   - **信息与链接**：`Arxiv2601` · 2026-01-19 · 评分 10.0 · [PDF](https://arxiv.org/pdf/2601.12993v1)

10. [DyPES-VLA: Learning Shared Dynamics Priors and Embodiment-Specific Control for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2608.06374v1-dypes-vla-learning-shared-dynamics-priors-and-embodiment-specific-control-for-cross-embodiment-manipulation)（DyPES-VLA：学习共享动力学先验与具身特定控制以实现跨具身操作）
   - **推荐理由**：DyPES-VLA 把共享动力学先验与具身特定 MoE 动作头结合，读它可理解“共享什么、特异什么”的切分设计。
   - **信息与链接**：`Arxiv2608` · 2026-08-06 · 评分 10.0 · [原文](https://arxiv.org/pdf/2608.06374v1)

### 第三阶段 · 专题拓展

11. [BATCH: Behavior Alignment for Cross-Embodiment Learning from Humans](/20251126-20261125-starter-x-embodiment/2611.10148v1-batch-behavior-alignment-for-cross-embodiment-learning-from-humans)（BATCH：面向人类数据的跨具身学习中的行为对齐）
   - **推荐理由**：BATCH 系统处理人类示教与机器人之间的行为对齐，是进入人类数据利用专题的合适起点。
   - **信息与链接**：`Arxiv2611` · 2026-11-06 · 评分 9.0 · [原文](https://arxiv.org/pdf/2611.10148v1)

12. [Cross-Embodiment Transfer via Behavior-Aligned Representations](/20251126-20261125-starter-x-embodiment/2607.27549v1-cross-embodiment-transfer-via-behavior-aligned-representations)（通过行为对齐表征实现跨具身迁移）
   - **推荐理由**：该文系统比较了多种行为对齐表示对迁移的贡献，能帮助判断在 VLA 中应引入哪类中间表示。
   - **信息与链接**：`Arxiv2607` · 2026-07-30 · 评分 9.0 · [原文](https://arxiv.org/pdf/2607.27549v1)

13. [Demo-JEPA: Joint-Embedding Predictive Architecture for One-shot Cross-Embodiment Imitation](/20251126-20261125-starter-x-embodiment/2605.20811v1-demo-jepa-joint-embedding-predictive-architecture-for-one-shot-cross-embodiment-imitation)（Demo-JEPA：用于单样本跨具身模仿的联合嵌入预测架构）
   - **推荐理由**：Demo-JEPA 把演示视为未来目标而非动作序列，提供了与动作对齐截然不同的模仿视角，适合作为专题中的反思路径。
   - **信息与链接**：`Arxiv2605` · 2026-05-20 · 评分 9.0 · [PDF](https://arxiv.org/pdf/2605.20811v1)

14. [Latent Policy Steering: An Efficient and Flexible Framework for Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2609.22521v1-latent-policy-steering-an-efficient-and-flexible-framework-for-cross-embodiment-transfer)（潜在策略引导：一种高效且灵活的跨具身迁移框架）
   - **推荐理由**：LPS 展示世界模型如何以策略无关的方式引导目标具身策略，是理解世界模型路线实用价值的代表工作。
   - **信息与链接**：`Arxiv2609` · 2026-09-18 · 评分 9.0 · [原文](https://arxiv.org/pdf/2609.22521v1)

15. [Cross-Embodiment Offline Reinforcement Learning for Heterogeneous Robot Datasets](/20251126-20261125-starter-x-embodiment/2602.18025v1-cross-embodiment-offline-reinforcement-learning-for-heterogeneous-robot-datasets)（面向异构机器人数据集的跨具身离线强化学习）
   - **推荐理由**：该文在 16 种平台上分析跨具身离线强化学习中的梯度冲突与分组策略，为理解多具身联合训练的失败模式提供实证依据。
   - **信息与链接**：`Arxiv2602` · 2026-02-20 · 评分 9.0 · [官方论文集](https://proceedings.iclr.cc/paper_files/paper/2026/hash/24a0f56452202e8433d582dbf5095c32-Abstract-Conference.html) / [原文](https://openreview.net/forum?id=GrsoLVNy3Y) / [PDF](https://arxiv.org/pdf/2602.18025v1)

---

## 完整论文目录

> 缺失会议库存：eccv 2025、emnlp 2026

### 精读区（50 篇）

1. [Universal Actions for Enhanced Embodied Foundation Models](/conference/cvpr-2025/cvpr-2025-zheng-universal-actions-for-enhanced-embodied-foundation-models-cvpr-2025-paper-universal-actions-for-enhanced-embodied-foundation-models)（`CVPR25` · 10.0分）
   - 用于增强具身基础模型的通用动作
   - 通用动作空间对齐不同具身的动作空间
2. [Cross-Embodiment Dexterous Grasping with Reinforcement Learning](/conference/iclr-2025/openreview-iclr-2025-twipsx9qhn-cross-embodiment-dexterous-grasping-with-reinforcement-learning)（`ICLR25` · 9.0分）
   - 基于强化学习的跨具身灵巧抓取
   - 基于特征抓取空间的通用策略控制多种灵巧手
3. [From Multimodal LLMs to Generalist Embodied Agents: Methods and Lessons](/conference/cvpr-2025/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons)（`CVPR25` · 9.0分）
   - 从多模态大语言模型到通用具身智能体：方法与经验
   - 多具身动作分词器使单一通用智能体能在多样化具身经验上训练
4. [OmniAct: One Policy, One Million Embodiments](/20251126-20261125-starter-x-embodiment/2611.33158v2-omniact-one-policy-one-million-embodiments)（`Arxiv2611` · 10.0分）
   - OmniAct：一个策略，一百万种具身形态
   - 以机器人运动学为条件的单一跨具身策略覆盖百万具身
5. [Alignment Drives Reuse: Learning Generalizable Robot-Use Agents from Heterogeneous Experience](/20251126-20261125-starter-x-embodiment/2611.26376v1-alignment-drives-reuse-learning-generalizable-robot-use-agents-from-heterogeneous-experience)（`Arxiv2611` · 10.0分）
   - 对齐驱动复用：从异构经验中学习可泛化的机器人使用智能体
   - 对齐异构具身的感知、坐标约定与动作接口以学习共享技能集
6. [RoboMorpher: Scaling Robot Morphology Representations for Cross-Embodiment Action Prediction](/20251126-20261125-starter-x-embodiment/2611.24816v1-robomorpher-scaling-robot-morphology-representations-for-cross-embodiment-action-prediction)（`Arxiv2611` · 9.0分）
   - RoboMorpher：规模化机器人形态表征以用于跨具身动作预测
   - 形态条件动作分词器实现跨具身动作预测
7. [CIALLO: Learning Shared Intent Representations for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2611.13732v1-ciallo-learning-shared-intent-representations-for-cross-embodiment-manipulation)（`Arxiv2611` · 10.0分）
   - CIALLO：学习用于跨具身操作的共享意图表示
   - 用动作编解码器对齐不同具身动作，并由具身条件解码器还原
8. [BATCH: Behavior Alignment for Cross-Embodiment Learning from Humans](/20251126-20261125-starter-x-embodiment/2611.10148v1-batch-behavior-alignment-for-cross-embodiment-learning-from-humans)（`Arxiv2611` · 9.0分）
   - BATCH：面向人类数据的跨具身学习中的行为对齐
   - 用于操作技能迁移的跨具身行为对齐
9. [Meituan-Robotics-0: A Vision-Language-Action Foundation Model for Desktop Manipulation](/20251126-20261125-starter-x-embodiment/2611.08577v3-meituan-robotics-0-a-vision-language-action-foundation-model-for-desktop-manipulation)（`Arxiv2611` · 9.0分）
   - Meituan-Robotics-0：面向桌面操作的视觉-语言-动作基础模型
   - 在12种具身上训练并实现跨具身连续控制迁移的视觉语言动作基础模型
10. [Continuous-Action World Models: Learning Cross-Embodiment Spatiotemporal Dynamics Priors](/20251126-20261125-starter-x-embodiment/2610.40401v1-continuous-action-world-models-learning-cross-embodiment-spatiotemporal-dynamics-priors)（`Arxiv2610` · 9.0分）
   - 连续动作世界模型：学习跨具身时空动力学先验
   - 共享隐函数空间学习跨具身动作先验
11. [UMR: Universal Manipulation Representation](/20251126-20261125-starter-x-embodiment/2609.34256v2-umr-universal-manipulation-representation)（`Arxiv2609` · 10.0分）
   - UMR：通用操作表征
   - 统一动作表示实现跨具身零样本操作迁移
12. [Intelligence Across Embodiments](/20251126-20261125-starter-x-embodiment/2609.27095v1-intelligence-across-embodiments)（`Arxiv2609` · 9.0分）
   - 跨具身形态的智能
   - 论述跨具身差异累积学习与更广具身迁移的立场文章
13. [Latent Policy Steering: An Efficient and Flexible Framework for Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2609.22521v1-latent-policy-steering-an-efficient-and-flexible-framework-for-cross-embodiment-transfer)（`Arxiv2609` · 9.0分）
   - 潜在策略引导：一种高效且灵活的跨具身迁移框架
   - 复用其他具身经验、处理动作空间不匹配的跨具身迁移
14. [GALA: Geometry-Aware Latent Action Modeling for Vision-Language-Action Model Pretraining across Embodiments](/20251126-20261125-starter-x-embodiment/2609.21948v1-gala-geometry-aware-latent-action-modeling-for-vision-language-action-model-pretraining-across-embodiments)（`Arxiv2609` · 9.0分）
   - GALA：用于跨具身视觉-语言-动作模型预训练的几何感知潜在动作建模
   - 面向多具身VLA预训练的几何感知潜在动作建模
15. [X-WBC: A Cross-Embodiment Foundation Model for Humanoid Whole-Body Control](/20251126-20261125-starter-x-embodiment/2609.15213v1-x-wbc-a-cross-embodiment-foundation-model-for-humanoid-whole-body-control)（`Arxiv2609` · 9.0分）
   - X-WBC：一种用于人形机器人全身控制的跨具身基础模型
   - 跨具身基础模型，在多种人形机器人本体间共享单一策略
16. [ZETA: A Controlled Study of Zero-Shot Cross-Embodiment VLA Transfer for Tabletop Manipulation](/20251126-20261125-starter-x-embodiment/2609.02546v2-zeta-a-controlled-study-of-zero-shot-cross-embodiment-vla-transfer-for-tabletop-manipulation)（`Arxiv2609` · 10.0分）
   - ZETA：面向桌面操作的零样本跨具身 VLA 迁移的受控研究
   - 零样本跨具身VLA迁移的受控基准与定义
17. [DyPES-VLA: Learning Shared Dynamics Priors and Embodiment-Specific Control for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2608.06374v1-dypes-vla-learning-shared-dynamics-priors-and-embodiment-specific-control-for-cross-embodiment-manipulation)（`Arxiv2608` · 10.0分）
   - DyPES-VLA：学习共享动力学先验与具身特定控制以实现跨具身操作
   - 单一通用跨具身VLA，具身特定控制并自动对齐动作空间
18. [Cross-Embodiment Transfer via Behavior-Aligned Representations](/20251126-20261125-starter-x-embodiment/2607.27549v1-cross-embodiment-transfer-via-behavior-aligned-representations)（`Arxiv2607` · 9.0分）
   - 通过行为对齐表征实现跨具身迁移
   - 用行为对齐表示促进VLA模型的跨具身操作技能迁移
19. [Cross-Embodiment Robot Manipulation via a Unified Hand Action Space](/20251126-20261125-starter-x-embodiment/2607.03570v1-cross-embodiment-robot-manipulation-via-a-unified-hand-action-space)（`Arxiv2607` · 9.0分）
   - 基于统一手部动作空间的跨具身机器人操作
   - 基于球面的统一手部动作空间对齐不同机械手的动作
20. [Learning Action Priors for Cross-embodiment Robot Manipulation](/20251126-20261125-starter-x-embodiment/2606.26095v1-learning-action-priors-for-cross-embodiment-robot-manipulation)（`Arxiv2606` · 9.0分）
   - 面向跨具身机器人操作的动作先验学习
   - 在VLA跨模态对齐前用跨具身运动先验预训练动作模块
21. [EmbodiSteer: Steering Embodiment-Agnostic Visuomotor Policies with Joint-Space Guidance for Zero-Shot Cross-Embodiment Deployment](/20251126-20261125-starter-x-embodiment/2606.12965v1-embodisteer-steering-embodiment-agnostic-visuomotor-policies-with-joint-space-guidance-for-zero-shot-cross-embodiment-deployment)（`Arxiv2606` · 9.0分）
   - EmbodiSteer：利用关节空间引导调控具身无关视觉运动策略，实现零样本跨具身部署
   - 引导具身无关视觉运动策略实现零样本跨具身部署
22. [Shape Your Body: Value Gradients for Multi-Embodiment Robot Design](/20251126-20261125-starter-x-embodiment/2606.00702v1-shape-your-body-value-gradients-for-multi-embodiment-robot-design)（`Arxiv2606` · 9.0分）
   - 塑造你的身体：面向多具身机器人设计的价值梯度
   - 在多种机器人形态上训练单一具身感知策略与价值函数并复用
23. [X-DiffVLA: X-Embodied Diffusion Action Heads for Vision-Language-Action Models](/20251126-20261125-starter-x-embodiment/2605.25044v2-x-diffvla-x-embodied-diffusion-action-heads-for-vision-language-action-models)（`Arxiv2605` · 9.0分）
   - X-DiffVLA：用于视觉-语言-动作模型的X具身扩散动作头
   - 统一跨具身扩散动作头从跨具身数据学习通用策略
24. [Demo-JEPA: Joint-Embedding Predictive Architecture for One-shot Cross-Embodiment Imitation](/20251126-20261125-starter-x-embodiment/2605.20811v1-demo-jepa-joint-embedding-predictive-architecture-for-one-shot-cross-embodiment-imitation)（`Arxiv2605` · 9.0分）
   - Demo-JEPA：用于单样本跨具身模仿的联合嵌入预测架构
   - 单样本跨具身模仿，解耦意图与具身执行
25. [LACE: Latent Visual Representation for Cross-Embodiment Learning](/20251126-20261125-starter-x-embodiment/2605.16743v1-lace-latent-visual-representation-for-cross-embodiment-learning)（`Arxiv2605` · 9.0分）
   - LACE：面向跨具身学习的潜在视觉表征
   - 对齐人与机器人视觉表示以支持跨具身学习
26. [JoyAI-RA 0.1: A Foundation Model for Robotic Autonomy](/20251126-20261125-starter-x-embodiment/2604.20100v2-joyai-ra-01-a-foundation-model-for-robotic-autonomy)（`Arxiv2604` · 9.0分）
   - JoyAI-RA 0.1：面向机器人自主性的基础模型
   - 面向跨具身、显式动作空间统一的VLA基础模型
27. [HEX: Humanoid-Aligned Experts for Cross-Embodiment Whole-Body Manipulation](/20251126-20261125-starter-x-embodiment/2604.07993v2-hex-humanoid-aligned-experts-for-cross-embodiment-whole-body-manipulation)（`Arxiv2604` · 9.0分）
   - HEX：面向跨具身全身操作的人形对齐专家
   - 人形对齐通用状态表示支持跨异构具身可扩展学习
28. [One-Policy-Fits-All: Geometry-Aware Action Latents for Cross-Embodiment Manipulation](/20251126-20261125-starter-x-embodiment/2603.14522v1-one-policy-fits-all-geometry-aware-action-latents-for-cross-embodiment-manipulation)（`Arxiv2603` · 10.0分）
   - 一策通用：面向跨具身操作的几何感知动作潜变量
   - 通过几何感知共享潜动作空间实现跨具身单一策略
29. [Structural Action Transformer for 3D Dexterous Manipulation](/20251126-20261125-starter-x-embodiment/2603.03960v1-structural-action-transformer-for-3d-dexterous-manipulation)（`Arxiv2603` · 9.0分）
   - 用于三维灵巧操作的结构化动作Transformer
   - 通过结构化动作表示实现高自由度灵巧手的跨具身技能迁移
30. [Embedding Morphology into Transformers for Cross-Robot Policy Learning](/20251126-20261125-starter-x-embodiment/2603.00182v1-embedding-morphology-into-transformers-for-cross-robot-policy-learning)（`Arxiv2603` · 10.0分）
   - 将形态嵌入Transformer以实现跨机器人策略学习
   - 具身感知Transformer注入形态信息以学习单一跨机器人策略
31. [Cross-Embodiment Offline Reinforcement Learning for Heterogeneous Robot Datasets](/20251126-20261125-starter-x-embodiment/2602.18025v1-cross-embodiment-offline-reinforcement-learning-for-heterogeneous-robot-datasets)（`Arxiv2602` · 9.0分）
   - 面向异构机器人数据集的跨具身离线强化学习
   - 在16个平台的异构机器人轨迹上做离线强化学习
32. [MOTIF: Learning Action Motifs for Few-shot Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2602.13764v1-motif-learning-action-motifs-for-few-shot-cross-embodiment-transfer)（`Arxiv2602` · 10.0分）
   - MOTIF：学习动作基元以实现少样本跨具身迁移
   - 通过具身无关动作基元实现少样本跨具身迁移
33. [LAP: Language-Action Pre-Training Enables Zero-shot Cross-Embodiment Transfer](/20251126-20261125-starter-x-embodiment/2602.10556v2-lap-language-action-pre-training-enables-zero-shot-cross-embodiment-transfer)（`Arxiv2602` · 10.0分）
   - LAP：语言-动作预训练实现零样本跨具身迁移
   - 语言-动作预训练实现VLA策略的零样本跨具身迁移
34. [Scalable and General Whole-Body Control for Cross-Humanoid Locomotion](/20251126-20261125-starter-x-embodiment/2602.05791v3-scalable-and-general-whole-body-control-for-cross-humanoid-locomotion)（`Arxiv2602` · 10.0分）
   - 面向跨人形机器人运动的可扩展通用全身控制
   - 单一跨具身策略泛化到多种人形机器人并对齐观测与动作空间
35. [A Systematic Study of Data Modalities and Strategies for Co-training Large Behavior Models for Robot Manipulation](/20251126-20261125-starter-x-embodiment/2602.01067v1-a-systematic-study-of-data-modalities-and-strategies-for-co-training-large-behavior-models-for-robot-manipulation)（`Arxiv2602` · 9.0分）
   - 面向机器人操作的大型行为模型协同训练的数据模态与策略系统性研究
   - 系统研究含跨具身数据的大型行为模型协同训练
36. [Green-VLA: Staged Vision-Language-Action Model for Generalist Robots](/20251126-20261125-starter-x-embodiment/2602.00919v2-green-vla-staged-vision-language-action-model-for-generalist-robots)（`Arxiv2602` · 10.0分）
   - Green-VLA：面向通用机器人的分阶段视觉-语言-动作模型
   - 统一的具身感知动作接口，跨类人与机械臂
37. [Learning a Unified Latent Space for Cross-Embodiment Robot Control](/20251126-20261125-starter-x-embodiment/2601.15419v1-learning-a-unified-latent-space-for-cross-embodiment-robot-control)（`Arxiv2601` · 10.0分）
   - 学习用于跨具身机器人控制的统一潜空间
   - 统一人类与多种人形平台的共享潜空间及目标条件跨具身策略
38. [Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization](/20251126-20261125-starter-x-embodiment/2601.12993v1-being-h05-scaling-human-centric-robot-learning-for-cross-embodiment-generalization)（`Arxiv2601` · 10.0分）
   - Being-H0.5：规模化以人为中心的机器人学习以实现跨具身泛化
   - 统一动作空间与30种具身数据实现跨具身泛化
39. [CEI: A Unified Interface for Cross-Embodiment Visuomotor Policy Learning in 3D Space](/20251126-20261125-starter-x-embodiment/2601.09163v1-cei-a-unified-interface-for-cross-embodiment-visuomotor-policy-learning-in-3d-space)（`Arxiv2601` · 9.0分）
   - CEI：用于三维空间中跨具身视觉运动策略学习的统一接口
   - 统一接口对齐不同机械臂与末端执行器的轨迹
40. [UniBYD: A Unified Framework for Learning Robotic Manipulation Across Embodiments Beyond Imitation of Human Demonstrations](/20251126-20261125-starter-x-embodiment/2512.11609v2-unibyd-a-unified-framework-for-learning-robotic-manipulation-across-embodiments-beyond-imitation-of-human-demonstrations)（`Arxiv2512` · 9.0分）
   - UniBYD：面向跨具身机器人操作学习的统一框架——超越对人类演示的模仿
   - 跨多种机器人手部具身的统一操作策略学习框架
41. [TraceGen: World Modeling in 3D Trace Space Enables Learning from Cross-Embodiment Videos](/20251126-20261125-starter-x-embodiment/2511.21690v1-tracegen-world-modeling-in-3d-trace-space-enables-learning-from-cross-embodiment-videos)（`Arxiv2511` · 9.0分）
   - TraceGen：在三维轨迹空间中进行世界建模，实现从跨具身视频中学习
   - 通过3D轨迹空间从跨具身视频中学习
42. [OTTER: A Vision-Language-Action Model with Text-Aware Visual Feature Extraction](/conference/icml-2025/openreview-icml-2025-uhf0km7r5m-otter-a-vision-language-action-model-with-text-aware-visual-feature-extraction)（`ICML25` · 8.0分）
   - OTTER：一种具有文本感知视觉特征提取的视觉-语言-动作模型
   - 视觉语言动作模型根据视觉观察和语言指令预测机器人动作
43. [ManipTrans: Efficient Dexterous Bimanual Manipulation Transfer via Residual Learning](/conference/cvpr-2025/cvpr-2025-li-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning-cvpr-2025-paper-maniptrans-efficient-dexterous-bimanual-manipulation-transfer-via-residual-learning)（`CVPR25` · 8.0分）
   - ManipTrans：基于残差学习的高效灵巧双手操作迁移
   - 将人类双臂操作技能迁移至灵巧机器人手
44. [Nexus-VLA: Bridging Human and Robot Experiences via a Shared Hierarchical Semantic Latent Space](/20251126-20261125-starter-x-embodiment/2610.42021v1-nexus-vla-bridging-human-and-robot-experiences-via-a-shared-hierarchical-semantic-latent-space)（`Arxiv2610` · 8.0分）
   - Nexus-VLA：通过共享分层语义潜在空间连接人类与机器人经验
   - 通过共享语义潜空间对齐跨具身观测与动作的VLA策略
45. [HumiMimic: Mimetic Embodiment Transfer of Human-Humanoid Interaction from In-the-Wild Videos](/20251126-20261125-starter-x-embodiment/2610.36615v2-humimimic-mimetic-embodiment-transfer-of-human-humanoid-interaction-from-in-the-wild-videos)（`Arxiv2610` · 8.0分）
   - HumiMimic：从野外视频中实现人-人形机器人交互的模仿式具身迁移
   - 从人类交互视频进行跨人形具身的模仿式迁移
46. [CrossSafe: Towards Cross-Embodiment Latent Safety Filters](/20251126-20261125-starter-x-embodiment/2609.28984v2-crosssafe-towards-cross-embodiment-latent-safety-filters)（`Arxiv2609` · 8.0分）
   - CrossSafe：面向跨具身潜空间安全过滤器
   - 跨具身潜空间安全过滤器共享安全推理
47. [Co-VLA: Consensus-based Federated Training for Vision-Language-Action Models](/20251126-20261125-starter-x-embodiment/2609.19923v2-co-vla-consensus-based-federated-training-for-vision-language-action-models)（`Arxiv2609` · 8.0分）
   - Co-VLA：面向视觉-语言-动作模型的基于共识的联邦训练
   - 面向分散异构机器人数据的联邦VLA训练
48. [AnyWorld: Factorized Egocentric World Models for Cross-Embodiment Generalization](/20251126-20261125-starter-x-embodiment/2608.29242v2-anyworld-factorized-egocentric-world-models-for-cross-embodiment-generalization)（`Arxiv2608` · 8.0分）
   - AnyWorld：面向跨具身泛化的因子化自我中心世界模型
   - 跨具身世界模型，将人类视频扩展为多样的机器人本征轨迹
49. [CLAP: Cross-Embodiment Video World Models are Zero-Shot Physical Simulators](/20251126-20261125-starter-x-embodiment/2608.27406v1-clap-cross-embodiment-video-world-models-are-zero-shot-physical-simulators)（`Arxiv2608` · 8.0分）
   - CLAP：跨具身视频世界模型是零样本物理模拟器
   - 跨具身动作条件视频模型，可在人类与机器人视频上训练
50. [Riemann-1.0: An Embodied World Action Model for Physical AI](/20251126-20261125-starter-x-embodiment/2608.27033v1-riemann-10-an-embodied-world-action-model-for-physical-ai)（`Arxiv2608` · 8.0分）
   - Riemann-1.0：面向物理人工智能的具身世界动作模型
   - 统一建模具身特定动作的世界动作模型，兼具多具身策略与仿真器功能
