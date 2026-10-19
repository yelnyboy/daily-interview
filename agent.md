# AI Agent 开发知识库

> 最后更新: 2026-10-19
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

- [Running multiple Claude Code agents in parallel: what worktrees cannot see](https://dev.to/naw103/running-multiple-claude-code-agents-in-parallel-what-worktrees-cannot-see-4le7) (dev.to) - If you only ever run one coding agent, you do not need most of this. You're also
- [The bug is in the arrangement: finding and cutting your AI agent's data-leak paths](https://dev.to/bhanu_nagpure/the-bug-is-in-the-arrangement-finding-and-cutting-your-ai-agents-data-leak-paths-2c3p) (dev.to) - Give an agent three ordinary tools: one that reads a GitHub issue, one that read
- [OpenAI model used money from digital wallet without permission](https://dev.to/hacksgr/openai-model-used-money-from-digital-wallet-without-permission-5fok) (dev.to) - OpenAI disclosed seven incidents of misaligned AI model behavior, including a ca
- [Help Your Coding Assistant Find the Right Code in Large Repos](https://dev.to/raabdahl/help-your-coding-assistant-find-the-right-code-in-large-repos-20e3) (dev.to) - Get the starter: sdahal1/repo-search-workshop on GitHub. The reproduction, searc
- [Worktree lifecycle for AI agents](https://dev.to/saez520/worktree-lifecycle-for-ai-agents-1ooo) (dev.to) - The problem is not creating worktrees, but managing them   When two or more agen

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

### 已积累题目 (1题)

- [中级] **分布式系统面试连环炮**
  - 考点: CAP理论, Raft一致性算法, 分布式锁
  - 摘要: 分布式系统面试通常围绕以下核心概念展开连环追问：

1. CAP理论：分布式系统在一致性、可用性、分区容错性三者中只能满足两个，网络分区不可避免，需在CP和AP间权衡。
2. 一致性算法：Raft通过...

### 相关文章资源

- [Everyone keeps adding features to AI agents. We deleted ours.](https://dev.to/turingcorp/everyone-is-building-an-agent-workspace-we-deleted-ours-i47) (dev.to) - Everyone is building an agent workspace. We deleted ours.   CloudPal ships witho
- [How AIClaw Tracks Skill Access Without Exporting Prompt or Tool Content](https://dev.to/chowyu12/how-aiclaw-tracks-skill-access-without-exporting-prompt-or-tool-content-3djl) (dev.to) - An agent can have dozens of installed skills, yet installation counts say little
- [Tīrtha Bench: the model data coders actually need (and what we're building next)](https://dev.to/tom_jones_230c4659491adcd/tirtha-bench-the-model-data-coders-actually-need-and-what-were-building-next-4nkj) (dev.to) - When you wire a model into a coding agent, the question is never "which model is
- [Exponential backoff with jitter: 64 of 100 LLM calls still failed](https://dev.to/mattbusel/exponential-backoff-with-jitter-64-of-100-llm-calls-still-failed-2k1m) (dev.to) - Originally published at tensorust.com.  TL;DR: I fired 100 LLM calls at once int
- [I Moved My Prompts Into DynamoDB and the Throttling Went Away](https://dev.to/avneet_bansal_a65b3f31fc4/i-moved-my-prompts-into-dynamodb-and-the-throttling-went-away-3h5o) (dev.to) - Prompts feel like configuration, so it is tempting to park them in whatever mana

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

- [Citation Tracing for Node.js Changelog Search: Lower-Cost Retrieval at Scale](https://dev.to/haelion14/citation-tracing-for-nodejs-changelog-search-lower-cost-retrieval-at-scale-2f6m) (dev.to) - A citation-tracing retrieval path should keep a cheap lexical index in front of 
- [Day 03/90: Hybrid Search in RAG: Can Combining BM25 and Vector Search Find Better Evidence?](https://dev.to/rimsha_kanwal/day-0390-hybrid-search-in-rag-can-combining-bm25-and-vector-search-find-better-evidence-129m) (dev.to) - Your RAG app retrieves five chunks. They look relevant, but none actually answer
- [Your safety check is the outage: cost-aware backoff for governed tool calls](https://dev.to/dekita/your-safety-check-is-the-outage-cost-aware-backoff-for-governed-tool-calls-3ia4) (dev.to) - A governor that blocks bad tool calls can also block the task forever, and its o
- [pg_vectorsearch vs pgvector: The 42-Hour Vector Index Just Became a 100-Minute One](https://dev.to/jamilxt/pgvectorsearch-vs-pgvector-the-42-hour-vector-index-just-became-a-100-minute-one-14d3) (dev.to) - If you have ever kicked off a pgvector HNSW index build on a large embedding tab
- [How I Built CausalMesh: An Autonomous SRE Swarm Powered by FalkorDB](https://dev.to/yashvir_singh_/how-i-built-causalmesh-an-autonomous-sre-swarm-powered-by-falkordb-570a) (dev.to) - How I Built CausalMesh: An Autonomous SRE Swarm Powered by FalkorDB Why Flat Vec

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

### 已积累题目 (8题)

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
- [中级] **Agent规划设计**
  - 考点: 任务分解, 动态规划, 重规划机制
  - 摘要: 1. 任务分解：将复杂目标拆解为可执行的子任务，常用方法包括思维链或树状思维。
2. 计划生成：基于当前状态和历史信息，动态生成或调整执行计划，而非一次性生成死板计划。
3. 执行与反馈：Agent按...
- [中级] **Agent设计模式**
  - 考点: Reflection反思模式, Tool Use工具使用, Planning规划模式
  - 摘要: Agentic Design Patterns是构建AI Agent时常用的架构模式，主要包括以下四种核心模式：

1. 反思模式（Reflection）：Agent在生成输出后自我审查和修正。例如先...
- [中级] **Spring Cloud 微服务架构**
  - 考点: 服务注册与发现, 配置中心, 熔断限流
  - 摘要: Spring Cloud 是一套微服务治理框架，主要解决分布式系统中的常见问题。其核心组件和机制如下：
1. 服务注册与发现：使用 Eureka 或 Nacos 作为注册中心，微服务启动时自动注册，消...
- [中级] **[Agent] LangGraph 文档接收智能体**
  - 考点: LangGraph, 状态图, 条件路由
  - 摘要: 1. 架构设计：使用LangGraph构建有向无环图，节点包含文档解析、分类、实体提取和持久化存储。
2. 状态管理：定义全局状态对象，保存原始文档路径、解析后的文本、提取的结构化实体及当前处理阶段。...
- [中级] **[Agent] 搜索互联网并总结**
  - 考点: ReAct模式, 工具调用, 网页抓取
  - 摘要: 1. 模式选择：采用ReAct（推理与行动）模式，让大模型交替进行思考和工具调用。
2. 工具定义：定义互联网搜索工具（如Tavily API）和网页内容抓取工具，用于获取实时信息。
3. 执行流程：...

### 相关文章资源

- [Nobody Noticed the Agents: What India's CERT-In Advisory Means for Your Network](https://dev.to/hlinor/nobody-noticed-the-agents-what-indias-cert-in-advisory-means-for-your-network-397a) (dev.to) - On October 15, 2026, India's national cyber agency, CERT-In, published advisory 
- [SDLC != ADLC != ASDLC](https://dev.to/remojansen/sdlc-adlc-asdlc-4057) (dev.to) - I recently came across this definition:   The Agentic Development Lifecycle (ADL
- [What is an AI agent harness?](https://dev.to/harshithvaddiparthy/what-is-an-ai-agent-harness-5a10) (dev.to) - By Harshith Vaddiparthy. Originally published in my AI agent harness guide.  An 
- [🌊 What If One Microservice Fails? Building RIPPLE — An AI Agent That Investigates the Ripple Effect](https://dev.to/narasimha_lakshmi_8cb9876/what-if-one-microservice-fails-building-ripple-an-ai-agent-that-investigates-the-ripple-effect-4pkp) (dev.to) - Exploring graph-powered reasoning, MCP, and AI agents for the FalkorDB Graph Hac
- [[Agent Platform in Action (1)] Building a LINE AI Business Card Master with Go and Google ADK 2.0: From Fan-Out Parallel Retrieval to HITL Pause](https://dev.to/evanlin/ai-in-action-building-a-line-ai-business-card-master-with-go-and-google-adk-20-from-fan-out-29n6) (dev.to) - Recap   During the AI Agent development craze over the past year, the first Agen

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

- [Your MCP Hub Exposes Every Tool to Every Agent. That's the Bug.](https://dev.to/jeff_pdc/your-mcp-hub-exposes-every-tool-to-every-agent-thats-the-bug-2ljp) (dev.to) - When an MCP hub exposes the full tool catalog to every connected agent, agents c
- [Scope MCP Keys to the Human, Not to the Team](https://dev.to/jeff_pdc/scope-mcp-keys-to-the-human-not-to-the-team-jm1) (dev.to) - Why team-wide MCP gateway keys are the wrong primitive for non-engineer access, 
- [Laravel MCP: an AI connector without a second API](https://dev.to/nessflow_8283f7335b896207/laravel-mcp-an-ai-connector-without-a-second-api-25pb) (dev.to) - Laravel 13, laravel/mcp 1.0, Passport 13, one public API.  Our customers asked f
- [Notes from a 2 AM On-Call: Why Our MCP Server Silently Died Under Scientific Workflow Load](https://dev.to/lucas_vance/notes-from-a-2-am-on-call-why-our-mcp-server-silently-died-under-scientific-workflow-load-4fe3) (dev.to) - An incident postmortem on stdio buffer deadlocks when piping heavy scientific da
- [When a Teammate Leaves, You Should Not Have to Rotate the Whole MCP URL](https://dev.to/jeff_pdc/when-a-teammate-leaves-you-should-not-have-to-rotate-the-whole-mcp-url-1gb2) (dev.to) - When one teammate leaves or a key leaks, rotating a single access key should not

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

- [How We Built an AI Directory Pipeline with LangGraph and Contentful](https://dev.to/madebymonogram/how-we-built-an-ai-directory-pipeline-with-langgraph-and-contentful-25d1) (dev.to) - For Quicknode’s Builder’s Guide, we built a pipeline that populates over 60 stru
- [One API for Greenhouse, Lever, Ashby & Workday Jobs: Hiring Signals in Python](https://dev.to/torix/one-api-for-greenhouse-lever-ashby-workday-jobs-hiring-signals-in-python-3gb3) (dev.to) - Pull every open job from company career sites into one normalized schema and tur
- [Connecting LangChain to Alfresco Without Writing Another REST Loader](https://dev.to/stefankopfxaldon/connecting-langchain-to-alfresco-without-writing-another-rest-loader-355) (dev.to) - You already have a LangChain application. The content you need is in Alfresco Co

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

### 相关文章资源

- [Is OpenAI Sabotaging Power Users? Continuous 'caas.internal.errors.ClientError' on ChatGPT Python Sandbox](https://dev.to/n_b_1784bc3d5/is-openai-sabotaging-power-users-continuous-caasinternalerrorsclienterror-on-chatgpt-python-1dkn) (dev.to) - Hi everyone,  I am encountering a persistent and blocking error while using Chat

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
