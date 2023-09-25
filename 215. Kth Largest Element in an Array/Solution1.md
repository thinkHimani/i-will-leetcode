Question: https://leetcode.com/problems/kth-largest-element-in-an-array/description/
```python
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        heap = nums
        heapq.heapify(nums)
        while len(heap) > k:
            heapq.heappop(heap)
        return heap[0]
```
