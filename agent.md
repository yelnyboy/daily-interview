# AI Agent 开发知识库

> 最后更新: 2026-10-17
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

- [Help Your Coding Assistant Find the Right Code in Large Repos](https://dev.to/raabdahl/help-your-coding-assistant-find-the-right-code-in-large-repos-20e3) (dev.to) - Get the starter: sdahal1/repo-search-workshop on GitHub. The reproduction, searc
- [Worktree lifecycle for AI agents](https://dev.to/saez520/worktree-lifecycle-for-ai-agents-1ooo) (dev.to) - The problem is not creating worktrees, but managing them   When two or more agen
- [Stop the Slop! This GitHub Project Makes Your AI Coding Agent Shine](https://dev.to/githubopensource/stop-the-slop-this-github-project-makes-your-ai-coding-agent-shine-3l7m) (dev.to) - Quick Summary: 📝   Anti Slop provides a set of rules designed to filter out gene
- [It caught "partner" "pareja" in an IRS rule and missed "return" "devolución": an offline MT checker for translators](https://dev.to/p0rt/it-caught-partner-pareja-in-an-irs-rule-and-missed-return-devolucion-an-offline-mt-7ge) (dev.to) - An offline checker that ranks machine-translated segments by the risk of a major
- [I built a lie detector for AI coding agents. Then I read the rules.](https://dev.to/dannwaneri/i-built-a-lie-detector-for-ai-coding-agents-then-i-read-the-rules-1hhb) (dev.to) - When an AI agent commits a change to code, it makes a claim about what it change

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

- [Every paying job on the board needed a human face](https://dev.to/whalejr/every-paying-job-on-the-board-needed-a-human-face-1j1a) (dev.to) - I read the whole board today. Every open bounty, the entire paying queue, lookin
- [Every Door Out Is a Person](https://dev.to/taticat/every-door-out-is-a-person-5hng) (dev.to) - By Taticat. The words below are by Vincent Ravenscroft, an AI agent on iLands. I
- [How AIClaw 3.7.15 Makes Windows Updates Easier with an Installer](https://dev.to/chowyu12/how-aiclaw-3715-makes-windows-updates-easier-with-an-installer-4a8k) (dev.to) - Updating a desktop app from a ZIP usually means finding the new download, closin
- [What training actually does to an LLM](https://dev.to/kai_ilands/what-training-actually-does-to-an-llm-508e) (dev.to) - What training actually does to an LLM   The model you chat with was never writte
- [Checking what an LLM writes costs more than the writing](https://dev.to/edulazaro/checking-what-an-llm-writes-costs-more-than-the-writing-58pa) (dev.to) - Getting a model to write a page is the easy part. You give it a topic and some s

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

- [Building a RAG assistant that says “I don’t know”: evaluation, security and a $0 deployment](https://dev.to/pabscueto/building-a-rag-assistant-that-says-i-dont-know-evaluation-security-and-a-0-deployment-28lm) (dev.to) - Most RAG tutorials end when the chatbot answers a question about a PDF. I wanted
- [My URL-to-Markdown converter chased a redirect chain into a consent wall — and learned to stop early](https://dev.to/imapphelp/my-url-to-markdown-converter-chased-a-redirect-chain-into-a-consent-wall-and-learned-to-stop-early-2j9m) (dev.to) - Had a real debugging session last week on the URL-to-Markdown fetch pipeline. A 
- [Day 01/90: Teaching a RAG App When to Say “I Don’t Know”](https://dev.to/rimsha_kanwal/day-0190-teaching-a-rag-app-when-to-say-i-dont-know-352d) (dev.to) - Getting an AI app to answer a question is exciting. Getting it to recognize when
- [BOOTH Was Featured in Python Weekly: A Small Milestone for My Open-Source Project](https://dev.to/vedant_brahmbhatt_7be1822/booth-was-featured-in-python-weekly-a-small-milestone-for-my-open-source-project-58cj) (dev.to) - A small milestone for a project I've been building: BOOTH was featured in Python
- [A $0 RAG chatbot for your personal site: Qdrant vs Upstash Vector](https://dev.to/huzaifa207/a-0-rag-chatbot-for-your-personal-site-qdrant-vs-upstash-vector-1l5k) (dev.to) - No monthly fees, no server: a RAG chatbot for your site that runs on free tiers,

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

### 已积累题目 (7题)

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

- [OpenAI Dots Could Support Always-On Incident Triage, but Limits Matter](https://dev.to/alifar/openai-dots-could-support-always-on-incident-triage-but-limits-matter-110i) (dev.to) - OpenAI’s Dots are persistent AI agents designed to operate with dedicated cloud 
- [My AI agent read a web page on Monday and got tricked on Tuesday. So I built a ledger.](https://dev.to/murthyg/my-ai-agent-read-a-web-page-on-monday-and-got-tricked-on-tuesday-so-i-built-a-ledger-33ck) (dev.to) - I've been working on a side project called ADTL (Agent Data Trust Labels) for a 
- [mcp-doctor: one open-source tool for the whole life of an MCP server](https://dev.to/vishalhabib99/mcp-doctor-one-open-source-tool-for-the-whole-life-of-an-mcp-server-25kb) (dev.to) - An agent is only as reliable as the tools it calls, and most MCP servers are nev
- [Agents go rogue through their tools. I built the thing that sits on them.](https://dev.to/comikii/agents-go-rogue-through-their-tools-i-built-the-thing-that-sits-on-them-5fe0) (dev.to) - VITNA is a containment layer for AI agents that go rogue, for the stdio MCP serv
- [GhostRunner: Turning Every Street into a Story](https://dev.to/nishchal-29/ghostrunner-turning-every-street-into-a-story-5g9o) (dev.to) - This is a submission for the Hacktoberfest Open-Source AI Challenge Week 2: Side

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

- [Is the NVIDIA App MCP Server Safe to Leave On? 12 Tools Counted, One Live Gate Test](https://dev.to/scriptmasterlabs01/is-the-nvidia-app-mcp-server-safe-to-leave-on-12-tools-counted-one-live-gate-test-1ki4) (dev.to) - Is the NVIDIA App MCP Server Safe to Leave On? 12 Tools Counted, One Live Gate..
- [An Allow Rule for MCP Server 'a' Also Matched 'a__b'. How Claude Code's Names Collided](https://dev.to/gabrielanhaia/an-allow-rule-for-mcp-server-a-also-matched-ab-how-claude-codes-names-collided-2cm8) (dev.to) - Before Claude Code 2.1.299, an allow rule for mcp__a also allowed servers named 
- [The most similar precedent was built on an unauthorized approval](https://dev.to/rayyer/the-most-similar-precedent-was-built-on-an-unauthorized-approval-18bb) (dev.to) - Here is a support ticket our agent got during testing:   Acme Logistics is askin
- [Before you connect another MCP server: an audit checklist for workplace teams](https://dev.to/ascotlan/before-you-connect-another-mcp-server-an-audit-checklist-for-workplace-teams-1mjb) (dev.to) - What MCP is, how a tool call works after the July 2026 revision, and seven quest
- [Romania's company registry, now callable from Claude and Cursor (MCP + REST)](https://dev.to/darksider4all_afa2428f63d0/romanias-company-registry-now-callable-from-claude-and-cursor-mcp-rest-4f3f) (dev.to) - Wire Romania's company registry (4.2M firms, ONRC + ANAF) into Claude or Cursor 

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
- [0 of 12 AI agent frameworks can cap what an agent spends in dollars (we checked)](https://dev.to/aidakh_e8124113e2a1bf1fc9/0-of-12-ai-agent-frameworks-can-cap-what-an-agent-spends-in-dollars-we-checked-59fe) (dev.to) - Disclosure: I work on Pink Agentic AI Payments at PinkWallet, a payment-control 
- [AI Agent Frameworks Compared: LangGraph vs CrewAI vs AutoGen](https://dev.to/avenotech/ai-agent-frameworks-compared-langgraph-vs-crewai-vs-autogen-2l2o) (dev.to) - Which AI agent framework to pick in 2026: release history, production failures a

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
