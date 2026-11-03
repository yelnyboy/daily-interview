# 构建简单的数据分析 Agent（Notebook 实践）

**日期**: 2026-11-03 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

核心思路：以LLM为大脑，采用ReAct模式（推理→行动→观察循环）驱动数据分析流程。关键设计点：1）工具定义：封装代码执行器（Python REPL/沙箱）、数据加载（read_csv）、可视化（matplotlib）等工具，用JSON Schema描述参数供LLM调用；2）执行循环：LLM根据任务生成pandas代码→沙箱执行→将输出或报错作为观察结果回传→LLM修正或继续下一步；3）错误处理：执行异常需完整回传给模型自我修复，这是Agent可靠性的关键；4）安全：任意代码必须运行在隔离沙箱（如Docker、受限解释器），限制文件与网络访问；5）产物输出：表格、图表与自然语言结论。典型流程：用户提问→读取数据→head()/describe()探索→清洗与聚合→生成图表→总结洞察。常见追问：如何防止LLM幻觉出不存在的API？如何评估分析质量？上下文过长时如何只回传摘要而非全量输出？

## 核心考点

- ReAct循环
- 工具定义与JSON Schema
- 代码沙箱执行
- 错误反馈与自我修复
- 数据探索流程

## 常见追问

> 如何设计沙箱保证代码执行安全，以及LLM生成代码报错后如何实现自动重试与修复？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/simple_data_analysis_agent_notebook.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/simple_data_analysis_agent_notebook.ipynb)
