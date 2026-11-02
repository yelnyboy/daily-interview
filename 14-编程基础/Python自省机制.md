# Python自省机制

**日期**: 2026-11-02 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

自省指程序在运行时检查对象类型与属性的能力。核心要点：1）type()与isinstance()：获取对象类型及判断继承关系，isinstance能正确处理子类。2）dir()：列出对象所有属性和方法名。3）hasattr()/getattr()/setattr()：动态检查、读取、设置属性，getattr(obj, name, default)可带默认值避免异常。4）inspect模块：获取函数签名inspect.signature()、源码inspect.getsource()、判断类型inspect.isfunction()。5）__dict__与__class__：查看实例属性字典与所属类。6）callable()：判断对象是否可调用。典型应用：动态插件加载、ORM字段映射、依赖注入框架、序列化库。追问点：getattr是内置函数，而__getattr__是属性不存在时才触发的魔法方法，注意区分。

## 核心考点

- type/isinstance
- dir()
- getattr/hasattr/setattr
- inspect模块
- __dict__

## 常见追问

> getattr()与__getattr__、__getattribute__的区别和触发时机是什么？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
