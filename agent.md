# AI Agent 开发知识库

> 最后更新: 2026-11-11
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

- [# The 0 / 5 / 20 incident learning curve: watching an agent get better without retraining](https://dev.to/mohith__gowda/-the-0-5-20-incident-learning-curve-watching-an-agent-get-better-without-retraining-1e7h) (dev.to) - "It learns over time" is the most common claim made about AI agents with memory,
- [Digital Garden RAG - post DEV](https://dev.to/arthur2122/digital-garden-rag-post-dev-5ekf) (dev.to) - Digital gardens from what I study: the first one, RAG or Grep? / Jardins digitai
- [What broke when I tested pgvector vs Postgres full-text search vs Hybrid RRF on 30 tricky RAG chunks (and how I fixed it for $0)](https://dev.to/mtalha5/what-broke-when-i-tested-pgvector-vs-postgres-full-text-search-vs-hybrid-rrf-on-30-tricky-rag-4f8l) (dev.to) - Over the last few weeks, while working on a FastAPI and PostgreSQL RAG pipeline,
- [My first month of hackathons: 4 local AI projects, 4 lessons](https://dev.to/devcarlat800/my-first-month-of-hackathons-4-local-ai-projects-4-lessons-2528) (dev.to) - October 2026 was my first month of hackathons. I wanted a few real projects on G
- [Three agents and one memory: a proposal pipeline for a small agency](https://dev.to/jtersoli/three-agents-and-one-memory-a-proposal-pipeline-for-a-small-agency-66j) (dev.to) - Josefina Tersoli, October 2026. The code is at github.com/JTersoli/bigpickle-bra

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
  - 考点: CAP与BASE理论, 分布式事务（2PC/TCC/Saga）, Raft/Paxos共识协议
  - 摘要: 分布式系统面试连环炮通常按知识链层层深入，核心考点如下。1）CAP理论：分布式系统在一致性、可用性、分区容错性中最多同时满足两个，网络分区不可避免，实际是在CP与AP间权衡。2）BASE理论：基本可用...

### 相关文章资源

- [What Fable 5.2's Speed Improvements Mean for Builders](https://dev.to/richard_smith_154156d471ef/what-fable-52s-speed-improvements-mean-for-builders-p08) (dev.to) - After reading through the benchmarks and user reports on Fable 5.2, one thing ke
- [Stitch Skills: How Google's Agent Skills Standard Turns MCP Servers into Reusable Workflow Primitives](https://dev.to/mech_app_ai/stitch-skills-how-googles-agent-skills-standard-turns-mcp-servers-into-reusable-workflow-2la6) (dev.to) - How the Agent Skills standard defines skill boundaries, plugin distribution via 
- [How to classify and route text with the Azure OpenAI Decisions API](https://dev.to/carlosjcastrog/how-to-classify-and-route-text-with-the-azure-openai-decisions-api-3kon) (dev.to) - Asking a language model to pick a category usually ends with code that parses it
- [AI Agents Need a Runtime, Not Another Framework](https://dev.to/jonlunsford/ai-agents-need-a-runtime-not-another-framework-569d) (dev.to) - We've gotten really good at building AI Agents. With so many frameworks, and hig
- [/Make_PPTX Skill for Agent](https://dev.to/maximer/makepptx-skill-for-agent-392a) (dev.to) - For at least two years now, I have made it a habit to stop creating PowerPoint p

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

- [FIELD INTEL REPORT-025](https://dev.to/liminaljermo/field-intel-report-025-1003) (dev.to) - Coverage window: 30 October – 6 November 2026 · Previous report: FIR-024 (30 Oct
- [How to Test Node.js Retrieval Schemas for Reliable Real-Estate Listing Discovery](https://dev.to/tatefletcher6754/how-to-test-nodejs-retrieval-schemas-for-reliable-real-estate-listing-discovery-2559) (dev.to) - Reliability is the first design constraint for semantic duplicate detection in a
- [Healthcare Retrieval Architecture: Source Deduplication for Grounded Appointment Answers](https://dev.to/siegfriedfletcher5869/healthcare-retrieval-architecture-source-deduplication-for-grounded-appointment-answers-4oe9) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [Is semantic chunking actually better than rule-based splitting for RAG retrieval?](https://dev.to/shenao_yu_e15c14815264a44/is-semantic-chunking-actually-better-than-rule-based-splitting-for-rag-retrieval-d42) (dev.to) - The claim that needs examining   A common framing in RAG tutorials goes like thi
- [How to Build Legal Contract Retrieval Fallbacks: A 3-Stage Architecture](https://dev.to/jedidiahrhodes8293/how-to-build-legal-contract-retrieval-fallbacks-a-3-stage-architecture-513i) (dev.to) - Short answer: for legal contract review, use a staged retrieval architecture wit

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

### 已积累题目 (27题)

- [初级] **12-Factor原则第7条：端口绑定**
  - 考点: 端口绑定概念, 自包含服务, 本地与生产一致性
  - 摘要: 12-Factor第7条是'端口绑定'，核心要点：1) 应用应通过端口绑定对外提供服务，自包含地成为一个独立服务，不依赖外部Web容器（如Tomcat）注入运行环境。2) 应用自己监听端口并对外暴露H...
- [中级] **Agent 12-Factor 第12条原则**
  - 考点: 进程隔离, 环境一致性, 无状态执行
  - 摘要: Agent 12-Factor 的第12条原则通常关注“管理任务”或“可观测性”。以管理任务为例，核心思想是将一次性管理任务作为独立进程运行。具体包括以下几点：
1. 进程隔离：数据迁移、状态清理或模...
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
- [高级] **基于 LangGraph 的汽车购买 Agent 设计**
  - 考点: LangGraph 状态图编排, 条件边与循环路由, TypedDict 状态管理
  - 摘要: 这是一个典型的 ReAct + 状态机式 Agent 应用，用 LangGraph 编排购车决策流程。核心设计要点：
1. 状态定义：用 TypedDict 定义 GraphState，包含用户预算、...
- [中级] **基于 LangGraph 的社交媒体发布 Agent（publora）**
  - 考点: LangGraph StateGraph 状态建模, 条件边与反思循环, 工具调用封装
  - 摘要: publora 是一个基于 LangGraph 构建的社交媒体发布 Agent，展示了将 Agent 用于内容创作与多平台发布的完整设计模式。

核心设计要点：
1. 状态图建模：LangGraph ...
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

- [Agent Experience (AX) in 2026: Designing for the Day 20 AI Agents Are Your Hardest-Working Users](https://dev.to/tamizuddin/agent-experience-ax-in-2026-designing-for-the-day-20-ai-agents-are-your-hardest-working-users-4c3b) (dev.to) - A deep-dive into Agent Experience (AX): the systems engineering discipline for k
- [The limit you configured is not the limit it applies](https://dev.to/cleiton_augusto_/the-limit-you-configured-is-not-the-limit-it-applies-53mp) (dev.to) - An agent that pays for things needs a limit: a maximum price per call, a payee y
- [Stop Trusting npm Scans: Run Untrusted Packages in an Isolated AWS Sandbox](https://dev.to/aws-builders/stop-trusting-npm-scans-run-untrusted-packages-in-an-isolated-aws-sandbox-cmm) (dev.to) - Static scanners read npm packages without running them, so they miss the postins
- [Top 5 AI Agent Patterns for Frontend Devs](https://dev.to/erikch/top-5-ai-agent-patterns-for-frontend-devs-5g5m) (dev.to) - When I code, I prompt, wait, and see what comes back. For a bigger feature I mig
- [Behind the scenes, two months later: How we ship Google Agent Skills like products](https://dev.to/googleai/behind-the-scenes-two-months-later-how-we-ship-google-agent-skills-like-products-b1l) (dev.to) - In my previous post, I took you behind the scenes of Google Agent Skills, coveri

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

- [J-Quants for agents: what it covers, and when you need more](https://dev.to/ikkun1222/j-quants-for-agents-what-it-covers-and-when-you-need-more-1bcb) (dev.to) - J-Quants is the official JPX route to Japanese prices and quarterly figures, and
- [Build a Python deal checker on an MCP server with plain JSON-RPC](https://dev.to/secretpass/build-a-python-deal-checker-on-an-mcp-server-with-plain-json-rpc-2le6) (dev.to) - Most MCP examples connect a server to Claude or Cursor and stop there. Under the
- [Build a Node.js CLI that answers Zucoin wallet questions with cited sources](https://dev.to/myzucoins/build-a-nodejs-cli-that-answers-zucoin-wallet-questions-with-cited-sources-2n5h) (dev.to) - When an assistant answers a wallet question, the most useful part of the answer 
- [AI Decompiler Workflows for Agents, and Where They Stall](https://dev.to/devirt/ai-decompiler-workflows-for-agents-and-where-they-stall-4ha2) (dev.to) - An AI decompiler is a language model wired into a decompiler or disassembler tha
- [Add a contact form to your site from Claude Code or Cursor](https://dev.to/harsimran_jeetsingh_83e2/add-a-contact-form-to-your-site-from-claude-code-or-cursor-5463) (dev.to) - Connect your AI coding assistant to Formkove over MCP and ask it to add a workin

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

- [LangGraph Practical Guide: When to Use It Over LangChain](https://dev.to/amrendra_n_mishra/langgraph-practical-guide-when-to-use-it-over-langchain-2nei) (dev.to) - Why Automate Content Creation   Creating content manually for 9 channels would t
- [Why Linear Agent Chains Break in Production Banking (And How We Built Deterministic State Graphs with LangGraph + Redis)](https://dev.to/chaman_shah_elesium/why-linear-agent-chains-break-in-production-banking-and-how-we-built-deterministic-state-graphs-5go4) (dev.to) - Author: Chaman Shah, Principal AI Systems Architect at Elesium  The "Prompt and 
- [Uneven Branches Make a LangGraph.js Join Node Run Twice. Super-Steps Explain Why](https://dev.to/gabrielanhaia/uneven-branches-make-a-langgraphjs-join-node-run-twice-super-steps-explain-why-4k3p) (dev.to) - One branch has one step, the other has two, both feed combine. LangGraph.js runs
- [The A2A CLI on Azure: One Client for Container Apps, Agent Framework and Localhost](https://dev.to/xbill/the-a2a-cli-on-azure-one-client-for-container-apps-agent-framework-and-localhost-4b6k) (dev.to) - A Rust A2A v1.0 agent and a Microsoft Agent Framework A2A v1.0 coordinator on Az

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

- [A rewrite deleted the guardrail: what the Grok wallet drain says about agent permissions](https://dev.to/cleiton_augusto_/a-rewrite-deleted-the-guardrail-what-the-grok-wallet-drain-says-about-agent-permissions-387c) (dev.to) - On May 4, 2026, about 3 billion DRB tokens left a wallet linked to the @grok acc
- [Prompt injection isn't a prompt problem. It's an authorization problem.](https://dev.to/cyclopt_dimitrisk/prompt-injection-isnt-a-prompt-problem-its-an-authorization-problem-59j6) (dev.to) - A lot of security reviews of AI features start and end in the same place: the sy
- [What unshare -n leaves behind: building a boundary for an AI recon agent](https://dev.to/gnomeman4201/what-unshare-n-leaves-behind-building-a-boundary-for-an-ai-recon-agent-75b) (dev.to) - Why the boundary has to hold   My AI agent's sandbox passed all 13 of its isolat

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
