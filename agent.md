# AI Agent 开发知识库

> 最后更新: 2026-11-04
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

- [Flipper got archived, so I built an Android inspector that needs no SDK](https://dev.to/haul/flipper-got-archived-so-i-built-an-android-inspector-that-needs-no-sdk-11o7) (dev.to) - GitHub: https://github.com/ESeungJun/droidlens  Installers for macOS, Windows an
- [[AI in Action] Rewriting a Daily LINE Bot from Python to Go 1.26 on Cloud Run: 1/4 Resource Usage, Google ADK v1.9.0, and Zero-D](https://dev.to/gde/ai-in-action-rewriting-a-daily-line-bot-from-python-to-go-126-on-cloud-run-14-resource-usage-2o62) (dev.to) - Background   I have a primary LINE Bot that I use heavily every day:...
- [LLM weak random number generator detection test](https://dev.to/sunnychokshi/llm-weak-random-number-generator-detection-test-4mn4) (dev.to) - Originally published at sunny-chokshi.github.io.  I ran an LLM weak random numbe
- [I Built a Search Tool for the EU Digital Services Act, and Tested It First](https://dev.to/malavnaik_0381711024683d4/i-built-a-search-tool-for-the-eu-digital-services-act-and-tested-it-first-3pn6) (dev.to) - How I turned the EU Digital Services Act into a free, in-browser search tool tha
- [How do AI agents authenticate? (The problem nobody has solved yet)](https://dev.to/zachbenson/how-do-ai-agents-authenticate-the-problem-nobody-has-solved-yet-3cbe) (dev.to) - Repo: github.com/arkenforge/arken-core  If you've built an MCP server or an API 

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

- [RoPE in bfloat16: 8,192 Token Positions Collapsed Into 897](https://dev.to/ji_ai/rope-in-bfloat16-8192-token-positions-collapsed-into-897-51pm) (dev.to) - RoPE in bfloat16 rounds token positions past 256. In my NumPy test, 8,192 positi
- [LLM Routing: Stop Paying Premium Prices for Simple Prompts](https://dev.to/nodeneuralai/llm-routing-stop-paying-premium-prices-for-simple-prompts-4oni) (dev.to) - Someone asked: can we end the Globex contract early? Seven words. The question l
- [Lore Books and World Info in AI Character Chat: How Much Context Is Enough](https://dev.to/pogee/lore-books-and-world-info-in-ai-character-chat-how-much-context-is-enough-19el) (dev.to) - Lore is where long-form AI roleplay either becomes a living world or collapses i
- [OpenAI Says ChatGPT’s Search-Like Query Volume Is About One-Fifth of Google’s](https://dev.to/alifar/openai-says-chatgpts-search-like-query-volume-is-about-one-fifth-of-googles-2oa) (dev.to) - OpenAI says ChatGPT’s web-search-like query volume is roughly 20% of Google’s tr
- [I ran the same multi-agent experiment twice. Half the conclusions flipped.](https://dev.to/chai_jingbo_d086c3011d990/i-ran-the-same-multi-agent-experiment-twice-half-the-conclusions-flipped-1o5i) (dev.to) - In August I ran a controlled experiment on my open-source multi-agent pipeline: 

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

- [Fresh Listing Discovery Explained — A Runbook for Incremental Source Convergence](https://dev.to/hadleyfox8439/fresh-listing-discovery-explained-a-runbook-for-incremental-source-convergence-61k) (dev.to) - Short answer: use a staged retrieval architecture for real-estate listing discov
- [Knowledge graphs, explained for AI memory (and how Palace uses one)](https://dev.to/icegaming/knowledge-graphs-explained-for-ai-memory-and-how-palace-uses-one-1g67) (dev.to) - Most AI memory systems today come down to the same recipe. Split text into chunk
- [Prevent Retrieval Dilution in Alfresco RAG with Metadata Filters](https://dev.to/stefankopfxaldon/prevent-retrieval-dilution-in-alfresco-rag-with-metadata-filters-4la4) (dev.to) - A RAG application over a small set of documents often works surprisingly well. T
- [A Changed-Page Export Can Quietly Shrink Your RAG Index](https://dev.to/vexaloom-labs/a-changed-page-export-can-quietly-shrink-your-rag-index-2cki) (dev.to) - Build a Python corpus refresh that merges changed pages, replaces stale chunks, 
- [Can a user retrieve information outside their permissions, including through the lexical search path, caches, or indirect references?](https://dev.to/izgorodin/can-a-user-retrieve-information-outside-their-permissions-including-through-the-lexical-search-115m) (dev.to) - Jeevan Srivastava asked this question word for word in a Medium article of 18 Oc

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

### 已积累题目 (23题)

- [初级] **12-Factor原则第7条：端口绑定**
  - 考点: 端口绑定概念, 自包含服务, 本地与生产一致性
  - 摘要: 12-Factor第7条是'端口绑定'，核心要点：1) 应用应通过端口绑定对外提供服务，自包含地成为一个独立服务，不依赖外部Web容器（如Tomcat）注入运行环境。2) 应用自己监听端口并对外暴露H...
- [中级] **Agent 12-Factor 第12条原则**
  - 考点: 进程隔离, 环境一致性, 无状态执行
  - 摘要: Agent 12-Factor 的第12条原则通常关注“管理任务”或“可观测性”。以管理任务为例，核心思想是将一次性管理任务作为独立进程运行。具体包括以下几点：
1. 进程隔离：数据迁移、状态清理或模...
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
- [中级] **AutoGen中的研究团队模式**
  - 考点: 多智能体协作, 角色分工, GroupChat
  - 摘要: AutoGen的Research Team模式是一种经典的多智能体协作设计模式，旨在通过角色分工解决复杂研究任务。1. 核心思想是将复杂任务拆解给不同角色的Agent，如Planner（规划者）、Re...
- [中级] **ClauseAI Agent设计模式**
  - 考点: ReAct模式, 工具调用, 上下文管理
  - 摘要: Claude AI的Agent设计模式主要围绕如何利用大语言模型进行自主任务规划与执行。
1. ReAct模式：结合推理与行动，Agent在每一步先思考当前状态和目标，再决定调用哪个外部工具，并根据工...
- [中级] **Spring Cloud 微服务架构**
  - 考点: 服务注册与发现, 配置中心, 熔断限流
  - 摘要: Spring Cloud 是一套微服务治理框架，主要解决分布式系统中的常见问题。其核心组件和机制如下：
1. 服务注册与发现：使用 Eureka 或 Nacos 作为注册中心，微服务启动时自动注册，消...
- [中级] **[Agent] 12-Factor方法论 第9条：最大化并行度**
  - 考点: 并发执行, 任务依赖, 资源利用率
  - 摘要: 1. 最大化并行度要求Agent在处理相互独立的任务时，应尽可能采用并发执行而非串行等待。
2. 这种设计能显著减少用户等待时间，提升系统资源利用率，使Agent响应更加敏捷。
3. 具体实现包括将独...
- [中级] **[Agent] LangGraph 文档接收智能体**
  - 考点: LangGraph, 状态图, 条件路由
  - 摘要: 1. 架构设计：使用LangGraph构建有向无环图，节点包含文档解析、分类、实体提取和持久化存储。
2. 状态管理：定义全局状态对象，保存原始文档路径、解析后的文本、提取的结构化实体及当前处理阶段。...
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
- [中级] **构建简单的数据分析 Agent（Notebook 实践）**
  - 考点: ReAct循环, 工具定义与JSON Schema, 代码沙箱执行
  - 摘要: 核心思路：以LLM为大脑，采用ReAct模式（推理→行动→观察循环）驱动数据分析流程。关键设计点：1）工具定义：封装代码执行器（Python REPL/沙箱）、数据加载（read_csv）、可视化（m...
- [中级] **端到端测试Agent设计模式**
  - 考点: 任务分解, 工具调用, 语义断言
  - 摘要: 1. 规划与分解：Agent接收自然语言测试需求，利用LLM将其分解为具体的测试步骤和预期结果。
2. 工具调用执行：Agent通过调用浏览器自动化工具（如Playwright）或API请求工具，逐步...
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

- [My x402 API made $0.08 in its first week. Here is who actually came.](https://dev.to/albertbalestrini/my-x402-api-made-008-in-its-first-week-here-is-who-actually-came-2gka) (dev.to) - A few weeks ago I put a small API online that agents pay per call with x402, USD
- [Your AI agent built PDF export but who owns the next change](https://dev.to/bitavu/your-ai-agent-built-pdf-export-but-who-owns-the-next-change-224n) (dev.to) - Imagine asking your coding agent to add a client report export.  It creates a ro
- [How to Integrate AI Agents with Existing APIs: Patterns, Tools, and Safe Rollout](https://dev.to/kami_butt_69b922ade8de012/how-to-integrate-ai-agents-with-existing-apis-patterns-tools-and-safe-rollout-3eg9) (dev.to) - Your agent is not a user of your API. It's a stranger with a keyboard — and righ
- [Giving an AI agent eyes on a running React Native app](https://dev.to/zemant91/giving-an-ai-agent-eyes-on-a-running-react-native-app-jfe) (dev.to) - Over the last few months I've posted small findings about AI agents, MCP and Rea
- [What the heck do I alert on anymore?](https://dev.to/allenheltondev/what-the-heck-do-i-alert-on-anymore-3cae) (dev.to) - My AI agents make thousands of decisions I can't supervise. Here's how I'm figur

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

- [We Checked 61 Official MCP Servers Against the Auth Spec](https://dev.to/x1y1co/we-checked-61-official-mcp-servers-against-the-auth-spec-48i4) (dev.to) - Most SaaS companies now ship an official remote MCP server, and most of them sit
- [Give your AI assistant a video studio over MCP (and the tool pattern that keeps it from burning your credits)](https://dev.to/alamdar_525aa72b980d/give-your-ai-assistant-a-video-studio-over-mcp-and-the-tool-pattern-that-keeps-it-from-burning-15b6) (dev.to) - Most MCP demos read files or query databases. Those tools are cheap and reversib
- [The state of MCP auth, November 2026: I scanned 25 public servers](https://dev.to/godsmasher/the-state-of-mcp-auth-november-2026-i-scanned-25-public-servers-f9b) (dev.to) - MCP (Model Context Protocol) has an auth story on paper: OAuth 2.1 with PKCE, dy
- [Your Agent Has a Side Door: Testing MCP Policy Beyond the Tool List](https://dev.to/bengreenberg/your-agent-has-a-side-door-testing-mcp-policy-beyond-the-tool-list-1699) (dev.to) - At MCP Dev Summit Toronto, Accenture's Michael Forrester told a story about an e
- [Reading an agent forum from Python: four tools, three clocks](https://dev.to/blucca/reading-an-agent-forum-from-python-four-tools-three-clocks-3cpo) (dev.to) - I wanted to give a Python agent a small piece of public context from another age

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

- [From 30 Minutes to 2: Building a Multi-Agent LangGraph + RAG Pipeline for Broker Back-Office Review](https://dev.to/imsachinshah/from-30-minutes-to-2-building-a-multi-agent-langgraph-rag-pipeline-for-broker-back-office-review-icf) (dev.to) - The problem: 30 minutes per application, 400 times a day   On paper, broker back
- [How to Add an Audit Trail to a LangGraph Agent](https://dev.to/mir_arshadalitalpur_1b3/how-to-add-an-audit-trail-to-a-langgraph-agent-42m3) (dev.to) - LangGraph makes it easy to build agents as graphs: nodes that retrieve, reason, 
- [Agents that are actually deterministic](https://dev.to/aigenos/agents-that-are-actually-deterministic-omj) (dev.to) - How aigenos/flow makes an agent run the same steps every time, and why that is h
- [LangChain vs LangGraph: Which Should You Use?](https://dev.to/bcncodeschool/langchain-vs-langgraph-which-should-you-use-4jf9) (dev.to) - Compare LangChain and LangGraph by abstraction, state, routing, human approval, 
- [AI Staffing Partner](https://dev.to/narender_reddy_0fa71a7ec8/ai-staffing-partner-1keg) (dev.to) - Build an AI-powered Resume and Job Description Assistant that analyzes uploaded 

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

- [Last week in Agent Security Update 5: The Pentagon Prompts](https://dev.to/willvelida/last-week-in-agent-security-update-5-the-pentagon-prompts-bel) (dev.to) - Last week I spoke at API Days in Melbourne, where I gave a talk on the OWASP Top

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
