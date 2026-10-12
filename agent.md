# AI Agent 开发知识库

> 最后更新: 2026-10-12
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

- [Meta and OpenAI present digital assistants that work even when you turn off the device](https://dev.to/hacksgr/meta-and-openai-present-digital-assistants-that-work-even-when-you-turn-off-the-device-54ia) (dev.to) - Meta and OpenAI introduced persistent autonomous AI agents, Muse and ChatGPT Dot
- [Prompts mal usados y cómo corregir prompts de IA](https://dev.to/henryramireztech/prompts-mal-usados-y-como-corregir-prompts-de-ia-3oe1) (dev.to) - Los prompts mal usados y la falta de criterio técnico para corregir prompts de I
- [README Clew 2: Built with AdaL. Labeled by Jev. Judged by Code. Explained by Haiku.](https://dev.to/earlgreyhot1701d/readme-clew-2-built-with-adal-labeled-by-jev-judged-by-code-explained-by-haiku-196e) (dev.to) - Jev labels the line. Code makes the call.   TL;DR: README Clew 2 checks whether 
- [How Do We Extract the “Why” from a PR into a CHANGELOG with Jev? 🤔](https://dev.to/nyaomaru/how-do-we-extract-the-why-from-a-pr-into-a-changelog-with-jev-52pk) (dev.to) - Hoi hoi! 👋  I'm @nyaomaru, a frontend engineer currently building an AI-assisted
- [I built a self-hosted AI agent for GitLab. It has reviewed 1,000+ merge requests.](https://dev.to/vrajpal-jhala/i-built-a-self-hosted-ai-agent-for-gitlab-it-has-reviewed-1000-merge-requests-2g7b) (dev.to) - Assign a GitLab issue to a bot, and a few minutes later there's a draft merge re

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

- [The terminal is the most honest place to test an agent](https://dev.to/usehive/the-terminal-is-the-most-honest-place-to-test-an-agent-4ohk) (dev.to) - The most honest place to test an agent is the command line. There is no dashboar
- [Bridging Environmental Compliance and LLM Reasoning: The Math Behind Air Emission Protocols](https://dev.to/renato_marinho/bridging-environmental-compliance-and-llm-reasoning-the-math-behind-air-emission-protocols-1edm) (dev.to) - An analysis of how specialized MCP connectors transition AI agents from mere tex
- [A Burning Bridges AI Prompt, Line by Line: What Each Sentence Is Preventing](https://dev.to/jim_l_efc70c3a738e9f4baa7/a-burning-bridges-ai-prompt-line-by-line-what-each-sentence-is-preventing-5hf7) (dev.to) - Most prompts for a party clip fail the same way: the face drifts by second four 
- [Banked resets changed the meaning of "waiting" — what I learned logging Codex limits for five months](https://dev.to/jimmy_ai/banked-resets-changed-the-meaning-of-waiting-what-i-learned-logging-codex-limits-for-five-months-5hc8) (dev.to) - Part 3 in my notes on reading public Codex reset signals. This one is about how 
- [LLM Capability Gaps, OpenAI Revenue Shocks, and AI Decompilation](https://dev.to/trillioniar_s_14a3c313e14/llm-capability-gaps-openai-revenue-shocks-and-ai-decompilation-2ib3) (dev.to) - Exploring the widening gap in LLM understanding and the latest shocks from OpenA

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

- [Developer Changelog Retrieval Architecture with Node.js: 4 Schema Design Decisions](https://dev.to/dawnli2026/developer-changelog-retrieval-architecture-with-nodejs-4-schema-design-decisions-3284) (dev.to) - Short answer: use a staged retrieval design with explicit collections, bounded q
- [Node.js 3-Stage Retrieval Architecture for Restaurant Menu Assistant Delete Semantics](https://dev.to/caderaven6851/nodejs-3-stage-retrieval-architecture-for-restaurant-menu-assistant-delete-semantics-19na) (dev.to) - Short answer: use a staged retrieval design with explicit collections, bounded q
- [Why I Chose a Node.js 3-Stage Plan for Healthcare Appointment Retrieval](https://dev.to/sladebarrett9642/why-i-chose-a-nodejs-3-stage-plan-for-healthcare-appointment-retrieval-4eb9) (dev.to) - Healthcare appointment assistants have a nasty retrieval constraint: the same po
- [Implementing Node.js Retrieval for Internal Engineering Docs: Safe Delete Semantics](https://dev.to/marcorossi4891/implementing-nodejs-retrieval-for-internal-engineering-docs-safe-delete-semantics-5fci) (dev.to) - Short answer: for retrieval architecture over internal engineering documentation
- [The Atomic Answer Rule: Engineering Content for RAG Chunking and AI Search](https://dev.to/tarikmostafa/the-atomic-answer-rule-engineering-content-for-rag-chunking-and-ai-search-203e) (dev.to) - The Atomic Answer Rule states that every H2 section of a document must answer it

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

### 已积累题目 (1题)

- [中级] **Agent上下文工程**
  - 考点: 上下文窗口管理, 动态上下文组装, 信息压缩与摘要
  - 摘要: 上下文工程是指在LLM Agent中，系统性地管理和组织输入给大模型的上下文信息，以最大化模型推理性能和任务完成率。其核心在于如何在有限的上下文窗口内，提供最相关、最有效的信息。
1. 窗口管理：合理...

### 相关文章资源

- [Ten more things that go wrong when you build with a team of AI agents (part 2)](https://dev.to/theducttapeio/ten-more-things-that-go-wrong-when-you-build-with-a-team-of-ai-agents-part-2-i5l) (dev.to) - Part 1 covered the first ten: symptom fixes, hidden sharing, lost messages, "don
- [When you paste an error into an AI agent, you're handing it your conclusion](https://dev.to/jeff_pdc/when-you-paste-an-error-into-an-ai-agent-youre-handing-it-your-conclusion-dc0) (dev.to) - Pasting only the error line into an AI coding agent means it fixes the symptom y
- [Your Agent Paid. That Does Not Mean It Should Have.](https://dev.to/dailycontext/your-agent-paid-that-does-not-mean-it-should-have-2dnd) (dev.to) - An AI agent is writing a report and needs one data point. The API answers: this 
- [Banks Are Renting Their Agents. These Two Built One.](https://dev.to/dailycontext/banks-are-renting-their-agents-these-two-built-one-j96) (dev.to) - Most banks aren't building their own agents. They're renting them.  Bank Directo
- [Does your agent have ID?](https://dev.to/dailycontext/does-your-agent-have-id-58ok) (dev.to) - Last month, an AI agent in Denmark booked a coffee tasting and paid for it. Dans

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

- [Codex Claude Bridge: let Codex coordinate Claude Code](https://dev.to/lordfine/codex-claude-bridge-let-codex-coordinate-claude-code-10nh) (dev.to) - Codex Claude Bridge lets Codex delegate coding to Claude Code, receive results, 
- [Riskified's Agent Identity Risk Intelligence Answers the Wrong Question First](https://dev.to/scriptmasterlabs01/riskifieds-agent-identity-risk-intelligence-answers-the-wrong-question-first-23eb) (dev.to) - On October 8, 2026, Riskified (NYSE: RSKD) launched Agent Identity Risk Intellig
- [Put a permission gate between your agent and its tools](https://dev.to/seaneboneslang/put-a-permission-gate-between-your-agent-and-its-tools-p9a) (dev.to) - An agent can understand a task and still attempt an action you did not authorize
- [From a URL to Markdown: a first collection and MCP setup with DeepSFetch](https://dev.to/rafael_souza_2f0438f4d82e/from-a-url-to-markdown-a-first-collection-and-mcp-setup-with-deepsfetch-4jdn) (dev.to) - I'm building DeepSFetch, a hosted service for collecting web content and connect
- [I Built MegasMoves: An Open-Source MCP Platform for Cross-Device Automation](https://dev.to/abhinavmusrif/i-built-megasmoves-an-open-source-mcp-platform-for-cross-device-automation-38ig) (dev.to) - Introducing MegasMoves   I'm Abhinav Musrif, a 22-year-old software developer an

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

- [What Are LLMs, and How Do You Build Stuff With Them?](https://dev.to/0xadityaa/what-are-llms-and-how-to-build-stuff-using-it-4l68) (dev.to) - An LLM just predicts the next token. Everything useful is the scaffolding around
- [Benchmarking AI vs. Human Interviewers: Can LangGraph Outperform Staff Engineers?](https://dev.to/apparao_aremanda_1f792aeb/benchmarking-ai-vs-human-interviewers-can-langgraph-outperform-staff-engineers-36kn) (dev.to) - Benchmarking AI vs. Human Interviewers: Kovi Evaluation Accuracy Report   Engine
- [Give your AI agent a stock photo tool in 5 lines](https://dev.to/marouane_tijani_3a7fc19a7/give-your-ai-agent-a-stock-photo-tool-in-5-lines-1gmh) (dev.to) - Real, free-to-use photos with their licence and credit line, for LangChain, the 
- [LangGraph vs LangChain: What Is the Difference?](https://dev.to/techsimplus_learnings/langgraph-vs-langchain-what-is-the-difference-4pbf) (dev.to) - Short answer: LangChain gives you high-level building blocks and a ready-made ag
- [Project Mariner runs ten tasks at once on cloud VMs. Fan out your own agents with LangChain](https://dev.to/burrowbox/project-mariner-runs-ten-tasks-at-once-on-cloud-vms-fan-out-your-own-agents-with-langchain-16n2) (dev.to) - Google moved its browsing agent to virtual machines in the cloud so it can run t

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
