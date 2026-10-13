# AI Agent 开发知识库

> 最后更新: 2026-10-13
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

- [Fallback Design in Legal Contract Review Retrieval Architecture for Teams](https://dev.to/algernoncross4103/fallback-design-in-legal-contract-review-retrieval-architecture-for-teams-42pg) (dev.to) - Use a staged retrieval design with explicit collections, bounded queries, and tr
- [Meta and OpenAI present digital assistants that work even when you turn off the device](https://dev.to/hacksgr/meta-and-openai-present-digital-assistants-that-work-even-when-you-turn-off-the-device-54ia) (dev.to) - Meta and OpenAI introduced persistent autonomous AI agents, Muse and ChatGPT Dot
- [Prompts mal usados y cómo corregir prompts de IA](https://dev.to/henryramireztech/prompts-mal-usados-y-como-corregir-prompts-de-ia-3oe1) (dev.to) - Los prompts mal usados y la falta de criterio técnico para corregir prompts de I
- [README Clew 2: Built with AdaL. Labeled by Jev. Judged by Code. Explained by Haiku.](https://dev.to/earlgreyhot1701d/readme-clew-2-built-with-adal-labeled-by-jev-judged-by-code-explained-by-haiku-196e) (dev.to) - Jev labels the line. Code makes the call.   TL;DR: README Clew 2 checks whether 
- [How Do We Extract the “Why” from a PR into a CHANGELOG with Jev? 🤔](https://dev.to/nyaomaru/how-do-we-extract-the-why-from-a-pr-into-a-changelog-with-jev-52pk) (dev.to) - Hoi hoi! 👋  I'm @nyaomaru, a frontend engineer currently building an AI-assisted

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

- [How to stop one customer from blowing up your OpenAI bill](https://dev.to/llmbrake/how-to-stop-one-customer-from-blowing-up-your-openai-bill-3ooh) (dev.to) - Per-customer AI budgets: price every call, check before, record after, degrade b
- [Can a local LLM replace Claude Code? The benchmark everyone quotes is the wrong one.](https://dev.to/rudratosh/can-a-local-llm-replace-claude-code-the-benchmark-everyone-quotes-is-the-wrong-one-2kna) (dev.to) - Every "7 local models that replace Claude Code" list opens the same way: a table
- [What happens when you delete 30 cron jobs and replace them with one heartbeat](https://dev.to/openamer/what-happens-when-you-delete-30-cron-jobs-and-replace-them-with-one-heartbeat-2kd9) (dev.to) - What happens when you delete 30 cron jobs and replace them with one heartbeat   
- [I Asked for a Video. Claude Motion Gave Me an HTML File.](https://dev.to/dishant0406/i-asked-for-a-video-claude-motion-gave-me-an-html-file-459o) (dev.to) - Claude Motion turns prompts into animated explainers, but it's locked to Team an
- [Shivacon-Energy: The 0.5B Energy LLM That Refuses to Hallucinate](https://dev.to/shivaysinghrajput/shivacon-energy-the-05b-energy-llm-that-refuses-to-hallucinate-59c0) (dev.to) - TL;DR: Shivacon-Energy is a LoRA fine-tune of Qwen2.5-0.5B-Instruct for energy-d

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

- [FastAPI Retrieval Collections for Fresh Semantic Matching in Developer Changelogs](https://dev.to/sullivanreed1247/fastapi-retrieval-collections-for-fresh-semantic-matching-in-developer-changelogs-4cd0) (dev.to) - Use staged retrieval with explicit collections, bounded queries, and traceable s
- [E-commerce Product Search Retrieval Architecture — 2-Stage Metadata Filters](https://dev.to/kasimirberg5341/e-commerce-product-search-retrieval-architecture-2-stage-metadata-filters-336d) (dev.to) - Short answer: use a two-stage retrieval path. Apply tenant, catalog, and access 
- [Retrieval Architecture for Legal Contract Review Workspace Freshness (Release Checklist)](https://dev.to/jamesanderson3589/retrieval-architecture-for-legal-contract-review-workspace-freshness-release-checklist-i7f) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [How to Build Customer-Support Retrieval Architecture: Query Limits That Hold](https://dev.to/owensullivan9135/how-to-build-customer-support-retrieval-architecture-query-limits-that-hold-hng) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [Learning LangChain](https://dev.to/sabimantock/learning-langchain-4jlp) (dev.to) - A while back I built Synapse, a small app that answers questions using my own no

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

### 已积累题目 (2题)

- [中级] **Agent上下文工程**
  - 考点: 上下文窗口管理, 动态上下文组装, 信息压缩与摘要
  - 摘要: 上下文工程是指在LLM Agent中，系统性地管理和组织输入给大模型的上下文信息，以最大化模型推理性能和任务完成率。其核心在于如何在有限的上下文窗口内，提供最相关、最有效的信息。
1. 窗口管理：合理...
- [中级] **Agent实战：GenAI职业助手黑客松**
  - 考点: ReAct模式, 工具集成, 记忆机制
  - 摘要: 1. 需求分析：明确GenAI职业助手的核心功能，如简历优化、模拟面试、职位推荐及职业规划咨询。2. 架构设计：采用ReAct（Reasoning and Acting）设计模式，让Agent能够先推...

### 相关文章资源

- [The Industrial Revolution of Software Is Here](https://dev.to/remojansen/the-industrial-revolution-of-software-is-here-14f6) (dev.to) - The Industrial Revolution changed much more than how goods were manufactured. It
- [Your Agent's PR Grows Three 'While I Was in Here' Cleanups, and Now You Can't Review It](https://dev.to/jeff_pdc/your-agents-pr-grows-three-while-i-was-in-here-cleanups-and-now-you-cant-review-it-2oaf) (dev.to) - You asked an agent for one endpoint. The diff contains the endpoint, a rename ac
- [Brakes Let You Go Fast: Balancing Acceleration and Safety for AI Agents](https://dev.to/dailycontext/brakes-let-you-go-fast-balancing-acceleration-and-safety-for-ai-agents-49p9) (dev.to) - Written by John Feminella  We now inhabit a world where agents can execute opera
- [Code is abundant. Confidence is a formula.](https://dev.to/dailycontext/code-is-abundant-confidence-is-a-formula-gn6) (dev.to) - AI can make code creation abundant. The harder challenge is building confidence 
- [We checked 49 payment MCP servers. 37 can move money. Only 4 document a spending budget.](https://dev.to/aidakh_e8124113e2a1bf1fc9/we-checked-49-payment-mcp-servers-37-can-move-money-only-4-document-a-spending-budget-1bd5) (dev.to) - Disclosure: I work on Pink Agentic AI Payments at PinkWallet, which is one of th

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

- [Your MCP server's tool descriptions are the product: a 40-line Node script to dump and review them](https://dev.to/renev3408/your-mcp-servers-tool-descriptions-are-the-product-a-40-line-node-script-to-dump-and-review-them-4ki2) (dev.to) - Agents pick MCP tools by reading name, description and inputSchema from tools/li
- [A browser pool for agents that stop taking each other's tabs](https://dev.to/danmercede/a-browser-pool-for-agents-that-stop-taking-each-others-tabs-2e5b) (dev.to) - How to give cooperative agents persistent Chrome identities, exclusive leases, a
- [Shipping a Claude Code plugin with an eval suite: testing that the agent doesn't make things up](https://dev.to/vishalhabib99/shipping-a-claude-code-plugin-with-an-eval-suite-testing-that-the-agent-doesnt-make-things-up-26ck) (dev.to) - An agent calling your MCP server never sees your code. It sees tool names, descr
- [agentevals v0.10.0: Scores Come Back as OpenTelemetry Events](https://dev.to/webofmike/agentevals-v0100-scores-come-back-as-opentelemetry-events-ko3) (dev.to) - agentevals v0.10.0 sends scores back as gen_ai.evaluation.result OpenTelemetry e
- [stairway: from a chat idea to a running Claude Code experiment on my own server](https://dev.to/sirmmo/stairway-from-a-chat-idea-to-a-running-claude-code-experiment-on-my-own-server-2eoh) (dev.to) - Most of my side projects start the same way: I'm on my phone, talking an idea th

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
