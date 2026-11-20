# Python 中的拷贝（浅拷贝与深拷贝）

**日期**: 2026-11-20 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python 拷贝分为三种情况：

1. 赋值（引用传递）：b = a 只是复制了对象引用，a 和 b 指向同一对象，修改互相可见；
2. 浅拷贝：copy.copy(a) 或 a[:]、a.copy()，创建新对象，但只复制最外层容器，内部嵌套的子对象仍是引用。修改嵌套元素会互相影响；
3. 深拷贝：copy.deepcopy(a)，递归复制所有层级，完全独立的新对象。

示例：
```python
import copy
a = [[1, 2], [3, 4]]
b = copy.copy(a)
b[0].append(99)   # a 也变成 [[1,2,99],[3,4]]
c = copy.deepcopy(a)
c[0].append(77)   # a 不受影响
```

关键细节：
- 不可变对象（int、str、tuple）无需拷贝，赋值即安全；
- deepcopy 内部用 memo 字典处理循环引用，避免无限递归；
- 自定义类可通过实现 __copy__ 和 __deepcopy__ 控制拷贝行为；
- 切片 a[:] 是浅拷贝，嵌套列表仍共享。

常见追问：函数默认参数用可变对象（如 def f(x=[])）的坑，本质也是引用共享问题；以及 pandas/numpy 中的视图（view）与拷贝（copy）的区别。

## 核心考点

- 引用赋值 vs 浅拷贝 vs 深拷贝
- copy.copy 与 copy.deepcopy
- 嵌套对象共享问题
- 循环引用与 memo 机制
- 可变默认参数陷阱

## 常见追问

> deepcopy 是如何处理循环引用避免无限递归的？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
