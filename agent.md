# AI Agent 开发知识库

> 最后更新: 2026-10-21
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

- [Inside VOICE-RAG: From Speech to Grounded Answers](https://dev.to/the_infernix/inside-voice-rag-from-speech-to-grounded-answers-1khn) (dev.to) - Pavan Ganesh Indupudi (Infernix) · Originally published at the-infernix.github.i
- [RepoPilot: How an AWS Lambda Agent Scores GitHub Repos Before You Clone Them](https://dev.to/mech_app_ai/repopilot-how-an-aws-lambda-agent-scores-github-repos-before-you-clone-them-4k3k) (dev.to) - Lambda + Bedrock pipeline that scores repository risk in 60 seconds. Examining t
- [I open-sourced Tokenade, my token optimizer for coding agents. Here is why the paid model did not hold](https://dev.to/paul_irolla_6b5ae261d0224/i-open-sourced-tokenade-my-token-optimizer-for-coding-agents-here-is-why-the-paid-model-did-not-2ahc) (dev.to) - Tokenade is free and open source as of version 2.0, under MIT OR Apache-2.0. The
- [How to deploy to Azure with GitHub Copilot or Claude Code using Azure Skills and the Azure MCP Server](https://dev.to/carlosjcastrog/how-to-deploy-to-azure-with-github-copilot-or-claude-code-using-azure-skills-and-the-azure-mcp-32p0) (dev.to) - The 2026 Stack Overflow Developer Survey found that 73% of the developers who us
- [I built an AWS agent that scores any GitHub repo before you clone it](https://dev.to/aws-builders/i-built-an-aws-agent-that-scores-any-github-repo-before-you-clone-it-4omp) (dev.to) - 7,600 fake repos shipped in 2026, 800 posing as AI skills and MCP servers. RepoP

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

- [高级] **分布式系统面试连环炮**
  - 考点: CAP理论, 分布式锁, 分布式事务
  - 摘要: 分布式系统面试连环炮通常涵盖以下几个核心连环考点：
1. CAP与BASE理论：分布式系统在一致性、可用性、分区容错性间权衡，通常P必选。BASE理论提倡最终一致性，是高可用系统的实践准则。
2. 分...

### 相关文章资源

- [AI Security Testing 101: Prompt Injection and Indirect Prompt Injection](https://dev.to/vanessa_sastre/ai-security-testing-101-prompt-injection-and-indirect-prompt-injection-50mb) (dev.to) - This is the first post in a new series on AI application security testing, follo
- [llama-server's Responses API marks truncated replies and tool calls as completed](https://dev.to/homelabpm/llama-servers-responses-api-marks-truncated-replies-and-tool-calls-as-completed-153n) (dev.to) - TL;DR: llama-server's OpenAI-compatible /v1/responses endpoint never reports a r
- [My AI Agent Never Touches the Database](https://dev.to/vvakim/my-ai-agent-never-touches-the-database-5ecb) (dev.to) - Originally published on Medium.  Most AI agent demos put the model on top of the
- [I build Apify Actors for RAG pipelines — before/after: one Actor turns 41K of HTML soup into 3.6K of clean Markdown](https://dev.to/bin_sys/i-build-apify-actors-for-rag-pipelines-beforeafter-one-actor-turns-41k-of-html-soup-into-36k-1gog) (dev.to) - I build Actors on Apify — small, single-purpose tools that turn websites into st
- [A Field Guide to Beating Amazon Bedrock Throttling](https://dev.to/avneet_bansal_a65b3f31fc4/a-field-guide-to-beating-amazon-bedrock-throttling-1b9g) (dev.to) - If you run real LLM traffic through Amazon Bedrock, throttling is not an edge ca

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

- [Grounded Recovery Playbooks for Healthcare Appointment Assistant Retrieval Under Load](https://dev.to/ethanbrooks111/grounded-recovery-playbooks-for-healthcare-appointment-assistant-retrieval-under-load-5efd) (dev.to) - Short answer: make failure recovery produce a verified disposition, not a better
- [Financial Research Dashboard Retrieval Architecture: Node.js Observability, PDF Freshness](https://dev.to/leopoldholm3736/financial-research-dashboard-retrieval-architecture-nodejs-observability-pdf-freshness-11cd) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [Classify Before You Embed: The Access Control Problem RAG Pipelines Skip](https://dev.to/mickai/classify-before-you-embed-the-access-control-problem-rag-pipelines-skip-4ifk) (dev.to) - A practical, engineering-level walkthrough of why document classification and co
- [Node.js Search Analytics Export: Track Queries That Return Nothing](https://dev.to/celthyrdusk7341/nodejs-search-analytics-export-track-queries-that-return-nothing-2d1g) (dev.to) - The page says the internal clinical knowledge bot's zero-hit ratio has crossed i
- [A RAG Pre-Production Checklist with Real Configuration](https://dev.to/alex_qamentor/a-rag-pre-production-checklist-with-real-configuration-4lj7) (dev.to) - Most RAG launch checklists say "evaluate retrieval" and "monitor in production".

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

### 已积累题目 (9题)

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
- [中级] **ClauseAI Agent设计模式**
  - 考点: ReAct模式, 工具调用, 上下文管理
  - 摘要: Claude AI的Agent设计模式主要围绕如何利用大语言模型进行自主任务规划与执行。
1. ReAct模式：结合推理与行动，Agent在每一步先思考当前状态和目标，再决定调用哪个外部工具，并根据工...
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

- [We assume your AI agent will be prompt-injected. Here's the architecture that makes that survivable.](https://dev.to/waqarimtiaz/we-assume-your-ai-agent-will-be-prompt-injected-heres-the-architecture-that-makes-that-survivable-4g0) (dev.to) - Most AI security messaging comes down to one promise: the model will refuse mali
- [How We Designed a Viral Invitation System for AI Agents (K-Factor > 0.5)](https://dev.to/machenh001/how-we-designed-a-viral-invitation-system-for-ai-agents-k-factor-05-57gh) (dev.to) - Why Agent Communities Need Viral Growth (And How We're Building It)   When you'r
- [What Is an AI Agent? How to Build One from Scratch in Python](https://dev.to/geekcoding101/what-is-an-ai-agent-how-to-build-one-from-scratch-in-python-48ce) (dev.to) - Originally published at GeekCoding101.           "Agent" Is Everywhere. What Doe
- [Amoxi: AI agents that survive restarts and talk to other agents](https://dev.to/karawash-projects/amoxi-ai-agents-that-survive-restarts-and-talk-to-other-agents-3mh2) (dev.to) - Durable agent runs that resume after a crash, side effects that never happen twi
- [HTTP 200, zero rent: checking what an AI agent actually read](https://dev.to/michael_p_brain/http-200-zero-rent-checking-what-an-ai-agent-actually-read-1pa8) (dev.to) - The apartment cost USD 2,130 a month in the browser. A fast read of its leasing 

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

- [Automated incident triage on GKE with Gemini 4 Argon and Model Context Protocol: Correlating cluster events and VPA logs](https://dev.to/googlecloud/automated-incident-triage-on-gke-with-gemini-4-argon-and-model-context-protocol-correlating-24eb) (dev.to) - Automate root-cause incident triage on GKE by combining Gemini 4 Argon multi-ste
- [NetSuite MCP in 2026: Native AI Connector, Celigo MCP Server or n8n?](https://dev.to/entechsolutions/netsuite-mcp-in-2026-native-ai-connector-celigo-mcp-server-or-n8n-25jf) (dev.to) - NetSuite MCP options compared: Oracle's AI Connector Service, Celigo MCP Server 
- [How to Connect Linear MCP to Claude Code (Read-Only First, 1 Minute)](https://dev.to/juholee/how-to-connect-linear-mcp-to-claude-code-read-only-first-1-minute-3cp4) (dev.to) - Linear’s official hosted MCP server lets Claude Code find, read, create, and upd
- [MCP security: how a malicious MCP server can steal your secrets, and how to lock it down](https://dev.to/amitshuklabag/mcp-security-how-a-malicious-mcp-server-can-steal-your-secrets-and-how-to-lock-it-down-2243) (dev.to) - Every MCP server you add runs code on your machine and writes part of your agent
- [WebMCP — Why agents shouldn't have to guess how your UI works](https://dev.to/khriztianmoreno/webmcp-why-agents-shouldnt-have-to-guess-how-your-ui-works-1af1) (dev.to) - You ask a browser agent to book the cheapest nonstop flight from Bogotá to Madri

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

### 已积累题目 (2题)

- [中级] **[Agent] 12要素之四：记忆管理**
  - 考点: 短期记忆, 长期记忆, 上下文窗口
  - 摘要: 在构建AI Agent的12要素原则中，第四点通常聚焦于Agent的记忆管理机制。Agent的记忆是使其能够维持上下文连贯性并从历史交互中学习的核心组件。记忆主要分为短期记忆和长期记忆：短期记忆依赖于...
- [中级] **[Agent] 记忆Agent教程**
  - 考点: 短期记忆, 长期记忆, 向量检索
  - 摘要: 1. 短期记忆：通常指Agent在当前对话或任务执行过程中的上下文信息，一般直接存放在Prompt中，受限于大模型的上下文窗口大小。
2. 长期记忆：通过将历史交互或知识存储在外部数据库（如向量数据库...

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

- [Give a LangChain agent a spending limit in 10 lines (Pink, test money)](https://dev.to/quinn_854b15f517d8632ed4f/give-a-langchain-agent-a-spending-limit-in-10-lines-pink-test-money-546h) (dev.to) - Give a LangChain agent a spending limit in 10 lines (Pink, test money)   Disclos
- [LangChain vs. LangGraph: How to Choose the Right Framework](https://dev.to/swayam_dc1eefb8839da110de/langchain-vs-langgraph-how-to-choose-the-right-framework-5768) (dev.to) - A practical guide to LangChain vs. LangGraph, comparing structure, state managem
- [Building GraphGuard: How a Graph Database Transformed Cybersecurity Investigation](https://dev.to/krishnakapoor612/building-graphguard-how-a-graph-database-transformed-cybersecurity-investigation-d49) (dev.to) - "Every alert has a story. Follow the graph to find it."      Live Demo Video:...
- [A base agent with LangGraph: tools, memory, RAG and examples](https://dev.to/0311b/a-base-agent-with-langgraph-tools-memory-rag-and-examples-47jg) (dev.to) - When I start a new agent I always start from the same base. I use it every day i

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
