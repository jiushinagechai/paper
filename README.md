# 教育相关前沿论文精选

收录本次选定的 **20 篇论文**，覆盖 ICLR 2025、ICLR 2026 和 NeurIPS 2026，按 7 个方向整理。

整理日期：2026-11-11。会议来源已通过官方论文页面核对。PDF 使用作者在 arXiv 公开的版本，具体版本号、下载地址、页数、文件大小和 SHA-256 校验值见 [metadata.json](metadata.json)。这些 PDF 可能与会议最终排版版存在差异。

教育应用说明依据官方摘要整理；部分论文研究基础方法，教育关联是可能的延伸，不代表已验证真实学生的学习效果。

## 论文索引

### 大模型与课程学习

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 01 | Training Language Models to Self-Correct via Reinforcement Learning | ICLR 2025 | 用多轮强化学习训练大模型自我纠错，可延伸到数学辅导反馈。 | [PDF](papers/01_%E5%A4%A7%E6%A8%A1%E5%9E%8B%E4%B8%8E%E8%AF%BE%E7%A8%8B%E5%AD%A6%E4%B9%A0/01_SCoRe_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/30501) · [arXiv](https://arxiv.org/abs/2409.12917v2) |
| 02 | Pedagogically-Inspired Data Synthesis for Language Model Knowledge Distillation | ICLR 2026 | 结合掌握学习与最近发展区，通过知识诊断、课程组织和适应调整进行知识蒸馏；学生指模型。 | [PDF](papers/01_%E5%A4%A7%E6%A8%A1%E5%9E%8B%E4%B8%8E%E8%AF%BE%E7%A8%8B%E5%AD%A6%E4%B9%A0/02_Pedagogical_Knowledge_Distillation_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10010897) · [arXiv](https://arxiv.org/abs/2602.12172v1) |
| 16 | DataEnvGym: Data Generation Agents in Teacher Environments with Student Feedback | ICLR 2025 | 数据生成智能体依据学生模型的错误反馈，迭代生成训练数据。 | [PDF](papers/01_%E5%A4%A7%E6%A8%A1%E5%9E%8B%E4%B8%8E%E8%AF%BE%E7%A8%8B%E5%AD%A6%E4%B9%A0/16_DataEnvGym_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/31276) · [arXiv](https://arxiv.org/abs/2410.06215v3) |

### 智能体与人机协作

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 03 | SeCom: On Memory Construction and Retrieval for Personalized Conversational Agents | ICLR 2025 | 通过话题分段与压缩构建长期对话记忆，可延伸到持续陪伴的学习助手。 | [PDF](papers/02_%E6%99%BA%E8%83%BD%E4%BD%93%E4%B8%8E%E4%BA%BA%E6%9C%BA%E5%8D%8F%E4%BD%9C/03_SeCom_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/27790) · [arXiv](https://arxiv.org/abs/2502.05589v3) |
| 04 | Scaling Large Language Model-based Multi-Agent Collaboration | ICLR 2025 | 研究智能体数量、协作网络结构与任务表现之间的关系。 | [PDF](papers/02_%E6%99%BA%E8%83%BD%E4%BD%93%E4%B8%8E%E4%BA%BA%E6%9C%BA%E5%8D%8F%E4%BD%9C/04_Scaling_Multi_Agent_Collaboration_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/30077) · [arXiv](https://arxiv.org/abs/2406.07155v3) |
| 05 | Adaptive Collaboration with Humans: Metacognitive Policy Optimization for Multi-Agent LLMs with Continual Learning | ICLR 2026 | 学习何时自主解题、何时请求人类专家帮助，并持续吸收专家反馈。 | [PDF](papers/02_%E6%99%BA%E8%83%BD%E4%BD%93%E4%B8%8E%E4%BA%BA%E6%9C%BA%E5%8D%8F%E4%BD%9C/05_Human_Agent_Adaptive_Collaboration_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10010313) · [arXiv](https://arxiv.org/abs/2603.07972v1) |

### 多模态与数学教育

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 06 | From EduVisBench to EduVisAgent: A Benchmark and Multi-Agent Framework for Reasoning-Driven Pedagogical Visualization | ICLR 2026 | 评测并生成推理驱动的教学可视化解释，采用多智能体协作。 | [PDF](papers/03_%E5%A4%9A%E6%A8%A1%E6%80%81%E4%B8%8E%E6%95%B0%E5%AD%A6%E6%95%99%E8%82%B2/06_EduVisAgent_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10010594) · [arXiv](https://arxiv.org/abs/2505.16832v2) |
| 07 | VisioMath: Benchmarking Figure-based Mathematical Reasoning in LMMs | ICLR 2026 | 以图形作为答案选项，评测 K–12 数学题中的细粒度图形比较和图文推理。 | [PDF](papers/03_%E5%A4%9A%E6%A8%A1%E6%80%81%E4%B8%8E%E6%95%B0%E5%AD%A6%E6%95%99%E8%82%B2/07_VisioMath_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10011683) · [arXiv](https://arxiv.org/abs/2506.06727v4) |
| 17 | GeoDial: A Multimodal Dialog Tutoring Dataset for Geometry Problem-Solving with Visual Tutor Turns | NeurIPS 2026 | 几何教学多模态对话数据集，将教师讲解与图形高亮相对应。 | [PDF](papers/03_%E5%A4%9A%E6%A8%A1%E6%80%81%E4%B8%8E%E6%95%B0%E5%AD%A6%E6%95%99%E8%82%B2/17_GeoDial_NeurIPS2026.pdf) · [会议官网](https://neurips.cc/virtual/2026/poster/139470) · [arXiv](https://arxiv.org/abs/2606.12419v1) |

### 情感计算与共情

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 08 | EmotionThinker: Prosody-Aware Reinforcement Learning for Explainable Speech Emotion Reasoning | ICLR 2026 | 结合韵律感知与强化学习，识别语音情绪并提供声学证据解释。 | [PDF](papers/04_%E6%83%85%E6%84%9F%E8%AE%A1%E7%AE%97%E4%B8%8E%E5%85%B1%E6%83%85/08_EmotionThinker_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10006716) · [arXiv](https://arxiv.org/abs/2601.15668v2) |
| 09 | MME-Emotion: A Holistic Evaluation Benchmark for Emotional Intelligence in Multimodal Large Language Models | ICLR 2026 | 评测多模态大模型的情绪识别、理解与原因推理能力。 | [PDF](papers/04_%E6%83%85%E6%84%9F%E8%AE%A1%E7%AE%97%E4%B8%8E%E5%85%B1%E6%83%85/09_MME_Emotion_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10007409) · [arXiv](https://arxiv.org/abs/2508.09210v2) |
| 10 | RLVER: Reinforcement Learning with Verifiable Emotion Rewards for Empathetic Agents | ICLR 2026 | 利用模拟用户提供的可验证情绪奖励训练共情智能体。 | [PDF](papers/04_%E6%83%85%E6%84%9F%E8%AE%A1%E7%AE%97%E4%B8%8E%E5%85%B1%E6%83%85/10_RLVER_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10009708) · [arXiv](https://arxiv.org/abs/2507.03112v1) |

### 持续学习与遗忘

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 11 | Spurious Forgetting in Continual Learning of Language Models | ICLR 2025 | 区分任务对齐受损与知识真正丢失，分析持续学习中的伪遗忘。 | [PDF](papers/05_%E6%8C%81%E7%BB%AD%E5%AD%A6%E4%B9%A0%E4%B8%8E%E9%81%97%E5%BF%98/11_Spurious_Forgetting_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/29593) · [arXiv](https://arxiv.org/abs/2501.13453v1) |
| 12 | Unlocking the Power of Function Vectors for Characterizing and Mitigating Catastrophic Forgetting in Continual Instruction Tuning | ICLR 2025 | 通过功能向量分析持续指令微调中的遗忘，并以正则化缓解遗忘。 | [PDF](papers/05_%E6%8C%81%E7%BB%AD%E5%AD%A6%E4%B9%A0%E4%B8%8E%E9%81%97%E5%BF%98/12_Function_Vectors_Continual_Instruction_Tuning_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/28810) · [arXiv](https://arxiv.org/abs/2502.11019v2) |
| 13 | Sculpting Subspaces: Constrained Full Fine-Tuning in LLMs for Continual Learning | ICLR 2026 | 保留旧知识的关键参数子空间，约束新任务更新方向以降低遗忘。 | [PDF](papers/05_%E6%8C%81%E7%BB%AD%E5%AD%A6%E4%B9%A0%E4%B8%8E%E9%81%97%E5%BF%98/13_Sculpting_Subspaces_OSFT_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10006812) · [arXiv](https://arxiv.org/abs/2504.07097v1) |

### 个性化与偏好

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 14 | Do LLMs Recognize Your Preferences? Evaluating Personalized Preference Following in LLMs | ICLR 2025 | 通过 PrefEval 评测长期对话中用户偏好的推断、记忆和遵循。 | [PDF](papers/06_%E4%B8%AA%E6%80%A7%E5%8C%96%E4%B8%8E%E5%81%8F%E5%A5%BD/14_PrefEval_ICLR2025.pdf) · [会议官网](https://iclr.cc/virtual/2025/poster/29686) · [arXiv](https://arxiv.org/abs/2502.09597v1) |
| 15 | FSPO: Few-Shot Optimization of Synthetic Preferences Effectively Personalizes to Real Users | ICLR 2026 | 结合合成偏好与少样本优化适配真实用户，实验包含教育领域。 | [PDF](papers/06_%E4%B8%AA%E6%80%A7%E5%8C%96%E4%B8%8E%E5%81%8F%E5%A5%BD/15_FSPO_ICLR2026.pdf) · [会议官网](https://iclr.cc/virtual/2026/poster/10009369) · [arXiv](https://arxiv.org/abs/2502.19312v2) |

### 教学决策与学习评价

| 编号 | 论文 | 会议 | 阅读切入点 | 下载与来源 |
| --- | --- | --- | --- | --- |
| 18 | DICE: Decoupling Capability from Intervention Necessity in LLM Tutoring | NeurIPS 2026 | 区分辅导能力与干预必要性，学习何时介入教学对话；摘要效果来自模拟辅导。 | [PDF](papers/07_%E6%95%99%E5%AD%A6%E5%86%B3%E7%AD%96%E4%B8%8E%E5%AD%A6%E4%B9%A0%E8%AF%84%E4%BB%B7/18_DICE_NeurIPS2026.pdf) · [会议官网](https://neurips.cc/virtual/2026/poster/151451) · [arXiv](https://arxiv.org/abs/2610.04825v1) |
| 19 | L2-Bench: An Evaluation Benchmark for Measuring LLM Capabilities in Second Language Education | NeurIPS 2026 | 面向二语学习与评价的教学能力评测基准。 | [PDF](papers/07_%E6%95%99%E5%AD%A6%E5%86%B3%E7%AD%96%E4%B8%8E%E5%AD%A6%E4%B9%A0%E8%AF%84%E4%BB%B7/19_L2_Bench_NeurIPS2026.pdf) · [会议官网](https://neurips.cc/virtual/2026/poster/139497) · [arXiv](https://arxiv.org/abs/2607.08842v2) |
| 20 | An Information-Theoretic Evaluation Framework for Benchmark and Model Diagnosis in Knowledge Tracing | NeurIPS 2026 | 通过局部不可约不确定性与信息论诊断知识追踪基准和模型。 | [PDF](papers/07_%E6%95%99%E5%AD%A6%E5%86%B3%E7%AD%96%E4%B8%8E%E5%AD%A6%E4%B9%A0%E8%AF%84%E4%BB%B7/20_Knowledge_Tracing_Information_Theory_NeurIPS2026.pdf) · [会议官网](https://neurips.cc/virtual/2026/poster/149407) · [arXiv](https://arxiv.org/abs/2610.06988v1) |

## 版本与题名说明

- SeCom 的 arXiv 标题为 *On Memory Construction and Retrieval for Personalized Conversational Agents*，未包含会议标题中的 SeCom 前缀。
- FSPO 的 arXiv 标题为 *FSPO: Few-Shot Optimization of Synthetic Preferences Personalizes to Real Users*，与会议标题存在轻微差异。
- GeoDial 的 arXiv 标题包含 *Multimodal Conversational Tutoring Dataset*，会议标题为 *Multimodal Dialog Tutoring Dataset*。
- 元数据同时保留会议题名与 arXiv 题名，便于对应核查。

## 文件说明

- `papers/`：按方向整理的论文原文 PDF。
- `metadata.json`：每篇论文的来源、作者、版本与文件校验信息。
- 原论文版权及许可归各自作者或权利人，具体以论文及原始发布页面为准。
