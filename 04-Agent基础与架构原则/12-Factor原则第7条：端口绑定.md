# 12-Factor原则第7条：端口绑定

**日期**: 2026-11-04 | **类型**: Theory | **原始分类**: Agent基础 | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 初级 | **来源**: GitHub

## 解答

12-Factor第7条是'端口绑定'，核心要点：1) 应用应通过端口绑定对外提供服务，自包含地成为一个独立服务，不依赖外部Web容器（如Tomcat）注入运行环境。2) 应用自己监听端口并对外暴露HTTP服务，而不是由外部服务器把请求转发给应用进程。3) 在本地开发时，应用通过localhost的端口直接访问，与生产环境行为一致。4) 部署时，一个应用进程与一个端口绑定，通过反向代理或服务发现对外暴露，便于水平扩展。5) 对Agent/LLM应用的启示：Agent服务应打包为独立进程（如FastAPI/Flask监听端口），以HTTP API形式提供服务，这样便于容器化部署、K8s编排和弹性伸缩。6) 与环境配置的关系：端口通过环境变量（如PORT）注入，符合第3条配置分离原则。常见追问：端口绑定与传统的WAR部署到Tomcat有何区别；在Docker/K8s中如何体现端口绑定；多实例时端口冲突如何处理（每容器独立网络命名空间）。

## 核心考点

- 端口绑定概念
- 自包含服务
- 本地与生产一致性
- 容器化部署
- 水平扩展

## 常见追问

> 在Kubernetes中部署Agent服务时，端口绑定原则如何与Service/Ingress配合实现负载均衡？

**参考链接**: [https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-7-contact-humans-with-tools.md](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-7-contact-humans-with-tools.md)
