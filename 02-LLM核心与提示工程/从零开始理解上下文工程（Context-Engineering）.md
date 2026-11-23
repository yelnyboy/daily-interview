# 从零开始理解上下文工程（Context Engineering）

**日期**: 2026-11-23 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 02-LLM核心与提示工程 | **难度**: 高级 | **来源**: GitHub

## 解答

上下文工程是提示词工程的进化版，指系统性地管理进入 LLM 上下文窗口的所有信息，是构建可靠 Agent 的核心技能。核心要点：
1. 上下文窗口是稀缺资源：LLM 的注意力有限且存在“迷失在中间”问题，需精心编排内容顺序与密度。
2. 上下文的组成：系统提示、工具定义、对话历史、检索到的知识（RAG）、记忆、中间推理状态等，需统一规划。
3. 读写框架（Anthropic 提出）：Agent 每轮都在“读取”上下文并“写入”新内容（工具调用结果、思考过程），要管理这个循环中的信息流。
4. 常见策略：压缩（summarization）、裁剪（pruning）、结构化（如 XML/JSON 标签分区）、分层记忆（工作记忆 vs 长期记忆）。
5. Just-in-time 检索：不要一次性塞入所有信息，而是按需在合适的时机注入相关上下文，减少噪音。
6. 上下文腐烂（context rot）：随着轮次增加，无关信息累积导致性能下降，需要主动清理和重置。
7. 实践模式：为不同信息类型分配固定格式区块；工具结果做摘要而非原文全量放入；关键指令放在上下文首尾。
常见追问：上下文工程与 RAG 的关系（RAG 是上下文工程的一个子问题）；如何评估上下文质量；多轮对话中如何做历史压缩。

## 核心考点

- 上下文窗口管理
- 读写循环
- 信息压缩与裁剪
- Just-in-time 检索
- 上下文腐烂

## 常见追问

> 在一个长会话 Agent 中，你会设计怎样的机制来防止上下文腐烂并保持关键信息不丢失？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/context_engineering_from_scratch.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/context_engineering_from_scratch.ipynb)
