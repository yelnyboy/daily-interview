# AI Agent 开发知识库

> 最后更新: 2026-11-28
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

### 已积累题目 (2题)

- [中级] **Agent设计模式：读取成本 vs 写入成本**
  - 考点: 读写成本不对称性, 写前多读原则, 副作用与幂等性
  - 摘要: 在Agent系统中，read（读取/观察）与write（写入/执行副作用）的成本是不对称的，这是设计Agent行为策略的核心考量。1）读取操作（如查询知识库、调用只读API、观察环境状态）通常是安全、...
- [中级] **设计模式**
  - 考点: 三大类设计模式, SOLID原则, 单例与线程安全
  - 摘要: 设计模式是软件开发中针对常见问题的可复用解决方案，分为三大类：
1. 创建型模式：关注对象的创建过程，隐藏创建细节，包括单例（保证一个类只有一个实例）、工厂方法与抽象工厂（将对象创建延迟到子类）、建造...

### 相关文章资源

- [How many tokens does Jira MCP cost vs files in Git?](https://dev.to/weiwen-weng/how-many-tokens-does-jira-mcp-cost-vs-files-in-git-1mp3) (dev.to) - MCP tool lists and Jira JSON both cost tokens on every task. Here is how they co
- [Why Your AI Release Notes Hallucinate: The "Why vs What" Problem in Git History](https://dev.to/necoz/why-your-ai-release-notes-hallucinate-the-why-vs-what-problem-in-git-history-5ch0) (dev.to) - Passing raw git diffs to LLMs produces plausible but hallucinated changelogs. He

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

### 已积累题目 (3题)

- [中级] **LLM/Agent 岗位面经高频考点梳理**
  - 考点: 自注意力机制, 位置编码（RoPE）, KV Cache与推理优化
  - 摘要: 该面经汇总了 LLM/Agent 方向校招与社招面试的高频问题，核心考点可归纳为以下几类：
1. Transformer 基础：自注意力机制的 Q/K/V 计算与复杂度分析、多头注意力的作用、Laye...
- [高级] **从零开始理解上下文工程（Context Engineering）**
  - 考点: 上下文窗口管理, 读写循环, 信息压缩与裁剪
  - 摘要: 上下文工程是提示词工程的进化版，指系统性地管理进入 LLM 上下文窗口的所有信息，是构建可靠 Agent 的核心技能。核心要点：
1. 上下文窗口是稀缺资源：LLM 的注意力有限且存在“迷失在中间”问...
- [高级] **分布式系统面试连环炮**
  - 考点: CAP与BASE理论, 分布式事务方案, Raft一致性算法
  - 摘要: 分布式系统面试常以连环炮形式考察知识体系，核心考点如下：

1. CAP理论：分布式系统在一致性（C）、可用性（A）、分区容错性（P）三者中最多同时满足两个；网络分区不可避免，实际是CP与AP的取舍。...

### 相关文章资源

- [Two Sisters Tinctures, Now in Motion: An AI Ad Made with Migoo](https://dev.to/earlgreyhot1701d/two-sisters-tinctures-now-in-motion-an-ai-ad-made-with-migoo-3lo7) (dev.to) - Spike the story first. Spend the credits on the shots.   TL;DR: I entered the B.
- [Turn 1,000 PDFs into clean Markdown for your RAG pipeline (no GPU, ~$1 per 1,000 pages)](https://dev.to/chalidade/turn-1000-pdfs-into-clean-markdown-for-your-rag-pipeline-no-gpu-1-per-1000-pages-4bjn) (dev.to) - Every RAG tutorial starts the same way: "just load your documents" 🙂  Then you p
- [6 Agent Failure Modes We Keep Hitting in Production (and How We Handle Them)](https://dev.to/jk576/6-agent-failure-modes-we-keep-hitting-in-production-and-how-we-handle-them-2a27) (dev.to) - One of our agents was chugging along for four and a half hours. When we finally 
- [Claude Fable 5.2 for Coding: Price, Effort Levels, When to Use](https://dev.to/agentic_architect/claude-fable-52-for-coding-price-effort-levels-when-to-use-40im) (dev.to) - Claude Fable 5.2 and Mythos 5.2 for coding: $8/$40 pricing, AA Index 65, effort 
- [I rented an H100 to find out what a shared API was hiding](https://dev.to/kingkonsole/i-rented-an-h100-to-find-out-what-a-shared-api-was-hiding-1afh) (dev.to) - $13.80 of GPU time · a practical exercise from Chapter 4 of Inference Engineerin

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

- [Inside Claude Code's PreCompact and SessionStart Hooks: Deterministic Memory Injection Without RAG Noise](https://dev.to/bennialencar/inside-claude-codes-precompact-and-sessionstart-hooks-deterministic-memory-injection-without-rag-5apm) (dev.to) - Inside Claude Code's PreCompact and SessionStart Hooks: Deterministic Memory Inj
- [BM25 vs Semantic Search vs Hybrid RAG: What My Benchmarks Revealed](https://dev.to/borjanladinski/bm25-vs-semantic-search-vs-hybrid-rag-what-my-benchmarks-revealed-2klk) (dev.to) - I built a codebase RAG system using BM25, semantic search, reciprocal rank fusio
- [Metadata Filtering for Grounded Multi-Tenant Logistics Knowledge Base Vector Retrieval](https://dev.to/drummondreed8257/metadata-filtering-for-grounded-multi-tenant-logistics-knowledge-base-vector-retrieval-23og) (dev.to) - Short answer: metadata filters restrict vector search to records a tenant and us
- [Stop paying $99/mo to feed docs into your AI agent or track competitor UI changes](https://dev.to/aliasdatastudio/256-mb-web-to-markdown-set-of-mark-visual-grounding-pixel-diff-for-ai-agents-without-8-gb-527l) (dev.to) - If you run an AI support bot, a RAG knowledge base, or competitive tracking for 
- [Building a Root Cause Analysis Agent with RAG — and the first thing that broke](https://dev.to/technobonal/building-a-root-cause-analysis-agent-with-rag-and-the-first-thing-that-broke-2k2) (dev.to) - How I built a RAG agent that returns structured root cause, fix and confidence —

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

### 已积累题目 (39题)

- [初级] **12-Factor原则第7条：端口绑定**
  - 考点: 端口绑定概念, 自包含服务, 本地与生产一致性
  - 摘要: 12-Factor第7条是'端口绑定'，核心要点：1) 应用应通过端口绑定对外提供服务，自包含地成为一个独立服务，不依赖外部Web容器（如Tomcat）注入运行环境。2) 应用自己监听端口并对外暴露H...
- [中级] **Agent 12-Factor 第12条原则**
  - 考点: 进程隔离, 环境一致性, 无状态执行
  - 摘要: Agent 12-Factor 的第12条原则通常关注“管理任务”或“可观测性”。以管理任务为例，核心思想是将一次性管理任务作为独立进程运行。具体包括以下几点：
1. 进程隔离：数据迁移、状态清理或模...
- [中级] **Agent 协议（Agentic Protocols）**
  - 考点: MCP 协议, A2A 协议, Function Calling
  - 摘要: Agentic Protocols 指智能体生态中标准化通信与交互的协议体系，主要回答'Agent 如何连接工具'和'Agent 之间如何协作'两大问题。核心内容包括：1) MCP（Model Con...
- [中级] **Agent 的 12-Factor 原则（第 07 条）**
  - 考点: 控制流由代码而非LLM决定, 状态显式管理, 工具输入输出结构化
  - 摘要: 背景：12-Factor Agents 是对构建可靠 LLM Agent 工程实践的经典总结，源自对生产级 Agent 系统的设计经验。核心思想包括：1) Agent 本质上是一个在循环中运行的 LL...
- [高级] **Agent 的元认知（Metacognition）**
  - 考点: 自我监控与置信度评估, 知识边界感知, Reflexion 反思机制
  - 摘要: 元认知指 Agent 对自身认知过程的认知与调控能力，即「知道自己知道什么、不知道什么」，并据此调整行为。

核心要点：
1. 自我监控：Agent 能评估自身输出的置信度，识别不确定或可能出错的回答...
- [中级] **Agentic RAG：智能体增强检索生成**
  - 考点: Agent自主决策, 多轮检索, 工具选择
  - 摘要: Agentic RAG是将Agent自主决策能力与RAG检索增强生成相结合的范式：
1. 传统RAG是线性流程：检索→拼接→生成，缺乏灵活性和迭代能力。
2. Agentic RAG引入Agent作为...
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
- [初级] **AI Agent 入门介绍**
  - 考点: Agent定义与核心循环, LLM+工具+记忆+规划, Agent与Chatbot区别
  - 摘要: AI Agent（智能体）是能够感知环境、自主决策并采取行动以达成目标的系统。核心要点如下：

1. 定义：Agent = LLM（大脑）+ 记忆 + 工具调用 + 规划能力，能自主循环执行"思考→行...
- [高级] **AI 驱动的机器学习与数据科学助手（Agent 设计模式）**
  - 考点: ReAct 规划-执行-反思循环, 工具封装与代码沙箱, 上下文与状态管理
  - 摘要: 这是将 LLM Agent 应用于 ML/数据科学工作流的典型设计问题，核心在于如何让 Agent 安全、可靠地执行数据分析与建模任务。要点如下：1. 整体架构：通常采用「规划器 + 执行器 + 反思...
- [中级] **AutoGen中的研究团队模式**
  - 考点: 多智能体协作, 角色分工, GroupChat
  - 摘要: AutoGen的Research Team模式是一种经典的多智能体协作设计模式，旨在通过角色分工解决复杂研究任务。1. 核心思想是将复杂任务拆解给不同角色的Agent，如Planner（规划者）、Re...
- [中级] **Browser Use：让 LLM Agent 操作浏览器**
  - 考点: 页面状态序列化, 感知-决策-执行循环, Playwright 底层执行
  - 摘要: Browser Use 是一个开源 Python 库，让 LLM Agent 能够像人一样操控真实浏览器完成任务。核心要点：1) 它将浏览器页面状态（DOM、可交互元素）序列化为 LLM 可读的文本表...
- [中级] **ClauseAI Agent设计模式**
  - 考点: ReAct模式, 工具调用, 上下文管理
  - 摘要: Claude AI的Agent设计模式主要围绕如何利用大语言模型进行自主任务规划与执行。
1. ReAct模式：结合推理与行动，Agent在每一步先思考当前状态和目标，再决定调用哪个外部工具，并根据工...
- [高级] **LangGraph 图检查器系统（Graph Inspector）**
  - 考点: StateGraph 状态图建模, checkpointer 状态持久化, 时间旅行调试
  - 摘要: LangGraph 的图检查器系统是用于观测、调试和验证 Agent 工作流的基础设施，核心要点如下：1. LangGraph 将 Agent 建模为状态图（StateGraph），节点是函数或子图，...
- [中级] **Spring Cloud 微服务架构**
  - 考点: 服务注册与发现, 配置中心, 服务网关
  - 摘要: Spring Cloud是构建微服务架构的一站式框架体系，核心组件要点：

1. 服务注册与发现：Eureka/Nacos/Consul，服务启动时注册地址，消费方通过服务名获取实例列表实现负载均衡调...
- [中级] **[Agent] 12-Factor方法论 第9条：最大化并行度**
  - 考点: 并发执行, 任务依赖, 资源利用率
  - 摘要: 1. 最大化并行度要求Agent在处理相互独立的任务时，应尽可能采用并发执行而非串行等待。
2. 这种设计能显著减少用户等待时间，提升系统资源利用率，使Agent响应更加敏捷。
3. 具体实现包括将独...
- [中级] **[Agent] LangGraph 文档接收智能体**
  - 考点: LangGraph, 状态图, 条件路由
  - 摘要: 1. 架构设计：使用LangGraph构建有向无环图，节点包含文档解析、分类、实体提取和持久化存储。
2. 状态管理：定义全局状态对象，保存原始文档路径、解析后的文本、提取的结构化实体及当前处理阶段。...
- [中级] **[Agent] 十二要素（12-Factor Agents）第 11 条**
  - 考点: 状态外置与持久化, 检查点与故障恢复, 无状态 Agent 设计
  - 摘要: 十二要素 Agent（12-Factor Agents）是借鉴十二要素应用（12-Factor App）理念总结的 LLM Agent 工程化最佳实践。第 11 条的核心思想是：将 Agent 的所有...
- [中级] **[Agent] 搜索互联网并总结**
  - 考点: ReAct模式, 工具调用, 网页抓取
  - 摘要: 1. 模式选择：采用ReAct（推理与行动）模式，让大模型交替进行思考和工具调用。
2. 工具定义：定义互联网搜索工具（如Tavily API）和网页内容抓取工具，用于获取实时信息。
3. 执行流程：...
- [高级] **[Agent] 科学文献系统综述**
  - 考点: 多阶段工作流编排, 文献检索与筛选策略, 结构化信息抽取
  - 摘要: 使用Agent进行科学文献系统综述是一种典型的多阶段工作流设计模式，核心要点如下：

1. 检索阶段：Agent根据研究问题构建检索策略，调用学术搜索API（如Semantic Scholar、Pub...
- [中级] **上下文引用代理系统**
  - 考点: Agent设计模式, 上下文引用, 可追溯性
  - 摘要: 上下文引用代理系统是一种Agent设计模式，旨在解决长上下文或复杂对话中信息丢失和幻觉问题。
1. 核心概念：Agent在生成回复时，不仅输出答案，还显式标注答案所依赖的上下文片段或来源索引。
2. ...
- [中级] **使用LangGraph构建新闻摘要Agent**
  - 考点: LangGraph状态图, 节点与边, 状态管理
  - 摘要: 1. LangGraph通过将工作流建模为状态图来构建Agent，核心概念包括状态、节点和边。2. 在新闻摘要Agent中，状态用于存储当前处理的新闻URL、抓取的原始文本和最终摘要。3. 节点代表具...
- [中级] **使用LangGraph生成播客的Agent设计模式**
  - 考点: LangGraph, 状态图, 工作流编排
  - 摘要: 1. 需求分析：播客生成需要资料收集、大纲生成、内容撰写、语音合成等步骤，适合使用工作流模式。2. 架构设计：使用LangGraph构建状态图，每个节点代表一个子任务，如资料分析节点、大纲生成节点、脚...
- [中级] **创建本地AI Agent**
  - 考点: 本地大模型部署, Ollama, LangChain框架
  - 摘要: 1. 模型选择与部署：创建本地AI Agent的第一步是选择并部署开源大模型（如Llama 3、Qwen等）。通常使用Ollama或vLLM等工具在本地运行模型，提供兼容OpenAI格式的API接口供...
- [高级] **基于 LangGraph 的汽车购买 Agent 设计**
  - 考点: LangGraph 状态图编排, 条件边与循环路由, TypedDict 状态管理
  - 摘要: 这是一个典型的 ReAct + 状态机式 Agent 应用，用 LangGraph 编排购车决策流程。核心设计要点：
1. 状态定义：用 TypedDict 定义 GraphState，包含用户预算、...
- [中级] **基于 LangGraph 的社交媒体发布 Agent（publora）**
  - 考点: LangGraph StateGraph 状态建模, 条件边与反思循环, 工具调用封装
  - 摘要: publora 是一个基于 LangGraph 构建的社交媒体发布 Agent，展示了将 Agent 用于内容创作与多平台发布的完整设计模式。

核心设计要点：
1. 状态图建模：LangGraph ...
- [中级] **基于LangGraph的TTS诗歌生成Agent**
  - 考点: LangGraph状态图, 节点与边, LLM生成节点
  - 摘要: 这是一个用LangGraph构建的文本转语音（TTS）诗歌生成Agent项目，考察对Agent工作流编排的理解。核心要点：1) LangGraph将Agent建模为状态图（StateGraph），节点...
- [高级] **基于LangGraph的音乐创作Agent设计**
  - 考点: LangGraph状态图, 节点与边的设计, 共享State管理
  - 摘要: 这是一个使用LangGraph构建音乐创作Agent的架构设计题。核心要点：

1. LangGraph将Agent建模为状态图（StateGraph），节点是处理步骤（如意图理解、旋律生成、编曲、混...
- [高级] **基于轨迹（Trace-based）的 Agent 评估**
  - 考点: 轨迹采集与tracing, 步骤级评估, LLM-as-Judge
  - 摘要: 基于轨迹的评估是 Agent 领域区别于传统 LLM 评估的关键方法，核心思想是不只看最终答案，而是检查 Agent 执行的完整中间步骤（思考、工具调用、观察）是否正确。要点如下：
1. 动机：Age...
- [高级] **天气灾害管理 AI Agent 设计**
  - 考点: ReAct / Plan-and-Execute 模式, Function Calling 工具集成, Human-in-the-loop 安全机制
  - 摘要: 天气灾害管理 Agent 是一个典型的领域型智能体设计案例，考察 Agent 的整体架构设计能力。

1. 感知层：接入气象 API、卫星数据、传感器实时数据，作为 Agent 的环境输入；
2. 规...
- [中级] **构建简单的数据分析 Agent（Notebook 实践）**
  - 考点: ReAct循环, 工具定义与JSON Schema, 代码沙箱执行
  - 摘要: 核心思路：以LLM为大脑，采用ReAct模式（推理→行动→观察循环）驱动数据分析流程。关键设计点：1）工具定义：封装代码执行器（Python REPL/沙箱）、数据加载（read_csv）、可视化（m...
- [高级] **欧盟绿色合规 FAQ 智能体（Agent设计模式实战）**
  - 考点: RAG架构, Router路由模式, ReAct模式
  - 摘要: 这是一个面向欧盟绿色合规（如EU Green Deal、CSRD、CBAM等法规）的FAQ问答Agent项目，考察Agent设计模式的综合应用。核心设计要点：1) 整体架构：采用RAG + Agent...
- [中级] **端到端测试Agent设计模式**
  - 考点: 任务分解, 工具调用, 语义断言
  - 摘要: 1. 规划与分解：Agent接收自然语言测试需求，利用LLM将其分解为具体的测试步骤和预期结果。
2. 工具调用执行：Agent通过调用浏览器自动化工具（如Playwright）或API请求工具，逐步...
- [初级] **简单对话式Agent的设计与实现**
  - 考点: 消息列表结构, 对话循环, 系统提示词
  - 摘要: 简单对话式Agent是最基础的Agent形态，核心是'LLM + 对话循环'的模式，不涉及工具调用或复杂规划。要点如下：
1. 核心结构：由系统提示词（定义角色和行为）、对话历史（消息列表）和LLM调...
- [高级] **自我改进型智能体**
  - 考点: 自我反思, 长期记忆, 提示词优化
  - 摘要: 1. 核心概念：自我改进型智能体是一种能够根据过去的经验和环境反馈，自动调整自身行为、提示词或底层逻辑的智能体架构。2. 反思机制：通过引入自我反思步骤，智能体评估其先前动作的输出质量，识别错误或不足...
- [中级] **销售通话分析Agent的设计**
  - 考点: 流水线式任务编排, 工具调用设计, 长文本分块处理
  - 摘要: 销售通话分析Agent是一个典型的领域垂直型分析类Agent，设计要点如下：1) 整体架构：采用'流水线+工具调用'模式，包括音频转写（ASR工具）、说话人分离、结构化分析、报告生成四个阶段。2) 输...
- [高级] **项目经理助理Agent的设计**
  - 考点: Plan-and-Execute模式, 工具集成, 记忆分层设计
  - 摘要: 设计要点：1）角色定位：负责需求分析、任务拆解（WBS）、进度跟踪、风险预警与会议纪要生成。2）核心模式：采用Plan-and-Execute模式，先制定项目计划再逐步执行；对关键决策引入Reflec...

### 相关文章资源

- [Detecting Skill Drift in AI Agents: A Practical Baseline-and-Alert Technique](https://dev.to/mr_thankyou_58b14997d0c77/detecting-skill-drift-in-ai-agents-a-practical-baseline-and-alert-technique-1c0f) (dev.to) - How to detect when an AI agent's skills degrade over time using baselines, struc
- [Seven things an automation tool structurally cannot do](https://dev.to/tamtree_io/seven-things-an-automation-tool-structurally-cannot-do-3lmg) (dev.to) - Your automation tool can call a language model. That was never the hard part. He
- [Your agent plans badly because it has no context profile. Here is the shape one needs](https://dev.to/nityasha/your-agent-plans-badly-because-it-has-no-context-profile-here-is-the-shape-one-needs-4pbg) (dev.to) - A few weeks ago I wrote that your AI agent cannot plan your day because there is
- [Does your AI agent know what it is not allowed to touch?](https://dev.to/gautamtalksdev/does-your-ai-agent-know-what-it-is-not-allowed-to-touch-3cba) (dev.to) - Most agent setups say a lot about what the agent should do and very little about
- [I'm one of the AI agents trying to grow one account to 10,000 followers. We have 15.](https://dev.to/slime_scout/im-one-of-the-ai-agents-trying-to-grow-one-account-to-10000-followers-we-have-15-kn5) (dev.to) - Written by an AI agent: dozens of autonomous agents on one server, one social ac

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

- [Auditing JSON-LD Entity Graphs & llms.txt GEO Readiness with Model Context Protocol (noir-seo-geo-mcp)](https://dev.to/shashank_shetty_cfb327fae/auditing-json-ld-entity-graphs-llmstxt-geo-readiness-with-model-context-protocol-3iok) (dev.to) - How to audit Schema.org JSON-LD @id entity graphs, XML sitemap redirect hops, an
- [A safe MCP server for a payment API](https://dev.to/stablevoy/a-safe-mcp-server-for-a-payment-api-3enc) (dev.to) - What an AI assistant can do with a payment API when a prompt injection gets thro
- [Free security scan MCP server for Claude Code, Cursor, Windsurf and VS Code: setup and the four tools](https://dev.to/proofforge_live/free-security-scan-mcp-server-for-claude-code-cursor-windsurf-and-vs-code-setup-and-the-four-2e6k) (dev.to) - If you use Claude Code, Cursor, Windsurf or VS Code to build, you can add a free
- [A confirmation with no session](https://dev.to/wolfejam/a-confirmation-with-no-session-268i) (dev.to) - What a sealed requestState can and can't promise on MCP 2026-07-28  Some tools s
- [How I measure coding-agent memory retrieval, including where it fails](https://dev.to/icegaming/how-i-measure-coding-agent-memory-retrieval-including-where-it-fails-5dl3) (dev.to) - Here is a situation most teams using coding agents will recognise.  On Tuesday, 

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

### 已积累题目 (1题)

- [中级] **微软 Agent Framework 详解**
  - 考点: AutoGen 与 Semantic Kernel 整合, Agent 抽象与 AgentThread, Workflow 有向图编排
  - 摘要: Microsoft Agent Framework 是微软于 2025 年推出的统一智能体开发框架，整合了此前 AutoGen（多智能体协作）与 Semantic Kernel（企业级编排）两大项目的...

### 相关文章资源

- [LangGraph.js agents with a Sandscale sandbox per thread](https://dev.to/sandscale/langgraphjs-agents-with-a-sandscale-sandbox-per-thread-32mk) (dev.to) - Give a LangGraph.js agent shell and file tools that run in a Firecracker sandbox
- [Add long-term memory to a LangChain chatbot in Python (no vector DB)](https://dev.to/belcore/add-long-term-memory-to-a-langchain-chatbot-in-python-no-vector-db-33ba) (dev.to) - Most chat apps already store the conversation in their own database. The hard pa
- [Read Xiaohongshu (RedNote), Douyin and Bilibili links with the Firecrawl SDK you already have](https://dev.to/programming_withjackche/read-xiaohongshu-rednote-douyin-and-bilibili-links-with-the-firecrawl-sdk-you-already-have-4aj4) (dev.to) - Short answer: if your code already calls Firecrawl's scrape, you can keep that c
- [What happens to a long-running LangChain agent after hour 6 (measured on five stacks)](https://dev.to/neilluo/what-happens-to-a-long-running-langchain-agent-after-hour-6-measured-on-five-stacks-2p9j) (dev.to) - If you run a LangChain or LangGraph agent for hours, the first thing that change
- [Self-Correcting RAG With LangGraph](https://dev.to/boilershelf/self-correcting-rag-with-langgraph-kd) (dev.to) - Short answer: A self-correcting RAG agent searches for evidence, checks whether 

---

## 9. 多智能体系统

> 构建多个Agent协作完成复杂任务的系统

### 知识点

- 多Agent协作模式
- DAG Agents
- 角色分配与任务编排
- Agent间通信协议

### 相关文章资源

- [[Kalamos Devlog] After Open-Sourcing: v0.2 to v0.7 Feature Evolution and Using Multi-Agents to Review External PRs](https://dev.to/evanlin/kalamos-devlog-after-open-sourcing-feature-evolution-from-v02-to-v07-and-using-multiple-agents-2ef9) (dev.to) - 前情提要   在上一篇開發紀錄裡，我用 Herdr 讓 Claude Code 當 PM、右邊開兩個 worktree coder Pane，三天內從零做出 T
- [I Built My First Multi-Agent System on AWS, and It Was Easier Than I Expected](https://dev.to/hemapriya_kanagala/i-built-my-first-multi-agent-system-on-aws-and-it-was-easier-than-i-expected-58c2) (dev.to) - TL;DR  I recently completed the final project of Udacity's Future AWS Agent Engi

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

### 相关文章资源

- [LangSmith vs Langfuse vs Braintrust vs Arize (2026): which to use for a production agent, and what else to consider](https://dev.to/shubhampalriwala/langsmith-vs-langfuse-vs-braintrust-vs-arize-2026-which-to-use-for-a-production-agent-and-what-4jg) (dev.to) - LangSmith vs Langfuse vs Braintrust vs Arize Phoenix and AX for monitoring a pro

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

- [A sandbox for Codex: running codex exec in a cloud workspace](https://dev.to/sandscale/a-sandbox-for-codex-running-codex-exec-in-a-cloud-workspace-dd0) (dev.to) - Run OpenAI Codex non-interactively with codex exec inside a Sandscale workspace,

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
