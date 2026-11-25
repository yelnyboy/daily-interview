# Python 自省机制

**日期**: 2026-11-25 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python 自省是指程序在运行时检查对象类型、属性和结构的能力，核心要点如下：1. type() 和 isinstance()：获取对象类型及判断继承关系，isinstance 能识别子类实例，推荐优先使用。2. dir()：列出对象的所有属性和方法名，常用于交互式探索未知对象。3. getattr()/setattr()/hasattr()：动态读取、设置和检测属性，是元编程和插件系统的基础。4. inspect 模块：功能最强大，可获取函数签名 inspect.signature()、源码 inspect.getsource()、参数类型（是否可变参数、默认值）、调用栈 inspect.stack() 等。5. __dict__ 与 vars()：查看实例或类的属性字典，理解属性查找顺序（实例 → 类 → 基类）。6. 反射应用场景：ORM 字段映射、依赖注入、自动序列化、装饰器参数校验。示例：

def introspect(obj):
    print(type(obj), isinstance(obj, object))
    print([a for a in dir(obj) if not a.startswith('_')])
    import inspect
    print(inspect.signature(obj) if callable(obj) else vars(obj))

常见追问：type() 与 __class__ 的区别（元类场景下可能不同）；如何用 __getattr__ 与 __getattribute__ 自定义自省行为；自省的性能开销。

## 核心考点

- type 与 isinstance
- dir 与 vars
- getattr/setattr/hasattr
- inspect 模块
- 反射与元编程

## 常见追问

> __getattr__ 和 __getattribute__ 的区别是什么，各自适合什么场景？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
