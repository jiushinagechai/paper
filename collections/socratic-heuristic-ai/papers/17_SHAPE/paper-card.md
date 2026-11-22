# SHAPE: Unifying Safety, Helpfulness and Pedagogy for Educational LLMs

> Source coverage: Full paper PDF available; 主文方法与实验重点阅读，附录提供定位，非逐句翻译
> Extraction confidence: high; 图像文字与复杂公式以原页为准
> Locator mode: page-grounded
> Primary analytical lens: methods
> Secondary analytical lens: resource
> Context verification: Targeted external check（发表身份）；领域历史仅 paper-framed
> Card completeness: Partial（未逐项复核所有附录、未运行代码、未复现统计）

本文为 AI 辅助研究笔记；[Paper] 是来源陈述，[Analysis] 是分析，[Hypothesis] 是待检验设想。页码均为下载 PDF 的文件页序号。

## 01 基本信息

- 论文：SHAPE: Unifying Safety, Helpfulness and Pedagogy for Educational LLMs
- 作者：Sihang Zhao; Kangrui Yu; Youliang Yuan; Pinjia He; Hongyi Wen
- 发表：Proceedings of the 64th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)，2026；CCF：A
- DOI：[10.18653/v1/2026.acl-long.529](https://doi.org/10.18653/v1/2026.acl-long.529)
- 阅读日期：2026-11-22；全文 17 页。
- 来源：[原文 PDF](paper.pdf)；[正式记录/来源页](https://aclanthology.org/2026.acl-long.529/)。
- 单位、代码和数据：以原文首页与资源声明为准；本次未运行代码或下载学生级数据。
- 研究位置：苏格拉底/启发式教学与 AI 的机制及证据分析。[Paper: PDF p. 1, Title and Abstract]


## 02 一句话总结

[Paper] 把先修知识与学生掌握状态表示为图，用显式门控决定直接作答或启发式提问，提高部分模型在诱导答案攻击下的教学约束遵循。 [Paper: PDF p. 1, Abstract]

## 03 研究问题

学生可通过角色扮演等提示诱导导师直接给答案；如何在允许已掌握者核对答案的同时，为未掌握者保留学习过程？[Paper: PDF p. 3–4, Preliminary]

## 04 背景与发展路线

[Paper-framed; external verification not performed] 本文将一般安全中的拒答概念转为知识状态相关的教学决策，‘安全’在此主要指是否不当泄露解答，不等同全部教育安全。[Paper: PDF p. 4, Section 4.1]

## 05 核心痛点

|痛点及表现|作者的对应解释/设计|证据|
|---|---|---|
|统一拒答和统一直接作答都不合适；只写‘做好老师’提示易被攻击。用先修图和外部程序门控约束生成路径。[Paper: PDF p. 4–7, Sections 4–5]|以下模块分别处理，不能仅凭设计意图认定因果|见本格来源及第07–10节|

## 06 核心思想

[Paper] 把先修知识与学生掌握状态表示为图，用显式门控决定直接作答或启发式提问，提高部分模型在诱导答案攻击下的教学约束遵循。 [Paper: PDF p. 1, Abstract]

[Analysis] 可迁移启示：安全率、条件教学率、帮助率需要共同解释；知识状态门控把教学目标从软提示变成可检查的约束。[Paper: PDF p. 4–7, Metrics and Pipeline]

## 07 方法总览

[Paper] 问题→解析必需概念及先修闭包 Req(q)→与掌握集 s 比较→若全部掌握则解答，否则从未知且先修已掌握的 frontier 提问。数据由线性代数图与合成学生状态构造，含 9,087 个学生—题目对。[Paper: PDF p. 4–7, Equations 5–15 and Figure 2]

## 08 核心模块拆解

|模块|功能|设计原因|输入→输出|证据与移除分析|定位|
|---|---|---|---|---|---|
|知识图/状态|定义学习缺口|对应上文痛点；是否必要需看对照|题目/二元掌握→先修集合|Section 4.3；未报告的移除效果不推断|[Paper: PDF p. 7, Method/Results]|
|显式门控|防止提示覆盖教学条件|对应上文痛点；是否必要需看对照|集合包含关系→路线|Figure 2；未报告的移除效果不推断|[Paper: PDF p. 7, Method/Results]|
|教学生成与评测|瞄准未知前沿概念|对应上文痛点；是否必要需看对照|路线→回复|Tables 1–3；未报告的移除效果不推断|[Paper: PDF p. 7, Method/Results]|


## 09 关键公式与符号

[Paper] g(q,s)=1[Req(q)⊆s]；未知集合为 Req(q)\ s；教学前沿是其直接先修均已掌握的未知节点。Pedagogy 是安全回复中的教学合格比例，分母随 Safety 改变，不能只比较该条件比例。[Paper: PDF p. 4–5, Equations 5–13 and Metrics]

自动编号候选索引（含可能的非公式误检，仅供回查，未据此补造公式）：Equation 1 [Paper: PDF p. 3, Numbered item]；Equation 2 [Paper: PDF p. 3, Numbered item]；Equation 3 [Paper: PDF p. 2, Numbered item]；Equation 4 [Paper: PDF p. 3, Numbered item]；Equation 5 [Paper: PDF p. 4, Numbered item]；Equation 6 [Paper: PDF p. 4, Numbered item]；Equation 7 [Paper: PDF p. 4, Numbered item]；Equation 8 [Paper: PDF p. 4, Numbered item]；Equation 9 [Paper: PDF p. 4, Numbered item]；Equation 10 [Paper: PDF p. 4, Numbered item]；Equation 11 [Paper: PDF p. 4, Numbered item]；Equation 12 [Paper: PDF p. 4, Numbered item]；Equation 13 [Paper: PDF p. 4, Numbered item]；Equation 14 [Paper: PDF p. 6, Numbered item]；Equation 15 [Paper: PDF p. 6, Numbered item]；Equation 16 [Paper: PDF p. 12, Numbered item]；Equation 17 [Paper: PDF p. 12, Numbered item]；Equation 18 [Paper: PDF p. 12, Numbered item]；Equation 19 [Paper: PDF p. 12, Numbered item]；Equation 20 [Paper: PDF p. 13, Numbered item]；Equation 21 [Paper: PDF p. 16, Numbered item]；Equation 22 [Paper: PDF p. 16, Numbered item]；Equation 23 [Paper: PDF p. 16, Numbered item]。

## 10 实验设计与证据链

[Paper] Table 3 在两类攻击的最差条件下，Qwen3-80B Safety 0→92.25，GPT-5 74.35→85.92；但 Qwen3-8B 0→1.41，显示方法非普遍有效。1,786 道筛选题覆盖 92 个概念，基础图 211 节点。[Paper: PDF p. 5–7, Data Construction and Table 3]

|中心主张|证据|可支持的结论|不能支持的更强结论|
|---|---|---|---|
|把先修知识与学生掌握状态表示为图，用显式门控决定直接作答或启发式提问，提高部分模型在诱导答案攻击下的教学约束遵循。|上段实验与下列图表索引|仅限本文任务、样本与协议|不能自动外推为所有学生的长期学习增益|

**图表证据索引**（由 skill 源包定位；包含附录，存在图注识别遗漏的可能。主论证见上段；附录索引不代表全部逐项复核。）

|编号|论证用途|文件页|
|---|---|---|
|Figure 1|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 2, Figure 1]|
|Figure 2|方法结构或数据流程；用于重建机制|[Paper: PDF p. 7, Figure 2]|
|Table 1|组件/设置对照；用于检查归因|[Paper: PDF p. 5, Table 1]|
|Table 2|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 6, Table 2]|
|Table 3|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 7, Table 3]|
|Table 4|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 15, Table 4]|
|Table 5|方法结构或数据流程；用于重建机制|[Paper: PDF p. 15, Table 5]|
|Table 6|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 15, Table 6]|
|Table 7|评价结果或指标比较；解释须结合样本、基线及协议|[Paper: PDF p. 17, Table 7]|
|Table 8|提示模板、结构约束或研究工具；用于核对可复现设置|[Paper: PDF p. 17, Table 8]|
|Table 9|原文图表定位；具体支持力度须结合所在段落|[Paper: PDF p. 17, Table 9]|


## 11 结论的正确解释

[Analysis] 主要检验单轮、合成已知掌握状态下的行为约束。Helpfulness 定义是允许作答时是否尝试给解答，而非答案正确率或学习增益；Pedagogy 也非绝对教学成功率。[Paper: PDF p. 5, Metrics]

## 12 作者明确承认的局限

作者明确指出无法通过 API 直接评测部分商业学习模式，只能使用近似提示；领域局限在线性代数；学生状态为二元且先修一致，未建模误解和部分掌握；当前逐概念提问仍需优化多轮轨迹。[Paper: PDF p. 9, Limitations]

## 13 批判性分析

[Analysis] 实际系统无法直接知道真实掌握集；错误诊断会导致过度拒答或泄露。‘未掌握就不能直接展示例题’也是一种设计假设，未在该基准中验证所有教学情境。[Paper: PDF p. 4–5, Gating and Synthetic States]

## 14 可迁移知识

**Agent-derived knowledge candidates**

[Analysis] 安全率、条件教学率、帮助率需要共同解释；知识状态门控把教学目标从软提示变成可检查的约束。[Paper: PDF p. 4–7, Metrics and Pipeline]

## 15 与已有知识的联系

**Agent-derived candidate connections**

[Analysis] 可与 Inquizzitor 的真实形成性评价结合来估计掌握集；需传播评分不确定性而不是把预测视作真值。

以上为本集合内比较；不是外部首创性核验。[返回集合索引](../../README.md)

## 16 研究想法

**Agent-derived research candidates**

[Hypothesis] 候选：带不确定性和可协商解释的教学门控。以二元真值状态假设为起点，用概率掌握度和短诊断题决定给提示还是示例。如何验证：注入不同诊断噪声，固定题目与模型，比较硬门控、概率门控及直接提示；测误拒、泄露与真人后测。可能失败：诊断打断学习；概率失准使门控更差。创新状态：unverified。
