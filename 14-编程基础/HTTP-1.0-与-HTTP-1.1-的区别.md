# HTTP 1.0 与 HTTP 1.1 的区别

**日期**: 2026-11-03 | **类型**: Theory | **原始分类**: 计算机网络 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

主要区别：1）连接方式：HTTP 1.0默认短连接，每个请求都新建TCP连接（三次握手开销大）；1.1默认持久连接，同一TCP连接可复用多个请求/响应。2）管道化：1.1支持pipelining，客户端可连续发送多个请求无需等待响应，但响应必须按序返回，存在队头阻塞。3）Host头：1.1强制要求Host字段，支持一个IP托管多个虚拟域名（虚拟主机）。4）缓存控制：1.1引入更完善的缓存机制，如Cache-Control、ETag/If-None-Match、If-Modified-Since等条件请求。5）带宽优化：1.1支持Range断点续传（206 Partial Content）和chunked分块传输编码。6）方法与状态码：1.1新增OPTIONS、PUT、DELETE、CONNECT等方法，状态码更丰富。常见追问：队头阻塞如何解决（HTTP/2多路复用）？keep-alive的超时机制？HTTPS在两者之上如何工作？

## 核心考点

- 持久连接keep-alive
- 管道化与队头阻塞
- Host头与虚拟主机
- 缓存控制Cache-Control
- Range断点续传与分块传输

## 常见追问

> HTTP 1.1的管道化为什么仍存在队头阻塞？HTTP/2是如何解决的？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
