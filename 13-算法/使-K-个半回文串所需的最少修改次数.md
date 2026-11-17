# 使 K 个半回文串所需的最少修改次数

**日期**: 2026-11-17 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 高级 | **来源**: LeetCode

**Tags**: 双指针, 字符串, 动态规划

## 解答

思路：本题是典型的「预处理 + 划分型动态规划」难题。第一步，理解半回文定义：字符串 s 的子串是半回文，当且仅当存在 s 的一个真因子 t（t < len(s)），使得下标 i 与 i+t 位置字符全部对应相等。第二步，预处理代价：对每个子串 s[i..j]，枚举其长度的所有真因子 d，按 d 分组，组内首尾向中间双指针统计不匹配字符数，取所有分组的最小值作为 cost[i][j]，可用 O(n^2·√n) 完成。第三步，DP 划分：设 dp[i][k] 表示前 i 个字符划分成 k 个半回文子串的最小修改数，转移为 dp[i][k] = min(dp[j][k-1] + cost[j][i-1])，j 从 0 到 i-1。最终答案为 dp[n][k]。代码框架：

def minimumChanges(s, k):
    n = len(s)
    cost = [[float('inf')]*n for _ in range(n)]
    for i in range(n):
        for j in range(i, n):
            L = j - i + 1
            best = float('inf')
            for d in range(1, L):
                if L % d == 0:
                    c = 0
                    for a in range(i, i + d):
                        x, y = a, j - (a - i)
                        # 分组内双指针
                        while x < y:
                            if s[x] != s[y]: c += 1
                            x += d; y -= d
                    best = min(best, c)
            cost[i][j] = best
    dp = [[float('inf')]*(k+1) for _ in range(n+1)]
    dp[0][0] = 0
    for i in range(1, n+1):
        for m in range(1, k+1):
            for j in range(i):
                dp[i][m] = min(dp[i][m], dp[j][m-1] + cost[j][i-1])
    return dp[n][k]

常见追问：如何枚举因子优化到 O(√n)；预处理能否用前缀和按步长分组加速；划分型 DP 的状态设计与复杂度分析。

## 核心考点

- 划分型动态规划
- 子串代价预处理
- 因子枚举与分组双指针
- 时间复杂度优化
- 回文判定变体

## 常见追问

> 如何将预处理复杂度从 O(n^3) 优化到 O(n^2·√n) 甚至更低？

**参考链接**: [https://leetcode.cn/problems/minimum-changes-to-make-k-semi-palindromes/](https://leetcode.cn/problems/minimum-changes-to-make-k-semi-palindromes/)
