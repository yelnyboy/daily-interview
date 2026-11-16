# 基于LangGraph的TTS诗歌生成Agent

**日期**: 2026-11-16 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

这是一个用LangGraph构建的文本转语音（TTS）诗歌生成Agent项目，考察对Agent工作流编排的理解。核心要点：1) LangGraph将Agent建模为状态图（StateGraph），节点是处理步骤（如LLM生成诗歌、TTS合成语音），边定义执行流向；2) 诗歌生成节点调用LLM（如GPT）根据用户主题生成诗歌文本；3) TTS节点调用语音合成API（如Edge-TTS、Azure TTS）将文本转为音频文件；4) 状态（State）在节点间传递，通常用TypedDict定义，包含诗歌文本、音频路径等字段；5) 可加入条件边实现循环或分支，如用户不满意可重新生成。典型流程：用户输入主题 → LLM生成节点 → TTS节点 → 输出音频。常见追问点：为什么选LangGraph而非LangChain Chain（图结构支持循环、条件分支，更适合多步Agent）；如何处理TTS API失败的容错与重试；如何流式输出中间结果；状态持久化与checkpoint机制。

## 核心考点

- LangGraph状态图
- 节点与边
- LLM生成节点
- TTS语音合成
- 状态传递与条件边

## 常见追问

> 如果要在生成诗歌后让用户试听并反馈修改，如何在LangGraph中设计循环和条件边？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/tts_poem_generator_agent_langgraph.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/tts_poem_generator_agent_langgraph.ipynb)
