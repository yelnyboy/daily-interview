# 基于 LangGraph 的汽车购买 Agent 设计

**日期**: 2026-11-10 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 高级 | **来源**: GitHub

## 解答

这是一个典型的 ReAct + 状态机式 Agent 应用，用 LangGraph 编排购车决策流程。核心设计要点：
1. 状态定义：用 TypedDict 定义 GraphState，包含用户预算、用途偏好、候选车型列表、当前对话轮次等字段。
2. 节点设计：将流程拆分为需求收集节点、车型检索节点（调用工具查询数据库/API）、比较分析节点（LLM 推理）、试驾预约节点等。
3. 条件边路由：用 conditional_edges 根据状态决定下一步，如信息不足则回到提问节点，信息完整则进入推荐节点，形成循环图而非简单线性链。
4. 工具集成：通过 ToolNode 或 function calling 接入库存查询、价格计算、贷款计算器等外部工具。
5. 记忆与人工接管：用 checkpointer 持久化会话状态，在关键决策（如下单）前设置 interrupt 实现人机协同（HITL）。
6. 防死循环：设置最大迭代次数 recursion_limit，并对节点输出做校验。常见追问：如何处理 LLM 输出不符合状态 schema、如何做流式输出、如何评估 Agent 决策质量。

## 核心考点

- LangGraph 状态图编排
- 条件边与循环路由
- TypedDict 状态管理
- 工具调用集成
- Checkpointer 持久化与 HITL

## 常见追问

> 如果用户需求在对话中途发生变化，你的图结构如何支持回退和状态更新？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/car_buyer_agent_langgraph.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/car_buyer_agent_langgraph.ipynb)
