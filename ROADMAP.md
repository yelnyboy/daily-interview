# AI Agent 开发学习路线图

> 基于 [roadmap.sh/ai-agents](https://roadmap.sh/ai-agents)、[Microsoft AI Agents for Beginners](https://github.com/microsoft/ai-agents-for-beginners)、[12-Factor Agents](https://github.com/humanlayer/12-factor-agents) 综合

## 学习路径

按以下顺序学习，`[高]` 为核心必学，`[中]` 为进阶提升。

### 1. 基础与先决条件 `[高]`
- 后端开发基础
- Git 与终端操作
- REST API 设计与调用
- 流式与非流式响应处理
- 模型定价与成本控制基础

### 2. LLM 核心与提示工程 `[高]`
- Transformer 与 LLM 基础
- 分词与上下文窗口
- 模型参数调优 (Temperature, Top-p, 惩罚项等)
- 提示工程技巧 (具体化、提供上下文、使用示例)
- 上下文工程
- 开源与闭源模型选择
- 推理模型与标准模型对比
- 微调与提示工程权衡

### 3. RAG 与向量数据库 `[高]`
- 文本嵌入与向量搜索
- RAG 基础架构
- Agentic RAG 设计模式
- 向量数据库集成与用户画像存储

### 4. Agent 基础与架构原则 `[高]`
- 什么是 AI Agent 及其应用场景
- Agent 循环 (感知-推理-行动-观察)
- 自然语言到工具调用
- 拥有你的提示词与上下文窗口
- 工具即结构化输出
- 小型专注的 Agent 设计
- 统一执行状态与无状态 Reducer

### 5. 工具使用与集成 `[高]`
- 工具定义 (Web 搜索, 代码执行/REPL, 数据库查询等)
- 手动工具调用 vs LLM 原生函数调用
- 模型上下文协议 (MCP: Hosts, Clients, Servers)
- 创建 MCP 服务器
- 浏览器自动化使用

### 6. Agent 记忆与状态管理 `[高]`
- 短期与长期记忆
- 情景记忆与语义记忆
- 记忆总结与压缩
- 遗忘与老化机制
- 启动/暂停/恢复与随处触发
- 通过工具联系人类

### 7. Agent 设计模式与规划 `[高]`
- ReAct 模式
- 思维链 (Chain of Thought) 与思维树 (Tree of Thought)
- 规划器-执行器 (Planner-Executor)
- 拥有你的控制流
- 元认知与自我反思
- 自批评 Agent 设计

### 8. Agent 框架与生态系统 `[中]`
- OpenAI Assistant API 与 Gemini 函数调用
- LangChain 与 LlamaIndex
- LangGraph 与状态图
- AutoGen 与 CrewAI (多 Agent 框架)
- Microsoft Agent Framework
- Haystack 与 Smol Depot

### 9. 多智能体系统 `[中]`
- 多 Agent 协作模式
- DAG Agents (有向无环图 Agent)
- 角色分配与任务编排
- Agent 间通信协议

### 10. 测试、评估与可观测性 `[高]`
- 关键指标追踪与单元/集成测试
- 人类在环评估
- 评估工具 (LangSmith, Ragas, DeepEval)
- 结构化日志与追踪
- 可观测性平台 (LangSmith, Helicone, LangFuse, openllmetry)

### 11. 安全与可信赖性 `[高]`
- 提示注入与越狱防御
- 工具沙箱与权限控制
- 数据隐私与 PII 脱敏
- 偏见与毒性防护栏
- 红队测试与构建可信赖的 Agent

### 12. 生产部署与扩展 `[高]`
- 部署可扩展的 Agent 架构
- 本地 AI Agent 部署
- 错误压缩与处理机制
- Agno 与 LangGraph 生产实践

## 目录结构

```
daily-interview/
├── README.md           (本文件)
├── ROADMAP.md          (学习导图)
├── index.md            (题目索引)
├── 01-基础与先决条件/
├── 02-LLM核心与提示工程/
├── 03-RAG与向量数据库/
├── 04-Agent基础与架构原则/
├── 05-工具使用与集成/
├── 06-Agent记忆与状态管理/
├── 07-Agent设计模式与规划/
├── 08-Agent框架与生态系统/
├── 09-多智能体系统/
├── 10-测试评估与可观测性/
├── 11-安全与可信赖性/
└── 12-生产部署与扩展/
```
