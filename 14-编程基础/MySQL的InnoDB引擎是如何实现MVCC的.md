# MySQL的InnoDB引擎是如何实现MVCC的

**日期**: 2026-10-12 | **类型**: Theory | **原始分类**: 数据库 | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

InnoDB通过MVCC（多版本并发控制）实现了非阻塞读，提高了并发性能。
1. 隐藏字段：InnoDB在每行记录中添加了两个必要的隐藏字段：DB_TRX_ID（最近修改的事务ID）和DB_ROLL_PTR（回滚指针，指向Undo Log中的上一个版本）。
2. Undo Log版本链：每次修改记录时，旧版本会被记录到Undo Log中，通过回滚指针将不同版本的记录串联起来，形成版本链。
3. ReadView机制：当一个事务发起查询时，会生成一个ReadView，包含当前活跃事务的ID列表。通过比较记录的DB_TRX_ID和ReadView，决定当前事务能看到哪个版本的数据。
4. 隔离级别差异：在RC（读已提交）级别下，每次SELECT都会生成新的ReadView；在RR（可重复读）级别下，只在事务第一次SELECT时生成ReadView，后续复用。
常见追问点：RR级别下MVCC如何解决幻读？快照读和当前读的区别是什么？

## 核心考点

- 隐藏字段
- Undo Log版本链
- ReadView
- 隔离级别

## 常见追问

> RR隔离级别下MVCC是否完全解决了幻读问题？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
