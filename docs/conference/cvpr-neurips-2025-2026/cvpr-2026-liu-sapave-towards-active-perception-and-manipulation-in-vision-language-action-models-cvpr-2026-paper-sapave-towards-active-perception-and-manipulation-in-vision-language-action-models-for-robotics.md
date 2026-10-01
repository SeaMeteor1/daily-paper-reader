---
title: "SaPaVe: Towards Active Perception and Manipulation in Vision-Language Action Models for Robotics"
title_zh: SaPaVe：面向机器人视觉-语言-动作模型的主动感知与操作
authors: "Liu, Mengzhen, Zhou, Enshen, Chi, Cheng, Han, Yi, Rong, Shanyu, Chen, Liming, Wang, Pengwei, Wang, Zhongyuan, Zhang, Shanghang"
date: 2026
publication_date: 2026
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
pdf: "https://openaccess.thecvf.com/content/CVPR2026/papers/Liu_SaPaVe_Towards_Active_Perception_and_Manipulation_in_Vision-Language_Action_Models_CVPR_2026_paper.pdf"
tags: ["query:vla"]
score: 8.0
evidence: 面向机器人主动感知与操作的端到端VLA框架
tldr: 复杂场景中的机器人需要主动调整视角并稳健地执行操作，但现有方法难以将语义驱动的主动感知与视角不变的操作执行统一起来。本文提出SaPaVe端到端框架，将相机动作与操作动作解耦，采用自底向上策略先训练语义相机控制再联合优化，并构建了ActiveViewPose-200K数据集。实验表明该框架以数据高效的方式统一了两类能力。该工作为VLA模型赋予主动感知与操作能力提供了新范式。
source: CVPR-2026-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 1247, \"height\": 768}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 1247, \"height\": 768}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-007.webp\", \"caption\": \"\", \"page\": 1, \"index\": 7, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-008.webp\", \"caption\": \"\", \"page\": 1, \"index\": 8, \"width\": 942, \"height\": 706}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-009.webp\", \"caption\": \"\", \"page\": 1, \"index\": 9, \"width\": 990, \"height\": 706}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-010.webp\", \"caption\": \"\", \"page\": 1, \"index\": 10, \"width\": 970, \"height\": 684}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-011.webp\", \"caption\": \"\", \"page\": 1, \"index\": 11, \"width\": 990, \"height\": 684}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-012.webp\", \"caption\": \"\", \"page\": 1, \"index\": 12, \"width\": 975, \"height\": 682}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-013.webp\", \"caption\": \"\", \"page\": 1, \"index\": 13, \"width\": 1001, \"height\": 659}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-014.webp\", \"caption\": \"\", \"page\": 1, \"index\": 14, \"width\": 970, \"height\": 682}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-015.webp\", \"caption\": \"\", \"page\": 1, \"index\": 15, \"width\": 960, \"height\": 633}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-016.webp\", \"caption\": \"\", \"page\": 1, \"index\": 16, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-017.webp\", \"caption\": \"\", \"page\": 4, \"index\": 17, \"width\": 325, \"height\": 475}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-018.webp\", \"caption\": \"\", \"page\": 4, \"index\": 18, \"width\": 434, \"height\": 364}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-019.webp\", \"caption\": \"\", \"page\": 4, \"index\": 19, \"width\": 362, \"height\": 678}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-020.webp\", \"caption\": \"\", \"page\": 4, \"index\": 20, \"width\": 1660, \"height\": 729}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-021.webp\", \"caption\": \"\", \"page\": 4, \"index\": 21, \"width\": 540, \"height\": 606}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-022.webp\", \"caption\": \"\", \"page\": 4, \"index\": 22, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-023.webp\", \"caption\": \"\", \"page\": 4, \"index\": 23, \"width\": 866, \"height\": 911}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-024.webp\", \"caption\": \"\", \"page\": 4, \"index\": 24, \"width\": 864, \"height\": 811}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-025.webp\", \"caption\": \"\", \"page\": 4, \"index\": 25, \"width\": 800, \"height\": 600}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-026.webp\", \"caption\": \"\", \"page\": 4, \"index\": 26, \"width\": 645, \"height\": 329}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-027.webp\", \"caption\": \"\", \"page\": 4, \"index\": 27, \"width\": 645, \"height\": 329}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-028.webp\", \"caption\": \"\", \"page\": 4, \"index\": 28, \"width\": 713, \"height\": 521}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-029.webp\", \"caption\": \"\", \"page\": 4, \"index\": 29, \"width\": 1280, \"height\": 953}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-030.webp\", \"caption\": \"\", \"page\": 4, \"index\": 30, \"width\": 1280, \"height\": 975}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-031.webp\", \"caption\": \"\", \"page\": 4, \"index\": 31, \"width\": 1280, \"height\": 957}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-032.webp\", \"caption\": \"\", \"page\": 4, \"index\": 32, \"width\": 640, \"height\": 480}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-033.webp\", \"caption\": \"\", \"page\": 4, \"index\": 33, \"width\": 902, \"height\": 719}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-034.webp\", \"caption\": \"\", \"page\": 5, \"index\": 34, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-035.webp\", \"caption\": \"\", \"page\": 5, \"index\": 35, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-036.webp\", \"caption\": \"\", \"page\": 5, \"index\": 36, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-037.webp\", \"caption\": \"\", \"page\": 5, \"index\": 37, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-038.webp\", \"caption\": \"\", \"page\": 5, \"index\": 38, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-039.webp\", \"caption\": \"\", \"page\": 5, \"index\": 39, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-040.webp\", \"caption\": \"\", \"page\": 5, \"index\": 40, \"width\": 1641, \"height\": 1231}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-041.webp\", \"caption\": \"\", \"page\": 5, \"index\": 41, \"width\": 1440, \"height\": 1097}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-042.webp\", \"caption\": \"\", \"page\": 5, \"index\": 42, \"width\": 1413, \"height\": 1077}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-043.webp\", \"caption\": \"\", \"page\": 5, \"index\": 43, \"width\": 1634, \"height\": 1146}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-044.webp\", \"caption\": \"\", \"page\": 5, \"index\": 44, \"width\": 1240, \"height\": 956}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-045.webp\", \"caption\": \"\", \"page\": 5, \"index\": 45, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-046.webp\", \"caption\": \"\", \"page\": 5, \"index\": 46, \"width\": 1280, \"height\": 785}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-047.webp\", \"caption\": \"\", \"page\": 5, \"index\": 47, \"width\": 2090, \"height\": 476}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-048.webp\", \"caption\": \"\", \"page\": 5, \"index\": 48, \"width\": 1006, \"height\": 752}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-049.webp\", \"caption\": \"\", \"page\": 5, \"index\": 49, \"width\": 1008, \"height\": 752}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-050.webp\", \"caption\": \"\", \"page\": 5, \"index\": 50, \"width\": 1008, \"height\": 758}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-051.webp\", \"caption\": \"\", \"page\": 5, \"index\": 51, \"width\": 1006, \"height\": 752}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-052.webp\", \"caption\": \"\", \"page\": 5, \"index\": 52, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-053.webp\", \"caption\": \"\", \"page\": 5, \"index\": 53, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-054.webp\", \"caption\": \"\", \"page\": 5, \"index\": 54, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-055.webp\", \"caption\": \"\", \"page\": 5, \"index\": 55, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-056.webp\", \"caption\": \"\", \"page\": 5, \"index\": 56, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-057.webp\", \"caption\": \"\", \"page\": 5, \"index\": 57, \"width\": 1280, \"height\": 960}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-058.webp\", \"caption\": \"\", \"page\": 6, \"index\": 58, \"width\": 1108, \"height\": 753}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-059.webp\", \"caption\": \"\", \"page\": 6, \"index\": 59, \"width\": 1214, \"height\": 750}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-060.webp\", \"caption\": \"\", \"page\": 6, \"index\": 60, \"width\": 1117, \"height\": 749}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-061.webp\", \"caption\": \"\", \"page\": 6, \"index\": 61, \"width\": 1080, \"height\": 746}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-062.webp\", \"caption\": \"\", \"page\": 6, \"index\": 62, \"width\": 1657, \"height\": 1077}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-063.webp\", \"caption\": \"\", \"page\": 6, \"index\": 63, \"width\": 1591, \"height\": 1082}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-064.webp\", \"caption\": \"\", \"page\": 6, \"index\": 64, \"width\": 1564, \"height\": 1078}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-065.webp\", \"caption\": \"\", \"page\": 6, \"index\": 65, \"width\": 1509, \"height\": 1062}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-066.webp\", \"caption\": \"\", \"page\": 6, \"index\": 66, \"width\": 1459, \"height\": 1093}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-067.webp\", \"caption\": \"\", \"page\": 6, \"index\": 67, \"width\": 1673, \"height\": 1077}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-068.webp\", \"caption\": \"\", \"page\": 6, \"index\": 68, \"width\": 1447, \"height\": 1086}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-069.webp\", \"caption\": \"\", \"page\": 6, \"index\": 69, \"width\": 1718, \"height\": 1100}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-070.webp\", \"caption\": \"\", \"page\": 6, \"index\": 70, \"width\": 1414, \"height\": 1082}, {\"url\": \"assets/figures/cvpr-2026-accepted/cvpr-2026-liu-sapave-towards-active-perception-and-manipulation-in-vision-language-action-models-cvpr-2026-paper/fig-071.webp\", \"caption\": \"\", \"page\": 6, \"index\": 71, \"width\": 1330, \"height\": 755}]"
motivation: 现有VLA方法难以统一语义驱动的主动感知与视角不变的操作执行。
method: 提出端到端框架，解耦相机与操作动作，先训练语义相机控制再联合优化，并构建20万图像-语言-相机运动数据集。
result: 在主动感知与操作任务上以数据高效方式取得统一且鲁棒的表现。
conclusion: 为VLA模型引入主动感知能力提供了统一框架与大规模数据支持。
---

## Abstract
Active perception and manipulation are crucial for robots to interact with complex scenes. Existing methods struggle to unify semantic-driven perception actively with robust, viewpoint-invariant execution accordingly. To this end, we propose SaPaVe, an end-to-end framework that jointly learns these capabilities in a data-efficient manner. Central to our approach is a decoupling of camera and manipulation actions, contrary to shared-action-space, and learning in a bottom-up strategy: we first train semantic camera control on our proposed large-scale dataset, then jointly optimizes both action types via hybrid data. To support this, we introduce ActiveViewPose-200K, comprising 200k image-language-camera movement pairs for semantic camera movement learning, and a 3D geometry-aware module that improves execution robustness under dynamic viewpoints. We further present ActiveManip-Bench, the first benchmark filling the gap to evaluate active manipulation. Extensive experiments in both simulation and real-world settings show that SaPaVe outperforms recent VLA models such as GR00T N1 and pi0, achieving up to 31.25% higher success rates in real-world tasks. Our results show that tightly coupled perception and execution, when trained with decoupled yet coordinated strategies, enable efficient and generalizable active manipulation.

---

## 论文详细总结（自动生成）

# SaPaVe 论文中文总结

## 1. 核心问题与整体含义

- **研究背景**：机器人要在复杂、动态、杂乱的场景中完成操作，需要两项互补能力——**语义主动感知**（策略性调整视角以揭示被遮挡或视野外的关键信息）与**主动视角执行**（把新获得的感知线索落地为即时动作，即使视角并非最优也能完成任务）。
- **现有方法的困境**：
  - 传统主动感知多被建模为 Next-Best-View 或 VQA 式的离散视角选择，**无法在连续相机位姿空间中精细控制**，且缺乏语义输入。
  - 主流 VLA 模型（如 GR00T N1、π0）大多在**固定、近最优的头部相机视角**下训练与评测，对视角偏移敏感，难以胜任主动视角执行。
  - 若简单地把相机动作并入 VLA 的统一动作空间，会**破坏大规模固定视角操作先验**，并因真实世界主动操作数据稀缺而难以扩展。
- **整体含义**：论文主张主动操作的关键在于"感知与执行的紧耦合"，但这种耦合应通过**解耦的动作空间 + 自底向上的训练**来实现，从而在数据高效的前提下同时获得语义主动感知与鲁棒执行能力。

## 2. 方法论

### 2.1 核心思想

- **解耦相机动作与操作动作**（而非共享动作空间）：相机运动是具身无关的、更易学习，先独立学习再联合优化，可减少相互干扰。
- **自底向上的两阶段训练**：先学语义相机控制，再联合优化两类动作。

### 2.2 问题形式化

- 学习策略 πθ：O × L → A，输入观测 Ot（RGB 图像 It 及可选 3D 几何信息 Gt，如深度图、相机内外参）与语言指令 L，输出动作轨迹 At = {Ahead,t, Aother,t}。
- 采用动作分块（action chunking）：头部相机动作为相对 pitch/yaw 调整（2 维），操作动作为 26 维关节位置增量（Unitree G1 人形机器人，双臂 7-DoF + 双手 6-DoF）。

### 2.3 关键架构组件

- **相机适配器（Camera Adapter）**：在 VLM 上以 LoRA 形式添加，学习语义主动感知先验，**不改变原 VLM 权重**，避免破坏通用语义理解。
- **解耦动作头（Decoupled Action Head）**：两个独立解码器分别处理相机运动与其他动作，轻量且便于快速学习。
- **通用空间知识注入（Universal Spatial Knowledge Injection）**：继承自强前馈 3D 几何模型的通用空间编码器，支持任意 3D 几何配置输入而无需重训或改架构；编码后的空间 token 与 VLM 输出 token 逐元素相加，注入动作去噪过程。

### 2.4 两阶段训练流程

- **Stage 1：语义主动感知对齐**。在 ActiveViewPose-200K 上训练相机适配器与相机动作解码器，监督相机运动，损失为预测头部相机运动与真值的均方误差：L_stage1 = L_MSE(Ahead,t, A*head,t)。完成后模型获得语义主动感知先验。
- **Stage 2：主动操作微调**。数据为 ActiveViewPose-200K 与主动操作机器人数据的混合；冻结相机适配器，训练解耦动作头，损失 L_stage2 = λhead·Lhead + λother·Lother，从而获得完整的主动操作技能。

### 2.5 数据集与基准构建

- **ActiveViewPose-200K**：首个大规模高质量语义主动感知数据集，含 20 万条图像–语言–最优相机运动对。构建流程为半自动化：从 Objaverse 收集 4k 高质量语义标注资产、500 个多样场景，用启发式算法生成图像–相机运动对，半自动构建 3,000 个任务模板，再由 GPT-4o 生成指令并人工精修。
- **ActiveManip-Bench**：首个面向主动操作的仿真基准，基于 NVIDIA Isaac Sim，搭载 G1 人形机器人（双 Inspire 手 + 主动头部相机），覆盖 100 个物体、20 个场景、12 个语义主动操作任务，且易于扩展。

## 3. 实验设计

### 3.1 数据集与场景

- **ActiveViewPose-200K**：分为 Train/Val/Test1/Test2。Test1 的指令含显式位置指示（如"在左边"）；Test2 省略详细相机运动描述，要求模型结合文本与图像推断。
- **ActiveManip-Bench（仿真）**：6 类任务——无遮挡/遮挡/视野外抓放，以及无遮挡/遮挡/视野外铰接物体操作。
- **真实世界遥操作数据集**：4 类任务——遮挡/视野外抓放、遮挡/视野外铰接操作。

### 3.2 对比方法

- 语义主动感知实验：Qwen2.5-VL-72B、Gemini-2.5-Pro、Multi-SpatialMLLM。
- 相机配置对比：固定相机、固定相机 + 腕部相机、主动相机 + 腕部相机、仅主动相机（本文）。
- VLA 对比：π0、GR00T-N1。

### 3.3 评价指标

- 统一报告成功率（%）。语义主动感知中，预测落在真值 pitch/yaw 容差内即视为成功。

### 3.4 实验组别

- 语义主动感知评测（表 1）
- 仿真中固定/动态相机评测（表 2）
- 与现有 VLA 模型对比（表 3）
- 泛化能力评测（表 4，涉及未见物体、光照、场景变化）
- 消融实验（表 5，覆盖 Stage 1/Stage 2、解耦动作头、相机适配器、通用空间知识注入）

## 4. 资源与算力

- **论文正文未明确说明**所使用的 GPU 型号、数量、训练时长或总算力开销。
- 论文仅提及模型规模约为 **2B 参数**（在语义主动感知任务上以 2B 规模超越 Gemini-2.5-Pro），以及相机适配器采用 LoRA 等轻量化设计，但未给出具体训练硬件配置。
- 因此，关于算力资源的信息在本篇论文中**存在明显缺失**，无法评估其训练成本与可复现性。

## 5. 实验数量与充分性

- **实验数量**：共约 5 组主要实验（语义主动感知、相机配置对比、VLA 对比、泛化、消融），其中消融含 4 个组件维度，泛化覆盖 3 类变化（物体、光照、场景），整体实验组数较为丰富。
- **充分性**：
  - 仿真与真实世界均有覆盖，且同时包含抓放与铰接物体操作两类任务，任务类型较全面。
  - 消融实验系统性地验证了两阶段训练、解耦动作头、相机适配器、空间知识注入各自的作用，逻辑清晰。
  - 泛化实验验证了模型对未见物体、光照与场景的鲁棒性。
- **客观性与公平性**：
  - 相机配置对比采用**相同底层架构**，仅改变相机设置，控制变量较好。
  - VLA 对比中，π0 与 GR00T-N1 均在相同数据上微调后比较，较为公平。
  - 但真实世界任务仅 4 类，样本量与任务多样性有限，且未报告多次随机种子或统计显著性，可能影响结论的稳健性。

## 6. 主要结论与发现

- **语义主动感知**：SaPaVe（Stage 1）在 ActiveViewPose-200K 上平均 84.3%，比 Gemini-2.5-Pro 高 11.6%（仅 2B 参数）；在需语义推断的 Test2 上优势尤为明显，说明**主动感知并非通用 VLM 的涌现能力，专门数据训练至关重要**。
- **动态视角必要性**：固定视角下遮挡与视野外任务成功率大幅下降（视野外任务下降超 60%）；固定 + 腕部相机仍不足；主动相机 + 腕部相机的增益有限甚至可能下降，说明**主视角的主动旋转才是关键**。
- **与 VLA 对比**：直接微调 π0、GR00T-N1 均不如 SaPaVe；真实世界平均成功率达 85%，超过 π0 达 40%、超过 GR00T-N1 达 31.25%。
- **自底向上策略有效**：缺少 Stage 1 时视野外铰接操作成功率减半；缺少 Stage 2 则整体成功率下降。
- **解耦动作空间正确**：统一动作解码器会同时损害语义主动感知先验与主动操作能力。
- **相机适配器优于全量微调**：全量微调在全部 4 个真实任务上均导致性能下降。
- **空间知识注入关键**：移除后即使在简单的遮挡抓放任务上也下降 15%。

## 7. 优点

- **方法设计亮点**：
  - 提出**解耦动作空间 + 自底向上两阶段训练**，巧妙规避了统一动作空间带来的先验破坏与数据冲突问题。
  - **相机适配器（LoRA）** 在保留 VLM 通用语义能力的同时学习主动感知先验，兼顾数据效率与泛化。
  - **通用空间知识注入**支持任意 3D 几何配置输入，无需重训或改架构，提升了动态视角下的执行鲁棒性。
- **数据与基准贡献**：
  - 构建了首个大规模语义主动感知数据集 ActiveViewPose-200K（20 万对），填补了固定视角数据的空白。
  - 提出首个主动操作仿真基准 ActiveManip-Bench，可复现性强、易于扩展，弥补了现有基准仅限固定视角的缺陷。
- **实验设计亮点**：
  - 仿真与真实世界双重验证，任务类型覆盖抓放与铰接操作。
  - 相机配置对比控制变量严谨，清晰论证了主动主视角的必要性。
  - 消融实验覆盖全部关键组件，结论具有说服力。

## 8. 不足与局限

- **算力信息缺失**：论文未报告 GPU 型号、数量与训练时长，难以评估训练成本与可复现性。
- **真实世界实验规模有限**：仅 4 类真实任务，样本量与任务多样性不足，且未报告多次实验的统计显著性，结论的稳健性有待加强。
- **平台依赖**：方法在 Unitree G1 人形机器人（26-DoF 操作 + 2-DoF 头部）上验证，向其他具身平台（如单臂 + 腕部相机）的迁移性未充分讨论。
- **基准仿真到现实的差距**：ActiveManip-Bench 为仿真环境，虽可复现，但与真实世界物理交互仍存在 sim-to-real 差距。
- **数据集构建依赖 GPT-4o 与启发式算法**：指令质量与相机运动最优性可能受生成流程限制，存在潜在偏差。
- **应用限制**：主动感知策略在高度动态或快速变化场景中的实时性与安全性未做深入讨论；额外视角（腕部相机）增益有限这一发现也提示多视角融合策略仍有优化空间。

（完）
