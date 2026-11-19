# Browser Use：让 LLM Agent 操作浏览器

**日期**: 2026-11-19 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

Browser Use 是一个开源 Python 库，让 LLM Agent 能够像人一样操控真实浏览器完成任务。核心要点：1) 它将浏览器页面状态（DOM、可交互元素）序列化为 LLM 可读的文本表示，为每个可点击元素分配索引编号；2) Agent 通过 LLM 决策下一步动作（点击、输入、导航、滚动等），再由 Playwright 执行，形成感知-决策-执行的循环；3) 支持多标签页管理、元素高亮定位、页面截图与视觉模型结合；4) 内置记忆机制，可记录已访问页面和操作历史，避免重复探索；5) 支持与 LangChain、LangGraph 等框架集成，也可绑定自定义 LLM。常见追问点：与直接调用网页 API 相比的优势（无需 API、可处理动态渲染页面、通用性强）；如何处理验证码和登录态（Cookie 注入、人工介入）；元素定位失败的容错机制（重新提取 DOM、视觉定位兜底）。

## 核心考点

- 页面状态序列化
- 感知-决策-执行循环
- Playwright 底层执行
- 多标签页管理
- 与 Agent 框架集成

## 常见追问

> Browser Use 如何保证元素定位的准确性，遇到动态加载页面如何处理？

**参考链接**: [https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/15-browser-use](https://github.com/microsoft/ai-agents-for-beginners/tree/main/translations/zh-CN/15-browser-use)
