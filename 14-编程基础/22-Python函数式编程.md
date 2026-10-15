# 22 Python函数式编程

**日期**: 2026-10-15 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

1. Python支持函数式编程范式，核心特性包括高阶函数、闭包、匿名函数以及内置的map/filter/reduce等。
2. 函数是一等公民，可以作为参数传递、作为返回值返回，也可以赋值给变量。
3. 闭包是指延伸了作用域的函数，能够记住并访问其定义时所在的词法作用域中的变量，即使该作用域外被调用。
4. 偏函数通过functools.partial固定部分参数，生成新的可调用对象，简化复杂函数的调用。
5. 虽然Python没有纯粹的不可变数据结构，但可以通过元组、frozenset以及纯函数（无副作用）的设计理念来实践函数式编程。
常见追问点：Python中的闭包与装饰器有什么关系？lambda表达式的限制有哪些？

## 核心考点

- 高阶函数
- 闭包
- lambda表达式
- map/filter/reduce
- 一等公民

## 常见追问

> Python中的闭包是如何实现的，它与装饰器有什么联系？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
