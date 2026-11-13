# LLM/Agent 岗位面经高频考点梳理

**日期**: 2026-11-13 | **类型**: Theory | **原始分类**: LLM核心 | **路线图模块**: 02-LLM核心与提示工程 | **难度**: 中级 | **来源**: GitHub

## 解答

该面经汇总了 LLM/Agent 方向校招与社招面试的高频问题，核心考点可归纳为以下几类：
1. Transformer 基础：自注意力机制的 Q/K/V 计算与复杂度分析、多头注意力的作用、LayerNorm 与残差连接的位置（Pre-LN vs Post-LN）、Encoder 与 Decoder 的区别。
2. 位置编码：正弦编码、可学习编码、RoPE 旋转位置编码的原理与外推性，以及 ALiBi 等相对位置方案。
3. 训练与解码：预训练/微调/RLHF 三阶段流程、交叉熵损失、temperature/top-p/top-k 采样、beam search 与贪心解码的差异。
4. 工程与推理优化：KV Cache 原理、FlashAttention、量化（INT8/INT4）、推理吞吐与延迟的权衡（batch、continuous batching）。
5. Agent 与 RAG 相关：ReAct 范式、Function Calling 的实现、向量检索与重排序、幻觉的成因与缓解手段。
面试建议：基础题要能手推注意力公式并分析复杂度；工程题结合项目经历说明踩坑与优化数据；Agent 题要能对比不同设计模式的适用场景。常见追问：为什么除以 sqrt(d_k)；RoPE 如何作用于 Q 和 K；KV Cache 为何能加速自回归解码。

## 核心考点

- 自注意力机制
- 位置编码（RoPE）
- KV Cache与推理优化
- RLHF训练流程
- Agent与RAG基础

## 常见追问

> 请手推 Self-Attention 的计算公式，并解释为什么要除以 sqrt(d_k)？

**参考链接**: [https://github.com/wolverinn/Waking-Up](https://github.com/wolverinn/Waking-Up)
