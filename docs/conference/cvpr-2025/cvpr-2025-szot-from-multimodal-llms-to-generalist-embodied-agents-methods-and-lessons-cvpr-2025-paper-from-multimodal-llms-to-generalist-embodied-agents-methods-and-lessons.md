---
title: "From Multimodal LLMs to Generalist Embodied Agents: Methods and Lessons"
title_zh: 从多模态大语言模型到通用具身智能体：方法与经验
authors: "Szot, Andrew, Mazoure, Bogdan, Attia, Omar, Timofeev, Aleksei, Agrawal, Harsh, Hjelm, Devon, Gan, Zhe, Kira, Zsolt, Toshev, Alexander"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Szot_From_Multimodal_LLMs_to_Generalist_Embodied_Agents_Methods_and_Lessons_CVPR_2025_paper.pdf"
tags: ["query:x-embodiment"]
score: 9.0
evidence: 多具身动作分词器使单一通用智能体能在多样化具身经验上训练
tldr: 多模态大语言模型能否统一处理具身智能、游戏、界面控制与规划等多样任务尚不清楚。作者提出将多模态LLM适配为通用具身智能体GEA，通过多具身动作分词器把不同领域的观测与动作统一到单一模型，并用大规模具身经验监督学习和交互仿真在线强化学习训练。实验分析了数据与算法选择对性能的影响，表明统一模型可跨多个具身领域落地，为跨具身通用机器人智能体提供了实践路径。
source: CVPR-2025-Accepted
selection_source: topic_research
id: cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper
canonical_id: "work:fdb22da385a01ad5e21299b4"
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
conference_acceptance_status: accepted
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 459, \"height\": 992}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 670, \"height\": 658}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 1190, \"height\": 1138}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 1080, \"height\": 1082}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 480, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 1, \"index\": 7, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 1, \"index\": 8, \"width\": 1080, \"height\": 720}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 3, \"index\": 9, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-010.webp\", \"caption\": \"\", \"page\": 3, \"index\": 10, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-011.webp\", \"caption\": \"\", \"page\": 3, \"index\": 11, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-012.webp\", \"caption\": \"\", \"page\": 3, \"index\": 12, \"width\": 452, \"height\": 452}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-013.webp\", \"caption\": \"\", \"page\": 3, \"index\": 13, \"width\": 768, \"height\": 512}]"
motivation: 探索多模态大语言模型能否从语言视觉任务扩展到具身智能、游戏、界面控制和规划等多样领域。
method: 将多模态LLM适配为通用具身智能体，采用多具身动作分词器统一不同领域的动作接口，并结合监督学习与在线强化学习训练。
result: 实验表明单一统一模型可在多个具身领域实现落地，并揭示数据与算法选择的重要性。
conclusion: 为构建跨领域、跨具身的通用机器人智能体提供了方法与实践经验。
---

## 摘要
我们考察多模态大语言模型（MLLMs）处理多样化领域的能力，这些领域超出了此类模型通常训练所涉及的传统语言与视觉任务。具体而言，我们关注具身人工智能、游戏、UI 控制和规划等方向。为此，我们提出一种将 MLLM 适配为通用具身智能体（GEA）的流程。GEA 是一个单一的统一模型，能够通过多具身动作分词器在这些不同领域中实现 grounding。GEA 通过监督学习在大规模具身经验数据集上进行训练，并在交互式模拟器中进行在线强化学习。我们探索了开发此类模型所需的数据与算法选择。我们的发现揭示了使用跨域数据和在线强化学习训练对于构建通用智能体的重要性。与其他通用模型和针对特定基准的方法相比，最终的 GEA 模型在多样化基准中的未见任务上取得了较强的泛化性能。

## Abstract
We examine the capability of Multimodal Large Language Models (MLLMs) to tackle diverse domains that extend beyond the traditional language and vision tasks these models are typically trained on. Specifically, our focus lies in areas such as Embodied AI, Games, UI Control, and Planning. To this end, we introduce a process of adapting an MLLM to a Generalist Embodied Agent (GEA). GEA is a single unified model capable of grounding itself across these varied domains through a multi-embodiment action tokenizer. GEA is trained with supervised learning on a large dataset of embodied experiences and with online RL in interactive simulators. We explore the data and algorithmic choices necessary to develop such a model. Our findings reveal the importance of training with cross-domain data and online RL for building generalist agents. The final GEA model achieves strong generalization performance to unseen tasks across diverse benchmarks compared to other generalist models and benchmark-specific approaches.

---

## 论文详细总结（自动生成）

# 《From Multimodal LLMs to Generalist Embodied Agents: Methods and Lessons》论文总结

## 一、核心问题与研究动机

- **背景**：多模态大语言模型（MLLM）在语言与图像理解上表现强大，视觉-语言-动作（VLA）模型也已在机器人操作、网页/UI 智能体等单一领域取得成功。但“**能否用单一模型统一覆盖具身智能、游戏、UI 控制、规划等差异极大的领域**”仍是一个开放问题。
- **难点**：
  - 各领域对物理与几何推理的要求不同；
  - 具身形态差异大（固定机械臂、移动底盘+机械臂、虚拟游戏角色、纯屏幕 UI）；
  - 任务常为长时程、部分可观测，需要跨长序列观测推理；
  - 动作空间既有连续控制（末端执行器、关节速度/位置）也有离散控制（语言化技能、点击/输入）。
- **核心假设**：这些领域存在共性，**跨域联合训练可能带来正向迁移**，使单一智能体优于只在单域训练的智能体。
- **贡献定位**：提出把预训练 MLLM 适配为**通用具身智能体 GEA**（Generalist Embodied Agent）的完整流程，并系统回答“需要什么样的数据和算法选择”。

## 二、方法论

### 2.1 问题形式化
- 建模为**目标条件 POMDP**：每个环境 \(M_i=(O_i,A_i,G_i,R_i)\)，观测为 RGB 图像（机器人相机或屏幕截图），目标 \(G_i\) 为自然语言指令。
- 模型输入：环境/具身提示 \(P_i\) + 任务指令 \(I\) + 最多 \(c=3\) 组交错的“观测-动作”历史；输出：当前动作 \(a_t\)。

### 2.2 多具身动作分词器（核心技术创新）
- 统一词表 \(V = V_{disc} \cup V_{cont}\)：
  - **离散动作**：用自然语言描述动作（如 “pick apple”“right”），再文本分词，构成 \(V_{disc}\)；
  - **连续动作**：训练 **Residual VQ-VAE（RVQ）** 把动作向量编码为 \(M\) 个 token \(k_1(a),\dots,k_M(a)\)，第 \(m\) 个码本编码“前面码本编码后的残差”，从而用少量 token 精确表示连续动作。
- **跨具身统一**：只用**一个** tokenizer/de-tokenizer 覆盖所有连续动作空间（末端执行器、关节速度、关节位置等）。做法是把所有动作向量 **padding 到最大维度**训练，推理时解码后 **按目标具身维度截断**。
- 配置：**2 个码本 × 512 token，token 向量维度 1024**；用 \(V_{cont}\) 替换原 LLM 词表中**最不常用**的 token。
- 基座模型：**LLaVA-OneVision**，选择理由是其在交错图文序列/视频上的长上下文能力，契合具身数据的长轨迹特性。

### 2.3 两阶段训练流程
- **Stage 1：监督指令微调（SFT）→ GEA-Base**
  - 数据 \(D=\bigcup_i D_i\) 覆盖全部环境；对动作 token（交互数据）或回答 token（视觉语言数据）做交叉熵：
    \[
    L_{SFT}(D)=-\sum_{(I,o_{t-c:t},a_{t-c:t})\in D}\log p(a_t\mid P,I,o_{t-c},a_{t-c},\dots,o_t)
    \]
  - 细节：全模型微调，75k 步，AdamW + cosine 衰减 + 前 10% 线性 warmup，lr \(1e^{-5}\)，全局 batch 256，观测上下文 \(c=3\)。
- **Stage 2：在线强化学习（PPO）+ 联合 SFT → GEA**
  - 仅在部分有仿真器的域 \(E_{PPO}=\{\text{HabPick, LangR, Procgen}\}\) 做在线 RL，同时保留全部域的 SFT 损失：
    \[
    L_{GEA}=\sum_{i\in E_{PPO}}L_{PPO}(M_i)+\omega\sum_{i\in E}L_{SFT}(D_i),\quad \omega=0.1
    \]
  - PPO 细节：价值函数为从零初始化的 MLP，输入为动作 token 前一步的 LLM 末层激活 + 视觉编码器嵌入的平均池化（可选加入训练期才有的特权状态）；用 **PopArt** 做回报归一化以适配各域不同奖励尺度；用**约束解码**把采样限制在合法动作空间；对熵做按环境归一化，使单一熵系数通用。
  - 为省显存采用 **LoRA** 微调 LLM、冻结其余组件；rollout 长度 128，lr \(3e^{-4}\)，熵系数 \(1e^{-4}\)，价值损失权重 \(1.5e^{-4}\)，共 100M 累计环境步。

## 三、实验设计

### 3.1 数据集（SFT 共 2.2M 条成功轨迹）
- **静态操作**：OpenX（1.2M，22 种真实机器人）、Meta-World（45k，脚本）、CALVIN（18k，人类）、ManiSkill（5k，运动规划）。
- **移动操作**：Habitat Pick / Place（各 50k，RL 专家）。
- **导航**：Habitat Nav（13k，最短路径）、BabyAI（50k，最短路径）。
- **规划**：LangR（150k，RL 专家）。
- **视频游戏**：Procgen（320k）、Atari（286k），均为 RL 专家。
- **UI 控制**：AndroidControl（14k，人类，覆盖 833 个 App）。
- **视觉语言指令数据**：VQAv2、OKVQA、A-OKVQA、GQA、LLaVA-Instruct-150k，用于缓解遗忘、增强泛化。

### 3.2 Benchmark 与对比方法
- 评测 11 个 benchmark：Meta-World、CALVIN（ABC→D）、ManiSkill、Habitat Pick、Habitat Place、Procgen（16 游戏）、Atari（44 游戏）、Habitat Nav、BabyAI、AndroidControl、LangR；泛化类型包括新物体位置、新场景/房屋、新背景、新指令、新任务。
- 对比两类基线：
  - **领域专家**（只在该 benchmark 数据上训练）：MLLM+IL、IL+点云（3D Diffuser Actor）、IL / IL+PPO、离线 RL（Multi-Game DT）、RL+仿真真值状态等；
  - **领域通才**：Gato、GPT-4o + Set-of-Marks。
- 公平性说明：GEA 只用 RGB 图像、不用特权信息（真值状态、点云）；表中用灰色标注了使用额外输入模态、因而“不完全可比”的基线。

### 3.3 消融/分析实验
1. **RL 的作用**（表 3）：GEA vs GEA-Base（7B）在 RL 域与其余域上的对比。
2. **跨域数据 vs 单域数据**（表 4）：以 LLaVA-OV-500m 为基座，比较“仅域内数据”与“全域数据”。
3. **预训练权重的作用**（表 4）：仅初始化 LLM / 仅初始化视觉编码器 / 都不初始化 / 完整 MLLM。
4. **策略自采数据的三种用法对比**（图 4，Habitat Pick）：Success-SFT、IQL 离线 RL、PPO 在线 RL。
5. **基座模型规模与家族**（图 5）：LLaVA-OneVision 0.5B/7B、MM1.5 1.2B/6.4B。
6. 附录：数据集两两迁移性分析（G.4）、RL 样本效率分析（G.2）。

## 四、资源与算力

- **Stage 1（SFT）**：8 个节点 × 8×H100（即 64 张 H100），约 **2 天**；75k 更新、全局 batch 256。
- **Stage 2（在线 RL）**：8 个节点 × 8×H100，约 **1 天**；每 GPU 4 个并行环境，节点内按 3 GPU（HabPick）/3 GPU（Procgen）/2 GPU（LangR）划分环境，SFT 每设备 batch 2，共 100M 累计步。
- **分析实验**：为降低开销统一缩至 32% 的 SFT 数据、40k 更新、每个 benchmark 约 200 条评测 episode。
- 注：文中未给出总 GPU 小时数；按上述描述推算，两阶段合计约 **4,600 GPU-hours（H100）** 量级（仅为估算，非原文数字）。数据采集、tokenizer 训练与附录实验的算力未在正文明确列出。

## 五、实验数量与充分性

- **规模**：主实验覆盖 **11 个 benchmark、5 大领域、10+ 种具身/动作空间**，对比约 15 个基线（专家 + 通才）；另有 4 组系统性消融（RL、跨域数据、预训练初始化、模型规模/家族）与 2 组附录深入分析。
- **充分性**：整体较为充分——既有“对标 SOTA”的横向评测，也有针对“数据从哪来、模型从哪初始化、RL 是否必要”的纵向拆解；对 RL 还额外做了 Success-SFT / 离线 RL / 在线 RL 的三方对照，直接回应模仿学习中的 covariate shift 问题。
- **客观性/公平性**：
  - 优点：明确标注了使用点云或仿真真值状态的基线“不可直接比较”；说明部分基线训练/测试划分不透明（如 Gato 数据未公开）；所有评测均为在线交互（AndroidControl 除外，为与真值轨迹比对）。
  - 保留意见：消融实验为节省算力使用 500m 小模型、32% 数据和约 200 episode，绝对数值与主表不可直接对齐；部分基线数字引自原论文，评测协议（episode 数、随机种子、方差）未在正文完整披露，缺少误差棒/显著性检验。

## 六、主要结论与发现

- **单一模型可跨域通用**：GEA 在多个 benchmark 上达到或接近专家水平，并普遍优于其他通才模型。
  - Meta-World 94.7%（优于 MLLM+IL 84.0 与 Gato 87.0）；
  - CALVIN ABC→D 90.0%（超同类 MLLM 方法约 10 个点，接近使用点云+深度的 3D Diffuser Actor 92.2%）；
  - Habitat Pick 82.5%（远超 IL 的 29%，并超过使用仿真真值状态的 RL 策略 81.0）；
  - Procgen 44.0% 专家分（比此前专家模型高近 20 点）；Atari 32.7%（优于 Gato 31）；
  - AndroidControl 57.3%（优于 GPT-4o+SoM 的 45%）；BabyAI 91.1%、LangR 50.0%、Habitat Nav 62.5%、Habitat Place 93.5% 接近但略逊专家。
- **在线 RL 是关键增益来源**：在做过 RL 的三个域上提升显著（HabPick 60.5→82.5、LangR 15.5→50.0、Procgen 36.1→44.0），其余域因联合 SFT 而基本不掉（69.5→70.5）。Habitat Pick 上在线 RL 把成功率从 57% 提到 83%，明显优于 Success-SFT 与 IQL 离线 RL（后两者甚至在 GEA-Base 之上**下降**）。
- **跨域数据有正迁移**：全域联合训练在所有 benchmark 上均优于单域训练；与其它域重叠少的域（AndroidControl、Procgen）增益较小。
- **预训练 MLLM 不可替代**：完整初始化远优于仅初始化 LLM 或仅初始化视觉编码器或随机初始化；其中**视觉编码器的初始化影响更大**（具身数据不足以从零训练 SigLIP）。
- **规模有效、家族无关**：0.5B→7B（LLaVA-OV）、1.2B→6.4B（MM1.5）性能随参数量提升；但不同 7B 级基座（不同网页级预训练数据）差异可忽略。
- **RL 必须建立在 SFT 之上**：单独用 RL 无法把基座 MLLM 拉到 GEA-Base 水平；GEA-Base 的 RL 样本效率也远高于原始 MLLM。

## 七、优点

- **架构统一性强**：单一 RVQ 动作分词器同时覆盖离散与连续、静态与移动、真实与虚拟具身，通过 padding+截断实现“一套词表控制多种具身”，工程上简洁可复用。
- **训练范式清晰且可验证**：“大规模跨域 SFT + 少量域在线 RL（LoRA+PPO）”的两阶段设计，被消融实验逐项验证，不是黑箱堆料。
- **评测覆盖面广、跨域跨度大**：从真实机器人数据（OpenX）到 Atari/Procgen 游戏、再到 Android UI，属同类工作中域覆盖较宽的一档。
- **对基线公平性有自觉**：显式区分专家/通才、标注特权信息使用情况，并主动指出自身在 ManiSkill/Atari 上落后于使用 RL 或离线 RL 的方法。
- **若干“经验教训”具普适价值**：在线 RL 优于自采数据 SFT 与离线 RL；视觉编码器初始化比 LLM 初始化更关键；跨域数据带来正迁移。

## 八、不足与局限

- **作者自述局限**：GEA 尚不是“决策领域的基础模型”，无法零样本控制任意具身、在任意环境运行；ManiSkill、Atari、AndroidControl 上性能仍远未饱和（ManiSkill 仅 13.6%，Atari 32.7% 对比离线 RL 的 85%）。
- **RL 覆盖有限**：在线 RL 只用于 3 个域（HabPick、LangR、Procgen），Atari、ManiSkill、UI 控制等仍纯靠 SFT，导致这些域明显落后于使用 RL 的专家。
- **上下文受限**：观测历史仅 3 帧，部分可观测/长时程场景（如 Habitat Nav 62.5% vs 专家 72%）受限，缺少记忆机制的讨论。
- **评测局限**：全部在仿真/离线数据中进行，**无真实机器人闭环部署**；AndroidControl 用与真值轨迹的对应关系代替在线成功率，与其它 benchmark 指标不同质；未报告方差、置信区间与随机种子数，统计显著性不明。
- **消融规模偏小**：分析实验用 500m 模型 + 32% 数据 + ~200 episode，结论向 7B 全量模型的迁移性未完全验证；跨域迁移的细粒度分析放在附录。
- **对比口径风险**：部分基线数字直接引用原论文，训练/测试划分与评测协议不完全一致（作者亦承认 Gato 数据未公开）；不同工作的专家分定义、episode 预算可能不同，横向比较存在偏差风险。
- **数据偏差**：SFT 数据几乎全为**成功轨迹**（OpenX、脚本、RL 专家、最短路径），缺少失败与恢复行为，正是需要靠 RL 弥补的短板；数据分布严重偏向操作类（OpenX 1.2M 占多数），可能影响非操作域的迁移收益。
- **应用限制**：动作分词器的 padding 到最大维度、按具身截断的做法在动作维度差异极大或高维灵巧操作场景下可能损失精度；对未见具身仍需人工提供环境提示 \(P_i\)，并非真正“零样本新具身”。

（完）
