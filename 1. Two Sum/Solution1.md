Question: https://leetcode.com/problems/two-sum/description/
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        #Brute Force
        for i in range(0,len(nums)-1):
            for j in range(i+1,len(nums)):
                if nums[i]+nums[j]==target:
                    return [i,j]
        return []

        
```
