# 创建本地AI Agent

**日期**: 2026-10-25 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

1. 模型选择与部署：创建本地AI Agent的第一步是选择并部署开源大模型（如Llama 3、Qwen等）。通常使用Ollama或vLLM等工具在本地运行模型，提供兼容OpenAI格式的API接口供Agent调用。
2. 框架集成：使用LangChain或LlamaIndex等框架连接本地模型API。通过定义Prompt模板和LLM Chain，构建Agent的交互基础。
3. 工具与记忆绑定：为Agent配置必要的工具（如网络搜索、本地文件读取、代码执行器）以及记忆模块（如对话缓冲记忆），使其具备感知和执行能力。
4. ReAct模式实现：通过提示词工程让模型按照ReAct（Reasoning and Acting）模式工作，实现“思考-行动-观察”的循环，直到得出最终答案。
常见追问：在本地算力有限的情况下，如何优化Agent的响应速度？

## 核心考点

- 本地大模型部署
- Ollama
- LangChain框架
- ReAct模式
- 工具调用

## 常见追问

> 在本地算力有限的情况下，如何优化Agent的响应速度？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/17-creating-local-ai-agents](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/17-creating-local-ai-agents)
