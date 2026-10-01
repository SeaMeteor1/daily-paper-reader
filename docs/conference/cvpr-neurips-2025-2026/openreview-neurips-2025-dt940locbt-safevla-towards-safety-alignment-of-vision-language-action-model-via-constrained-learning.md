---
title: "SafeVLA: Towards Safety Alignment of Vision-Language-Action Model via Constrained Learning"
title_zh: SafeVLA：通过约束学习实现视觉-语言-动作模型的安全对齐
authors: "Borong Zhang, Yuhao Zhang, Jiaming Ji, Yingshan Lei, Josef Dai, Yuanpei Chen, Yaodong Yang"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=dt940loCBT"
tags: ["query:vla"]
score: 7.0
evidence: VLA模型的安全对齐
tldr: 视觉-语言-动作模型有望成为通用机器人策略，但在真实部署中带来伤害环境、机器人自身及人类的风险。本文提出集成安全方法，系统建模安全需求，主动诱发多样不安全行为，并通过安全强化学习约束VLA策略，最终经针对性评估确保安全。该方法基于约束马尔可夫决策过程从极小极大角度优化VLA。这为VLA的安全对齐提供了系统化方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: VLA模型作为通用机器人策略在真实部署中带来环境、机器人和人类安全风险。
method: 提出集成安全方法，建模安全需求、诱发不安全行为并经安全强化学习约束策略。
result: 基于约束马尔可夫决策过程从极小极大角度优化VLA并通过评估验证安全性。
conclusion: 为VLA的安全对齐提供了系统化方案。
---

## Abstract
Vision-language-action models (VLAs) show potential as generalist robot policies. However, these models pose extreme safety challenges during real-world deployment, including the risk of harm to the environment, the robot itself, and humans. *How can safety constraints be explicitly integrated into VLAs?* We address this by exploring an integrated safety approach (ISA), systematically **modeling** safety requirements, then actively **eliciting** diverse unsafe behaviors, effectively **constraining** VLA policies via safe reinforcement learning, and rigorously **assuring** their safety through targeted evaluations. Leveraging the constrained Markov decision process (CMDP) paradigm, ISA optimizes VLAs from a min-max perspective against elicited safety risks. Thus, policies aligned through this comprehensive approach achieve the following key features: (I) effective **safety-performance trade-offs**, reducing the cumulative cost of safety violations by 83.58\% compared to the state-of-the-art method, while also maintaining task success rate (+3.85\%). (II) strong **safety assurance**, with the ability to mitigate long-tail risks and handle extreme failure scenarios. (III) robust **generalization** of learned safety behaviors to various out-of-distribution perturbations. The effectiveness is evaluated on long-horizon mobile manipulation tasks.

---

## 论文详细总结（自动生成）

### 1. 检索相关性
VLA模型的安全对齐。

### 2. 核心内容
视觉-语言-动作模型有望成为通用机器人策略，但在真实部署中带来伤害环境、机器人自身及人类的风险。本文提出集成安全方法，系统建模安全需求，主动诱发多样不安全行为，并通过安全强化学习约束VLA策略，最终经针对性评估确保安全。该方法基于约束马尔可夫决策过程从极小极大角度优化VLA。这为VLA的安全对齐提供了系统化方案。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=dt940loCBT](https://openreview.net/forum?id=dt940loCBT)
