# 子数组不同元素平方和 I

**日期**: 2026-10-15 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 初级 | **来源**: LeetCode

**Tags**: 树状数组, 线段树, 数组, 哈希表

## 解答

思路：题目要求计算所有子数组中不同元素个数的平方和。由于是Easy版本，数据范围通常较小（如n<=100），可以直接暴力枚举所有子数组。对于每个子数组，使用哈希集合统计不同元素的个数，将其平方后累加到总和中即可。时间复杂度为O(n^2)。
代码框架(Python)：
def distinctSquares(nums):
    n = len(nums)
    total = 0
    for i in range(n):
        seen = set()
        for j in range(i, n):
            seen.add(nums[j])
            total += len(seen) ** 2
    return total
常见追问点：如果数据范围变大（如n=10^5），该如何优化？是否可以用线段树或树状数组维护贡献？

## 核心考点

- 子数组枚举
- 哈希表去重
- 暴力解法
- 复杂度优化

## 常见追问

> 如果数组长度达到 10^5，该如何优化时间复杂度？

**参考链接**: [https://leetcode.cn/problems/subarrays-distinct-element-sum-of-squares-i/](https://leetcode.cn/problems/subarrays-distinct-element-sum-of-squares-i/)
