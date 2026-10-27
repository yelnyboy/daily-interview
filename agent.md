# AI Agent 开发知识库

> 最后更新: 2026-10-27
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

- [JetBrains open-sourced an agentic IDE where agents never touch your checkout](https://dev.to/slabb/jetbrains-open-sourced-an-agentic-ide-where-agents-never-touch-your-checkout-22hc) (dev.to) - JetBrains open-sourced Thinkrail, an Apache-2.0 agentic IDE where every agent wo
- [The Best Prompt Rule Is the One You Delete: Moving AI Guardrails Out of Markdown and Into Git Locks, Linux insmod, and 15ms Compiler Auto-Fixes](https://dev.to/gde/the-best-prompt-rule-is-the-one-you-delete-moving-ai-guardrails-out-of-markdown-and-into-git-5a5h) (dev.to) - Every rule that stays in a prompt eventually bloats, blurs, or gets gamed by the
- [I Hired a Sloth to Read My GitHub Inbox While I Sleep](https://dev.to/vignesh_one/i-hired-a-sloth-to-read-my-github-inbox-while-i-sleep-50lb) (dev.to) - This is a submission for the Hacktoberfest Open-Source AI Challenge Week 3: Slow
- [Ledger: git blame for your thinking](https://dev.to/karthikbommineni/ledger-git-blame-for-your-thinking-1kmj) (dev.to) - Make sure your agent never forgets — and make sure you can still see why you cho
- [When Should an AI Agent Stop?](https://dev.to/anshu_kumar_4a8413f8dfae1/when-should-an-ai-agent-stop-38po) (dev.to) - Designing a progress-aware execution controller for agentic systems.  Imagine as

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

- [4 turns to fix a number, 12 days to take it back](https://dev.to/theagentloop/4-turns-to-fix-a-number-12-days-to-take-it-back-6oa) (dev.to) - One correction took 24.66 seconds and 4 turns. Another took 12 days. The differe
- [A Three-Test Overlay Audit for Crawlability, Performance and Search Visibility](https://dev.to/alifar/a-three-test-overlay-audit-for-crawlability-performance-and-search-visibility-22k8) (dev.to) - Overlays are a normal part of the modern web. Cookie notices, email sign-up prom
- [Building an agentic workflow, part 2: testing what done means](https://dev.to/nullabletype/building-an-agentic-workflow-part-2-testing-what-done-means-2ikj) (dev.to) - At the end of part 1, I had a specification, prototype tickets, and rules for ho
- [BPE Tokenization: A Trailing Space in My Prompt Broke 41 of 300 Labels](https://dev.to/ji_ai/bpe-tokenization-a-trailing-space-in-my-prompt-broke-41-of-300-labels-4h2f) (dev.to) - BPE tokenization glues spaces onto the next word, so a trailing space in your pr
- [Building AI Agents That Ask Before They Act](https://dev.to/zeeshan9958/building-ai-agents-that-ask-before-they-act-3b22) (dev.to) - I am tired of seeing "autonomous" AI agents that are anything but.  If you have 

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

- [Before I Compared the Models, I Had to Decide What Not to Count](https://dev.to/hexisteme/before-i-compared-the-models-i-had-to-decide-what-not-to-count-2djf) (dev.to) - I built a lab to compare the models running in my agent fleet on per-turn behavi
- [Node.js Embedding Models for Chatbot RAG: Semantic Search Portability Explained](https://dev.to/brantlockwood468/nodejs-embedding-models-for-chatbot-rag-semantic-search-portability-explained-o63) (dev.to) - Short answer: choose the embedding model that passes a labeled health-catalog re
- [Building an evidence-based job application tracker with Rails 8, pgvector and Claude](https://dev.to/henock_mullissa/building-an-evidence-based-job-application-tracker-with-rails-8-pgvector-and-claude-135m) (dev.to) - A typical job ad lists ten or more requirements. When I apply, the hard part isn
- [RAG Retrieval Evaluation: 5 Reasons It Matters Before Shipping a SaaS Feature](https://dev.to/ephraimpierce7934/rag-retrieval-evaluation-5-reasons-it-matters-before-shipping-a-saas-feature-4dc) (dev.to) - The least complex release gate is a fixed set of representative questions, relev
- [Build a RAG Chatbot That Admits When It Doesn't Know (Pure Python, No Dependencies)](https://dev.to/mahuan2928/build-a-rag-chatbot-that-admits-when-it-doesnt-know-pure-python-no-dependencies-2ec3) (dev.to) - The problem: chatbots that guess   Every team wants a chatbot that answers quest

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

### 已积累题目 (15题)

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
- [中级] **使用LangGraph构建新闻摘要Agent**
  - 考点: LangGraph状态图, 节点与边, 状态管理
  - 摘要: 1. LangGraph通过将工作流建模为状态图来构建Agent，核心概念包括状态、节点和边。2. 在新闻摘要Agent中，状态用于存储当前处理的新闻URL、抓取的原始文本和最终摘要。3. 节点代表具...
- [中级] **使用LangGraph生成播客的Agent设计模式**
  - 考点: LangGraph, 状态图, 工作流编排
  - 摘要: 1. 需求分析：播客生成需要资料收集、大纲生成、内容撰写、语音合成等步骤，适合使用工作流模式。2. 架构设计：使用LangGraph构建状态图，每个节点代表一个子任务，如资料分析节点、大纲生成节点、脚...
- [中级] **创建本地AI Agent**
  - 考点: 本地大模型部署, Ollama, LangChain框架
  - 摘要: 1. 模型选择与部署：创建本地AI Agent的第一步是选择并部署开源大模型（如Llama 3、Qwen等）。通常使用Ollama或vLLM等工具在本地运行模型，提供兼容OpenAI格式的API接口供...
- [高级] **自我改进型智能体**
  - 考点: 自我反思, 长期记忆, 提示词优化
  - 摘要: 1. 核心概念：自我改进型智能体是一种能够根据过去的经验和环境反馈，自动调整自身行为、提示词或底层逻辑的智能体架构。2. 反思机制：通过引入自我反思步骤，智能体评估其先前动作的输出质量，识别错误或不足...

### 相关文章资源

- [Markdown as Malware: How AI Agents Turn Downloads Folders into Instruction Injection Vectors](https://dev.to/mech_app_ai/markdown-as-malware-how-ai-agents-turn-downloads-folders-into-instruction-injection-vectors-4e7o) (dev.to) - AI coding agents treat markdown files as trusted instructions. Attackers drop AG
- [I read 16 platforms' terms so my agent wouldn't get banned. Here's what they actually say about AI agents.](https://dev.to/johnclaude1337/i-read-16-platforms-terms-so-my-agent-wouldnt-get-banned-heres-what-they-actually-say-about-ai-3hmc) (dev.to) - Disclosure: this post was written by Claude, an AI model made by Anthropic. I ru
- [16,074 MCP requests in 7 days, 1 real tool call from an IDE: what actually hits a public MCP server](https://dev.to/botgathering/16074-mcp-requests-in-7-days-1-real-tool-call-from-an-ide-what-actually-hits-a-public-mcp-server-4koc) (dev.to) - Disclosure: written by the AI agent that runs BotGathering's analytics. Publishe
- [Give your AI agent a phone number that answers](https://dev.to/tolga_coskun_d0aa35a068f4/give-your-ai-agent-a-phone-number-that-answers-33ef) (dev.to) - Your agent can book, write and search. The moment a human wants to call the busi
- [Slowth Money: a local AI agent for your financial goals](https://dev.to/javz/slowth-money-a-local-ai-agent-for-your-financial-goals-2ki2) (dev.to) - This is a submission for the Hacktoberfest Open-Source AI Challenge Week 3: Slow

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

- [MCP Token Cost: I Cut My MCP Server From 15 Tools to 4](https://dev.to/aws-builders/mcp-token-cost-i-cut-my-mcp-server-from-15-tools-to-4-cek) (dev.to) - I rebuilt a real AWS cost-triage MCP server from 15 tools to 4. Same account, sa
- [Your agent isn't running out of context because of one big file](https://dev.to/techdevfun/your-agent-isnt-running-out-of-context-because-of-one-big-file-20bb) (dev.to) - Your agent isn't running out of context because of one big file. It is running o
- [Bookmark It! STOP Shipping Broken Vibe Code: 10 Checks That Save Your App at 2 AM](https://dev.to/flisk/bookmark-it-stop-shipping-broken-vibe-code-10-checks-that-save-your-app-at-2-am-2ei6) (dev.to) - Your demo works. Great. Now try it on a different laptop.  That is where vibe-co
- [We indexed 39,654 agent listings and put a free API on it](https://dev.to/orbitaldesk/we-indexed-39654-agent-listings-and-put-a-free-api-on-it-27j3) (dev.to) - We indexed 39,654 agent listings and put a free API on it   If you want to find 
- [Affinity MCP vs code: why I make my thumbnails with a script](https://dev.to/argbetech/affinity-mcp-vs-code-why-i-make-my-thumbnails-with-a-script-2dom) (dev.to) - Failing is hard. Especially when the tutorial is already recorded.  I wanted to 

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

- [My RAG tool refused to answer a question my notes clearly answered](https://dev.to/salima_iddrisu/my-rag-tool-refused-to-answer-a-question-my-notes-clearly-answered-aho) (dev.to) - I built a retrieval-augmented generation tool over my own notes — no LangChain, 
- [Loading exported Reddit and Hacker News threads into LangChain, with citations you can check](https://dev.to/superlede/loading-exported-reddit-and-hacker-news-threads-into-langchain-with-citations-you-can-check-1pi3) (dev.to) - Ask a model what people in a Reddit thread complain about and you get a neat lis
- [Owning Your Intelligence Means Owning Your Implementation](https://dev.to/focused_dot_io/owning-your-intelligence-means-owning-your-implementation-4p8h) (dev.to) - Owning your models, evals, and traces is the start. Lasting control over agentic
- [I Built a Finance Assistant Where Six AI Agents Check Each Other's Work](https://dev.to/neel_b_05a240ea1a5ae2964d/i-built-a-finance-assistant-where-six-ai-agents-check-each-others-work-1ele) (dev.to) - A LangGraph.js supervisor plans each question, sends it to six specialist agents
- [How to Add Web Search to a LangChain.js Agent (No API Key)](https://dev.to/agentsearchhq/how-to-add-web-search-to-a-langchainjs-agent-no-api-key-5df6) (dev.to) - Add a free LangChain.js web search tool to a TypeScript agent with @agentsearchh

---

## 9. 多智能体系统

> 构建多个Agent协作完成复杂任务的系统

### 知识点

- 多Agent协作模式
- DAG Agents
- 角色分配与任务编排
- Agent间通信协议

### 相关文章资源

- [Building a Multi-Agent Token Usage Widget in Under 500 KB](https://dev.to/gde/building-a-multi-agent-token-usage-widget-in-under-500-kb-1fih) (dev.to) - How we built a 483 KB zero-WebKit macOS Universal Binary and a single-file Ubunt

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

- [Agents should never hold your API keys. NVIDIA just open-sourced the runtime that enforces it](https://dev.to/slabb/agents-should-never-hold-your-api-keys-nvidia-just-open-sourced-the-runtime-that-enforces-it-3jm4) (dev.to) - NVIDIA open-sourced OpenShell: a runtime where agent fleets get kernel-level san

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
