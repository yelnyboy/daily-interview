# 使数组元素相等的最小移动次数 II

**日期**: 2026-11-02 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 数组, 数学, 排序

## 解答

思路：每次移动可将某元素+1或-1，求让所有元素相等的最小总移动数。本质是找一点使所有数到该点的绝对距离之和最小，该点即中位数（中位数最小化L1距离，均值最小化L2距离）。解法一：排序后取中位数，累加每个元素与中位数的绝对差。解法二：排序后双指针，res += nums[j] - nums[i]，配对消去等价。代码框架（Python）：
def minMoves2(nums):
    nums.sort()
    median = nums[len(nums)//2]
    return sum(abs(x - median) for x in nums)
时间复杂度O(nlogn)，空间O(1)。常见追问：为何不取平均值？反例[1,0,0,8,6]取均值3移动次数反而更多；进阶可用快速选择找中位数，平均优化到O(n)。

## 核心考点

- 中位数性质
- L1距离最小化
- 排序
- 双指针
- 快速选择优化

## 常见追问

> 为什么目标是中位数而不是平均值？如何用快速选择将复杂度优化到O(n)？

**参考链接**: [https://leetcode.cn/problems/minimum-moves-to-equal-array-elements-ii/](https://leetcode.cn/problems/minimum-moves-to-equal-array-elements-ii/)
