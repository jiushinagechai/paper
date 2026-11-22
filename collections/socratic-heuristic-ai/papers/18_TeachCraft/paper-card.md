# From Knowing to Teaching: Scaffolding Pedagogical Decisions for LLM Agent

> Source coverage: Full paper PDF available; 主文方法与实验重点阅读，附录提供定位，非逐句翻译
> Extraction confidence: high; 图像文字与复杂公式以原页为准
> Locator mode: page-grounded
> Primary analytical lens: methods
> Secondary analytical lens: resource
> Context verification: Targeted external check（发表身份）；领域历史仅 paper-framed
> Card completeness: Partial（未逐项复核所有附录、未运行代码、未复现统计）

本文为 AI 辅助研究笔记；[Paper] 是来源陈述，[Analysis] 是分析，[Hypothesis] 是待检验设想。页码均为下载 PDF 的文件页序号。

## 01 基本信息

- 论文：From Knowing to Teaching: Scaffolding Pedagogical Decisions for LLM Agent
- 作者：Yucheng Wang; Shen Yang; Jifan Yu; Haoxuan Li; Joy Jia Yin Lim; Daniel Zhang-Li; Huiqin Liu; Lei Hou; Juanzi Li; Bin Xu
- 发表：Proceedings of the 64th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)，2026；CCF：A
- DOI：[10.18653/v1/2026.acl-long.1328](https://doi.org/10.18653/v1/2026.acl-long.1328)
- 阅读日期：2026-11-22；全文 24 页。
- 来源：[原文 PDF](paper.pdf)；[正式记录/来源页](https://aclanthology.org/2026.acl-long.1328/)。
- 单位、代码和数据：以原文首页与资源声明为准；本次未运行代码或下载学生级数据。
- 研究位置：苏格拉底/启发式教学与 AI 的机制及证据分析。[Paper: PDF p. 1, Title and Abstract]


## 02 一句话总结

[Paper] 通过资料教学意图识别、学习目标排序及跨组件结构约束生成课程，在专家材料偏好评估中优于多数基线，但不直接测量学生学习。 [Paper: PDF p. 1, Abstract]

## 03 研究问题

会回答知识题的模型未必能组织课程；如何让资料选择、目标排序和课件/讲稿/测验整合体现教学决策？[Paper: PDF p. 3–5, Method]

## 04 背景与发展路线

[Paper-framed; external verification not performed] 论文以 Pedagogical Content Knowledge 为背景，用三个可实现决策操作化教师备课经验。其主要用途是教学材料生成。[Paper: PDF p. 3–4, Formulation]

## 05 核心痛点

|痛点及表现|作者的对应解释/设计|证据|
|---|---|---|
|混合来源用途混淆、目标次序任意、讲稿与测验术语不一致；Explorer、Planner、Generator 分别控制。[Paper: PDF p. 4–5, Figure 2]|以下模块分别处理，不能仅凭设计意图认定因果|见本格来源及第07–10节|

## 06 核心思想

[Paper] 通过资料教学意图识别、学习目标排序及跨组件结构约束生成课程，在专家材料偏好评估中优于多数基线，但不直接测量学生学习。 [Paper: PDF p. 1, Abstract]

[Analysis] 可迁移启示：资料来源到学习目标再到测验的可追溯链条，可防止课件与评价脱节；‘知道’到‘会教’需要显式决策层。[Paper: PDF p. 4–5, Figure 2]

## 07 方法总览

[Paper] 异构文档→六类教学意图分块→提取并按 Bloom 层级排序目标→lesson_plan 与 content_outline→文件记忆读取前文→schema 约束课件、讲稿与测验。三代理用 Gemini 2.5 Pro。[Paper: PDF p. 4–6, Framework and Implementation]

## 08 核心模块拆解

|模块|功能|设计原因|输入→输出|证据与移除分析|定位|
|---|---|---|---|---|---|
|Explorer|按资料教学用途筛选|对应上文痛点；是否必要需看对照|文档→意图化块|Figure 2；未报告的移除效果不推断|[Paper: PDF p. 7, Method/Results]|
|Planner|组织目标和组件顺序|对应上文痛点；是否必要需看对照|块→计划|NoPlanning 消融；未报告的移除效果不推断|[Paper: PDF p. 7, Method/Results]|
|Generator|保持目标/术语一致|对应上文痛点；是否必要需看对照|计划/历史→课件测验|NoSchema 消融；未报告的移除效果不推断|[Paper: PDF p. 7, Method/Results]|


## 09 关键公式与符号

[Paper] Eq. 3 用 (组件类型 t_j,学习目标 o_j,Bloom 层级 β_j) 描述输出序列；Eq. 4 c_j=φ(M_j,σ_j) 表示根据记忆和 schema 生成组件。Bloom 单调顺序是作者设计约束，不代表所有课堂必须遵循的普遍定律。[Paper: PDF p. 5, Equations 3–4]

自动编号候选索引（含可能的非公式误检，仅供回查，未据此补造公式）：Equation 1 [Paper: PDF p. 3, Numbered item]；Equation 2 [Paper: PDF p. 4, Numbered item]；Equation 3 [Paper: PDF p. 5, Numbered item]；Equation 4 [Paper: PDF p. 5, Numbered item]；Equation 5 [Paper: PDF p. 9, Numbered item]。

## 10 实验设计与证据链

[Paper] 40 个课程任务，24 位评审、920 次成对判断；人类总体偏好胜率 67.8%，LLM 79.6%，对 NotebookLM 人类胜率约 49.8%。Figure 3 标示 123 份源文档和 53 个 quizzes，正文同页写 128 份文档和 512 道 quiz questions：题目与测验单元可能不同，但文档数存在未解释差异。[Paper: PDF p. 6–7, Figure 3 and Evaluation]

|中心主张|证据|可支持的结论|不能支持的更强结论|
|---|---|---|---|
|通过资料教学意图识别、学习目标排序及跨组件结构约束生成课程，在专家材料偏好评估中优于多数基线，但不直接测量学生学习。|上段实验与下列图表索引|仅限本文任务、样本与协议|不能自动外推为所有学生的长期学习增益|

**图表证据索引**（由 skill 源包定位；包含附录，存在图注识别遗漏的可能。主论证见上段；附录索引不代表全部逐项复核。）

|编号|论证用途|文件页|
|---|---|---|
|Figure 1|组件/设置对照；用于检查归因|[Paper: PDF p. 2, Figure 1]|
|Figure 2|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 4, Figure 2]|
|Figure 3|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 6, Figure 3]|
|Figure 4|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 7, Figure 4]|
|Figure 5|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 9, Figure 5]|
|Table 1|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 3, Table 1]|
|Table 2|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 7, Table 2]|
|Table 3|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 8, Table 3]|
|Table 4|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 11, Table 4]|
|Table 5|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 15, Table 5]|
|Table 6|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 16, Table 6]|
|Table 7|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 16, Table 7]|
|Table 8|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 17, Table 8]|
|Table 9|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 17, Table 9]|
|Table 10|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 18, Table 10]|
|Table 11|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 18, Table 11]|
|Table 12|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 19, Table 12]|
|Table 13|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 19, Table 13]|
|Table 14|方法结构或数据流程；用于重建机制|[Paper: PDF p. 19, Table 14]|
|Table 15|方法结构或数据流程；用于重建机制|[Paper: PDF p. 21, Table 15]|
|Table 16|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 21, Table 16]|
|Table 17|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 22, Table 17]|
|Table 18|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 22, Table 18]|
|Table 19|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 22, Table 19]|


## 11 结论的正确解释

[Analysis] 胜率是材料偏好，不是学生成绩；对 NotebookLM 接近持平。需要保留统计口径差异，不能把 40 个课程写成 40 个学科，也不能把 quizzes 与 questions 合并。[Paper: PDF p. 6–8, Main Results]

## 12 作者明确承认的局限

作者指出源文档为回溯检索匹配而非天然备课材料对，来源只含 MIT OCW/Khan Academy，六类意图未必全面，且多代理成本/延迟高。[Paper: PDF p. 8–9, Limitations]

## 13 批判性分析

[Analysis] 合成材料胜出可能部分来自额外调用和视觉组织；人类评审一致性 κ=0.10，宜报告不确定性与分维度结果。应固定预算，并加入课堂学习而非仅偏好评审。[Paper: PDF p. 6–8, Table 2 and Ablation]

## 14 可迁移知识

**Agent-derived knowledge candidates**

[Analysis] 资料来源到学习目标再到测验的可追溯链条，可防止课件与评价脱节；‘知道’到‘会教’需要显式决策层。[Paper: PDF p. 4–5, Figure 2]

## 15 与已有知识的联系

**Agent-derived candidate connections**

[Analysis] 可为 SPL 提供情境和教学目标，为 ScaffoldLM 提供计划来源；静态备课产物仍需在实时学生状态下重新调整。

以上为本集合内比较；不是外部首创性核验。[返回集合索引](../../README.md)

## 16 研究想法

**Agent-derived research candidates**

[Hypothesis] 候选：学生错误驱动的课程重排。以材料评分未检验学习为起点，把形成性错误接入 Planner。如何验证：同教材、时长和基座，对比静态 Bloom 序列与错误驱动序列，测迁移后测和目标覆盖。可能失败：诊断噪声造成反复重排；弱先修知识者认知负荷过高。创新状态：unverified。
