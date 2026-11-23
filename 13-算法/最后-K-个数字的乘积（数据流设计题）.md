# 最后 K 个数字的乘积（数据流设计题）

**日期**: 2026-11-23 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 设计, 数组, 数学, 数据流, 前缀和

## 解答

思路：这是典型的数据流设计题，要求支持 addNum 追加数字和 getProduct 查询最后 K 个数的乘积。暴力法每次查询遍历 K 个数，复杂度 O(K)，在频繁查询时性能差。优化方案是维护前缀乘积数组 pre，其中 pre[i] 表示前 i 个数的乘积，则最后 K 个数的乘积等于 pre[n] / pre[n-K]，查询 O(1)。关键难点是处理 0：一旦出现 0，前缀乘积全部归零，无法再用除法回溯。解决方法是遇到 0 时将前缀数组重置，并在 pre[0] 位置记录 0 出现的位置索引（即 pre = [当前长度]），这样查询时若 K 小于距离最近 0 的距离，则正常做除法；否则结果为 0。代码框架：

class ProductOfNumbers:
    def __init__(self):
        self.pre = [1]  # pre[0]=1 作为哨兵

    def add(self, num: int) -> None:
        if num == 0:
            self.pre = [len(self.pre)]  # 记录0出现的位置
        else:
            self.pre.append(self.pre[-1] * num)

    def getProduct(self, k: int) -> int:
        n = len(self.pre)
        if k < n - self.pre[0]:  # 范围内没有0
            return self.pre[-1] // self.pre[n - 1 - k]
        return 0

常见追问：为什么不能直接用除法（0 的存在）；前缀和/前缀积思想的迁移；如果数字可能是负数或浮点数如何处理（负数不影响，浮点会有精度问题）；能否用其他数据结构如单调栈或线段树实现。

## 核心考点

- 前缀乘积
- 零值特殊处理
- 数据流设计
- O(1)查询优化
- 哨兵元素

## 常见追问

> 如果查询的 K 可能超过当前元素总数或需要支持删除操作，你的设计需要如何调整？

**参考链接**: [https://leetcode.cn/problems/product-of-the-last-k-numbers/](https://leetcode.cn/problems/product-of-the-last-k-numbers/)
