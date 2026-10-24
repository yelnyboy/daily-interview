# AI Agent 开发知识库

> 最后更新: 2026-10-24
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

- [When Should an AI Agent Stop?](https://dev.to/anshu_kumar_4a8413f8dfae1/when-should-an-ai-agent-stop-38po) (dev.to) - Designing a progress-aware execution controller for agentic systems.  Imagine as
- [My AI Support Agent Crushed the Demo. Then Production Happened.](https://dev.to/msohailkhandev/my-ai-support-agent-crushed-the-demo-then-production-happened-3dfh) (dev.to) - Everyone shows the AI agent working. Nobody shows the week it fell apart.  I bui
- [Inside VOICE-RAG: From Speech to Grounded Answers](https://dev.to/the_infernix/inside-voice-rag-from-speech-to-grounded-answers-1khn) (dev.to) - Pavan Ganesh Indupudi (Infernix) · Originally published at the-infernix.github.i
- [RepoPilot: How an AWS Lambda Agent Scores GitHub Repos Before You Clone Them](https://dev.to/mech_app_ai/repopilot-how-an-aws-lambda-agent-scores-github-repos-before-you-clone-them-4k3k) (dev.to) - Lambda + Bedrock pipeline that scores repository risk in 60 seconds. Examining t
- [I open-sourced Tokenade, my token optimizer for coding agents. Here is why the paid model did not hold](https://dev.to/paul_irolla_6b5ae261d0224/i-open-sourced-tokenade-my-token-optimizer-for-coding-agents-here-is-why-the-paid-model-did-not-2ahc) (dev.to) - Tokenade is free and open source as of version 2.0, under MIT OR Apache-2.0. The

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

- [Audio Deadlines: Running On-Device TTS Without Audible Glitches](https://dev.to/dima_kruglov_608741d9a416/audio-deadlines-running-on-device-tts-without-audible-glitches-kdi) (dev.to) - Gradium open-sourced Phonon, its on-device TTS engine (https://gradium.ai/phonon
- [How We Won a Hackathon Without Writing a Single Line of Code (Part 2): AI Judging, the Pitch, and First Place](https://dev.to/goroman/how-we-won-a-hackathon-without-writing-a-single-line-of-code-part-2-ai-judging-the-pitch-and-3nmf) (dev.to) - Images from the original Japanese post.  Read Part 1 · Original Japanese version
- [Your semantic cache will happily replay the wrong command](https://dev.to/pomereneio/your-semantic-cache-will-happily-replay-the-wrong-command-4pg5) (dev.to) - Your semantic cache will happily replay the wrong command   Semantic caching wor
- [A 70-line model router: try the cheap LLM first, escalate only when the answer fails validation](https://dev.to/x3team/a-70-line-model-router-try-the-cheap-llm-first-escalate-only-when-the-answer-fails-validation-4opc) (dev.to) - Most LLM features I see in production use one model for everything. It is usuall
- [Your Model Is a Binary You Ship to Strangers: Release Engineering for Edge AI](https://dev.to/dima_kruglov_608741d9a416/your-model-is-a-binary-you-ship-to-strangers-release-engineering-for-edge-ai-1nn3) (dev.to) - Gradium open-sourcing its on-device TTS ([Phonon](https://gradium.ai/phonon)) is

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

- [Legal Contract Review Retrieval Architecture: A Release Checklist for Traceable Search](https://dev.to/zachariahholloway9058/legal-contract-review-retrieval-architecture-a-release-checklist-for-traceable-search-h43) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [Two Identical Chunks Are Not Always Duplicates](https://dev.to/swapnanilsaha/two-identical-chunks-are-not-always-duplicates-3hbl) (dev.to) - Copied scripts must collapse into one search result; generated accessors must no
- [Day 06/90: Reranking in RAG — When the Right Evidence Isn’t Ranked First](https://dev.to/rimsha_kanwal/day-0690-reranking-in-rag-when-the-right-evidence-isnt-ranked-first-5dha) (dev.to) - What happens when a RAG system retrieves the passage containing the answer, but 
- [When Should Engineering Leaders Choose RAG Instead of a Workflow Engine](https://dev.to/olivia-white/when-should-engineering-leaders-choose-rag-instead-of-a-workflow-engine-5doa) (dev.to) - Engineering leaders building enterprise AI systems must decide whether to invest
- [What Actually Happens When You Build a Production RAG Chatbot on Amazon Bedrock](https://dev.to/hieu_le/what-actually-happens-when-you-build-a-production-rag-chatbot-on-amazon-bedrock-4l2) (dev.to) - How we built a document Q&amp;A system with NestJS, PostgreSQL, pgvector, Hybrid

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

### 已积累题目 (12题)

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

### 相关文章资源

- [Give your AI agent web-data tools with Apify's MCP server (Python, no SDK, 2026)](https://dev.to/datawrightlabs/give-your-ai-agent-web-data-tools-with-apifys-mcp-server-python-no-sdk-2026-4lih) (dev.to) - Most AI agents can now talk to remote MCP servers. Apify runs one at https://mcp
- [How to Integrate Deep Research into Your AI Agent](https://dev.to/valyuai/how-to-integrate-deep-research-into-your-ai-agent-2n82) (dev.to) - Day 23 of 30 Days of Search.           TL;DR   To integrate deep research into a
- [[Agent Platform in Practice (5)] Building an AI Agent Quality Flywheel: Automated Benchmarking for LINE AI Business Card King wi](https://dev.to/gde/agent-platform-in-practice-5-building-an-ai-agent-quality-flywheel-automated-benchmarking-for-58m2) (dev.to) - Recap   In the first four articles of the "Agent Platform in Action" series, we 
- [926 Steps, Two Lobotomies, and Zero Nudges: Flight-Testing the Commitment Machine Across Gemini, Claude, and GPT-OSS](https://dev.to/gde/926-steps-two-lobotomies-and-zero-nudges-flight-testing-the-commitment-machine-across-gemini-55ca) (dev.to) - A 2026 Harvard study of 718 companies found that AI agents write 30% more code a
- [Independent OpenAI Agent Investigation Highlights Monitoring Lessons for Businesses](https://dev.to/alifar/independent-openai-agent-investigation-highlights-monitoring-lessons-for-businesses-6f1) (dev.to) - An independent investigation by METR and a contractor from Redwood Research exam

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

- [Why AI assistants don't know small businesses, and how we opened Kamchatka to agents with MCP](https://dev.to/vedarai/why-ai-assistants-dont-know-small-businesses-and-how-we-opened-kamchatka-to-agents-with-mcp-5gio) (dev.to) - AI assistants are getting good at planning trips. Ask one about Kamchatka, thoug
- [Ghidra MCP: Let AI Help You Reverse Engineer Binaries](https://dev.to/geekcoding101/ghidra-mcp-let-ai-help-you-reverse-engineer-binaries-5cc1) (dev.to) - Originally published at GeekCoding101.           Reverse Engineering Meets AI   
- [Agent memory: the FTS5 trigger bug that silently killed every update](https://dev.to/mrpkk/agent-memory-the-fts5-trigger-bug-that-silently-killed-every-update-5ah2) (dev.to) - Your agent's memory is an archive until you can update it. Ours was an archive f
- [A Read-Only WebMCP Tool Erased My React Form State](https://dev.to/raju_dandigam/a-read-only-webmcp-tool-erased-my-react-form-state-5a2c) (dev.to) - The read path in Trip Workbench can erase a person’s unsaved purpose without sen
- [The best Godot MCP server in 2026 depends on what you want the agent to touch](https://dev.to/orellanaed/the-best-godot-mcp-server-in-2026-depends-on-what-you-want-the-agent-to-touch-5aji) (dev.to) - The best Godot MCP server in 2026: Flockbay's to build and play-test a whole gam

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

- [Loading exported Reddit and Hacker News threads into LangChain, with citations you can check](https://dev.to/superlede/loading-exported-reddit-and-hacker-news-threads-into-langchain-with-citations-you-can-check-1pi3) (dev.to) - Ask a model what people in a Reddit thread complain about and you get a neat lis
- [Owning Your Intelligence Means Owning Your Implementation](https://dev.to/focused_dot_io/owning-your-intelligence-means-owning-your-implementation-4p8h) (dev.to) - Owning your models, evals, and traces is the start. Lasting control over agentic
- [I Built a Finance Assistant Where Six AI Agents Check Each Other's Work](https://dev.to/neel_b_05a240ea1a5ae2964d/i-built-a-finance-assistant-where-six-ai-agents-check-each-others-work-1ele) (dev.to) - A LangGraph.js supervisor plans each question, sends it to six specialist agents
- [How to Add Web Search to a LangChain.js Agent (No API Key)](https://dev.to/agentsearchhq/how-to-add-web-search-to-a-langchainjs-agent-no-api-key-5df6) (dev.to) - Add a free LangChain.js web search tool to a TypeScript agent with @agentsearchh
- [I am building a practical AI agents course (LangChain first, then LangGraph), and the certificate has to be earned](https://dev.to/ali_82f3409ed625e8ba8515b/i-am-building-a-practical-ai-agents-course-langchain-first-then-langgraph-and-the-certificate-34f3) (dev.to) - I have spent the last few months building AI agents with LangChain and LangGraph

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
