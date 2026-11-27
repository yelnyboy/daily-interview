# Python 的 List（列表）详解

**日期**: 2026-11-27 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python 的 list 是最常用的内置容器类型，核心要点如下：1. list 是有序、可变的动态数组，底层基于 CPython 的 PyObject* 指针数组实现，可存放任意类型的异构对象；2. 支持索引访问（正负索引）、切片操作（如 lst[1:4:2]），切片会返回新列表（浅拷贝）；3. 常用操作：append（尾部追加，均摊 O(1)）、insert(0, x)（头部插入 O(n)）、pop()（尾部弹出 O(1)）、remove(x)（按值删除 O(n)）、extend、sort、reverse 等；4. 扩容机制：list 采用超额分配策略，容量不足时按约 1.125 倍增长并重新分配内存，因此 append 是均摊 O(1)；5. 常见陷阱：[[0]*3]*3 创建的二维列表各行共享同一引用，应使用 [[0]*3 for _ in range(3)]；遍历时修改列表会导致跳过元素，应遍历副本或倒序删除；6. 与 tuple 的区别：tuple 不可变、可哈希（元素也可哈希时），可作为字典键，且更省内存。常见追问点：list 与 tuple、set、dict 的选型；浅拷贝与深拷贝（copy.deepcopy）；列表推导式的性能优势；list 线程安全性（CPython 中单个操作原子但复合操作不安全）。

## 核心考点

- 动态数组底层实现
- 均摊复杂度
- 切片与浅拷贝
- 扩容机制
- 可变对象的引用陷阱

## 常见追问

> 为什么 list 的 append 是均摊 O(1)？请解释其扩容策略。

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
