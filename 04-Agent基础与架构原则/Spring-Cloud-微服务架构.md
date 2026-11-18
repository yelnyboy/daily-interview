# Spring Cloud 微服务架构

**日期**: 2026-11-18 | **类型**: Theory | **原始分类**: Spring | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

Spring Cloud是构建微服务架构的一站式框架体系，核心组件要点：

1. 服务注册与发现：Eureka/Nacos/Consul，服务启动时注册地址，消费方通过服务名获取实例列表实现负载均衡调用。
2. 配置中心：Spring Cloud Config/Nacos Config，集中管理各环境配置，支持动态刷新（@RefreshScope）。
3. 服务调用与负载均衡：OpenFeign声明式调用 + Ribbon/LoadBalancer客户端负载均衡。
4. 网关：Spring Cloud Gateway，统一入口，负责路由转发、鉴权、限流、灰度分流。
5. 熔断降级：Resilience4j/Sentinel，防止雪崩效应，提供熔断、限流、降级策略。
6. 链路追踪：Sleuth + Zipkin/SkyWalking，通过TraceId/SpanId串联跨服务调用链路。
7. 消息总线：Spring Cloud Bus配合MQ实现配置批量广播刷新。

典型流程：请求→Gateway鉴权路由→Feign调用（从Nacos拉取服务列表负载均衡）→下游服务熔断保护→链路日志上报。

常见追问：Eureka与Nacos区别（CP vs AP、Nacos支持配置中心）；Gateway与Zuul区别（WebFlux非阻塞 vs 阻塞）；Sentinel限流算法原理；分布式事务Seata的AT模式。

## 核心考点

- 服务注册与发现
- 配置中心
- 服务网关
- 熔断限流降级
- 链路追踪

## 常见追问

> Nacos与Eureka在CAP取舍和功能上有何区别，生产环境如何选型？

**参考链接**: [https://github.com/doocs/advanced-java](https://github.com/doocs/advanced-java)
