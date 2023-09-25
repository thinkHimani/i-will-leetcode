Question: https://leetcode.com/problems/climbing-stairs/
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        #Solving with DP array of size 2
        one, two = 1, 1
        for i in range(n-1):
            temp = one
            one = one + two
            two = temp
        return one
```
