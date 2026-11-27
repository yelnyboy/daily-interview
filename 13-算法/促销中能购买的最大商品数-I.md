# 促销中能购买的最大商品数 I

**日期**: 2026-11-27 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 贪心, 数组, 动态规划

## 解答

思路：本题属于典型的贪心问题。给定若干商品价格和总预算，要求购买尽可能多的商品数量（而非最大化价值），贪心策略是优先购买最便宜的商品。1. 将所有商品价格升序排序；2. 从头开始依次累加价格，只要当前累计花费不超过预算就继续购买；3. 一旦超出预算即停止，已购买的数量即为答案。正确性证明：若存在更优解购买了 k+1 件商品，则其中最便宜的 k+1 件商品总花费必然不大于该解的花费，因此贪心取最小价格一定不会更差（交换论证）。时间复杂度 O(n log n)（排序），空间复杂度 O(1)（不计排序栈空间）。代码框架（Python）：

def maxItems(prices, budget):
    prices.sort()
    count = total = 0
    for p in prices:
        if total + p <= budget:
            total += p
            count += 1
        else:
            break
    return count

常见追问点：1. 如果要求恰好花完预算或最大化价值怎么办（转为0-1背包DP）；2. 为什么贪心正确，如何证明（交换论证）；3. 如果价格有折扣规则（如买二送一）如何建模；4. 数据量极大时能否用计数排序优化到 O(n + maxPrice)。

## 核心考点

- 贪心策略
- 排序
- 交换论证
- 背包问题对比
- 时间复杂度分析

## 常见追问

> 如果题目改为在预算内最大化商品总价值而非数量，你会如何修改算法？

**参考链接**: [https://leetcode.cn/problems/maximum-number-of-items-from-sale-i/](https://leetcode.cn/problems/maximum-number-of-items-from-sale-i/)
