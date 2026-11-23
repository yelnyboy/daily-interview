# Python 的 List（列表）详解

**日期**: 2026-11-23 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python 列表是最常用的内置数据结构，面试常考其底层实现与特性：
1. 基本特性：有序、可变（mutable）、允许混合类型元素、允许重复，支持索引和切片（如 lst[1:3]、lst[::-1]）。
2. 底层实现：list 是动态数组（PyObject 指针数组），通过过度分配（over-allocation）策略扩容，append 均摊 O(1)；在中间插入/删除是 O(n)，因为需要移动元素。
3. 常用操作复杂度：索引访问 O(1)、append O(1) 均摊、pop() 尾部 O(1)、pop(0) 或 insert(0, x) O(n)、in 查找 O(n)。
4. 常见陷阱：浅拷贝问题（b = a 只是引用，b = a[:] 或 copy.deepcopy 才是拷贝）；遍历时修改列表导致跳元素；默认参数使用可变对象（def f(x=[])）被共享。
5. 列表推导式：[x*2 for x in range(10) if x % 2 == 0]，比 for 循环 append 更快更 Pythonic；生成器表达式 (x for x in ...) 则惰性求值、省内存。
6. 与相关结构对比：需要频繁头部插入用 collections.deque；需要去重/快速查找用 set 或 dict；不可变需求用 tuple。
常见追问：list 和 tuple 的区别；list 扩容机制（按约 1.125 倍增长，CPython 实现）；为什么 list 不能作为 dict 的 key（不可哈希）。

## 核心考点

- 动态数组底层实现
- 操作时间复杂度
- 浅拷贝与深拷贝
- 列表推导式
- 可变默认参数陷阱

## 常见追问

> append 和 extend 的区别是什么？为什么在循环中用 + 拼接列表性能很差？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
