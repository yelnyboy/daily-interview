# HTTP1.0和HTTP1.1的区别

**日期**: 2026-11-01 | **类型**: Theory | **原始分类**: 计算机网络 | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

1. 长连接：HTTP1.0默认使用短连接，每次请求都要建立新的TCP连接；HTTP1.1默认长连接，多个请求可复用同一个TCP连接，减少了握手开销。
2. 管道化：HTTP1.1支持管道化，允许客户端在未收到前一个响应时发送下一个请求，但服务器仍需按序响应。
3. 缓存控制：HTTP1.1引入了更多的缓存控制策略，如Entity tag、If-None-Match等，缓存粒度更细。
4. 带宽优化：HTTP1.1支持断点续传，通过Range头实现部分资源传输，节约带宽。
5. Host头：HTTP1.1强制要求包含Host头，从而支持虚拟主机技术，而HTTP1.0没有此要求。
常见追问点：HTTP1.1的队头阻塞问题是什么？如何解决？

## 核心考点

- 长连接
- 管道化
- 缓存控制
- Host头
- 断点续传

## 常见追问

> HTTP1.1的队头阻塞问题是什么？HTTP2.0是如何解决的？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
