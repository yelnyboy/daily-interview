# Agent 的元认知（Metacognition）

**日期**: 2026-11-05 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 高级 | **来源**: GitHub

## 解答

元认知指 Agent 对自身认知过程的认知与调控能力，即「知道自己知道什么、不知道什么」，并据此调整行为。

核心要点：
1. 自我监控：Agent 能评估自身输出的置信度，识别不确定或可能出错的回答。
2. 自我反思：如 Reflexion 模式，Agent 在失败后生成反思文本，存入记忆用于下次改进。
3. 知识边界感知：Agent 应能识别问题超出自身能力或知识范围，主动求助或拒绝回答，而非幻觉式编造。
4. 任务规划调整：执行中发现计划不可行时，能重新规划（如 ReAct 中根据观察结果调整下一步行动）。
5. 自我评估与验证：对生成的答案进行自我批判、自我一致性检查（self-consistency）或调用验证工具。

实现方式：通常通过提示词引导 LLM 输出置信度、进行 Chain-of-Thought 自检；或引入独立的 Critic/Verifier 模块；或通过多轮反思循环（如 Self-Refine、Reflexion）实现。

常见追问：元认知与自我反思（Self-Reflection）的区别是什么？如何量化评估 Agent 的元认知能力？过度反思导致成本上升如何权衡？

## 核心考点

- 自我监控与置信度评估
- 知识边界感知
- Reflexion 反思机制
- 自我验证
- 动态重规划

## 常见追问

> 如何在工程上让 LLM Agent 可靠地表达自己的不确定性（如校准置信度）？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/09-metacognition](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/09-metacognition)
