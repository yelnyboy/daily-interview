# Agentic RAG：智能体增强检索生成

**日期**: 2026-10-27 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

Agentic RAG是将Agent自主决策能力与RAG检索增强生成相结合的范式：
1. 传统RAG是线性流程：检索→拼接→生成，缺乏灵活性和迭代能力。
2. Agentic RAG引入Agent作为控制器，自主决定何时检索、检索什么、如何使用检索结果。
3. 支持多轮检索：Agent可以先检索初步信息，根据结果决定是否需要补充检索。
4. 支持工具选择：Agent可以根据问题类型选择不同的检索工具（向量搜索、关键词搜索、SQL查询等）。
5. 支持结果评估：Agent可以对检索结果进行质量评估，过滤低质量内容。
6. 支持自我反思：Agent可以检查生成答案是否充分，决定是否需要再次检索。

常见追问：Agentic RAG相比传统RAG的延迟如何？如何平衡自主性和效率？

## 核心考点

- Agent自主决策
- 多轮检索
- 工具选择
- 结果评估
- 自我反思

## 常见追问

> Agentic RAG的多轮检索如何避免延迟过高？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/05-agentic-rag](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/05-agentic-rag)
