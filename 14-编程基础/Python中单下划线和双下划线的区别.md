# Python中单下划线和双下划线的区别

**日期**: 2026-10-18 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 初级 | **来源**: GitHub

## 解答

Python中下划线有多种用法，主要区别如下：

1. 单前导下划线 _var：是一种约定（非强制），表示该变量或方法是模块/类的内部实现，不建议外部直接访问。但Python不会阻止访问，只是一种编程规范。在`from module import *`时，以单下划线开头的名称不会被导入（除非在`__all__`中显式声明）。

2. 双前导下划线 __var：触发名称修饰（Name Mangling）。Python解释器会将其重写为`_ClassName__var`，例如在类MyClass中定义`__x`，实际存储为`_MyClass__x`。这主要用于避免子类中的命名冲突，提供一定程度的私有性，但仍可通过修饰后的名称访问。

3. 单尾随下划线 var_：用于避免与Python关键字冲突，如`class_`、`list_`。

4. 双前后下划线 __var__：Python的魔术方法/特殊属性，如`__init__`、`__str__`、`__len__`等。这些是Python预定义的，开发者一般不要自定义此类名称。

5. 单独下划线 _：在交互式环境中表示上一个表达式的结果；在循环中用作临时变量表示不关心的值，如`for _ in range(10)`。

## 核心考点

- 单下划线约定私有
- 双下划线名称修饰
- 魔术方法__dunder__
- from import *行为
- 尾随下划线避免冲突

## 常见追问

> 名称修饰（Name Mangling）在继承场景下如何影响子类对父类属性的访问？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
