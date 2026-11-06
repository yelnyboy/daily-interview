# 统计零请求服务器（Count Zero Request Servers）

**日期**: 2026-11-06 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 数组, 哈希表, 排序, 滑动窗口

## 解答

思路：这是一道典型的滑动窗口 + 哈希表计数题。给定服务器数量 n、日志 logs（每条含时间戳和服务器编号）以及查询数组 queries，对每个查询时间 x，需要统计在区间 [x - x + 1, x]（长度为 x 的窗口）内没有收到任何请求的服务器数量。做法是：1) 将 logs 按时间排序，将 queries 连同原始下标一起排序；2) 用双指针维护窗口，右指针不断加入时间 <= x 的日志，左指针移除时间 < x - x + 1 的日志；3. 用哈希表 count 记录窗口内每个服务器的请求次数，同时维护一个变量 zero 表示当前请求次数为 0 的服务器数（初始为 n，某服务器首次进入窗口时 zero 减 1，次数降为 0 时 zero 加 1）；4) 每个查询的答案即为 zero，按原下标写回结果数组。时间复杂度 O((L + Q) log(L + Q))，空间 O(n + L)。代码框架：

def countServers(n, logs, x, queries):
    logs.sort()
    qs = sorted((t, i) for i, t in enumerate(queries))
    count = defaultdict(int)
    zero, left, right = n, 0, 0
    ans = [0] * len(queries)
    for t, i in qs:
        while right < len(logs) and logs[right][1] <= t:
            sid = logs[right][0]
            if count[sid] == 0: zero -= 1
            count[sid] += 1
            right += 1
        while left < right and logs[left][1] < t - x + 1:
            sid = logs[left][0]
            count[sid] -= 1
            if count[sid] == 0: zero += 1
            left += 1
        ans[i] = zero
    return ans

常见追问：为什么排序后双指针不会遗漏？如何避免每次查询重新遍历窗口？zero 变量的维护时机（先判断再更新）。

## 核心考点

- 滑动窗口
- 哈希表计数
- 双指针
- 离线查询排序
- 增量维护零计数

## 常见追问

> 如果查询是在线的（无法预先排序），如何用树状数组或线段树解决？

**参考链接**: [https://leetcode.cn/problems/count-zero-request-servers/](https://leetcode.cn/problems/count-zero-request-servers/)
