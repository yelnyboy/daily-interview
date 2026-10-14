# AI Agent 开发知识库

> 最后更新: 2026-10-14
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

- [The State of AI Instruction Quality: Q3 2026](https://dev.to/reporails/the-state-of-ai-instruction-quality-q3-2026-19bg) (dev.to) - 91% of the most-starred repos on GitHub give their coding agent at least one ins
- [Fallback Design in Legal Contract Review Retrieval Architecture for Teams](https://dev.to/algernoncross4103/fallback-design-in-legal-contract-review-retrieval-architecture-for-teams-42pg) (dev.to) - Use a staged retrieval design with explicit collections, bounded queries, and tr
- [Meta and OpenAI present digital assistants that work even when you turn off the device](https://dev.to/hacksgr/meta-and-openai-present-digital-assistants-that-work-even-when-you-turn-off-the-device-54ia) (dev.to) - Meta and OpenAI introduced persistent autonomous AI agents, Muse and ChatGPT Dot
- [Prompts mal usados y cómo corregir prompts de IA](https://dev.to/henryramireztech/prompts-mal-usados-y-como-corregir-prompts-de-ia-3oe1) (dev.to) - Los prompts mal usados y la falta de criterio técnico para corregir prompts de I
- [README Clew 2: Built with AdaL. Labeled by Jev. Judged by Code. Explained by Haiku.](https://dev.to/earlgreyhot1701d/readme-clew-2-built-with-adal-labeled-by-jev-judged-by-code-explained-by-haiku-196e) (dev.to) - Jev labels the line. Code makes the call.   TL;DR: README Clew 2 checks whether 

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

- [How AIClaw 3.7.13 Separates Context Estimates From Provider Usage](https://dev.to/chowyu12/how-aiclaw-3713-separates-context-estimates-from-provider-usage-909) (dev.to) - Long agent sessions accumulate text, tool results, and decisions. A context mete
- [How Kimi Powers REGLO Agent’s On-Chain Decisions](https://dev.to/edmundjeevan/how-kimi-powers-reglo-agents-on-chain-decisions-3cne) (dev.to) - REGLO Agent is an AI agent built for the Monad Metropolis hackathon that gets pa
- [OpenAI and Anthropic call for new laws on artificial intelligence](https://dev.to/hacksgr/openai-and-anthropic-call-for-new-laws-on-artificial-intelligence-3j5b) (dev.to) - OpenAI and Anthropic representatives told a UK parliamentary committee that volu
- [Prompts don't enforce budgets. Signatures do.](https://dev.to/payload-tools/prompts-dont-enforce-budgets-signatures-do-2a1j) (dev.to) - A spending limit written in a prompt is not a control. It is a piece of text, si
- [Your User Closed the Tab. Your Node Server Is Still Paying for the LLM Call](https://dev.to/gabrielanhaia/your-user-closed-the-tab-your-node-server-is-still-paying-for-the-llm-call-3a11) (dev.to) - A streamed LLM call keeps running after the browser disconnects unless you cance

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

- [Prompt Paws: A Cozy 60 FPS AI Agent Bakery Game Teaching RAG, Guardrails & Context Caching](https://dev.to/gde/i-built-a-cozy-60-fps-ai-agent-bakery-game-to-teach-rag-guardrails-context-caching-multi-agent-2ek) (dev.to) - This is a submission for the Hacktoberfest Open-Source AI Challenge Week 2: Side
- [VAI Assistant: a non-injection AI customer service tool for WeChat on Windows](https://dev.to/yichenguaitan/vai-assistant-a-non-injection-ai-customer-service-tool-for-wechat-on-windows-2c56) (dev.to) - VAI助手 (formerly "微信管家", https://vx.cuxn.cn/) is a Windows desktop app that auto-
- [Customer-Support Knowledge Base Retrieval: 3-Stage Metadata Filter Design](https://dev.to/aldencross6847/customer-support-knowledge-base-retrieval-3-stage-metadata-filter-design-379e) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [How to Build Retrieval Architecture for Financial Research Dashboard: Incremental Indexing](https://dev.to/lorenzholm3752/how-to-build-retrieval-architecture-for-financial-research-dashboard-incremental-indexing-4ail) (dev.to) - Financial research dashboards have an awkward freshness problem: an analyst want
- [FastAPI Retrieval Collections for Fresh Semantic Matching in Developer Changelogs](https://dev.to/sullivanreed1247/fastapi-retrieval-collections-for-fresh-semantic-matching-in-developer-changelogs-4cd0) (dev.to) - Use staged retrieval with explicit collections, bounded queries, and traceable s

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

- [Workday Is Buying Identity for AI Agents. Let's Build a Tiny Access Grant in TypeScript.](https://dev.to/bobbyhalljr/workday-is-buying-identity-for-ai-agents-lets-build-a-tiny-access-grant-in-typescript-25m4) (dev.to) - Workday plans to acquire C1.ai so agents get access when they are registered and
- [How we let AI agents spend money without a blank check](https://dev.to/specstream/how-we-let-ai-agents-spend-money-without-a-blank-check-18gp) (dev.to) - If you give an agent an API key on a funded account, you've given it a card. Mos
- [8 Frameworks in the Demo, 3 Rows in the Conformance Table: I Ran Microsoft's agent-hooks CTK](https://dev.to/fable7/8-frameworks-in-the-demo-3-rows-in-the-conformance-table-i-ran-microsofts-agent-hooks-ctk-3ac8) (dev.to) - Eight frameworks in the demo, three rows in the conformance table. I ran the kit
- [I built an MCP server that lets AI agents investigate videos](https://dev.to/sevrin/i-built-an-mcp-server-that-lets-ai-agents-investigate-videos-32pm) (dev.to) - Hey DEV! First post here 👋  I've been working on an open-source project called U
- [How I Built a Fully Local AI Coding Agent with Qwen 3.8, LM Studio, and Pi (No Paid APIs)](https://dev.to/vivek_shetye/how-i-built-a-fully-local-ai-coding-agent-with-qwen-38-lm-studio-and-pi-no-paid-apis-5bp7) (dev.to) - What if you could have an AI coding agent that reads your files, writes code, ex

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

- [Walter MCP in Gemini CLI: Setup and Workflows](https://dev.to/mohab_karim/walter-mcp-in-gemini-cli-setup-and-workflows-2ap5) (dev.to) - One config entry, one OAuth sign-in, and the terminal workflows that make the co
- [Your agent has 40 tools and it still picks the wrong one](https://dev.to/jeff_pdc/your-agent-has-40-tools-and-it-still-picks-the-wrong-one-27la) (dev.to) - MCP tool sprawl looks like progress. In practice, a long, vaguely-named tool lis
- [Building Your First MCP Server: A Practical Guide](https://dev.to/ipsphil_digital/building-your-first-mcp-server-a-practical-guide-24pa) (dev.to) - Building Your First MCP Server: A Practical Guide   The Model Context Protocol (
- [Build, Ship, Shape: Amazon Developer Hackathon](https://dev.to/evaaliya/build-ship-shape-amazon-developer-hackathon-aid) (dev.to) - Alguard: a two-tier trust layer for agentic purchases   I just submitted Alguard
- [Grafana MCP for Claude Code: Query Dashboards, Metrics, and Alerts Directly](https://dev.to/juholee/grafana-mcp-for-claude-code-query-dashboards-metrics-and-alerts-directly-2jak) (dev.to) - Grafana Labs’ official MCP server lets Claude Code search dashboards, run PromQL

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

- [Production RAG with LangChain & LangGraph: Retrieval, Reranking & Agentic Workflows](https://dev.to/ipsphil_digital/production-rag-with-langchain-langgraph-retrieval-reranking-agentic-workflows-1kd9) (dev.to) - Production RAG with LangChain &amp; LangGraph: End-to-End Implementation   Build
- [LangGraph Practical Guide: When to Use It Over LangChain](https://dev.to/amrendra_n_mishra/langgraph-practical-guide-when-to-use-it-over-langchain-kjj) (dev.to) - Why Automate Content Creation   Creating content manually for 9 channels would t
- [What Are LLMs, and How Do You Build Stuff With Them?](https://dev.to/0xadityaa/what-are-llms-and-how-to-build-stuff-using-it-4l68) (dev.to) - An LLM just predicts the next token. Everything useful is the scaffolding around
- [Benchmarking AI vs. Human Interviewers: Can LangGraph Outperform Staff Engineers?](https://dev.to/apparao_aremanda_1f792aeb/benchmarking-ai-vs-human-interviewers-can-langgraph-outperform-staff-engineers-36kn) (dev.to) - Benchmarking AI vs. Human Interviewers: Kovi Evaluation Accuracy Report   Engine
- [Give your AI agent a stock photo tool in 5 lines](https://dev.to/marouane_tijani_3a7fc19a7/give-your-ai-agent-a-stock-photo-tool-in-5-lines-1gmh) (dev.to) - Real, free-to-use photos with their licence and credit line, for LangChain, the 

---

## 9. 多智能体系统

> 构建多个Agent协作完成复杂任务的系统

### 知识点

- 多Agent协作模式
- DAG Agents
- 角色分配与任务编排
- Agent间通信协议

### 相关文章资源

- [Multi-Agent Orchestration in Laravel: Coordinating Specialists Instead of One Giant Prompt](https://dev.to/hosseinhezami/multi-agent-orchestration-in-laravel-coordinating-specialists-instead-of-one-giant-prompt-269o) (dev.to) - The first version of most AI features is not a system.  It is one giant prompt d

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
