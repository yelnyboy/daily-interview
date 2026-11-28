# 促销商品最大获取数量 II

**日期**: 2026-11-28 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 贪心, 数组, 排序, 堆（优先队列）

## 解答

思路：本题是典型的贪心 + 优先队列问题。给定预算和若干商品，每类商品有价格和数量限制，要求在预算内购买最多的商品总数。核心贪心策略：优先购买最便宜的商品，因为花最少的钱获得最多的件数是最优的。实现步骤：1) 将所有商品按价格升序排序（或用小顶堆动态取出当前最便宜的可购商品）；2) 依次遍历，若当前预算足够买一件该商品，则尽可能多地购买该类商品（受数量限制和预算双重约束），件数取 min(剩余数量, 预算/价格)；3) 扣减预算，累加总数，直到预算不足或商品遍历完。时间复杂度：排序 O(n log n)，遍历 O(n)。代码框架：

def max_items(prices, budget):
    # prices: [(price, count), ...]
    prices.sort()
    total = 0
    for price, count in prices:
        if budget < price:
            break
        can_buy = min(count, budget // price)
        total += can_buy
        budget -= can_buy * price
    return total

常见追问：为什么贪心正确（交换论证：任何最优解中贵的商品换成便宜的不会变差）；若商品数量极大如何优化（用堆或二分）；若价格可拆分或存在折扣等变体如何处理。

## 核心考点

- 贪心算法
- 排序
- 堆（优先队列）
- 交换论证证明正确性
- 边界条件处理

## 常见追问

> 如何证明贪心策略的正确性？如果商品数量极大无法排序，如何用堆优化？

**参考链接**: [https://leetcode.cn/problems/maximum-number-of-items-from-sale-ii/](https://leetcode.cn/problems/maximum-number-of-items-from-sale-ii/)
