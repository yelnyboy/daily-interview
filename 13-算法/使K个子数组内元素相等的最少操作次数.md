# 使K个子数组内元素相等的最少操作次数

**日期**: 2026-11-04 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 高级 | **来源**: LeetCode

**Tags**: 数组, 哈希表, 数学, 动态规划, 滑动窗口

## 解答

思路：题目要求把数组划分成恰好 k 个非空子数组，每次操作可将某元素加1或减1，求使每个子数组内部所有元素相等的最少总操作数。核心分两步：1) 预处理：对每个可能的子数组区间 [i, j]，计算把该区间内元素变成中位数的最小代价。求中位数代价可用排序+前缀和，或用双堆（大顶堆+小顶堆）在线维护滑动窗口的中位数代价，将区间代价计算优化到 O(n²) 或均摊 O(n log n)。2) 动态规划：设 dp[i][j] 表示前 i 个元素分成 j 个子数组的最小代价，转移为 dp[i][j] = min(dp[m][j-1] + cost(m+1, i))，其中 cost 为区间变中位数的代价。最终答案为 dp[n][k]。总复杂度约 O(n²k)，需注意 n、k 范围优化。常见追问：为什么目标是中位数而不是平均值（中位数最小化绝对偏差之和，平均值最小化平方偏差）；如何用双堆维护滑动中位数；能否用前缀和快速计算区间代价；边界处理如 k=1 或 k=n。代码框架：

def minOperations(nums, k):
    n = len(nums)
    # cost[i][j]: 区间[i,j]变为中位数的代价（可用双堆或排序+前缀和）
    INF = float('inf')
    dp = [[INF]*(k+1) for _ in range(n+1)]
    dp[0][0] = 0
    for i in range(1, n+1):
        for j in range(1, min(i, k)+1):
            for m in range(j-1, i):
                dp[i][j] = min(dp[i][j], dp[m][j-1] + cost(m, i-1))
    return dp[n][k]

## 核心考点

- 中位数代价最小化
- 双堆维护滑动中位数
- 区间划分动态规划
- 前缀和优化
- 时间复杂度分析

## 常见追问

> 为什么把区间元素都变成中位数能使操作次数最少，如何证明？

**参考链接**: [https://leetcode.cn/problems/minimum-operations-to-make-elements-within-k-subarrays-equal/](https://leetcode.cn/problems/minimum-operations-to-make-elements-within-k-subarrays-equal/)
