# 简单对话式Agent的设计与实现

**日期**: 2026-11-14 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 初级 | **来源**: GitHub

## 解答

简单对话式Agent是最基础的Agent形态，核心是'LLM + 对话循环'的模式，不涉及工具调用或复杂规划。要点如下：
1. 核心结构：由系统提示词（定义角色和行为）、对话历史（消息列表）和LLM调用三部分组成。
2. 对话循环：接收用户输入 → 将用户消息追加到历史 → 调用LLM生成回复 → 将助手回复追加到历史 → 返回给用户，循环往复。
3. 状态管理：对话历史就是Agent的短期记忆，通常包含role（system/user/assistant）和content两个字段，需要考虑上下文窗口限制，超限时需截断或摘要压缩。
4. 流式输出：生产中通常使用streaming方式逐token返回，提升用户体验。
5. 基本代码框架（Python伪代码）：
messages = [{'role': 'system', 'content': '你是一个有用的助手'}]
while True:
    user_input = input('User: ')
    if user_input == 'quit': break
    messages.append({'role': 'user', 'content': user_input})
    response = llm.chat(messages)
    messages.append({'role': 'assistant', 'content': response})
    print('Assistant:', response)

常见追问：如何处理上下文超长？如何加入工具调用使其升级为ReAct式Agent？多轮对话中如何保持一致性？

## 核心考点

- 消息列表结构
- 对话循环
- 系统提示词
- 上下文窗口管理
- 流式输出

## 常见追问

> 如果要在这个简单Agent上加入工具调用能力，需要修改哪些部分？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/simple_conversational_agent.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/simple_conversational_agent.ipynb)
