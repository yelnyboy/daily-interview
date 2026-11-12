# [Agent] 十二要素（12-Factor Agents）第 11 条

**日期**: 2026-11-12 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

十二要素 Agent（12-Factor Agents）是借鉴十二要素应用（12-Factor App）理念总结的 LLM Agent 工程化最佳实践。第 11 条的核心思想是：将 Agent 的所有状态和上下文持久化到外部存储（如数据库），而不是依赖内存中的会话对象。具体要点：1) Agent 的运行状态（消息历史、中间变量、工具调用结果）应作为可序列化的数据存储在外部，使 Agent 无状态化；2) 这样可以实现故障恢复：进程崩溃后可从检查点（checkpoint）恢复继续执行；3) 支持人类介入（human-in-the-loop）：暂停等待用户审批后，从存储中加载上下文继续运行；4) 便于调试和回放：完整记录状态转换历史，可复现问题；5) 便于水平扩展：任意实例都能加载状态处理请求。常见追问点：为什么不能只依赖内存中的对话历史？如何设计状态存储的 Schema？检查点应该保存哪些内容（消息列表、工具调用记录、Agent 内部变量）？如何处理长时间运行任务的恢复？

## 核心考点

- 状态外置与持久化
- 检查点与故障恢复
- 无状态 Agent 设计
- human-in-the-loop
- 可调试性与回放

## 常见追问

> 如果 Agent 运行到一半进程挂掉，你会如何设计检查点机制让它从断点恢复执行？

**参考链接**: [https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-11-trigger-from-anywhere.md](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-11-trigger-from-anywhere.md)
