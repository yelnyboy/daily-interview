# MySQL InnoDB 引擎是如何实现 MVCC 的

**日期**: 2026-11-23 | **类型**: Theory | **原始分类**: 数据库 | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

MVCC（多版本并发控制）是 InnoDB 在 READ COMMITTED 和 REPEATABLE READ 隔离级别下，代替传统读锁实现高并发读写的关键机制。其实现依赖三个核心组件：

1. 隐藏列：每行记录包含 DB_TRX_ID（最近修改该行的事务ID）、DB_ROLL_PTR（回滚指针，指向 undo log 中的上一个版本）、DB_ROW_ID（隐藏主键）。

2. Undo Log 版本链：每次修改都会将旧版本写入 undo log，通过 roll_ptr 串联成版本链，形成该行的历史快照。

3. Read View（读视图）：事务发起快照读时生成 Read View，记录当时活跃（未提交）事务集合。判断某版本是否可见的规则：若 DB_TRX_ID 小于最小活跃事务ID，可见；若大于最大事务ID，不可见；若在活跃集合中，不可见；否则可见。不可见则沿版本链回溯找上一个版本。

两个隔离级别的区别在于 Read View 的生成时机：RC 级别每次 SELECT 都生成新 Read View，所以能看到其他事务已提交的最新数据（不可重复读）；RR 级别只在第一次 SELECT 时生成并复用，保证可重复读，并在一定程度上避免幻读。

注意：MVCC 只对快照读（普通 SELECT）生效，当前读（SELECT ... FOR UPDATE、UPDATE、DELETE）走加锁逻辑，RR 级别下需靠间隙锁防止幻读。

## 核心考点

- 隐藏三列（DB_TRX_ID / DB_ROLL_PTR / DB_ROW_ID）
- Undo Log 版本链
- Read View 可见性判断规则
- RC 与 RR 的 Read View 生成时机差异
- 快照读与当前读的区别

## 常见追问

> RR 隔离级别下 MVCC 为什么只能部分避免幻读，间隙锁在其中起什么作用？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
