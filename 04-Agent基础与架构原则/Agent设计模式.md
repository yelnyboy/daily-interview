# Agent设计模式

**日期**: 2026-10-23 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

Agentic Design Patterns是构建AI Agent时常用的架构模式，主要包括以下四种核心模式：

1. 反思模式（Reflection）：Agent在生成输出后自我审查和修正。例如先生成代码，再让Agent检查代码质量并提出改进建议，然后据此优化。代表实现如Self-Refine、Reflexion。

2. 工具使用模式（Tool Use）：Agent调用外部工具扩展能力边界，如搜索引擎、代码执行器、API调用等。LLM作为决策大脑，根据任务选择合适的工具并解析返回结果。

3. 规划模式（Planning）：Agent将复杂任务分解为可执行的子步骤。典型方法包括ReAct（推理+行动交替）、Tree of Thoughts（树状思维探索）、Plan-and-Execute（先规划再执行）。

4. 多智能体协作模式（Multi-Agent Collaboration）：多个Agent各司其职，通过对话或消息传递协作完成复杂任务。如AutoGen中的助手Agent与用户Agent交互，或CrewAI中多个角色Agent分工协作。

这些模式可以组合使用，例如先规划再分配给多个Agent执行，每个Agent使用工具并反思结果。

## 核心考点

- Reflection反思模式
- Tool Use工具使用
- Planning规划模式
- Multi-Agent多智能体协作
- ReAct与Tree of Thoughts

## 常见追问

> 在实际项目中，如何选择合适的Agent设计模式？是否应该组合使用多种模式？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/03-agentic-design-patterns](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/03-agentic-design-patterns)
