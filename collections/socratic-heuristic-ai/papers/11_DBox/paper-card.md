# DBox: Scaffolding Algorithmic Programming Learning through Learner-LLM Co-Decomposition

> Source coverage: Full paper PDF available; 主文方法与实验重点阅读，附录提供定位，非逐句翻译
> Extraction confidence: high; 图像文字与复杂公式以原页为准
> Locator mode: page-grounded
> Primary analytical lens: methods
> Secondary analytical lens: None
> Context verification: Targeted external check（发表身份）；领域历史仅 paper-framed
> Card completeness: Partial（未逐项复核所有附录、未运行代码、未复现统计）

本文为 AI 辅助研究笔记；[Paper] 是来源陈述，[Analysis] 是分析，[Hypothesis] 是待检验设想。页码均为下载 PDF 的文件页序号。

## 01 基本信息

- 论文：DBox: Scaffolding Algorithmic Programming Learning through Learner-LLM Co-Decomposition
- 作者：Ma, Shuai; Wang, Junling; Zhang, Yuanhao; Ma, Xiaojuan; Wang, April Yi
- 发表：Proceedings of the 2025 CHI Conference on Human Factors in Computing Systems，2025；CCF：A
- DOI：[10.1145/3706598.3713748](https://doi.org/10.1145/3706598.3713748)
- 阅读日期：2026-11-22；全文 20 页。
- 来源：[原文 PDF（作者/出版方）](https://arxiv.org/pdf/2502.19133)；[正式记录/来源页](https://doi.org/10.1145/3706598.3713748)。
- 单位、代码和数据：以原文首页与资源声明为准；本次未运行代码或下载学生级数据。
- 研究位置：苏格拉底/启发式教学与 AI 的机制及证据分析。[Paper: PDF p. 1, Title and Abstract]


## 02 一句话总结

[Paper] 用学习者主导的步骤树和分层提示支持算法分解，在 24 人短期实验中改善无工具相似题测试表现与多项学习体验。 [Paper: PDF p. 1, Abstract]

## 03 研究问题

现有答案浏览和 LLM 回复可能过度帮助或不贴合学生思路；能否保留学生分解主导权并提供节点级支架？[Paper: PDF p. 2, Introduction]

## 04 背景与发展路线

[Paper-framed; external verification not performed] 本文结合问题分解、支架教学及可视化思维外显；人机共同分解是设计核心，非仅增加一个对话窗口。[Paper: PDF p. 6–8, System]

## 05 核心痛点

|痛点及表现|作者的对应解释/设计|证据|
|---|---|---|
|学生难形成解题结构、难把思路映射到代码、帮助粒度不合适。步骤树、代码节点映射与渐进提示分别处理。[Paper: PDF p. 7–8, Figures 2–3]|以下模块分别处理，不能仅凭设计意图认定因果|见本格来源及第07–10节|

## 06 核心思想

[Paper] 用学习者主导的步骤树和分层提示支持算法分解，在 24 人短期实验中改善无工具相似题测试表现与多项学习体验。 [Paper: PDF p. 1, Abstract]

[Analysis] 可迁移启示：‘支持学习者构造’与‘让学习者评价 AI 给出的结构’是不同认知活动；分层提示需保留控制权和可见进度。[Paper: PDF p. 16–18, Discussion]

## 07 方法总览

[Paper] 自然语言或未完成代码→GPT-4o 生成/诊断步骤树→标记正确、错误、缺失及可分解节点→学生修改→映射代码实现。提示从一般问题到具体线索，再到主动请求揭示子步骤；实现阶段可在两次失败后请求揭示该步代码。[Paper: PDF p. 7–8, Progressive Hints]

## 08 核心模块拆解

|模块|功能|设计原因|输入→输出|证据与移除分析|定位|
|---|---|---|---|---|---|
|步骤树|外显学生自己的解法|对应上文痛点；是否必要需看对照|想法/代码→结构树|Figure 1–3；未报告的移除效果不推断|[Paper: PDF p. 9, Method/Results]|
|节点诊断|定位缺失或错误步骤|对应上文痛点；是否必要需看对照|树/题目→状态|175 个含错误树的技术评测；未报告的移除效果不推断|[Paper: PDF p. 9, Method/Results]|
|渐进提示|按请求升级帮助|对应上文痛点；是否必要需看对照|节点错误→问题/线索/揭示|Figure 2，非永不提供答案；未报告的移除效果不推断|[Paper: PDF p. 9, Method/Results]|


## 09 关键公式与符号

[Paper] Not applicable：核心机制为结构化表示、LLM 判断和帮助层级。统计分析使用含工具、题型与顺序固定效应、参与者随机效应的线性混合模型。[Paper: PDF p. 11, Data Analysis]

## 10 实验设计与证据链

[Paper] 技术评测由 25 道 LeetCode 题×7 类错误形成 175 个步骤树；用户研究 24 人、两类算法、四种顺序/题型配平组合。学习后测试阶段不允许用工具；Figure 5 为测试正确性及感知学习，Figure 6–7 为投入与体验。[Paper: PDF p. 9–13, Table 1 and Figures 4–7]

|中心主张|证据|可支持的结论|不能支持的更强结论|
|---|---|---|---|
|用学习者主导的步骤树和分层提示支持算法分解，在 24 人短期实验中改善无工具相似题测试表现与多项学习体验。|上段实验与下列图表索引|仅限本文任务、样本与协议|不能自动外推为所有学生的长期学习增益|

**图表证据索引**（由 skill 源包定位；包含附录，存在图注识别遗漏的可能。主论证见上段；附录索引不代表全部逐项复核。）

|编号|论证用途|文件页|
|---|---|---|
|Figure 1|方法结构或数据流程；用于重建机制|[Paper: PDF p. 6, Figure 1]|
|Figure 2|方法结构或数据流程；用于重建机制|[Paper: PDF p. 7, Figure 2]|
|Figure 3|方法结构或数据流程；用于重建机制|[Paper: PDF p. 8, Figure 3]|
|Figure 4|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 11, Figure 4]|
|Figure 5|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 13, Figure 5]|
|Figure 6|方法结构或数据流程；用于重建机制|[Paper: PDF p. 13, Figure 6]|
|Figure 7|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 13, Figure 7]|
|Figure 8|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 14, Figure 8]|
|Figure 9|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 16, Figure 9]|
|Table 1|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 10, Table 1]|
|Table 2|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 12, Table 2]|


## 11 结论的正确解释

[Analysis] 相较只评提示质量，本篇具有无工具测试证据，但仅相似题、短期单次学习；不能扩大为远迁移或长期保持。自报批判性思维不是独立能力测验。[Paper: PDF p. 11–13, Measures; PDF p. 18, Limitations]

## 12 作者明确承认的局限

作者承认仅两种题型、每条件一次学习、测试题相似、缺少更严格的前后测设计和长期使用研究；拟用浏览器插件扩展现场部署。[Paper: PDF p. 18, Limitations and Future Work]

## 13 批判性分析

[Analysis] 步骤树界面、诊断与提示同时变化，无法单独归因于 LLM 或启发式问题；测试题的相似性也可能偏好结构记忆。建议拆分 UI 与提示机制，并增加远迁移题。[Paper: PDF p. 7–13, Design and Study]

## 14 可迁移知识

**Agent-derived knowledge candidates**

[Analysis] ‘支持学习者构造’与‘让学习者评价 AI 给出的结构’是不同认知活动；分层提示需保留控制权和可见进度。[Paper: PDF p. 16–18, Discussion]

## 15 与已有知识的联系

**Agent-derived candidate connections**

[Analysis] 与 ScaffoldLM 均用步骤结构，但 DBox 让学习者主导构造，ScaffoldLM 由模型生成计划；可围绕主导权设计直接比较。

以上为本集合内比较；不是外部首创性核验。[返回集合索引](../../README.md)

## 16 研究想法

**Agent-derived research candidates**

[Hypothesis] 候选：逐渐撤去步骤树的支架。起点是短期相似题证据，假设逐步隐藏完成节点可减少依赖。如何验证：同 GPT-4o 与题库，比较固定树、渐隐树和纯对话，安排一周延迟与远迁移测试；若便利性提高但撤除后无收益则否证。可能失败：撤得过快增加负荷；错误诊断扰乱自建结构。创新状态：unverified。
