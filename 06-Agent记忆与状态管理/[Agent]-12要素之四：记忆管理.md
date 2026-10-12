# [Agent] 12要素之四：记忆管理

**日期**: 2026-10-12 | **类型**: Theory | **原始分类**: Agent记忆 | **路线图模块**: 06-Agent记忆与状态管理 | **难度**: 中级 | **来源**: GitHub

## 解答

在构建AI Agent的12要素原则中，第四点通常聚焦于Agent的记忆管理机制。Agent的记忆是使其能够维持上下文连贯性并从历史交互中学习的核心组件。记忆主要分为短期记忆和长期记忆：短期记忆依赖于LLM的上下文窗口，用于保持当前对话或任务执行的连贯性，但受限于Token长度；长期记忆则通过将历史交互、用户偏好或事实知识向量化并存储在外部数据库（如向量数据库）中，实现跨会话的知识沉淀。有效的记忆管理需要设计合理的检索与更新策略，确保Agent在需要时能快速召回相关信息，同时避免无关信息干扰上下文。常见追问点在于如何设计记忆的遗忘机制和重要性评估。

## 核心考点

- 短期记忆
- 长期记忆
- 上下文窗口
- 向量数据库
- 记忆检索策略

## 常见追问

> 在有限的上下文窗口中，如何设计机制来压缩或遗忘不重要的历史记忆？

**参考链接**: [https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-4-tools-are-structured-outputs.md](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-4-tools-are-structured-outputs.md)
