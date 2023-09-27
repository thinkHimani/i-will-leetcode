Question: https://leetcode.com/problems/kth-largest-element-in-an-array/description/
```python
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        heap = nums
        heapq.heapify(nums)  # - O(n)
        while len(heap) > k:
            heapq.heappop(heap)     
        return heap[0]

        # Option1: Sorting the array directly - O(nlogn) -> get (length-k)th element in O(1)
        # Option2: heapify entire array O(n) - pop until length is k k*(logn) - print root -> O(n+klogn) -> thus slightly better than option1
        #Option3: avg case O(n) & worst case O(n^2)
```
