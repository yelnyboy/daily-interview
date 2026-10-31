# [Agent] 科学文献系统综述

**日期**: 2026-10-31 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 高级 | **来源**: GitHub

## 解答

使用Agent进行科学文献系统综述是一种典型的多阶段工作流设计模式，核心要点如下：

1. 检索阶段：Agent根据研究问题构建检索策略，调用学术搜索API（如Semantic Scholar、PubMed），进行多轮迭代检索以覆盖相关文献。
2. 筛选阶段：基于纳入/排除标准，Agent对每篇文献进行相关性评估，输出筛选理由，支持人工审核回溯。
3. 信息抽取阶段：Agent从每篇文献中结构化提取关键信息（研究方法、样本量、结论、局限性），形成统一格式的证据表。
4. 综合分析阶段：Agent对提取信息进行跨文献对比与综合，识别研究趋势、矛盾点和知识空白，生成结构化综述报告。
5. 质量控制：引入批判性评估模块，对文献质量进行评分，并在综述中标注证据等级。

该模式的关键在于将复杂任务分解为可验证的子任务，每个阶段设置检查点，支持人机协作与回溯修正，确保综述的全面性和准确性。

## 核心考点

- 多阶段工作流编排
- 文献检索与筛选策略
- 结构化信息抽取
- 人机协作检查点
- 证据质量评估

## 常见追问

> 如何设计Agent之间的协作机制，使筛选阶段和信息抽取阶段能够并行处理以提高效率？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/systematic_review_of_scientific_articles.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/systematic_review_of_scientific_articles.ipynb)
