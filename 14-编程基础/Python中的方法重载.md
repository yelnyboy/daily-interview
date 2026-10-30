# Python中的方法重载

**日期**: 2026-10-30 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python作为动态类型语言，原生不支持传统面向对象语言（如Java/C++）中的方法重载（即同名不同参）。在Python中，后定义的同名函数会直接覆盖先定义的。实现类似重载效果的方法有以下几种：1. 使用默认参数和关键字参数：通过`def func(a, b=None)`或`*args, **kwargs`来适配不同的调用方式。2. 使用`functools.singledispatch`：基于第一个参数的类型进行分发，将不同类型的处理逻辑注册到同一个函数名下，实现单分派泛型。3. 使用`typing.overload`：仅用于类型提示，帮助静态类型检查器（如mypy）理解函数的多种调用签名，但运行时不提供实际的重载逻辑。4. 第三方库如`multipledispatch`：通过装饰器实现基于参数类型和数量的多分派。常见追问点包括`singledispatch`的底层实现原理，以及为什么Python选择不支持原生重载。

## 核心考点

- 动态类型特性
- 默认参数
- singledispatch
- typing.overload

## 常见追问

> 请解释`functools.singledispatch`的底层实现原理及其适用场景。

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
