# Agent 协议（Agentic Protocols）

**日期**: 2026-11-26 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

Agentic Protocols 指智能体生态中标准化通信与交互的协议体系，主要回答'Agent 如何连接工具'和'Agent 之间如何协作'两大问题。核心内容包括：1) MCP（Model Context Protocol）：Anthropic 推出的开放标准，统一 LLM 应用与外部工具、数据源的连接方式，采用 Client-Server 架构，提供 tools、resources、prompts 三类原语，解决 M×N 集成碎片化问题；2) A2A（Agent2Agent Protocol）：Google 主推的 Agent 间通信协议，基于 HTTP/JSON-RPC，通过 Agent Card 描述能力，支持任务委托与状态跟踪；3) ACP（Agent Communication Protocol）：IBM/Beam 提出，统一不同框架构建的 Agent 的互操作接口；4) Function Calling / Tool Use：OpenAI 等厂商的原生工具调用机制，是上述协议的底层基础；5) LSP 类比：MCP 之于 Agent 生态，类似 LSP 之于编辑器生态，一次实现处处可用。面试中常追问：MCP 与 Function Calling 的区别（前者是跨应用的标准协议，后者是模型厂商的私有接口）；MCP 的传输方式（stdio 与 SSE/HTTP Streamable）；协议标准化带来的安全与治理挑战。

## 核心考点

- MCP 协议
- A2A 协议
- Function Calling
- 互操作性
- Client-Server 架构

## 常见追问

> MCP 协议中的 tools、resources、prompts 三类原语分别适用于什么场景？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/11-agentic-protocols](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/11-agentic-protocols)
