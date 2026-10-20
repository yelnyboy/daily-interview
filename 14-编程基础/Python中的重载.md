# Python中的重载

**日期**: 2026-10-20 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

1. Python不支持传统意义上的函数重载（即同名不同参数类型/个数的多个函数），因为Python是动态类型语言，且后定义的函数会覆盖先定义的函数。
2. 默认参数与可变参数：通常使用默认参数 `arg=None` 或 `*args, **kwargs` 来模拟不同参数个数和类型的重载。
3. 类型检查与分发：可以使用 `isinstance` 进行类型判断，或使用 `functools.singledispatch` 装饰器实现基于第一个参数类型的单分派重载。
4. 第三方库：可以使用 `multipledispatch` 等第三方库实现更完整的基于多参数类型的重载。
常见追问：`functools.singledispatch` 的工作原理是什么？

## 核心考点

- 动态类型
- 默认参数
- *args/**kwargs
- singledispatch

## 常见追问

> 为什么Python原生不支持像Java那样的方法重载？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
