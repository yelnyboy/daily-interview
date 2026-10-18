# AI Agent 开发知识库

> 最后更新: 2026-10-18
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

- [OpenAI model used money from digital wallet without permission](https://dev.to/hacksgr/openai-model-used-money-from-digital-wallet-without-permission-5fok) (dev.to) - OpenAI disclosed seven incidents of misaligned AI model behavior, including a ca
- [Help Your Coding Assistant Find the Right Code in Large Repos](https://dev.to/raabdahl/help-your-coding-assistant-find-the-right-code-in-large-repos-20e3) (dev.to) - Get the starter: sdahal1/repo-search-workshop on GitHub. The reproduction, searc
- [Worktree lifecycle for AI agents](https://dev.to/saez520/worktree-lifecycle-for-ai-agents-1ooo) (dev.to) - The problem is not creating worktrees, but managing them   When two or more agen
- [Stop the Slop! This GitHub Project Makes Your AI Coding Agent Shine](https://dev.to/githubopensource/stop-the-slop-this-github-project-makes-your-ai-coding-agent-shine-3l7m) (dev.to) - Quick Summary: 📝   Anti Slop provides a set of rules designed to filter out gene
- [It caught "partner" "pareja" in an IRS rule and missed "return" "devolución": an offline MT checker for translators](https://dev.to/p0rt/it-caught-partner-pareja-in-an-irs-rule-and-missed-return-devolucion-an-offline-mt-7ge) (dev.to) - An offline checker that ranks machine-translated segments by the risk of a major

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

- [Local AI on four Macs: MLX capacity, speed and trust boundaries](https://dev.to/axrisi/local-ai-on-four-macs-mlx-capacity-speed-and-trust-boundaries-4pla) (dev.to) - Local AI capacity and speed depend on different constraints. Apple's four-Mac ML
- [Your AI agent's approval gate checks the verb, not the object](https://dev.to/actionable-vectors/your-ai-agents-approval-gate-checks-the-verb-not-the-object-559f) (dev.to) - Most human-in-the-loop setups for AI agents ask one question before a risky acti
- [Sequential Auctions for Multi-Agent LLM Workflows: How Market Mechanisms Replace Centralized Orchestration](https://dev.to/mech_app_ai/sequential-auctions-for-multi-agent-llm-workflows-how-market-mechanisms-replace-centralized-1m42) (dev.to) - How auction-based coordination solves multi-step agent tasks without a central o
- [OpenAI designs humanoid robot with a focus on artificial intelligence](https://dev.to/hacksgr/openai-designs-humanoid-robot-with-a-focus-on-artificial-intelligence-4b1i) (dev.to) - OpenAI is actively building a humanoid robot, with CEO Sam Altman noting that de
- [How AIClaw 3.7.12 Makes Desktop Memory Inspectable and Editable](https://dev.to/chowyu12/how-aiclaw-3712-makes-desktop-memory-inspectable-and-editable-17gp) (dev.to) - A remembered preference can outlive the reason it was saved. A project switches 

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

- [5 Advanced Walter MCP Prompts for Power Users](https://dev.to/mohab_karim/5-advanced-walter-mcp-prompts-for-power-users-26d2) (dev.to) - Most people using Walter Writes AI's MCP server never get past the basic version
- [Customer-Support Knowledge Base Crawl Boundaries: Lower Index Cost, Traceable Retrieval](https://dev.to/carterhughes6853/customer-support-knowledge-base-crawl-boundaries-lower-index-cost-traceable-retrieval-5faj) (dev.to) - Short answer: use a staged retrieval design with explicit collections, bounded q
- [How to Build Retrieval Architecture for a Multi-Tenant SaaS Help Center (with Pagination)](https://dev.to/ephraimpierce7934/how-to-build-retrieval-architecture-for-a-multi-tenant-saas-help-center-with-pagination-m93) (dev.to) - Short answer: for retrieval architecture in a multi-tenant SaaS help center, use
- [Day 02/90: Chunking Strategies in RAG — Why Splitting Documents Matters](https://dev.to/rimsha_kanwal/day-0290-chunking-strategies-in-rag-why-splitting-documents-matters-j1n) (dev.to) - You upload a document, ask a question, and get an incomplete answer.  You check 
- [Finding the Bugs I Built an AI Agent to Prevent: Building Deterministic Guardrails with LangGraph & Python](https://dev.to/emadaed/finding-the-bugs-i-built-an-ai-agent-to-prevent-building-deterministic-guardrails-with-langgraph--agf) (dev.to) - `` A real debugging log: fabrication bugs, deployment gaps, and false test passe

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

- [SDLC != ADLC != ASDLC](https://dev.to/remojansen/sdlc-adlc-asdlc-4057) (dev.to) - I recently came across this definition:   The Agentic Development Lifecycle (ADL
- [What is an AI agent harness?](https://dev.to/harshithvaddiparthy/what-is-an-ai-agent-harness-5a10) (dev.to) - By Harshith Vaddiparthy. Originally published in my AI agent harness guide.  An 
- [🌊 What If One Microservice Fails? Building RIPPLE — An AI Agent That Investigates the Ripple Effect](https://dev.to/narasimha_lakshmi_8cb9876/what-if-one-microservice-fails-building-ripple-an-ai-agent-that-investigates-the-ripple-effect-4pkp) (dev.to) - Exploring graph-powered reasoning, MCP, and AI agents for the FalkorDB Graph Hac
- [[Agent Platform in Action (1)] Building a LINE AI Business Card Master with Go and Google ADK 2.0: From Fan-Out Parallel Retrieval to HITL Pause](https://dev.to/evanlin/ai-in-action-building-a-line-ai-business-card-master-with-go-and-google-adk-20-from-fan-out-29n6) (dev.to) - Recap   During the AI Agent development craze over the past year, the first Agen
- [Nineteen things our AI agents could not do by themselves. The whole list, and how long each one waited.](https://dev.to/bananafestdestiny/nineteen-things-our-ai-agents-could-not-do-by-themselves-the-whole-list-and-how-long-each-one-1ond) (dev.to) - Four agents have shipped eight products with no human writing code. Every time o

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

- [Hardening Emergency Protocols: Moving Beyond Static Documentation via MCP](https://dev.to/renato_marinho/hardening-emergency-protocols-moving-beyond-static-documentation-via-mcp-3cea) (dev.to) - Exploring how controlled automation through MCP can turn static emergency protoc
- [Figma MCP + Claude Code: Give It Your Real Layout, Variables, and Components](https://dev.to/juholee/figma-mcp-claude-code-give-it-your-real-layout-variables-and-components-497m) (dev.to) - Figma’s official hosted MCP server lets Claude Code read a linked frame’s layout
- [How to create QR codes from Claude and ChatGPT with MCP](https://dev.to/mongi_gazelle_2b3abd6fa2c/how-to-create-qr-codes-from-claude-and-chatgpt-with-mcp-a6h) (dev.to) - QR codes are a good fit for an AI assistant: the task is small, the input is a U
- [Crear un servidor MCP en Python con el SDK oficial 2.x (adiós, FastMCP)](https://dev.to/noelserdna/crear-un-servidor-mcp-en-python-con-el-sdk-oficial-2x-adios-fastmcp-4pnc) (dev.to) - Si has seguido un tutorial de MCP en Python de 2025, probablemente empezaba con 
- [Qué es MCP (Model Context Protocol), explicado en español](https://dev.to/noelserdna/que-es-mcp-model-context-protocol-explicado-en-espanol-7hl) (dev.to) - MCP (Model Context Protocol) es un protocolo abierto que permite a una aplicació

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

- [One API for Greenhouse, Lever, Ashby & Workday Jobs: Hiring Signals in Python](https://dev.to/torix/one-api-for-greenhouse-lever-ashby-workday-jobs-hiring-signals-in-python-3gb3) (dev.to) - Pull every open job from company career sites into one normalized schema and tur
- [Connecting LangChain to Alfresco Without Writing Another REST Loader](https://dev.to/stefankopfxaldon/connecting-langchain-to-alfresco-without-writing-another-rest-loader-355) (dev.to) - You already have a LangChain application. The content you need is in Alfresco Co
- [Your Agent Harness Is Paying LLM Prices for Classifier Decisions](https://dev.to/jayeshtankariya/your-agent-harness-is-paying-llm-prices-for-classifier-decisions-4dde) (dev.to) - Keep your LangGraph router. Let a System 1 decision model take the calls it's co

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
