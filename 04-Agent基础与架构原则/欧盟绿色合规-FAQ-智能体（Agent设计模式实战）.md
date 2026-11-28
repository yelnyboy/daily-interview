# 欧盟绿色合规 FAQ 智能体（Agent设计模式实战）

**日期**: 2026-11-28 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 高级 | **来源**: GitHub

## 解答

这是一个面向欧盟绿色合规（如EU Green Deal、CSRD、CBAM等法规）的FAQ问答Agent项目，考察Agent设计模式的综合应用。核心设计要点：1) 整体架构：采用RAG + Agent混合模式，法规文档量大且更新频繁，需通过向量检索获取最新合规知识，避免LLM幻觉；2) Router模式：入口使用意图路由，区分'法规查询'、'合规计算'、'多轮澄清'等不同任务流；3) ReAct模式：对复杂问题采用Reasoning + Acting循环，Agent可调用检索工具、法规数据库API、计算器工具；4) RAG增强：文档分块需考虑法规条款结构（按条款号分块而非固定长度），并加入元数据过滤（法规版本、生效日期）；5) 护栏设计：合规场景高风险，需设置拒答机制——当检索置信度低时明确告知'无法确认'，避免给出错误合规建议；6) 评估：构建法规问答评测集，用准确率+引用正确率双指标评估。常见追问：如何处理法规更新（增量索引重建）；如何保证答案可溯源（引用条款号+原文片段）；如何做多语言支持（欧盟多语言场景）。

## 核心考点

- RAG架构
- Router路由模式
- ReAct模式
- 护栏与拒答机制
- 答案可溯源

## 常见追问

> 合规场景下如何设计护栏机制，避免Agent给出错误的法律建议？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/EU_Green_Compliance_FAQ_Bot.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/EU_Green_Compliance_FAQ_Bot.ipynb)
