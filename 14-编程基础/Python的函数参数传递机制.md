# Python的函数参数传递机制

**日期**: 2026-11-11 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python的参数传递是'传对象引用'（pass by object reference），也称为'共享传参'。要点如下：
1. Python中一切皆对象，变量名只是指向对象的标签，传递的是对象的引用（指针）。
2. 对于不可变对象（int、str、tuple），函数内重新赋值会创建新对象，不影响外部变量。
3. 对于可变对象（list、dict、set），函数内的原地修改（如append、修改键值）会影响外部对象。
4. 经典陷阱：可变默认参数 def f(a, lst=[])，默认列表在函数定义时只创建一次，多次调用会累积状态，正确写法是默认None再在函数体内初始化。
5. 参数类型：位置参数、关键字参数、*args可变位置参数、**kwargs可变关键字参数、仅关键字参数（*后定义）、仅位置参数（/前定义）。
示例：
def f(x, lst=[]):  # 陷阱
    lst.append(x)
    return lst
f(1); f(2)  # [1, 2] 而非 [2]

常见追问点：为什么不可变对象在函数内修改'无效'；如何避免可变默认参数陷阱；浅拷贝与深拷贝（copy.copy vs copy.deepcopy）的区别。

## 核心考点

- 传对象引用
- 可变与不可变对象
- 可变默认参数陷阱
- *args与**kwargs
- 深浅拷贝

## 常见追问

> 请解释可变默认参数陷阱的成因，以及如何用 id() 函数验证参数传递的是对象引用？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
