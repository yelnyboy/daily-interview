# 微软 Agent Framework 详解

**日期**: 2026-11-09 | **类型**: Theory | **原始分类**: Agent框架 | **路线图模块**: 08-Agent框架与生态系统 | **难度**: 中级 | **来源**: GitHub

## 解答

Microsoft Agent Framework 是微软于 2025 年推出的统一智能体开发框架，整合了此前 AutoGen（多智能体协作）与 Semantic Kernel（企业级编排）两大项目的优势，目标是成为构建生产级 AI Agent 的标准方案。核心要点：1) 统一抽象：提供 Agent、ChatClient、Workflow 等核心抽象，兼容 OpenAI、Azure OpenAI、Anthropic 等多种模型提供商；2) Agent 基础：Agent 是具备指令、身份和工具调用能力的对话实体，通过 AgentThread 管理会话状态；3) Workflow 编排：支持以有向图方式编排多个 Agent 与工具节点，内置顺序、并行、汇聚等模式，支持人机协同（Human-in-the-loop）节点；4) 多智能体支持：可组合多个 Agent 实现群聊、协作、评审等模式，继承 AutoGen 的多智能体能力；5) 工具集成：支持函数调用、MCP（Model Context Protocol）工具接入，以及 A2A 协议实现跨框架互操作；6) 可观测与安全：集成 OpenTelemetry 遥测、内容安全过滤器，适合企业级部署。常见追问：与 LangChain/LangGraph 的区别？AutoGen 和 Semantic Kernel 用户如何迁移？Workflow 的状态如何持久化？

## 核心考点

- AutoGen 与 Semantic Kernel 整合
- Agent 抽象与 AgentThread
- Workflow 有向图编排
- MCP 工具协议
- 多智能体协作

## 常见追问

> Microsoft Agent Framework 与 LangGraph 在编排模型和状态管理上的核心差异是什么？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/14-microsoft-agent-framework](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/14-microsoft-agent-framework)
