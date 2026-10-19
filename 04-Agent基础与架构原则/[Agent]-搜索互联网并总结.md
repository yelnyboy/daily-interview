# [Agent] 搜索互联网并总结

**日期**: 2026-10-19 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

1. 模式选择：采用ReAct（推理与行动）模式，让大模型交替进行思考和工具调用。
2. 工具定义：定义互联网搜索工具（如Tavily API）和网页内容抓取工具，用于获取实时信息。
3. 执行流程：Agent接收用户查询后，先调用搜索工具获取相关网页链接，再调用抓取工具提取网页正文内容。
4. 总结输出：将抓取到的多源信息作为上下文输入给LLM，进行去重、提炼和结构化总结，最终返回给用户。
5. 常见追问：如何处理搜索结果中的冗余信息或避免大模型幻觉？

## 核心考点

- ReAct模式
- 工具调用
- 网页抓取
- 信息总结

## 常见追问

> 如何在搜索和总结过程中避免大模型的幻觉并确保信息的时效性？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/search_the_internet_and_summarize.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/search_the_internet_and_summarize.ipynb)
