# [Agent] 12-Factor方法论 第9条：最大化并行度

**日期**: 2026-10-22 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

1. 最大化并行度要求Agent在处理相互独立的任务时，应尽可能采用并发执行而非串行等待。
2. 这种设计能显著减少用户等待时间，提升系统资源利用率，使Agent响应更加敏捷。
3. 具体实现包括将独立的工具调用并行化，或将无依赖的子任务分发给不同的并发执行流。
4. 开发者在设计工作流时，需严格识别任务间的依赖关系，仅对存在数据依赖的步骤进行串行编排。
5. 常见追问点：并行执行时如何进行状态同步与错误处理？

## 核心考点

- 并发执行
- 任务依赖
- 资源利用率
- 工作流编排

## 常见追问

> 在Agent并行执行任务时，如何保证状态的一致性和处理部分失败的情况？

**参考链接**: [https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-09-compact-errors.md](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-09-compact-errors.md)
