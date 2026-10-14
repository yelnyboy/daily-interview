# Spring Cloud 微服务架构

**日期**: 2026-10-14 | **类型**: Theory | **原始分类**: Spring | **路线图模块**: 04-Agent基础与架构原则 | **难度**: 中级 | **来源**: GitHub

## 解答

Spring Cloud 是一套微服务治理框架，主要解决分布式系统中的常见问题。其核心组件和机制如下：
1. 服务注册与发现：使用 Eureka 或 Nacos 作为注册中心，微服务启动时自动注册，消费方通过注册中心获取服务列表，实现动态路由。
2. 配置中心：通过 Spring Cloud Config 或 Nacos 提供集中式配置管理，支持配置的热更新，无需重启服务即可生效。
3. 熔断与限流：集成 Sentinel 或 Hystrix，在服务调用失败或响应过慢时进行熔断降级，防止雪崩效应，保障系统可用性。
4. API 网关：Spring Cloud Gateway 作为统一流量入口，负责路由转发、鉴权、限流和日志监控。
5. 分布式链路追踪：通过 Sleuth 结合 Zipkin 或 SkyWalking，记录请求在多个微服务间的调用链路，便于性能分析和故障定位。
常见追问点：在 Spring Cloud 中如何实现分布式事务？

## 核心考点

- 服务注册与发现
- 配置中心
- 熔断限流
- API网关
- 链路追踪

## 常见追问

> Spring Cloud 中如何解决微服务间的分布式事务问题？

**参考链接**: [https://github.com/doocs/advanced-java](https://github.com/doocs/advanced-java)
