---
title: "SAFE: Multitask Failure Detection for Vision-Language-Action Models"
title_zh: SAFE：视觉-语言-动作模型的多任务故障检测
authors: "Qiao Gu, Yuanliang Ju, Shengxiang Sun, Igor Gilitschenski, Haruki Nishimura, Masha Itkina, Florian Shkurti"
date: 2025
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openreview.net/pdf?id=XPyAukgsFf"
tags: ["query:vla"]
score: 5.0
evidence: 面向通用VLA策略的故障检测
tldr: 该文针对视觉-语言-动作模型在新任务上成功率有限、需要及时故障预警的问题，指出现有故障检测器仅在少数任务上训练与测试，难以泛化。作者提出多任务故障检测问题并给出SAFE检测器，使其能在未见任务与新环境中识别失败。实验验证该方法可提升通用机器人策略的安全性，为VLA部署时的可靠交互提供了保障机制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 通用VLA策略在新任务上成功率有限，需要能跨任务泛化的故障检测器。
method: 提出多任务故障检测问题并设计SAFE检测器，面向未见任务与新环境识别失败。
result: 检测器可泛化到新任务并给出及时预警。
conclusion: 为通用VLA策略的安全部署提供了故障检测保障。
---

## Abstract
While vision-language-action models (VLAs) have shown promising robotic behaviors across a diverse set of manipulation tasks, they achieve limited success rates when deployed on novel tasks out of the box. To allow these policies to safely interact with their environments, we need a failure detector that gives a timely alert such that the robot can stop, backtrack, or ask for help. However, existing failure detectors are trained and tested only on one or a few specific tasks, while generalist VLAs require the detector to generalize and detect failures also in unseen tasks and novel environments. In this paper, we introduce the multitask failure detection problem and propose SAFE, a failure detector for generalist robot policies such as VLAs. We analyze the VLA feature space and find that VLAs have sufficient high-level knowledge about task success and failure, which is generic across different tasks. Based on this insight, we design SAFE to learn from VLA internal features and predict a single scalar indicating the likelihood of task failure. SAFE is trained on both successful and failed rollouts and is evaluated on unseen tasks. SAFE is compatible with different policy architectures. We test it on OpenVLA, $\pi_0$, and $\pi_0$-FAST in both simulated and real-world environments extensively. We compare SAFE with diverse baselines and show that SAFE achieves state-of-the-art failure detection performance and the best trade-off between accuracy and detection time using conformal prediction. More qualitative results and code can be found at the project webpage: https://vla-safe.github.io/

---

## 论文详细总结（自动生成）

### 1. 检索相关性
面向通用VLA策略的故障检测。

### 2. 核心内容
该文针对视觉-语言-动作模型在新任务上成功率有限、需要及时故障预警的问题，指出现有故障检测器仅在少数任务上训练与测试，难以泛化。作者提出多任务故障检测问题并给出SAFE检测器，使其能在未见任务与新环境中识别失败。实验验证该方法可提升通用机器人策略的安全性，为VLA部署时的可靠交互提供了保障机制。

### 3. 对应检索需求
vision-language-action model for robot learning。

### 4. 来源与原文
- Source：NeurIPS-2025-Accepted
- OpenReview：[https://openreview.net/forum?id=XPyAukgsFf](https://openreview.net/forum?id=XPyAukgsFf)
