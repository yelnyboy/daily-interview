# HTTP1.0和HTTP1.1的区别

**日期**: 2026-10-22 | **类型**: Theory | **原始分类**: 计算机网络 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

1. 长连接：HTTP1.1默认支持持久连接，在一个TCP连接上可传送多个请求和响应，减少握手开销；HTTP1.0默认短连接，每次请求需新建连接。
2. 管道化：HTTP1.1允许客户端在未收到前一个响应时发送下一个请求，但服务器仍需按序响应；HTTP1.0不支持。
3. 缓存控制：HTTP1.1引入了ETag、If-Unmodified-Since等更丰富的缓存控制头，相比HTTP1.0的机制更加完善。
4. 断点续传：HTTP1.1通过Range请求头实现资源的部分请求和断点续传，有效节省带宽；HTTP1.0不支持。
5. Host头：HTTP1.1强制要求请求头包含Host字段，以支持虚拟主机技术；HTTP1.0无此要求。
常见追问点：HTTP1.1管道化存在什么队头阻塞问题？

## 核心考点

- 长连接
- 管道化
- 缓存控制
- 断点续传
- Host头

## 常见追问

> HTTP1.1管道化存在什么队头阻塞问题？HTTP/2是如何解决的？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
