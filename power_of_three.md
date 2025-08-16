# Power of Three

## Problem Description

Given an integer `n`, return _`true` if it is a power of three. Otherwise,
return `false`_.

An integer `n` is a power of three, if there exists an integer `x` such that
`n == 3x`.



**Example 1:**

    
    
    **Input:** n = 27
    **Output:** true
    **Explanation:** 27 = 33
    

**Example 2:**

    
    
    **Input:** n = 0
    **Output:** false
    **Explanation:** There is no x where 3x = 0.
    

**Example 3:**

    
    
    **Input:** n = -1
    **Output:** false
    **Explanation:** There is no x where 3x = (-1).
    



**Constraints:**

  * `-231 <= n <= 231 - 1`



**Follow up:** Could you solve it without loops/recursion?



## Your Submission

```python3
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        if n <= 0:
            return False
        # return True if math.log(n, 3) else False
        # return True if n % 1162261467 == 0 else False
        return True if 1162261467 % n == 0 else False
```
