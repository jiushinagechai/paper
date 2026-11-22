# MARS: Multi-Agent Adaptive Reasoning with Socratic Guidance for Automated Prompt Optimization

> Source coverage: Full paper PDF available; 主文方法与实验重点阅读，附录提供定位，非逐句翻译
> Extraction confidence: high; 图像文字与复杂公式以原页为准
> Locator mode: page-grounded
> Primary analytical lens: methods
> Secondary analytical lens: None
> Context verification: Targeted external check（发表身份）；领域历史仅 paper-framed
> Card completeness: Partial（未逐项复核所有附录、未运行代码、未复现统计）

本文为 AI 辅助研究笔记；[Paper] 是来源陈述，[Analysis] 是分析，[Hypothesis] 是待检验设想。页码均为下载 PDF 的文件页序号。

## 01 基本信息

- 论文：MARS: Multi-Agent Adaptive Reasoning with Socratic Guidance for Automated Prompt Optimization
- 作者：Jian Zhang; Zhangqi Wang; Haiping Zhu; Kangda Cheng; Kai He; Bo Li; Qika Lin; Jun Liu; Erik Cambria
- 发表：Proceedings of the AAAI Conference on Artificial Intelligence，2026；CCF：A
- DOI：[10.1609/aaai.v40i19.38668](https://doi.org/10.1609/aaai.v40i19.38668)
- 阅读日期：2026-11-22；全文 9 页。
- 来源：[原文 PDF（作者/出版方）](https://ojs.aaai.org/index.php/AAAI/article/download/38668/42630)；[正式记录/来源页](https://doi.org/10.1609/aaai.v40i19.38668)。
- 单位、代码和数据：以原文首页与资源声明为准；本次未运行代码或下载学生级数据。
- 研究位置：苏格拉底/启发式教学与 AI 的机制及证据分析。[Paper: PDF p. 1, Title and Abstract]


## 02 一句话总结

[Paper] 把苏格拉底对话用于提示词优化，以规划、提问、批评、修订和任务评估组成迭代流程，报告多项推理任务的准确率收益；其中教师和学生均为模型角色。 [Paper: PDF p. 1, Abstract]

## 03 研究问题

自动提示优化受固定模板与搜索效率限制；作者询问能否用任务分解和多角色反思引导离散文本搜索。[Paper: PDF p. 1–2, Introduction]

## 04 背景与发展路线

[Paper-framed; external verification not performed] 本文以 APE、ProTeGi、OPRO、PE2 为提示优化背景，属于把教学隐喻转化为算法控制，非人类学生教学实验。[Paper: PDF p. 7, Related Works]

## 05 核心痛点

|痛点及表现|作者的对应解释/设计|证据|
|---|---|---|
|优化路径僵化、改写局部化、缺乏质量反馈。Planner 管全局，Teacher/Critic/Student 管局部迭代，Target 提供任务反馈。[Paper: PDF p. 3–4, Figure 3]|以下模块分别处理，不能仅凭设计意图认定因果|见本格来源及第07–10节|

## 06 核心思想

[Paper] 把苏格拉底对话用于提示词优化，以规划、提问、批评、修订和任务评估组成迭代流程，报告多项推理任务的准确率收益；其中教师和学生均为模型角色。 [Paper: PDF p. 1, Abstract]

[Analysis] 可迁移启示：多角色分工可以形成可追踪的优化轨迹；算法评估必须区分优化反馈与最终评价数据，形式化保证也要核查假设。[Paper: PDF p. 3–5, Method]

## 07 方法总览

[Paper] 任务与初始提示 → Planner 生成子目标 → Teacher 提问 → Critic 审核 → Student 改写提示 → Target 测分 → 收益阈值终止。主要骨干 deepseek-v2.5-1210，温度 0.6，最大 10 轮、阈值 0.01。[Paper: PDF p. 3–5, Algorithm 1]

## 08 核心模块拆解

|模块|功能|设计原因|输入→输出|证据与移除分析|定位|
|---|---|---|---|---|---|
|Planner|规划优化子目标|对应上文痛点；是否必要需看对照|任务→轨迹|去除后 BBH 子集均分下降 6.77 点；未报告的移除效果不推断|[Paper: PDF p. 6, Method/Results]|
|Teacher–Critic–Student|提问、质检、综合改写|对应上文痛点；是否必要需看对照|子目标/历史→提示|去除整组下降 11.31 点；未报告的移除效果不推断|[Paper: PDF p. 6, Method/Results]|
|Target 与停止规则|用任务表现控制迭代|对应上文痛点；是否必要需看对照|提示→奖励与终止|Figure 6；收益依赖评估集设置；未报告的移除效果不推断|[Paper: PDF p. 6, Method/Results]|


## 09 关键公式与符号

[Paper] Eq. 4 描述 q_i=π_t(st_i,p_{i−1})、c_i=π_c(q_i)、p_i=π_s((q_i,c_i),p_{i−1})；Eq. 9–10 以 ΔR 与阈值 δ 控制停止。POMDP 是流程形式化，不能仅凭该记法认定做了参数级强化学习。[Paper: PDF p. 3–4, Equations 4, 9–10]

自动编号候选索引（含可能的非公式误检，仅供回查，未据此补造公式）：Equation 1 [Paper: PDF p. 2, Numbered item]；Equation 2 [Paper: PDF p. 3, Numbered item]；Equation 3 [Paper: PDF p. 3, Numbered item]；Equation 4 [Paper: PDF p. 3, Numbered item]；Equation 5 [Paper: PDF p. 4, Numbered item]；Equation 6 [Paper: PDF p. 4, Numbered item]；Equation 7 [Paper: PDF p. 4, Numbered item]；Equation 8 [Paper: PDF p. 4, Numbered item]；Equation 9 [Paper: PDF p. 4, Numbered item]；Equation 10 [Paper: PDF p. 4, Numbered item]。

## 10 实验设计与证据链

[Paper] 12 个通用任务和 5 个领域任务。Table 1 的均值：MARS 85.11、OPRO 79.07；Table 2 领域均值 75.81、PE2 69.39。Table 3 的 6 个 BBH 任务中完整 79.59、去 Socratic 模块 68.28、去 Critic 76.04。跨 Target 模型见 Table 4。[Paper: PDF p. 5–7, Tables 1–4]

|中心主张|证据|可支持的结论|不能支持的更强结论|
|---|---|---|---|
|把苏格拉底对话用于提示词优化，以规划、提问、批评、修订和任务评估组成迭代流程，报告多项推理任务的准确率收益；其中教师和学生均为模型角色。|上段实验与下列图表索引|仅限本文任务、样本与协议|不能自动外推为所有学生的长期学习增益|

**图表证据索引**（由 skill 源包定位；包含附录，存在图注识别遗漏的可能。主论证见上段；附录索引不代表全部逐项复核。）

|编号|论证用途|文件页|
|---|---|---|
|Figure 1|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 1, Figure 1]|
|Figure 2|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 2, Figure 2]|
|Figure 3|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 3, Figure 3]|
|Figure 4|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 4, Figure 4]|
|Figure 5|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 6, Figure 5]|
|Figure 6|方法结构或数据流程；用于重建机制|[Paper: PDF p. 7, Figure 6]|
|Table 1|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 5, Table 1]|
|Table 2|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 5, Table 2]|
|Table 3|组件/设置对照；用于检查归因|[Paper: PDF p. 6, Table 3]|
|Table 4|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 7, Table 4]|


## 11 结论的正确解释

[Analysis] 支持提示优化任务中的效果，完全不能作为人类启发式学习收益证据。文中 Algorithm 1 / Eq. 8 用 D_test 计算用于迭代的奖励，评估集是否真正隔离须额外确认。[Paper: PDF p. 4–5, Equation 8 and Algorithm 1]

## 12 作者明确承认的局限

在所读主文中未找到明确的独立作者局限性陈述；不将下面的测试集反馈问题归为作者自认局限。

## 13 批判性分析

[Analysis] 若同一测试集同时控制提示搜索和最终测分，会高估泛化；另，Lipschitz 有界性不自动推出全程单调改进。需分别固定训练/验证/最终测试集，并在相同 token 预算下复现实验。[Paper: PDF p. 4, Proposition 2; PDF p. 5, Algorithm 1]

## 14 可迁移知识

**Agent-derived knowledge candidates**

[Analysis] 多角色分工可以形成可追踪的优化轨迹；算法评估必须区分优化反馈与最终评价数据，形式化保证也要核查假设。[Paper: PDF p. 3–5, Method]

## 15 与已有知识的联系

**Agent-derived candidate connections**

[Analysis] 与 SocraticLM 共用提问与监督角色，但被优化对象由人类教学回复转为任务提示词。两者的‘学生’与目标变量必须在综述中分别说明。

以上为本集合内比较；不是外部首创性核验。[返回集合索引](../../README.md)

## 16 研究想法

**Agent-derived research candidates**

[Hypothesis] 候选：隔离评估的教学提示优化。以 Eq. 8 的反馈使用方式为起点，假设验证集上的提示优化能迁移到独立学生题库。改动是三划分数据和独立教学奖励。如何验证：固定基座、优化轮数和 token 预算，比较 MARS、OPRO 与无优化；最终集只测一次，指标含正确率、泄露率、教师盲评。可能失败：验证集过拟合；裁判奖励与学习不一致。创新状态：unverified。
