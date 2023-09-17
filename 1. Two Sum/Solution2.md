Question: https://leetcode.com/problems/two-sum/description/
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        #Hash Map
        prevVal = {} #val:index
    
        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevVal:
                return [prevVal[diff], i]
            prevVal[n] = i
        return []

        
```
