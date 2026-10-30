# 最多K个连续相同字符的最短路径

**日期**: 2026-10-30 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 图, 字符串, 最短路, 堆（优先队列）

## 解答

思路：本题是带状态约束的最短路径问题。由于不能有超过K个连续相同的字符，状态不仅需要记录当前节点，还要记录到达该节点时的上一个字符及连续长度。使用Dijkstra算法，优先队列中存储 (距离, 节点, 上一个字符, 连续相同字符数)。每次扩展相邻节点时，若边对应的字符与上一个字符相同，则连续数+1，且必须不超过K；若不同，则连续数重置为1。使用visited集合记录 (节点, 字符, 连续数) 避免重复访问。代码框架(Python)：
import heapq
def shortestPath(n, edges, s, K):
    graph = [[] for _ in range(n)]
    for u, v, w in edges:
        graph[u].append((v, w, s[v]))
        graph[v].append((u, w, s[u]))
    pq = [(0, 0, s[0], 1)]
    visited = set()
    while pq:
        d, u, last_c, cnt = heapq.heappop(pq)
        if (u, last_c, cnt) in visited: continue
        visited.add((u, last_c, cnt))
        if u == n - 1: return d
        for v, w, c in graph[u]:
            if c == last_c:
                if cnt + 1 <= K:
                    heapq.heappush(pq, (d + w, v, c, cnt + 1))
            else:
                heapq.heappush(pq, (d + w, v, c, 1))
    return -1
常见追问：如果要求恰好K个连续相同字符怎么处理？状态转移的时间复杂度是多少？

## 核心考点

- Dijkstra算法
- 状态压缩
- 优先队列
- 图遍历

## 常见追问

> 如果图存在负权边，该算法还能适用吗？需要改用什么算法？

**参考链接**: [https://leetcode.cn/problems/shortest-path-with-at-most-k-consecutive-identical-characters/](https://leetcode.cn/problems/shortest-path-with-at-most-k-consecutive-identical-characters/)
