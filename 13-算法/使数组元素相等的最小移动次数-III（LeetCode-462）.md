# 使数组元素相等的最小移动次数 III（LeetCode 462）

**日期**: 2026-11-03 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 初级 | **来源**: LeetCode

**Tags**: 数组, 数学

## 解答

题意：每次移动可将某个元素+1或-1，求使所有元素相等的最少移动次数。思路：最优目标值是中位数而非平均值，因为中位数能最小化所有元素到目标的绝对距离之和；若目标偏离中位数，一侧增加的代价会超过另一侧减少的量。做法一：排序后取中位数，累加每个元素与中位数之差的绝对值；做法二：排序后双指针，res += nums[j] - nums[i]，i、j向中间靠拢。代码框架（Python）：
def minMoves2(nums):
    nums.sort()
    mid = nums[len(nums)//2]
    return sum(abs(x - mid) for x in nums)
复杂度：时间O(nlogn)，空间O(1)。常见追问：1）为什么不用平均值？平均值最小化平方和，中位数最小化绝对值和；2）如何优化到平均O(n)？用快速选择找中位数；3）偶数长度取哪个中位数？两中位数之间任意值总代价相同；4）若只允许+1（LeetCode 453），等价于把所有元素降到最小值，答案为 sum(x - min)。

## 核心考点

- 中位数贪心
- 排序+双指针
- 绝对值和最小化
- 快速选择优化
- 与平均值方案对比

## 常见追问

> 为什么最优目标是中位数而不是平均值？如何用快速选择将复杂度优化到平均O(n)？

**参考链接**: [https://leetcode.cn/problems/minimum-moves-to-equal-array-elements-iii/](https://leetcode.cn/problems/minimum-moves-to-equal-array-elements-iii/)
