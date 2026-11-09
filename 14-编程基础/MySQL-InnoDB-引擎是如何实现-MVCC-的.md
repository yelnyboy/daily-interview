# MySQL InnoDB 引擎是如何实现 MVCC 的

**日期**: 2026-11-09 | **类型**: Theory | **原始分类**: 数据库 | **路线图模块**: 14-编程基础 | **难度**: 中级 | **来源**: GitHub

## 解答

MVCC（多版本并发控制）是 InnoDB 在 RC/RR 隔离级别下实现一致性读、避免加锁读的核心机制。实现要点：1) 隐藏列：每行记录额外保存 DB_TRX_ID（最近修改事务 ID）、DB_ROLL_PTR（回滚指针，指向 undo log 中的旧版本）、DB_ROW_ID；2) Undo Log 版本链：每次修改都会把旧版本写入 undo log，通过 roll_pointer 串成版本链，形成行的历史快照；3) Read View（读视图）：事务执行快照读时生成 ReadView，包含 m_ids（活跃事务集合）、min_trx_id、max_trx_id、creator_trx_id 四个关键信息；4) 可见性判断：沿版本链从新到旧遍历，若某版本的 trx_id 小于 min_trx_id 或等于 creator_trx_id 则可见；若 trx_id ≥ max_trx_id 或在 m_ids 中则不可见，继续找上一版本；5) 隔离级别差异：RC 级别每次 SELECT 都生成新 ReadView（能读到已提交的最新数据），RR 级别只在第一次 SELECT 时生成并复用（保证可重复读）；6) 快照读与当前读：普通 SELECT 是快照读走 MVCC，而 update、delete、select...for update 是当前读，读最新已提交版本并加锁。常见追问：RR 如何解决幻读（快照读靠 MVCC、当前读靠间隙锁）？长事务为何导致 undo log 膨胀？

## 核心考点

- DB_TRX_ID 与 DB_ROLL_PTR 隐藏列
- Undo Log 版本链
- ReadView 可见性判断
- RC 与 RR 生成时机差异
- 快照读与当前读

## 常见追问

> RR 隔离级别下 MVCC 为什么不能完全解决幻读，InnoDB 是如何补救的？

**参考链接**: [https://github.com/taizilongxu/interview_python](https://github.com/taizilongxu/interview_python)
