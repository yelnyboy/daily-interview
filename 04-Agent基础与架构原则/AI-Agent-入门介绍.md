# AI Agent 入门介绍

**日期**: 2026-11-21 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 初级 | **来源**: GitHub

## 解答

AI Agent（智能体）是能够感知环境、自主决策并采取行动以达成目标的系统。核心要点如下：

1. 定义：Agent = LLM（大脑）+ 记忆 + 工具调用 + 规划能力，能自主循环执行"思考→行动→观察"的过程。
2. 与普通LLM对话的区别：Chatbot是单轮问答，Agent具备自主性、目标导向和持续迭代能力，能多步执行任务。
3. 核心循环（Agent Loop）：接收任务→LLM推理→决定调用工具→执行工具→观察结果→继续推理，直到任务完成。
4. 四大核心组件：规划（任务分解、反思）、记忆（短期上下文+长期存储）、工具使用（API、搜索、代码执行）、行动执行。
5. 典型应用：客服自动化、代码助手、数据分析、深度研究（Deep Research）等。
6. 关键挑战：幻觉、错误累积、循环失控、成本控制、安全性。

常见追问点：Agent与Workflow（工作流）的区别——Workflow是开发者预定义的固定流程，Agent是LLM动态决定执行路径；ReAct范式（Reasoning + Acting）是什么；什么时候该用Agent什么时候不该用（任务简单、容错低时用固定流程更佳）。

## 核心考点

- Agent定义与核心循环
- LLM+工具+记忆+规划
- Agent与Chatbot区别
- Agent与Workflow区别
- ReAct范式

## 常见追问

> 什么场景下不应该使用Agent，而应该用固定的工作流？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/01-intro-to-ai-agents](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/01-intro-to-ai-agents)
