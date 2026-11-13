# K 次操作后非递减子数组的数目

**日期**: 2026-11-13 | **类型**: Algorithm | **原始分类**: 算法 | **路线图模块**: 13-算法 | **难度**: 高级 | **来源**: LeetCode

**Tags**: 栈, 线段树, 队列, 数组, 滑动窗口

## 解答

思路：本题要求统计最多进行 k 次「将元素减 1」的操作后，能变成非递减的子数组个数。核心观察：若只能减小元素，最优策略是从右往左处理，每个位置的有效值等于 min(自身, 右侧有效值)。因此当右端点固定为 r 时，窗口内每个元素的有效值是确定的，总代价 = sum(nums[i] - effective[i])。用滑动窗口 + 单调队列维护：队列存 (值, 个数)，从队首到队尾严格递减。加入 nums[r] 时，把队尾所有比它小的段弹出合并，代价增加 (nums[r] - v) * c；当总代价超过 k 时从左侧收缩窗口，移除最左元素只需减去它自身的代价 nums[l] - 队首值。每轮答案累加 r - l + 1。代码框架（Python）：

def countNonDecreasingSubarrays(nums, k):
    from collections import deque
    dq = deque()  # (有效值, 个数)，队首到队尾递减
    cost = ans = l = 0
    for r, x in enumerate(nums):
        cnt = 1
        while dq and dq[-1][0] < x:
            v, c = dq.pop()
            cost += (x - v) * c
            cnt += c
        dq.append((x, cnt))
        while cost > k:
            v, c = dq[0]
            cost -= v - nums[l]
            if c == 1: dq.popleft()
            else: dq[0] = (v, c - 1)
            l += 1
        ans += r - l + 1
    return ans

时间复杂度 O(n)，空间 O(n)。常见追问：为什么移除左端点只减自身代价（有效值只受右侧元素影响）；与「非递减子数组计数（无操作）」用单调栈解法的区别；能否用线段树维护区间最小值与代价。

## 核心考点

- 滑动窗口
- 单调队列/单调栈
- 均摊O(n)复杂度
- 贡献法计算代价
- 有效值从右向左传播

## 常见追问

> 如果操作是「加 1」而不是「减 1」，算法需要如何调整？

**参考链接**: [https://leetcode.cn/problems/count-non-decreasing-subarrays-after-k-operations/](https://leetcode.cn/problems/count-non-decreasing-subarrays-after-k-operations/)
