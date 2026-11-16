# Python中的元类（metaclass）

**日期**: 2026-11-16 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 14-编程基础 | **难度**: 高级 | **来源**: GitHub

## 解答

元类是创建类的类，即“类的类”。核心要点：1) Python中一切皆对象，类本身也是对象，创建类的模板就是元类，默认元类是type；2) type可以直接动态创建类：type('MyClass', (Base,), {'attr': 1})，三个参数分别是类名、基类元组、属性字典；3) 自定义元类需继承type，并重写__new__（在类创建前修改类属性）或__init__（类创建后初始化）；4) 元类的查找顺序：创建class时解释器查找metaclass关键字参数 → 父类的元类 → 默认type；5) 典型应用：ORM框架（如Django Model、SQLAlchemy）自动注册字段、单例模式、接口校验、API自动注册。代码示例：

class SingletonMeta(type):
    _instances = {}
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Config(metaclass=SingletonMeta):
    pass

常见追问：__new__与__init__在元类中的区别；元类与__init_subclass__的取舍（后者更简单，优先使用）；元类继承规则；new class与old class（Python2）的差异。

## 核心考点

- type是默认元类
- 类的创建过程
- __new__与__init__
- 单例实现
- ORM框架应用

## 常见追问

> 元类与__init_subclass__、类装饰器都能干预类创建，三者该如何选择？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
