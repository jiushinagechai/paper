# Teach AI How to Code: Using Large Language Models as Teachable Agents for Programming Education

> Source coverage: Full paper PDF available; 主文方法与实验重点阅读，附录提供定位，非逐句翻译
> Extraction confidence: high; 图像文字与复杂公式以原页为准
> Locator mode: page-grounded
> Primary analytical lens: methods
> Secondary analytical lens: None
> Context verification: Targeted external check（发表身份）；领域历史仅 paper-framed
> Card completeness: Partial（未逐项复核所有附录、未运行代码、未复现统计）

本文为 AI 辅助研究笔记；[Paper] 是来源陈述，[Analysis] 是分析，[Hypothesis] 是待检验设想。页码均为下载 PDF 的文件页序号。

## 01 基本信息

- 论文：Teach AI How to Code: Using Large Language Models as Teachable Agents for Programming Education
- 作者：Jin, Hyoungwook; Lee, Seonghee; Shin, Hyungyu; Kim, Juho
- 发表：Proceedings of the CHI Conference on Human Factors in Computing Systems，2024；CCF：A
- DOI：[10.1145/3613904.3642349](https://doi.org/10.1145/3613904.3642349)
- 阅读日期：2026-11-22；全文 28 页。
- 来源：[原文 PDF（作者/出版方）](https://arxiv.org/pdf/2309.14534)；[正式记录/来源页](https://doi.org/10.1145/3613904.3642349)。
- 单位、代码和数据：以原文首页与资源声明为准；本次未运行代码或下载学生级数据。
- 研究位置：苏格拉底/启发式教学与 AI 的机制及证据分析。[Paper: PDF p. 1, Title and Abstract]


## 02 一句话总结

[Paper] 限制 LLM 受教者的知识状态，并通过模式切换和教学反馈促进学生以教促学，提升知识建构话语密度，但自报元认知指标未显著改善。 [Paper: PDF p. 1, Abstract]

## 03 研究问题

知识丰富的 LLM 难扮演真正需要学生教的对象；如何让可教智能体稳定表现知识缺口并发起有效追问？[Paper: PDF p. 2, Introduction]

## 04 背景与发展路线

[Paper-framed; external verification not performed] 以教促学（LBT）将解释和发现知识缺口作为学习活动。本文用 LLM 降低传统可教智能体的知识模型编写成本。[Paper: PDF p. 2–3, Introduction and Related Work]

## 05 核心痛点

|痛点及表现|作者的对应解释/设计|证据|
|---|---|---|
|预训练知识泄露使受教者过强，持续被动接受也缺乏知识共建；知识状态约束和定期提问分别处理。[Paper: PDF p. 8–10, Pipeline and Mode-shifting]|以下模块分别处理，不能仅凭设计意图认定因果|见本格来源及第07–10节|

## 06 核心思想

[Paper] 限制 LLM 受教者的知识状态，并通过模式切换和教学反馈促进学生以教促学，提升知识建构话语密度，但自报元认知指标未显著改善。 [Paper: PDF p. 1, Abstract]

[Analysis] 可迁移启示：以教促学需要受教者适度提问和可观察知识变化；固定每三条消息的节律是经验性选择，可研究更自适应时机。[Paper: PDF p. 9, Mode-shifting]

## 07 方法总览

[Paper] Reflect 从近三条消息更新 facts/code_implementation JSON；Respond 仅检索当前状态生成回应。每三条消息切到提问者模式，追问 why/how；Teaching Helper 每六条消息按对话模式反馈。[Paper: PDF p. 8–10, Figures 3–5]

## 08 核心模块拆解

|模块|功能|设计原因|输入→输出|证据与移除分析|定位|
|---|---|---|---|---|---|
|Reflect–Respond|模拟可教而非全知的受教者|对应上文痛点；是否必要需看对照|对话→知识更新/受限回答|Tables 3–6；未报告的移除效果不推断|[Paper: PDF p. 15, Method/Results]|
|Mode-shifting|触发解释与知识共建|对应上文痛点；是否必要需看对照|对话阶段→问题|Figure 4；未报告的移除效果不推断|[Paper: PDF p. 15, Method/Results]|
|Teaching Helper|识别教学对话反模式|对应上文痛点；是否必要需看对照|分类→元认知提示|Tables 8–11；未报告的移除效果不推断|[Paper: PDF p. 15, Method/Results]|


## 09 关键公式与符号

[Paper] 知识建构密度 = 指定话语类型次数 / 交换消息数；它测对话行为，不能直接替代学习成绩。技术评价分别测试知识状态的可配置性、持续性、适应性。[Paper: PDF p. 10–16, Evaluation and Table 8]

自动编号候选索引（含可能的非公式误检，仅供回查，未据此补造公式）：Equation 1 [Paper: PDF p. 26, Numbered item]；Equation 3 [Paper: PDF p. 15, Numbered item]；Equation 5 [Paper: PDF p. 15, Numbered item]；Equation 10 [Paper: PDF p. 15, Numbered item]；Equation 40 [Paper: PDF p. 15, Numbered item]。

## 10 实验设计与证据链

[Paper] 40 名初学者，Baseline 与 TeachYou 各 20 人；约 40 分钟教二分查找。知识建构密度 3.5±6.6%→8.4±7.1%，p=0.03、d=0.71。Table 10 的元认知条目均未显示显著组间差异。基线已有知识状态配置，完整组额外含 Mode-shifting 和 Helper。[Paper: PDF p. 15–17, Tables 7–11]

|中心主张|证据|可支持的结论|不能支持的更强结论|
|---|---|---|---|
|限制 LLM 受教者的知识状态，并通过模式切换和教学反馈促进学生以教促学，提升知识建构话语密度，但自报元认知指标未显著改善。|上段实验与下列图表索引|仅限本文任务、样本与协议|不能自动外推为所有学生的长期学习增益|

**图表证据索引**（由 skill 源包定位；包含附录，存在图注识别遗漏的可能。主论证见上段；附录索引不代表全部逐项复核。）

|编号|论证用途|文件页|
|---|---|---|
|Figure 1|方法结构或数据流程；用于重建机制|[Paper: PDF p. 1, Figure 1]|
|Figure 2|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 7, Figure 2]|
|Figure 3|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 8, Figure 3]|
|Figure 4|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 9, Figure 4]|
|Figure 5|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 10, Figure 5]|
|Figure 6|方法结构或数据流程；用于重建机制|[Paper: PDF p. 11, Figure 6]|
|Table 1|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 5, Table 1]|
|Table 2|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 6, Table 2]|
|Table 3|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 13, Table 3]|
|Table 4|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 13, Table 4]|
|Table 5|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 13, Table 5]|
|Table 6|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 14, Table 6]|
|Table 7|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 15, Table 7]|
|Table 8|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 16, Table 8]|
|Table 9|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 16, Table 9]|
|Table 10|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 17, Table 10]|
|Table 11|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 17, Table 11]|


## 11 结论的正确解释

[Analysis] 可支持共建话语增加与部分体验变化，不能把 d=0.71 写成算法成绩效应；两项新增模块一起比较也不能单独证明 Helper 有效。[Paper: PDF p. 15–17, Results]

## 12 作者明确承认的局限

作者在讨论中指出提示微小变化使精确控制知识状态困难；统一配置忽略学习者先验差异，模式切换有时打断教学流。[Paper: PDF p. 17–18, Discussion]

## 13 批判性分析

[Analysis] 受教者是‘按设定表现不知道’，不等同真正形成可验证知识；元认知自报无显著差异应保留。需要分模块消融与不靠 AI 的迁移任务。[Paper: PDF p. 8–10, Knowledge State; PDF p. 17, Table 10]

## 14 可迁移知识

**Agent-derived knowledge candidates**

[Analysis] 以教促学需要受教者适度提问和可观察知识变化；固定每三条消息的节律是经验性选择，可研究更自适应时机。[Paper: PDF p. 9, Mode-shifting]

## 15 与已有知识的联系

**Agent-derived candidate connections**

[Analysis] 与 StudentSimulation 都限制‘完美学生’行为，但本篇的虚拟学生用于激发真人解释，后者用于研究仿真，两种评估目标不能混合。

以上为本集合内比较；不是外部首创性核验。[返回集合索引](../../README.md)

## 16 研究想法

**Agent-derived research candidates**

[Hypothesis] 候选：按解释缺口触发受教者追问。以固定节律打断为起点，改为仅在缺失因果或边界条件时提问。如何验证：固定知识状态、消息预算，比较固定周期、随机周期与缺口检测，测解释质量及独立迁移。可能失败：缺口检测误判；少提问降低互动量。创新状态：unverified。
