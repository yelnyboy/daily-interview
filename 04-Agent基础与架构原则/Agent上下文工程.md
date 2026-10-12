# Agent上下文工程

**日期**: 2026-10-12 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

上下文工程是指在LLM Agent中，系统性地管理和组织输入给大模型的上下文信息，以最大化模型推理性能和任务完成率。其核心在于如何在有限的上下文窗口内，提供最相关、最有效的信息。
1. 窗口管理：合理分配系统提示、用户输入、历史对话、工具描述和RAG检索内容的Token比例，避免超出限制导致截断。
2. 动态组装：根据当前任务状态，动态过滤和选择最相关的记忆或知识注入提示，而非全量塞入。
3. 信息压缩：对长对话历史或冗长文档进行摘要提取，保留核心语义，降低Token消耗。
4. 结构化引导：使用XML标签或Markdown等结构化格式组织上下文，引导模型注意力集中在关键信息上。
5. 检索增强：结合向量数据库，按需检索外部知识作为上下文补充。
常见追问：在多轮对话中，如何平衡近期上下文和长期记忆的权重？

## 核心考点

- 上下文窗口管理
- 动态上下文组装
- 信息压缩与摘要
- 结构化提示
- 检索增强生成

## 常见追问

> 在多轮对话中，如何平衡近期上下文和长期记忆的权重？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/12-context-engineering](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/12-context-engineering)
