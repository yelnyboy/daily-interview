# Python自省机制

**日期**: 2026-10-12 | **类型**: Theory | **分类**: Python基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python自省是指在程序运行时动态获取对象的类型、属性和方法等内部信息的能力。第一，type()和isinstance()用于获取和检查对象的类型，后者在处理继承关系时更推荐使用。第二，dir()函数可以列出对象的所有属性和方法，常用于快速探索未知模块或对象。第三，hasattr()、getattr()和setattr()用于动态判断、获取和设置对象的属性，是实现动态调用的关键。第四，inspect模块提供了更强大的自省功能，如获取函数签名、源代码、调用栈信息等。第五，__dict__属性可以查看对象实例自身的属性字典，但不包含类属性和继承属性。

## 核心考点

- type与isinstance
- dir函数
- 动态属性操作
- inspect模块
- __dict__属性

## 常见追问

> 如何利用自省机制实现一个通用的ORM映射框架？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
