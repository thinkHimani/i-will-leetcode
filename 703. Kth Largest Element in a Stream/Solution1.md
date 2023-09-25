Question: https://leetcode.com/problems/kth-largest-element-in-a-stream/
```python
class KthLargest:

    def __init__(self, k: int, nums: List[int]):
        #creating a min heap of k largest element
        self.minHeap = nums
        self.k = k
        heapq.heapify(self.minHeap) #O(n)
        while len(self.minHeap) > k :
            heapq.heappop(self.minHeap)

    def add(self, val: int) -> int:
        heapq.heappush(self.minHeap, val)
        if len(self.minHeap) > self.k:
            heapq.heappop(self.minHeap)
        return self.minHeap[0]


# Your KthLargest object will be instantiated and called as such:
# obj = KthLargest(k, nums)
# param_1 = obj.add(val)
```