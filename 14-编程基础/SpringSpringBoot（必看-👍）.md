# Spring/SpringBoot（必看 👍）

**日期**: 2026-10-31 | **类型**: Theory | **原始分类**: Spring | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

Spring/SpringBoot核心知识点如下：

1. IoC（控制反转）：通过容器管理对象生命周期和依赖关系，降低耦合度。核心接口为BeanFactory，ApplicationContext是其扩展，提供更多企业级功能。
2. AOP（面向切面编程）：通过动态代理实现横切关注点分离，常见应用包括日志、事务、权限控制。底层基于JDK动态代理（接口）或CGLIB字节码增强（类）。
3. Bean生命周期：实例化→属性注入→初始化（BeanPostProcessor前后置处理）→使用→销毁，理解各阶段回调钩子是面试重点。
4. 自动配置（SpringBoot）：基于@Conditional条件注解和spring.factories机制，根据类路径中的依赖自动装配Bean，约定优于配置。
5. 事务管理：通过@Transactional注解声明式管理事务，传播行为（REQUIRED、REQUIRES_NEW等）和隔离级别是核心考点。注意自调用导致的代理失效问题。
6. 启动流程：SpringApplication.run()启动，核心步骤包括创建应用上下文、刷新容器、执行CommandLineRunner。

## 核心考点

- IoC容器与依赖注入
- AOP动态代理机制
- Bean生命周期
- SpringBoot自动配置原理
- 声明式事务管理

## 常见追问

> Spring中同一个事务方法内部调用另一个事务方法时，事务传播行为为何会失效？如何解决？

**参考链接**: [https://github.com/Snailclimb/JavaGuide](https://github.com/Snailclimb/JavaGuide)
