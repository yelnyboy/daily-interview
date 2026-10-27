# Python自省机制

**日期**: 2026-10-27 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python自省是在运行时检查对象类型、属性和方法的能力，是Python动态特性的重要体现：
1. `type(obj)`：返回对象的类型，是最基础的自省函数。
2. `dir(obj)`：列出对象的所有属性和方法名称，包括特殊方法。
3. `hasattr(obj, name)` / `getattr(obj, name)` / `setattr(obj, name, value)`：检查、获取、设置对象属性。
4. `isinstance(obj, cls)` / `issubclass(cls1, cls2)`：类型和继承关系检查。
5. `inspect`模块：提供更强大的自省功能，如获取函数签名、源代码、调用栈等。
6. `obj.__dict__`：查看对象的实例属性字典。
7. `callable(obj)`：判断对象是否可调用。

常见追问：`type()`和`isinstance()`的区别？`inspect`模块有哪些常用功能？

## 核心考点

- type与isinstance
- dir与__dict__
- getattr/hasattr/setattr
- inspect模块
- 运行时类型检查

## 常见追问

> type()和isinstance()在处理继承关系时有什么区别？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
