# MySQL的InnoDB引擎是如何实现MVCC的

**日期**: 2026-10-23 | **类型**: Theory | **原始分类**: 数据库 | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

1. InnoDB通过多版本并发控制（MVCC）提高并发性能，主要依赖隐藏字段、Undo Log和Read View实现。2. 每行记录包含隐藏字段DB_TRX_ID（最近修改的事务ID）和DB_ROLL_PTR（指向Undo Log的回滚指针）。3. 当数据被修改时，旧版本会被记录在Undo Log中，通过回滚指针形成版本链。4. 事务在查询时生成Read View，包含当前活跃事务列表，用于判断版本可见性。5. 通过比较记录的DB_TRX_ID与Read View中的活跃事务ID，沿着版本链找到对当前事务可见的第一个版本。常见追问：RC和RR隔离级别下Read View的生成时机有何不同？

## 核心考点

- 隐藏字段
- Undo Log版本链
- Read View
- 可见性判断
- 并发控制

## 常见追问

> RC（读已提交）和RR（可重复读）隔离级别下Read View的生成时机有何不同？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
