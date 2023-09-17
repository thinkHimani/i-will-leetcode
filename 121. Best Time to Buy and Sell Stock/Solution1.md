Question: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        if len(prices)>1:
            L, R = 0, 1
            maxp = prices[R]-prices[L]

            while R < len(prices)-1:
                if prices[R]<prices[L]:
                    L = R 
                    R += 1
                    maxp = max(maxp, prices[R]-prices[L])
                else:
                    R += 1
                    maxp = max(maxp, prices[R]-prices[L])
            return max(maxp, 0)
        return 0
```
