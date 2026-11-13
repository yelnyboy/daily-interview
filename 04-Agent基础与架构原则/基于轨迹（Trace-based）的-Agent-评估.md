# 基于轨迹（Trace-based）的 Agent 评估

**日期**: 2026-11-13 | **类型**: Theory | **原始分类**: Agent设计模式 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 高级 | **来源**: GitHub

## 解答

基于轨迹的评估是 Agent 领域区别于传统 LLM 评估的关键方法，核心思想是不只看最终答案，而是检查 Agent 执行的完整中间步骤（思考、工具调用、观察）是否正确。要点如下：
1. 动机：Agent 任务多步长、非确定性，仅用最终结果评估会漏掉「答案碰巧对但过程错误」的情况，也无法定位失败发生在哪一步。
2. 轨迹采集：通过回调或 tracing 机制（如 LangSmith、OpenTelemetry）记录每一步的 LLM 输入输出、工具名与参数、返回观察，形成树状或链式 trace。
3. 评估维度：包括步骤级正确性（该步是否选对了工具、参数是否合法）、轨迹级匹配（与专家参考轨迹的编辑距离/关键节点覆盖率）、效率（步数、token 消耗）与最终任务成功率。
4. 评判方法：常用 LLM-as-Judge 对每步打分，或用规则校验工具调用 schema；也可用「轨迹蒸馏」把好轨迹作为 few-shot 示例反哺 prompt。
5. 工程实践：把 trace 存入数据库做回归测试，Agent 迭代后重放同一批任务对比轨迹差异，实现持续评估。
常见追问：如何降低 LLM-as-Judge 的评估成本（抽样评估、只评关键步骤）；轨迹评估与结果评估权重如何分配；如何处理同一任务的多种合法轨迹（用状态等价性而非严格路径匹配）。

## 核心考点

- 轨迹采集与tracing
- 步骤级评估
- LLM-as-Judge
- 轨迹匹配
- 回归测试与持续评估

## 常见追问

> 当同一任务存在多条合法执行路径时，如何设计轨迹匹配的评估指标？

**参考链接**: [https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/trace_based_agent_evaluation.ipynb](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/trace_based_agent_evaluation.ipynb)
