Question: https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        totalp = 0
        if len(prices)>1:
            buy, sell = 0, 1
            while sell<len(prices):
                if prices[sell]-prices[buy]>0:
                    totalp = totalp + prices[sell]-prices[buy]
                    buy += 1
                    sell += 1
                else:
                    buy += 1
                    sell += 1
        return totalp
```
