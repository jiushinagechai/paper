# Planning-Guided Tutoring with Assessment-Driven Memory for Pedagogical LLM Tutors

> Source coverage: Full paper PDF available; 主文方法与实验重点阅读，附录提供定位，非逐句翻译
> Extraction confidence: high; 图像文字与复杂公式以原页为准
> Locator mode: page-grounded
> Primary analytical lens: methods
> Secondary analytical lens: resource
> Context verification: Targeted external check（发表身份）；领域历史仅 paper-framed
> Card completeness: Partial（未逐项复核所有附录、未运行代码、未复现统计）

本文为 AI 辅助研究笔记；[Paper] 是来源陈述，[Analysis] 是分析，[Hypothesis] 是待检验设想。页码均为下载 PDF 的文件页序号。

## 01 基本信息

- 论文：Planning-Guided Tutoring with Assessment-Driven Memory for Pedagogical LLM Tutors
- 作者：Zechen Li; Qiannan Zhu; Mei Wang; Jia Li; Hua Huang
- 发表：Proceedings of the 64th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)，2026；CCF：A
- DOI：[10.18653/v1/2026.acl-long.325](https://doi.org/10.18653/v1/2026.acl-long.325)
- 阅读日期：2026-11-22；全文 24 页。
- 来源：[原文 PDF](paper.pdf)；[正式记录/来源页](https://aclanthology.org/2026.acl-long.325/)。
- 单位、代码和数据：以原文首页与资源声明为准；本次未运行代码或下载学生级数据。
- 研究位置：苏格拉底/启发式教学与 AI 的机制及证据分析。[Paper: PDF p. 1, Title and Abstract]


## 02 一句话总结

[Paper] 显式步骤计划与评估驱动记忆共同控制数学教学，微调后提升过程评测，并在模拟学习收益与答案泄露之间取得较好的折中。 [Paper: PDF p. 1, Abstract]

## 03 研究问题

无结构长对话容易丢失步骤和学生状态；能否将教学计划、学生诊断和进度更新统一为控制闭环？[Paper: PDF p. 2–4, Framework]

## 04 背景与发展路线

[Paper-framed; external verification not performed] 作者将提示控制、监督微调和教学 RL 三条路线对比，主张步骤计划与状态监督可改善长对话。该定位按本文相关工作陈述。[Paper: PDF p. 2–3, Related Work]

## 05 核心痛点

|痛点及表现|作者的对应解释/设计|证据|
|---|---|---|
|计划缺失、误认学生已理解、跨轮状态漂移、提前泄露答案；对应显式计划、Assess–Act–Track–Record 与一致性过滤。[Paper: PDF p. 4–6, Sections 4–5]|以下模块分别处理，不能仅凭设计意图认定因果|见本格来源及第07–10节|

## 06 核心思想

[Paper] 显式步骤计划与评估驱动记忆共同控制数学教学，微调后提升过程评测，并在模拟学习收益与答案泄露之间取得较好的折中。 [Paper: PDF p. 1, Abstract]

[Analysis] 可迁移启示：教学计划是控制信息，不等于给学生展示完整答案；状态、动作、进度、历史四部分可单独审计。[Paper: PDF p. 4–5, Memory]

## 07 方法总览

[Paper] 题目→(引导子问题,参考子答案)计划→判断学生状态→对应反馈→更新步骤完成向量和历史。训练混合计划与教学数据；数据生成中控制学生状态，并只保留导师诊断与目标状态一致的轮次。Qwen2.5-7B-Instruct 为基座。[Paper: PDF p. 4–6, Figure 1 and Table 1]

## 08 核心模块拆解

|模块|功能|设计原因|输入→输出|证据与移除分析|定位|
|---|---|---|---|---|---|
|步骤计划|设定可验证的局部目标|对应上文痛点；是否必要需看对照|题目→子问题/答案|去 Plan 的指导质量 0.525→0.468；未报告的移除效果不推断|[Paper: PDF p. 8, Method/Results]|
|评估记忆|判状态并维护进度|对应上文痛点；是否必要需看对照|回应→状态/历史|去 Assessment 指导质量降至 0.425；未报告的移除效果不推断|[Paper: PDF p. 8, Method/Results]|
|合成过滤/SFT|避免标签与回应冲突|对应上文痛点；是否必要需看对照|双代理轨迹→训练样本|Section 5；未报告的移除效果不推断|[Paper: PDF p. 8, Method/Results]|


## 09 关键公式与符号

[Paper] P(Q)=[(q_t,a_t)]；M=(P,p,H)，其中 p 为二元步骤完成向量；s_k=Assess(L_k,M_{k−1})，T_k=Act(L_k,s_k,M_{k−1})。完成判断改变 p 并记录历史，是状态显式化的关键。[Paper: PDF p. 4–5, Equations 1–6]

自动编号候选索引（含可能的非公式误检，仅供回查，未据此补造公式）：Equation 1 [Paper: PDF p. 4, Numbered item]；Equation 2 [Paper: PDF p. 4, Numbered item]；Equation 3 [Paper: PDF p. 4, Numbered item]；Equation 4 [Paper: PDF p. 4, Numbered item]；Equation 5 [Paper: PDF p. 5, Numbered item]；Equation 6 [Paper: PDF p. 5, Numbered item]；Equation 7 [Paper: PDF p. 5, Numbered item]；Equation 8 [Paper: PDF p. 6, Numbered item]；Equation 9 [Paper: PDF p. 6, Numbered item]。

## 10 实验设计与证据链

[Paper] BigMath 抽 10,000 训练题、300 留出题，过滤得到 5,635 计划样本和 49,815 单轮教学样本。Table 2 错误回应适应性 0.729（GPT-4o 0.713）；Figure 2 模拟 Δsolve 30.6%、泄露 8.8%，TutorRL λ=0.5 为 30.9%/25.1%。Math500 比基座低 1.2 个百分点。[Paper: PDF p. 6–9, Tables 2–4 and Figure 2]

|中心主张|证据|可支持的结论|不能支持的更强结论|
|---|---|---|---|
|显式步骤计划与评估驱动记忆共同控制数学教学，微调后提升过程评测，并在模拟学习收益与答案泄露之间取得较好的折中。|上段实验与下列图表索引|仅限本文任务、样本与协议|不能自动外推为所有学生的长期学习增益|

**图表证据索引**（由 skill 源包定位；包含附录，存在图注识别遗漏的可能。主论证见上段；附录索引不代表全部逐项复核。）

|编号|论证用途|文件页|
|---|---|---|
|Figure 1|方法结构或数据流程；用于重建机制|[Paper: PDF p. 3, Figure 1]|
|Figure 2|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 8, Figure 2]|
|Figure 3|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 13, Figure 3]|
|Figure 4|数据构成/分布；用于检查覆盖范围|[Paper: PDF p. 13, Figure 4]|
|Figure 5|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 17, Figure 5]|
|Figure 6|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 19, Figure 6]|
|Figure 7|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 20, Figure 7]|
|Figure 8|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 20, Figure 8]|
|Figure 9|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 21, Figure 9]|
|Figure 10|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 21, Figure 10]|
|Figure 11|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 22, Figure 11]|
|Figure 12|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 23, Figure 12]|
|Figure 13|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 23, Figure 13]|
|Figure 14|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 24, Figure 14]|
|Table 1|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 5, Table 1]|
|Table 2|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 7, Table 2]|
|Table 3|组件/设置对照；用于检查归因|[Paper: PDF p. 8, Table 3]|
|Table 4|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 9, Table 4]|
|Table 5|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 15, Table 5]|
|Table 6|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 16, Table 6]|
|Table 7|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 16, Table 7]|
|Table 8|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 18, Table 8]|
|Table 9|案例或交互界面；用于解释行为，不能单独证明效果|[Paper: PDF p. 18, Table 9]|


## 11 结论的正确解释

[Analysis] 证据是教学指标、模拟 solve rate 及解题基准，不能当作真人长期成绩；原文‘不损伤推理’应解释为所测基准变化有限，并非每项都上升。计划使用子答案是内部评估依据，需要单独验证计划正确性。[Paper: PDF p. 4, Planning; PDF p. 8–9, Results]

## 12 作者明确承认的局限

作者承认合成数学数据不充分覆盖真实学生不可预测性，对开放学科未验证；计算仅靠模型内部表示，未来拟引入外部工具检查中间步骤。[Paper: PDF p. 9, Limitations]

## 13 批判性分析

[Analysis] 把‘表示理解’设为完成状态可能误判掌握；一致性筛选可能移除最有教学价值的模糊案例。可加入口头说懂但实际错的真人样本，并做反事实步骤核验。[Paper: PDF p. 5, Table 1 and Data Synthesis]

## 14 可迁移知识

**Agent-derived knowledge candidates**

[Analysis] 教学计划是控制信息，不等于给学生展示完整答案；状态、动作、进度、历史四部分可单独审计。[Paper: PDF p. 4–5, Memory]

## 15 与已有知识的联系

**Agent-derived candidate connections**

[Analysis] 可与 LEAP 的长期状态检索组合，但必须验证增加记忆是否改善学习而不是只延长上下文；该组合是研究候选。

以上为本集合内比较；不是外部首创性核验。[返回集合索引](../../README.md)

## 16 研究想法

**Agent-derived research candidates**

[Hypothesis] 候选：反证式掌握检查。针对 Table 1 的 Comprehension 状态，增加一个短迁移问题后才推进。如何验证：同题库、同最大轮数与骨干，对比原推进和核验推进，测误推进率、泄露率及真人无辅助后测。可能失败：核验耗尽时间；核验题本身泄露答案。创新状态：unverified。
