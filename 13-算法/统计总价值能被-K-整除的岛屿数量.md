# 统计总价值能被 K 整除的岛屿数量

**日期**: 2026-10-26 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 深度优先搜索, 广度优先搜索, 并查集, 数组, 矩阵

## 解答

思路：本题是经典的矩阵连通块问题。首先遍历整个矩阵，当遇到一个未被访问且值不为0的格子时，启动深度优先搜索（DFS）或广度优先搜索（BFS）。在搜索过程中，累加该岛屿所有格子的值，并将访问过的格子标记为已访问（可使用visited矩阵或直接将原格子置0）。搜索结束后，检查该岛屿的总价值是否能被K整除，若能整除则结果计数加1。代码框架（Python）：
def count_islands(grid, k):
    m, n = len(grid), len(grid[0])
    visited = [[False]*n for _ in range(m)]
    def dfs(x, y):
        if x < 0 or x >= m or y < 0 or y >= n or visited[x][y] or grid[x][y] == 0:
            return 0
        visited[x][y] = True
        total = grid[x][y]
        for dx, dy in [(1,0),(-1,0),(0,1),(0,-1)]:
            total += dfs(x+dx, y+dy)
        return total
    count = 0
    for i in range(m):
        for j in range(n):
            if grid[i][j] != 0 and not visited[i][j]:
                if dfs(i, j) % k == 0:
                    count += 1
    return count
常见追问点：如果矩阵非常大导致递归栈溢出，该如何处理？

## 核心考点

- DFS/BFS
- 矩阵遍历
- 连通分量
- 状态标记
- 取模运算

## 常见追问

> 如果矩阵非常大导致递归栈溢出，该如何处理？

**参考链接**: [https://leetcode.cn/problems/count-islands-with-total-value-divisible-by-k/](https://leetcode.cn/problems/count-islands-with-total-value-divisible-by-k/)
