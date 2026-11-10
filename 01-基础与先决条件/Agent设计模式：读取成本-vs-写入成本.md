# Agent设计模式：读取成本 vs 写入成本

**日期**: 2026-11-10 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 01-基础与先决条件 | **难度**: 中级 | **来源**: GitHub

## 解答

在Agent系统中，read（读取/观察）与write（写入/执行副作用）的成本是不对称的，这是设计Agent行为策略的核心考量。1）读取操作（如查询知识库、调用只读API、观察环境状态）通常是安全、幂等、可重试的，失败代价低，因此Agent可以激进地多读、反复读。2）写入操作（如发送邮件、下单、修改数据库、执行shell命令）具有副作用，往往不可逆或难以回滚，一旦出错代价高昂。3）因此设计原则是：写前多读——在执行写操作前充分收集信息、验证前提条件，类似'先看后动'。4）工程上常对写操作增加确认机制、人工审批（human-in-the-loop）、dry-run预演、事务/补偿机制来降低风险。5）在成本敏感场景（如LLM token消耗），也要权衡读取上下文的成本：读太多浪费token，读太少信息不足导致写操作出错，需要平衡。常见追问：如何设计写操作的回滚与补偿？如何用工具描述让LLM区分只读与有副作用的工具？

## 核心考点

- 读写成本不对称性
- 写前多读原则
- 副作用与幂等性
- human-in-the-loop审批
- 补偿与回滚机制

## 常见追问

> 如果写操作失败且无法回滚，你会如何设计补偿策略来降低损失？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/read_vs_write_cost.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/read_vs_write_cost.ipynb)
