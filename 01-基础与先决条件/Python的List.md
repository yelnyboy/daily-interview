# Python的List

**日期**: 2026-10-12 | **类型**: Theory | **原始分类**: Python基础 | **路线图模块**: 01-基础与先决条件 | **难度**: 初级 | **来源**: GitHub

## 解答

Python的List是动态数组，底层由连续的内存块组成，存储的是对象的引用（指针）。
1. 底层结构：List底层是一个PyObject指针数组，存储指向实际对象的指针，这使得List可以存储不同类型的元素。
2. 动态扩容：当向List添加元素时，如果容量不足，会重新分配更大的内存空间，并将旧元素拷贝过去，时间复杂度均摊O(1)。
3. 有序可变：List是有序的，支持通过索引随机访问，时间复杂度为O(1)；同时List是可变的，可以原地修改元素。
4. 常见操作：插入和删除非尾部元素的时间复杂度为O(N)，因为需要移动后续元素；尾部追加append()和pop()的时间复杂度为O(1)。
常见追问点：List和Tuple的区别？List的扩容机制是怎样的？

## 核心考点

- 动态数组
- 对象引用
- 动态扩容
- 时间复杂度

## 常见追问

> List和Tuple在底层实现和性能上有什么区别？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
