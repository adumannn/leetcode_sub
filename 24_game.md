# 24 Game

## Problem Description

You are given an integer array `cards` of length `4`. You have four cards,
each containing a number in the range `[1, 9]`. You should arrange the numbers
on these cards in a mathematical expression using the operators `['+', '-',
'*', '/']` and the parentheses `'('` and `')'` to get the value 24.

You are restricted with the following rules:

  * The division operator `'/'` represents real division, not integer division. 
    * For example, `4 / (1 - 2 / 3) = 4 / (1 / 3) = 12`.
  * Every operation done is between two numbers. In particular, we cannot use `'-'` as a unary operator. 
    * For example, if `cards = [1, 1, 1, 1]`, the expression `"-1 - 1 - 1 - 1"` is **not allowed**.
  * You cannot concatenate numbers together 
    * For example, if `cards = [1, 2, 1, 2]`, the expression `"12 + 12"` is not valid.

Return `true` if you can get such expression that evaluates to `24`, and
`false` otherwise.



**Example 1:**

    
    
    **Input:** cards = [4,1,8,7]
    **Output:** true
    **Explanation:** (8-4) * (7-1) = 24
    

**Example 2:**

    
    
    **Input:** cards = [1,2,1,2]
    **Output:** false
    



**Constraints:**

  * `cards.length == 4`
  * `1 <= cards[i] <= 9`



## Your Submission

```python3
class Solution:
    def judgePoint24(self, cards: List[int]) -> bool:
        nums = [float(c) for c in cards]
        return self.solve(nums)

    def solve(self, nums: List[float]) -> bool:
        if len(nums) == 1:
            return abs(nums[0] - 24.0) < 1e-6

        n = len(nums)
        for i in range(n):
            for j in range(n):
                if i == j:
                    continue

                next_nums = [nums[k] for k in range(n) if k != i and k != j]
                a, b = nums[i], nums[j]

                results = [a + b, a - b, b - a, a * b]
                if abs(b) > 1e-6:
                    results.append(a / b)
                if abs(a) > 1e-6:
                    results.append(b / a)

                for val in results:
                    if self.solve(next_nums + [val]):
                        return True
        return False
```
