# AI Agent 开发知识库

> 最后更新: 2026-11-13
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

- [¿Por qué osFoundry obliga a Claude Code a indicar el commit cuando pide volver a ejecutar un check de GitNest?](https://dev.to/bbt-es/por-que-osfoundry-obliga-a-claude-code-a-indicar-el-commit-cuando-pide-volver-a-ejecutar-un-check-1jf4) (dev.to) - Esta es la herramienta que llama Claude Code cuando quiere que un check fallido 
- [Perché osFoundry obbliga Claude Code a indicare il commit quando chiede di rilanciare un check GitNest?](https://dev.to/bbt-it/perche-osfoundry-obbliga-claude-code-a-indicare-il-commit-quando-chiede-di-rilanciare-un-check-2jk4) (dev.to) - Questo è il tool che Claude Code chiama quando vuole rieseguire un check GitNest
- [Warum verlangt osFoundry von Claude Code den Commit, wenn es einen GitNest-Check neu starten will?](https://dev.to/bbt-de/warum-verlangt-osfoundry-von-claude-code-den-commit-wenn-es-einen-gitnest-check-neu-starten-will-5ee6) (dev.to) - Das ist das Tool, das Claude Code aufruft, wenn ein fehlgeschlagener GitNest-Che
- [I Wrote a Release Workflow So My Fix Would Ship. It Has Never Run.](https://dev.to/spranab/i-wrote-a-release-workflow-so-my-fix-would-ship-it-has-never-run-48mn) (dev.to) - In August I fixed a TrueNAS bug, tagged v1.0.1, and added a GitHub Actions workf
- [[Boost]](https://dev.to/anthonymax/-oi5) (dev.to) - Bifrost vs LiteLLM Rust: Do the 7x Benchmark Claims Hold Up?                    

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

### 已积累题目 (2题)

- [中级] **LLM/Agent 岗位面经高频考点梳理**
  - 考点: 自注意力机制, 位置编码（RoPE）, KV Cache与推理优化
  - 摘要: 该面经汇总了 LLM/Agent 方向校招与社招面试的高频问题，核心考点可归纳为以下几类：
1. Transformer 基础：自注意力机制的 Q/K/V 计算与复杂度分析、多头注意力的作用、Laye...
- [高级] **分布式系统面试连环炮**
  - 考点: CAP与BASE理论, 分布式事务（2PC/TCC/Saga）, Raft/Paxos共识协议
  - 摘要: 分布式系统面试连环炮通常按知识链层层深入，核心考点如下。1）CAP理论：分布式系统在一致性、可用性、分区容错性中最多同时满足两个，网络分区不可避免，实际是在CP与AP间权衡。2）BASE理论：基本可用...

### 相关文章资源

- [The 2B model scored 10%. 93% of its answers were right](https://dev.to/ikkun1222/the-2b-model-scored-10-93-of-its-answers-were-right-2l2p) (dev.to) - On 250-row Japanese classification sets, a local 2B model scored 10.8% overall b
- [Why one message after a break eats your Claude Code usage limit](https://dev.to/dinesh_rajendran_46fc29b4/the-hidden-cost-of-a-cold-session-why-your-claude-code-bill-spikes-after-lunch-4n8c) (dev.to) - When Claude Code's prompt cache expires, the first message back costs 12–80× a w
- [Reverse Engineering GPT-6 Cyber](https://dev.to/om_shree_0709/reverse-engineering-gpt-6-cyber-54gj) (dev.to) - OpenAI Just Shipped GPT-6 Cyber. Here's How It Actually Works, Reverse-Engineere
- [What Presidio misses for Canadian PII, and what I did about it](https://dev.to/arthur_jin_2aae6a72b94c25/what-presidio-misses-for-canadian-pii-and-what-i-did-about-it-2c2) (dev.to) - I'm Arthur, a systems engineer at Geek+ in Toronto, where I work on warehouse au
- [hinglish isn't free: measuring what three models pay to answer in romanized hindi](https://dev.to/sansk_ya/hinglish-isnt-free-measuring-what-three-models-pay-to-answer-in-romanized-hindi-342o) (dev.to) - hinglish - the romanized hindi-english code-mix typed across india every day - i

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

- [Legal Contract Workspace Search Explained: Controlled Evidence Fallbacks in Go](https://dev.to/darkveilcorvyn26/legal-contract-workspace-search-explained-controlled-evidence-fallbacks-in-go-7p1) (dev.to) - Short answer: use staged retrieval with explicit collections, bounded queries, a
- [Python Caption Retrieval for E-Commerce PDFs (Chunking Around Image Freshness)](https://dev.to/solomonfletcher5872/python-caption-retrieval-for-e-commerce-pdfs-chunking-around-image-freshness-4ojc) (dev.to) - TL;DR: For image caption search over a changing folder of e-commerce PDFs, index
- [Implementing Retrieval Architecture in Developer Changelog Tracker: Canonical Source Control](https://dev.to/jethrorhodes8268/implementing-retrieval-architecture-in-developer-changelog-tracker-canonical-source-control-4g2d) (dev.to) - Short answer: use a staged retrieval design with an explicit collection, bounded
- [Retrieval Architecture for Product Search: Freshness Windows That Hold Up](https://dev.to/jasperflint6947/retrieval-architecture-for-product-search-freshness-windows-that-hold-up-1jf2) (dev.to) - For e-commerce product search, use a two-speed retrieval architecture: a small, 
- [E-commerce Product Search Retrieval Architecture: Audit Logs for Replayable Decisions](https://dev.to/tony_chen_2026/e-commerce-product-search-retrieval-architecture-audit-logs-for-replayable-decisions-124p) (dev.to) - Short answer: for e-commerce product search, keep an append-only audit stream be

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

### 已积累题目 (29题)

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
- [高级] **基于轨迹（Trace-based）的 Agent 评估**
  - 考点: 轨迹采集与tracing, 步骤级评估, LLM-as-Judge
  - 摘要: 基于轨迹的评估是 Agent 领域区别于传统 LLM 评估的关键方法，核心思想是不只看最终答案，而是检查 Agent 执行的完整中间步骤（思考、工具调用、观察）是否正确。要点如下：
1. 动机：Age...
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

- [How to Stop Your PC Sleeping During Long AI Agent Runs](https://dev.to/codexam/how-to-stop-your-pc-sleeping-during-long-ai-agent-runs-23jc) (dev.to) - By Subham Maity · November 13, 2026  Download from:...
- [A VS Code extension to turn ANY free chatbot website into an AI agent (kind of)](https://dev.to/effessdev/a-vs-code-extension-to-turn-any-free-chatbot-website-into-an-ai-agent-kind-of-1jfb) (dev.to) - So, why should I bring this up again?  Because Qoder (Alibaba’s AI IDE) free pro
- [How to stop a runaway AI agent loop before it runs up your OpenAI or Anthropic bill](https://dev.to/akhil_5d07/how-to-stop-a-runaway-ai-agent-loop-before-it-runs-up-your-openai-or-anthropic-bill-58oi) (dev.to) - TL;DR: A runaway agent loop shows up in your API traffic before it shows up on y
- [MCP Is Dead Simple. And That's Exactly the Problem](https://dev.to/sylwia-lask/mcp-is-dead-simple-and-thats-exactly-the-problem-5811) (dev.to) - What exactly is MCP? Is it some mysterious technology that requires secret knowl
- [Very Well Written](https://dev.to/therealmrmumba/very-well-written-2k6k) (dev.to) - How to Build an AI Agent That Fixes Bugs Reliably: Practice in Sharkly          

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

- [¿Por qué osFoundry separa el progreso de Claude Code en una nota de sesión y un estado?](https://dev.to/bbt-es/por-que-osfoundry-separa-el-progreso-de-claude-code-en-una-nota-de-sesion-y-un-estado-14df) (dev.to) - Estas son las dos herramientas de escritura que usa un agente de programación pa
- [Kenapa osFoundry memisahkan progres Claude Code menjadi catatan sesi dan status?](https://dev.to/bbt-id/kenapa-osfoundry-memisahkan-progres-claude-code-menjadi-catatan-sesi-dan-status-202a) (dev.to) - Berikut dua tool tulis yang dipakai coding agent untuk melaporkan progres ke osF
- [Why We Built an MCP Server for AI Founders’ Go to Market](https://dev.to/tedcarstensen/why-we-built-an-mcp-server-for-ai-founders-go-to-market-4hge) (dev.to) - Launching a technical startup in the age of AI is challenging. So we built a ful
- [I Pointed 3 Static Scanners at an MCP Server That Fails 8 Auth Tests. They Found 0, Including Mine](https://dev.to/kielltampubolon/i-pointed-3-static-scanners-at-an-mcp-server-that-fails-8-auth-tests-they-found-0-including-mine-2fha) (dev.to) - mcpscan, Semgrep (200 rules) and Bandit gave a broken MCP server and its fixed t
- [J-Quants for agents: what it covers, and when you need more](https://dev.to/ikkun1222/j-quants-for-agents-what-it-covers-and-when-you-need-more-1bcb) (dev.to) - J-Quants is the official JPX route to Japanese prices and quarterly figures, and

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

### 相关文章资源

- [Temporal & AI: Agent Memory & Execution State](https://dev.to/temporalio/temporal-ai-agent-memory-execution-state-a7k) (dev.to) - Memory is what the agent knows: the context the model sees right now, plus anyth

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

- [Give your LangChain agent a data tool that says "I can't verify that" instead of guessing](https://dev.to/factqlai/give-your-langchain-agent-a-data-tool-that-says-i-cant-verify-that-instead-of-guessing-1io9) (dev.to) - Give an agent a database tool and ask it about last quarter's revenue. Most of t
- [Self-Host LangGraph Agents with Aegra on Control Plane: A Private Agent Server](https://dev.to/noahcontrolplane/self-host-langgraph-agents-with-aegra-on-control-plane-a-private-agent-server-2ngi) (dev.to) - To self-host LangGraph agents on Control Plane, create a dictionary secret with 
- [LangGraph Practical Guide: When to Use It Over LangChain](https://dev.to/amrendra_n_mishra/langgraph-practical-guide-when-to-use-it-over-langchain-2nei) (dev.to) - Why Automate Content Creation   Creating content manually for 9 channels would t

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

- [Our ChatGPT/Codex Kalshi starter would have bought the same contract 38 times in under 13 minutes](https://dev.to/botcookery/our-chatgptcodex-kalshi-starter-would-have-bought-the-same-contract-38-times-in-under-13-minutes-9c2) (dev.to) - Oct 25, 2026 rebuild of the BotCookery ChatGPT/Codex Kalshi demo starter: a re-b
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
