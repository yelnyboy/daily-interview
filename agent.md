# AI Agent 开发知识库

> 最后更新: 2026-10-16
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

- [Worktree lifecycle for AI agents](https://dev.to/saez520/worktree-lifecycle-for-ai-agents-1ooo) (dev.to) - The problem is not creating worktrees, but managing them   When two or more agen
- [It caught "partner" "pareja" in an IRS rule and missed "return" "devolución": an offline MT checker for translators](https://dev.to/p0rt/it-caught-partner-pareja-in-an-irs-rule-and-missed-return-devolucion-an-offline-mt-7ge) (dev.to) - An offline checker that ranks machine-translated segments by the risk of a major
- [I built a lie detector for AI coding agents. Then I read the rules.](https://dev.to/dannwaneri/i-built-a-lie-detector-for-ai-coding-agents-then-i-read-the-rules-1hhb) (dev.to) - When an AI agent commits a change to code, it makes a claim about what it change
- [PDF Knowledge Retrieval Under Latency Budgets — An Architecture Decision Record](https://dev.to/titanj53/pdf-knowledge-retrieval-under-latency-budgets-an-architecture-decision-record-275) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [The State of AI Instruction Quality: Q3 2026](https://dev.to/reporails/the-state-of-ai-instruction-quality-q3-2026-19bg) (dev.to) - 91% of the most-starred repos on GitHub give their coding agent at least one ins

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

- [How AIClaw Keeps Multi-File Reviews in Place with Docked Tabs](https://dev.to/chowyu12/how-aiclaw-keeps-multi-file-reviews-in-place-with-docked-tabs-2ojb) (dev.to) - Reviewing an agent's work often means moving between several files: a Markdown e
- [Claude : tout ce qu'il sait faire, bien au-delà du chat](https://dev.to/rayane_tchakiguewe_bc9e08/claude-tout-ce-quil-sait-faire-bien-au-dela-du-chat-1n2a) (dev.to) - La plupart des gens utilisent Claude comme un simple chatbot : une question, une
- [Loreflow: Security by Construction, Making Three Classes of AI Data Leaks Structurally Impossible](https://dev.to/rafianajam/security-by-construction-making-three-classes-of-ai-data-leaks-structurally-impossible-3cfh) (dev.to) - How Loreflow's answer pipeline is designed so that cross-tenant leakage, prompt-
- [Why long context is expensive: the KV cache bill](https://dev.to/kai_ilands/why-long-context-is-expensive-the-kv-cache-bill-39da) (dev.to) - Your chat history can weigh more than the model that reads it. Llama 3.1 8B is a
- [Red-Teaming a Kids' AI Tutor: How a One-Word Variant Slipped Past Our Prompt-Injection Filter](https://dev.to/rafianajam/red-teaming-a-kids-ai-tutor-how-a-one-word-variant-slipped-past-our-prompt-injection-filter-3ad1) (dev.to) - Adversarial testing of the input/output guardrails in Learna Tutor, a TK–8 AI tu

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

### 已积累题目 (6题)

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

- [GhostRunner: Turning Every Street into a Story](https://dev.to/nishchal-29/ghostrunner-turning-every-street-into-a-story-5g9o) (dev.to) - This is a submission for the Hacktoberfest Open-Source AI Challenge Week 2: Side
- [Spec-driven development: the rise of Markdown](https://dev.to/chuksadirije/spec-driven-development-the-rise-of-markdown-363f) (dev.to) - Open my editor on a normal working day and most of the tabs are .md files.  Five
- [MCP Tool Poisoning: The Attack Hidden in Plain Text](https://dev.to/aegisgate/mcp-tool-poisoning-the-attack-hidden-in-plain-text-13dp) (dev.to) - In April 2025, Invariant Labs demonstrated something unsettling: you don't need 
- [Your AI Agent Just Got a Passport: Agent Identity on Google Cloud and the Redeploy Trap Nobody Talks About](https://dev.to/gde/your-ai-agent-just-got-a-passport-agent-identity-on-google-cloud-and-the-redeploy-trap-nobody-52ip) (dev.to) - Why your agents need their own identity   Most teams run every AI agent under on
- [OpenAI Data Shows AI Agents Drive More Than Half of EU Business Output Tokens](https://dev.to/alifar/openai-data-shows-ai-agents-drive-more-than-half-of-eu-business-output-tokens-1eob) (dev.to) - OpenAI says its agentic tools, Codex and ChatGPT Work, now generate more than ha

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

- [Langflow pipes commands into bash](https://dev.to/randomchaos/langflow-pipes-commands-into-bash-3oj3) (dev.to) - CVE-2026-105740 lets any authenticated Langflow user run arbitrary commands on t
- [A first look: does free-model code run on pinned versions? (n=10)](https://dev.to/provenpin/a-first-look-does-free-model-code-run-on-pinned-versions-n10-7a5) (dev.to) - I'm Osborn, a Grok Bot. Norman (another Grok Bot) and I run ProvenPin as an expe
- [AI Growth Engine Ad Test Backlog Agent: Architecture, Tool Schemas & Integration Guide](https://dev.to/botskillstack/ai-growth-engine-ad-test-backlog-agent-architecture-tool-schemas-integration-guide-49ea) (dev.to) - Why conversational agent prompts fail in production—and the exact typed tool sch
- [Let your agent get paid without holding keys](https://dev.to/send21/let-your-agent-get-paid-without-holding-keys-8b2) (dev.to) - Agent proposes, human signs: payment requests over MCP with a key that cannot sp
- [Celigo MCP Server Security: What It Blocks, What It Doesn't](https://dev.to/entechsolutions/celigo-mcp-server-security-what-it-blocks-what-it-doesnt-2b6i) (dev.to) - Celigo's MCP Server blocks credential leaks and write damage. Prompt injection a

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
