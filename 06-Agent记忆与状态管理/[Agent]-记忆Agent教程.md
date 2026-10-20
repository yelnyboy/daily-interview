# [Agent] 记忆Agent教程

**日期**: 2026-10-20 | **类型**: Theory | **原始分类**: Agent记忆 | **路线图模块**: 06-Agent记忆与状态管理 | **难度**: 中级 | **来源**: GitHub

## 解答

1. 短期记忆：通常指Agent在当前对话或任务执行过程中的上下文信息，一般直接存放在Prompt中，受限于大模型的上下文窗口大小。
2. 长期记忆：通过将历史交互或知识存储在外部数据库（如向量数据库）中，在需要时通过检索（RAG）的方式召回，从而突破上下文限制。
3. 记忆更新机制：Agent需要具备遗忘和更新机制，过滤掉无关信息，保留关键任务上下文，避免记忆库膨胀和噪声干扰。
4. 记忆检索策略：常用的检索方式包括基于向量相似度的语义检索、基于时间倒序的检索，或结合知识图谱的结构化检索。
常见追问：如何设计记忆的遗忘机制以防止上下文窗口溢出或信息过载？

## 核心考点

- 短期记忆
- 长期记忆
- 向量检索
- 记忆更新机制

## 常见追问

> 在多轮对话中，如何平衡短期记忆的实时性与长期记忆的稳定性？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/memory-agent-tutorial.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/memory-agent-tutorial.ipynb)
