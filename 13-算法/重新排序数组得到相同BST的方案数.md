# 重新排序数组得到相同BST的方案数

**日期**: 2026-10-18 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 高级 | **来源**: LeetCode

**Tags**: 树, 并查集, 二叉搜索树, 记忆化, 数组

## 解答

思路：BST的根节点始终是数组的第一个元素。根节点确定后，比根小的元素构成左子树，比根大的构成右子树。关键性质是：左子树元素之间的相对顺序和右子树元素之间的相对顺序必须保持不变，但左右子树的元素可以任意交错排列。因此方案数为：C(n-1, left_count) * ways(left) * ways(right)，其中n-1是除去根后的元素总数，left_count是左子树元素个数。使用分治递归处理左右子树，组合数用费马小定理求逆元。代码框架(Python)：

MOD = 10**9+7
def numOfWays(nums):
    n = len(nums)
    # 预处理组合数
    fact = [1]*(n+1)
    inv = [1]*(n+1)
    for i in range(1,n+1): fact[i]=fact[i-1]*i%MOD
    inv[n]=pow(fact[n],MOD-2,MOD)
    for i in range(n-1,-1,-1): inv[i]=inv[i+1]*(i+1)%MOD
    def C(n,r): return fact[n]*inv[r]%MOD*inv[n-r]%MOD if 0<=r<=n else 0
    def dfs(arr):
        if len(arr)<=2: return 1
        root=arr[0]
        left=[x for x in arr[1:] if x<root]
        right=[x for x in arr[1:] if x>root]
        return C(len(arr)-1,len(left))*dfs(left)%MOD*dfs(right)%MOD
    return (dfs(nums)-1)%MOD

常见追问：为什么结果要减1？因为题目要求不同于原数组的排列数，dfs返回的是包含原始排列的总方案数。

## 核心考点

- 二叉搜索树性质
- 组合数学与交错排列
- 分治递归
- 费马小定理求逆元
- 动态规划记忆化

## 常见追问

> 如果BST节点值有重复，该如何修改算法？

**参考链接**: [https://leetcode.cn/problems/number-of-ways-to-reorder-array-to-get-same-bst/](https://leetcode.cn/problems/number-of-ways-to-reorder-array-to-get-same-bst/)
