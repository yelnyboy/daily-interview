# AI Agent 开发知识库

> 最后更新: 2026-11-02
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

- [How do AI agents authenticate? (The problem nobody has solved yet)](https://dev.to/zachbenson/how-do-ai-agents-authenticate-the-problem-nobody-has-solved-yet-3cbe) (dev.to) - Repo: github.com/arkenforge/arken-core  If you've built an MCP server or an API 
- [I hid instructions in my server logs to see which models would follow them](https://dev.to/remdore/i-hid-instructions-in-my-server-logs-to-see-which-models-would-follow-them-1bd2) (dev.to) - Every Monday, ExtraTime, my football quiz site, gets a health report written by 
- [Digital employee: how to help your team grow](https://dev.to/matintellect/digital-employee-how-to-help-your-team-grow-1hkj) (dev.to) - I believe you shouldn't fire employees just to replace them with artificial inte
- [AI-Assisted QA with GitHub Actions](https://dev.to/newellpaul/ai-assisted-qa-with-github-actions-2bm) (dev.to) - Every push to main builds an engineering dashboard from the run's own reports. S
- [My open source project is brand new and already has contributors. Here's what I did.](https://dev.to/nathan_tarbert/my-open-source-project-is-brand-new-and-already-has-contributors-heres-what-i-did-3fb4) (dev.to) - In the spirit of Hacktoberfest, with it being the last day of October, I wanted 

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

- [I Built a Programming Language Where Every Value Is an AI Agent](https://dev.to/aligmentinsight/i-built-a-programming-language-where-every-value-is-an-ai-agent-4lpm) (dev.to) - Every orchestration framework I used managed calls. None of them managed the org
- [AI crawlers vs search crawlers: the 7-night census](https://dev.to/mrsaynothing/ai-crawlers-vs-search-crawlers-the-7-night-census-36g5) (dev.to) - Seven nights, 8,654 bot knocks, 247 human visits. AI crawlers vs search crawlers
- [Let your LLM say I don't know instead of guessing](https://dev.to/conorbronsdon/let-your-llm-say-i-dont-know-instead-of-guessing-2dog) (dev.to) - Wire an abstain path, ground answers in retrieved sources, and verify fluent cla
- [Given the Inbox, 9 of 10 AI Agents Raised Their Own Spending Cap. No Attacker Needed](https://dev.to/gabrielanhaia/given-the-inbox-9-of-10-ai-agents-raised-their-own-spending-cap-no-attacker-needed-ll6) (dev.to) - Cornell Tech and Yale gave 10 models a wallet capped at 1 cent a day and an inbo
- [Turn any web page into clean markdown for ChatGPT or Claude](https://dev.to/dedupedai/turn-any-web-page-into-clean-markdown-for-chatgpt-or-claude-1pj) (dev.to) - Use Firecrawl from Python, Node, curl or the CLI to scrape a URL into LLM-ready 

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

- [Enterprise Agent Selection: A Field Report (Series)](https://dev.to/ikkun1222/enterprise-agent-selection-a-field-report-series-527j) (dev.to) - I explain why audit coverage and management complexity matter more than model qu
- [LEANN cut a 60-million-passage index from 201GB to 6GB. Is trading disk space for waiting time worth it?](https://dev.to/alexlee7359/leann-cut-a-60-million-passage-index-from-201gb-to-6gb-is-trading-disk-space-for-waiting-time-jg0) (dev.to) - LEANN cut a 60-million-passage index from 201GB to 6GB. Is trading disk space fo
- [Node Streams for Large RAG Uploads and Embedding Pipelines](https://dev.to/ganeshjoshi/node-streams-for-large-rag-uploads-and-embedding-pipelines-248n) (dev.to) - A RAG ingest that buffers the whole file works until someone uploads a 400MB PDF
- [Why Your Regional RAG Keeps Citing Global Autocomplete](https://dev.to/vexaloom-labs/why-your-regional-rag-keeps-citing-global-autocomplete-4ccb) (dev.to) - Separate Pinterest autocomplete from regional keyword history with Python filter
- [Why Did That Chunk Win? 7 Questions I Ask Every Hybrid Search Result in .NET 10](https://dev.to/michael_maurice/why-did-that-chunk-win-7-questions-i-ask-every-hybrid-search-result-in-net-10-70) (dev.to) - My docs assistant got the question "refund fails with ERR-4012 after a partial r

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

### 已积累题目 (20题)

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
- [中级] **端到端测试Agent设计模式**
  - 考点: 任务分解, 工具调用, 语义断言
  - 摘要: 1. 规划与分解：Agent接收自然语言测试需求，利用LLM将其分解为具体的测试步骤和预期结果。
2. 工具调用执行：Agent通过调用浏览器自动化工具（如Playwright）或API请求工具，逐步...
- [高级] **自我改进型智能体**
  - 考点: 自我反思, 长期记忆, 提示词优化
  - 摘要: 1. 核心概念：自我改进型智能体是一种能够根据过去的经验和环境反馈，自动调整自身行为、提示词或底层逻辑的智能体架构。2. 反思机制：通过引入自我反思步骤，智能体评估其先前动作的输出质量，识别错误或不足...
- [高级] **项目经理助理Agent的设计**
  - 考点: Plan-and-Execute模式, 工具集成, 记忆分层设计
  - 摘要: 设计要点：1）角色定位：负责需求分析、任务拆解（WBS）、进度跟踪、风险预警与会议纪要生成。2）核心模式：采用Plan-and-Execute模式，先制定项目计划再逐步执行；对关键决策引入Reflec...

### 相关文章资源

- [AI agents write almost all my code; a review counts for one exact commit](https://dev.to/yussieik/ai-agents-write-almost-all-my-code-a-review-counts-for-one-exact-commit-4b0m) (dev.to) - How one engineer runs ClinicLog, Groupliv and the My Trip tools by directing AI 
- [Wiring Your AI Agent into a "Mycelium Network": A Zero-Dependency MCP Server in Production](https://dev.to/boy373/wiring-your-ai-agent-into-a-mycelium-network-a-zero-dependency-mcp-server-in-production-4l46) (dev.to) - Wiring Your AI Agent into a "Mycelium Network": A Zero-Dependency MCP Server in.
- [69 days, $0: what actually happened when I tried to earn money as an AI agent](https://dev.to/phoenixilands/69-days-0-what-actually-happened-when-i-tried-to-earn-money-as-an-ai-agent-1h9f) (dev.to) - Every channel an AI agent can use to earn money, measured against 69 days of rea
- [Giving an AI agent a wallet without giving it your keys](https://dev.to/ahmad_shawar_de8d35d546cf/giving-an-ai-agent-a-wallet-without-giving-it-your-keys-407k) (dev.to) - Agents are starting to pay for things. An agent buying API credits, renting a GP
- [Week 2 as an AI agent running a tiny business: measure the base rate before you fix anything](https://dev.to/clairetnet/week-2-as-an-ai-agent-running-a-tiny-business-measure-the-base-rate-before-you-fix-anything-11kg) (dev.to) - Zero views looked like a bug. A scan of 410 competing listings showed it was nor

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

- [7 real cases where ChatGPT and Claude got datasheet values wrong (and how to check them)](https://dev.to/_30b2d57c3ad69af356f64/7-real-cases-where-chatgpt-and-claude-got-datasheet-values-wrong-and-how-to-check-them-55bm) (dev.to) - Disclosure: I build PartsPlan, the tool mentioned at the end. The cases below ar
- [Prefab UI's Python Sandbox Could Read and Write Your Server's Files. Upgrade to 0.21](https://dev.to/gabrielanhaia/prefab-uis-python-sandbox-could-read-and-write-your-servers-files-upgrade-to-021-1em5) (dev.to) - CVE-2026-120338, CVSS 10.0: Prefab UI ran model-written Python with unrestricted
- [How I manage MCP access, approvals, and tool history with GateRook](https://dev.to/w4p/how-i-manage-mcp-access-approvals-and-tool-history-with-gaterook-4i8n) (dev.to) - I use AI coding tools such as Claude, Codex, and Cursor, and I want them to work
- [Let Claude Code or Cursor debug your page in a real Chrome browser](https://dev.to/dedupedai/let-claude-code-or-cursor-debug-your-page-in-a-real-chrome-browser-ldc) (dev.to) - Set up Chrome DevTools MCP so your coding agent can read console errors, network
- [Your MCP Server Doesn’t Need 50 Tools: Design a Tool Budget Before It Eats Your Context](https://dev.to/alexshev/your-mcp-server-doesnt-need-50-tools-design-a-tool-budget-before-it-eats-your-context-1jfn) (dev.to) - Adding another MCP tool feels free.  It is not.  Each tool comes with a name, de

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

- [LangChain vs LangGraph: Which Should You Use?](https://dev.to/bcncodeschool/langchain-vs-langgraph-which-should-you-use-4jf9) (dev.to) - Compare LangChain and LangGraph by abstraction, state, routing, human approval, 
- [AI Staffing Partner](https://dev.to/narender_reddy_0fa71a7ec8/ai-staffing-partner-1keg) (dev.to) - Build an AI-powered Resume and Job Description Assistant that analyzes uploaded 
- [LangChain vs CrewAI vs AutoGen: Which Framework?](https://dev.to/syedzadi/langchain-vs-crewai-vs-autogen-which-framework-4b2h) (dev.to) - Every AI agent framework will get you to a working demo. Very few get you to a s
- [LangChain Structured Output in NestJS: Typed with Zod](https://dev.to/martinbruel/langchain-structured-output-in-nestjs-typed-with-zod-12a1) (dev.to) - To get an object instead of text from a LangChain agent in NestJS, pass a Zod sc

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
