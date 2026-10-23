# 排序排列的最大K值

**日期**: 2026-10-23 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 中级 | **来源**: LeetCode

**Tags**: 位运算, 数组

## 解答

思路：假设题目要求找到最大的K，使得可以通过交换距离为K的元素来对排列进行排序。对于给定的K，如果可以通过交换距离为K的元素来排序，那么对于所有下标i，i mod K相同的元素集合必须能够通过排序恢复原位。也就是说，把数组按i mod K分组，每组排序后应该等于原数组对应位置排序后的值。寻找最大的K，使得这个条件成立。
代码框架：
```python
def max_k_to_sort(perm):
    n = len(perm)
    sorted_perm = sorted(perm)
    def check(k):
        for r in range(k):
            group = []
            for i in range(r, n, k):
                group.append(perm[i])
            group.sort()
            idx = 0
            for i in range(r, n, k):
                if group[idx] != sorted_perm[i]:
                    return False
                idx += 1
        return True
    for k in range(n - 1, 0, -1):
        if check(k):
            return k
    return 1
```
常见追问点：时间复杂度是多少？如何优化check函数避免重复排序？

## 核心考点

- 数组分组
- 排序验证
- 贪心策略
- 时间复杂度优化

## 常见追问

> 如何优化check函数的时间复杂度，使其在O(N)内完成？

**参考链接**: [https://leetcode.cn/problems/maximum-k-to-sort-a-permutation/](https://leetcode.cn/problems/maximum-k-to-sort-a-permutation/)
