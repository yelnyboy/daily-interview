# 销售通话分析Agent的设计

**日期**: 2026-11-07 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

销售通话分析Agent是一个典型的领域垂直型分析类Agent，设计要点如下：1) 整体架构：采用'流水线+工具调用'模式，包括音频转写（ASR工具）、说话人分离、结构化分析、报告生成四个阶段。2) 输入处理：接收通话录音或转写文本，若是音频先调用Whisper等转写工具，再进行说话人分离区分销售与客户。3) 分析维度：提取关键信息如客户意向度评分、异议点、成交信号、竞品提及、合规风险词（如承诺收益）、通话时长与轮次统计。4) 结构化输出：用LLM结合JSON Schema输出结构化结果，便于入库和后续统计，需做输出校验与重试。5) 工具设计：可拆分为transcribe_audio、diarize、analyze_sentiment、extract_entities等工具，Agent负责任务编排。6) 记忆与上下文：长通话需分块处理（map-reduce模式），逐段摘要再汇总，避免超出上下文窗口。7) 评估：用人工标注的通话样本对比Agent分析结果，衡量准确率与一致性。常见追问：如何处理超长音频、如何保证评分一致性、如何做幻觉防护、是否需要人工复核环节。

## 核心考点

- 流水线式任务编排
- 工具调用设计
- 长文本分块处理
- 结构化输出与校验
- 评估与幻觉防护

## 常见追问

> 如果通话录音长达2小时超出上下文窗口，你会如何设计处理流程？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/sales_call_analyzer_agent.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/sales_call_analyzer_agent.ipynb)
