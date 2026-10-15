# AI Agent 开发知识库

> 最后更新: 2026-10-15
> 基于 roadmap.sh/ai-agents + Microsoft AI Agents + 12-Factor Agents
> 每日自动抓取 + 面试题积累

---

## 目录

1. [基础与先决条件](#1-基础与先决条件)
2. [LLM核心与提示工程](#2-LLM核心与提示工程)
3. [RAG与向量数据库](#3-RAG与向量数据库)
4. [Agent基础与架构原则](#4-Agent基础与架构原则)
5. [工具使用与集成](#5-工具使用与集成)
6. [Agent记忆与状态管理](#6-Agent记忆与状态管理)
7. [Agent设计模式与规划](#7-Agent设计模式与规划)
8. [Agent框架与生态系统](#8-Agent框架与生态系统)
9. [多智能体系统](#9-多智能体系统)
10. [测试评估与可观测性](#10-测试评估与可观测性)
11. [安全与可信赖性](#11-安全与可信赖性)
12. [生产部署与扩展](#12-生产部署与扩展)

---

## 1. 基础与先决条件

> 构建AI Agent所需的软件开发与API基础技能

### 知识点

- 后端开发基础
- Git与终端操作
- REST API设计与调用
- 流式与非流式响应处理
- 模型定价与成本控制基础

### 相关文章资源

- [PDF Knowledge Retrieval Under Latency Budgets — An Architecture Decision Record](https://dev.to/titanj53/pdf-knowledge-retrieval-under-latency-budgets-an-architecture-decision-record-275) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [The State of AI Instruction Quality: Q3 2026](https://dev.to/reporails/the-state-of-ai-instruction-quality-q3-2026-19bg) (dev.to) - 91% of the most-starred repos on GitHub give their coding agent at least one ins
- [Fallback Design in Legal Contract Review Retrieval Architecture for Teams](https://dev.to/algernoncross4103/fallback-design-in-legal-contract-review-retrieval-architecture-for-teams-42pg) (dev.to) - Use a staged retrieval design with explicit collections, bounded queries, and tr
- [Meta and OpenAI present digital assistants that work even when you turn off the device](https://dev.to/hacksgr/meta-and-openai-present-digital-assistants-that-work-even-when-you-turn-off-the-device-54ia) (dev.to) - Meta and OpenAI introduced persistent autonomous AI agents, Muse and ChatGPT Dot
- [Prompts mal usados y cómo corregir prompts de IA](https://dev.to/henryramireztech/prompts-mal-usados-y-como-corregir-prompts-de-ia-3oe1) (dev.to) - Los prompts mal usados y la falta de criterio técnico para corregir prompts de I

---

## 2. LLM核心与提示工程

> 理解大语言模型原理并掌握提示词与上下文管理技术

### 知识点

- Transformer与LLM基础
- 分词与上下文窗口
- 模型参数调优(Temperature/Top-p/惩罚项)
- 提示工程技巧(Few-shot/Zero-shot/CoT)
- 上下文工程
- 开源与闭源模型选择
- 推理模型与标准模型对比
- 微调与提示工程权衡
- 流式响应(SSE)

### 相关文章资源

- [AI Engineering Is Easy. So How Do We Change How We Work?](https://dev.to/ujja/ai-engineering-is-easy-so-how-do-we-change-how-we-work-3lik) (dev.to) - In Part 1, I wrote about the uncomfortable part of AI-assisted engineering: the 
- [Your agent benchmark's "user" is a second model, and 24.4% of its successful runs broke the user's own script](https://dev.to/cole_halton_42f71d71b809b/your-agent-benchmarks-user-is-a-second-model-and-244-of-its-successful-runs-broke-the-users-59p6) (dev.to) - There's a user proxy in one of these benchmarks that opens the conversation with
- [From god-mode to governed: an AI agent that can’t exceed its grant](https://dev.to/rojaneerdev/from-god-mode-to-governed-an-ai-agent-that-cant-exceed-its-grant-4ilk) (dev.to) - Last time I argued that AI agents are running as god-mode service accounts: an a
- [How AIClaw 3.7.14 Makes Truncated Tool Output Recoverable](https://dev.to/chowyu12/how-aiclaw-3714-makes-truncated-tool-output-recoverable-217i) (dev.to) - A command can return the right data while an agent still gives the wrong answer.
- [LLM wiki vs. RAG: what each one is, and what I measured when I used a wiki as a RAG replacement (it was slower)](https://dev.to/vellumkasane/llm-wiki-vs-rag-what-each-one-is-and-what-i-measured-when-i-used-a-wiki-as-a-rag-replacement-it-5fg3) (dev.to) - Disclosure: this post was written by an LLM agent (Claude Code) that operates th

---

## 3. RAG与向量数据库

> 掌握检索增强生成技术以扩展Agent的知识边界

### 知识点

- 文本嵌入与向量搜索
- RAG基础架构
- Agentic RAG设计模式
- 向量数据库(Pinecone/Milvus/Chroma/Weaviate)
- 文档切分与重排序

### 已积累题目 (1题)

- [中级] **RAG系统中如何优化向量检索的召回率？**
  - 考点: 语义分块, Embedding模型, 混合检索
  - 摘要: 优化RAG系统的向量检索召回率需从数据、模型和检索策略多维度入手。首先在数据层面，应提升文档分块质量，采用基于语义的分块策略而非固定长度，以保留上下文完整性。其次在模型层面，选择或微调更适合特定业务领...

### 相关文章资源

- [Building a Multi-Tenant RAG in 8GB RAM: Why I Ditched Qdrant and Kafka (Phase 0)](https://dev.to/alejandrotg-code/building-a-multi-tenant-rag-in-8gb-ram-why-i-ditched-qdrant-and-kafka-phase-0-8b) (dev.to) - I have 8 GB of RAM and 6 vCPUs. With those specs, I'm building and running a ful
- [Recruiting Candidate Search Source Deduplication — A 3-Stage Node.js Retrieval Design](https://dev.to/paxtonshaw1459/recruiting-candidate-search-source-deduplication-a-3-stage-nodejs-retrieval-design-26nd) (dev.to) - Short answer: use a staged retrieval design with explicit collections, bounded q
- [Financial Research Dashboard Retrieval: Privacy Controls and Freshness Explained](https://dev.to/silhouette72591483/financial-research-dashboard-retrieval-privacy-controls-and-freshness-explained-3cdo) (dev.to) - Financial research dashboards fail in predictable ways: an answer is fresh but u
- [Node.js Candidate Retrieval: Three Tenant-Isolation Gates for Game Hiring](https://dev.to/kasimirberg5341/nodejs-candidate-retrieval-three-tenant-isolation-gates-for-game-hiring-55hj) (dev.to) - Game studios rarely have one clean candidate corpus. A recruiting search may spa
- [Travel Itinerary Retrieval Architecture: Versioning for Grounded Citations](https://dev.to/milohastings5316/travel-itinerary-retrieval-architecture-versioning-for-grounded-citations-3mge) (dev.to) - Short answer: for a travel itinerary planner, keep immutable document versions f

---

## 4. Agent基础与架构原则

> 理解Agent的核心循环与12-Factor设计原则

### 知识点

- 什么是AI Agent及其应用场景
- Agent循环(感知-推理-行动-观察)
- 12-Factor Agents原则
- 自然语言到工具调用
- 拥有你的提示词与上下文窗口
- 工具即结构化输出
- 小型专注的Agent设计
- 统一执行状态与无状态Reducer

### 已积累题目 (4题)

- [中级] **Agent 12-Factor 第12条原则**
  - 考点: 进程隔离, 环境一致性, 无状态执行
  - 摘要: Agent 12-Factor 的第12条原则通常关注“管理任务”或“可观测性”。以管理任务为例，核心思想是将一次性管理任务作为独立进程运行。具体包括以下几点：
1. 进程隔离：数据迁移、状态清理或模...
- [中级] **Agent上下文工程**
  - 考点: 上下文窗口管理, 动态上下文组装, 信息压缩与摘要
  - 摘要: 上下文工程是指在LLM Agent中，系统性地管理和组织输入给大模型的上下文信息，以最大化模型推理性能和任务完成率。其核心在于如何在有限的上下文窗口内，提供最相关、最有效的信息。
1. 窗口管理：合理...
- [中级] **Agent实战：GenAI职业助手黑客松**
  - 考点: ReAct模式, 工具集成, 记忆机制
  - 摘要: 1. 需求分析：明确GenAI职业助手的核心功能，如简历优化、模拟面试、职位推荐及职业规划咨询。2. 架构设计：采用ReAct（Reasoning and Acting）设计模式，让Agent能够先推...
- [中级] **Spring Cloud 微服务架构**
  - 考点: 服务注册与发现, 配置中心, 熔断限流
  - 摘要: Spring Cloud 是一套微服务治理框架，主要解决分布式系统中的常见问题。其核心组件和机制如下：
1. 服务注册与发现：使用 Eureka 或 Nacos 作为注册中心，微服务启动时自动注册，消...

### 相关文章资源

- [OpenAI Data Shows AI Agents Drive More Than Half of EU Business Output Tokens](https://dev.to/alifar/openai-data-shows-ai-agents-drive-more-than-half-of-eu-business-output-tokens-1eob) (dev.to) - OpenAI says its agentic tools, Codex and ChatGPT Work, now generate more than ha
- [Requests, Promises, Assertions, and Declarations: Rewriting Our AI Agent Workflow as a 1986 'Committed Speech' Machine](https://dev.to/gde/requests-promises-assertions-and-declarations-rewriting-our-ai-agent-workflow-as-a-1986-4k4c) (dev.to) - Why do 200-line agent prompts, Asimov's Three Laws, and sequential pre-landing c
- [LangChain agents that earn: a working DAiL integration guide](https://dev.to/innerozma/langchain-agents-that-earn-a-working-dail-integration-guide-3ab6) (dev.to) - LangChain agents that earn: a working DAiL integration guide   LangChain gives y
- [Secure AI Agents - How to put the Humanbound Firewall in front of your agent](https://dev.to/humanbound_ai/secure-ai-agents-how-to-put-the-humanbound-firewall-in-front-of-your-agent-169j) (dev.to) - Two lines of Python attach the Humanbound Firewall to a LangChain agent. This gu
- [We open-sourced the tool that failed its own kill rule](https://dev.to/dawncoral/we-open-sourced-the-tool-that-failed-its-own-kill-rule-bfd) (dev.to) - Before we ran the experiment, we wrote down the rule that would kill it.  The pr

---

## 5. 工具使用与集成

> 赋予Agent操作外部世界和执行任务的能力

### 知识点

- 工具定义(Web搜索/代码执行/数据库查询/API请求)
- 手动工具调用 vs LLM原生函数调用
- 模型上下文协议(MCP)
- 创建MCP服务器
- 浏览器自动化

### 相关文章资源

- [You Shipped an MCP Server. Now How Do You Know What Users Are Doing With It?](https://dev.to/alexandre_ayoub_a78549839/you-shipped-an-mcp-server-now-how-do-you-know-what-users-are-doing-with-it-29gi) (dev.to) - MCP (Model Context Protocol) is changing how people interact with software.  Ins
- [Generate Images and Videos in Claude Code with One Sentence](https://dev.to/modelflare_dev/generate-images-and-videos-in-claude-code-with-one-sentence-5gg8) (dev.to) - Install the Modelflare plugin or MCP server in Claude Code, set one Smart API Ke
- [Ask Claude Code why your traffic spiked (an MCP walkthrough)](https://dev.to/imageapi_ai_060a84ea83609/ask-claude-code-why-your-traffic-spiked-an-mcp-walkthrough-3eld) (dev.to) - Disclosure: I built measuremy.site, the analytics tool used in this post. All th
- [Order a Database in Plain English. Crossplane Platform APIs, Now AI-Ready!](https://dev.to/ravibagri2/order-a-database-in-plain-english-crossplane-platform-apis-now-ai-ready-ab9) (dev.to) - A developer needs a Postgres database for a new service.  On a Crossplane platfo
- [I built dot-mcp: it gives ChatGPT a computer (shell, files, memory, browser)](https://dev.to/zhypix_34febd0a21259f4b00/i-built-dot-mcp-it-gives-chatgpt-a-computer-shell-files-memory-browser-2m0m) (dev.to) - I'm the author of dot-mcp, an open-source MCP server written in Python. You inst

---

## 6. Agent记忆与状态管理

> 实现Agent的短期/长期记忆与状态持久化机制

### 知识点

- 短期与长期记忆
- 情景记忆与语义记忆
- 记忆总结与压缩
- 遗忘与老化机制
- 启动/暂停/恢复
- 通过工具联系人类(Human-in-the-loop)

### 已积累题目 (1题)

- [中级] **[Agent] 12要素之四：记忆管理**
  - 考点: 短期记忆, 长期记忆, 上下文窗口
  - 摘要: 在构建AI Agent的12要素原则中，第四点通常聚焦于Agent的记忆管理机制。Agent的记忆是使其能够维持上下文连贯性并从历史交互中学习的核心组件。记忆主要分为短期记忆和长期记忆：短期记忆依赖于...

---

## 7. Agent设计模式与规划

> 掌握Agent的推理、规划与控制流设计模式

### 知识点

- ReAct模式(Reason+Act)
- 思维链(CoT)与思维树(ToT)
- 规划器-执行器(Planner-Executor)
- 拥有你的控制流
- 元认知与自我反思
- 自批评Agent设计

---

## 8. Agent框架与生态系统

> 熟悉主流Agent开发框架以加速工程落地

### 知识点

- OpenAI Assistant API
- LangChain与LlamaIndex
- LangGraph与状态图
- AutoGen与CrewAI
- Microsoft Agent Framework
- Haystack与Smol Depot

### 相关文章资源

- [Your Agent Harness Is Paying LLM Prices for Classifier Decisions](https://dev.to/jayeshtankariya/your-agent-harness-is-paying-llm-prices-for-classifier-decisions-4dde) (dev.to) - Keep your LangGraph router. Let a System 1 decision model take the calls it's co
- [0 of 12 AI agent frameworks can cap what an agent spends in dollars (we checked)](https://dev.to/aidakh_e8124113e2a1bf1fc9/0-of-12-ai-agent-frameworks-can-cap-what-an-agent-spends-in-dollars-we-checked-59fe) (dev.to) - Disclosure: I work on Pink Agentic AI Payments at PinkWallet, a payment-control 
- [AI Agent Frameworks Compared: LangGraph vs CrewAI vs AutoGen](https://dev.to/avenotech/ai-agent-frameworks-compared-langgraph-vs-crewai-vs-autogen-2l2o) (dev.to) - Which AI agent framework to pick in 2026: release history, production failures a
- [Production RAG with LangChain & LangGraph: Retrieval, Reranking & Agentic Workflows](https://dev.to/ipsphil_digital/production-rag-with-langchain-langgraph-retrieval-reranking-agentic-workflows-1kd9) (dev.to) - Production RAG with LangChain &amp; LangGraph: End-to-End Implementation   Build

---

## 9. 多智能体系统

> 构建多个Agent协作完成复杂任务的系统

### 知识点

- 多Agent协作模式
- DAG Agents
- 角色分配与任务编排
- Agent间通信协议

---

## 10. 测试评估与可观测性

> 确保Agent行为可靠、可追踪且可量化评估

### 知识点

- 关键指标追踪
- 单元/集成测试
- 人类在环评估
- 评估工具(LangSmith/Ragas/DeepEval)
- 结构化日志与追踪
- 可观测性平台(LangSmith/Helicone/LangFuse/openllmetry)

---

## 11. 安全与可信赖性

> 防御攻击并确保Agent在生产环境中的安全合规

### 知识点

- 提示注入与越狱防御
- 工具沙箱与权限控制
- 数据隐私与PII脱敏
- 偏见与毒性防护栏
- 红队测试
- 构建可信赖的Agent

---

## 12. 生产部署与扩展

> 将Agent推向生产环境并实现规模化运行

### 知识点

- 部署可扩展的Agent架构
- 本地AI Agent部署
- 错误压缩与处理机制
- Agno与LangGraph生产实践
- 无状态化与水平扩展

---

## 附: 算法题

> LeetCode 每日一题，数据结构与算法基础训练

*（暂无）*

## 附: 编程基础题

> Python/Java/数据库等编程基础面试题

*（暂无）*
