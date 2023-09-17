```python
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        myMap = {")":"(", "}":"{", "]":"["}
        for c in s:
            if c in myMap:
                if stack and stack[-1] == myMap[c]:
                    stack.pop()
                else:
                    return False
            else:
                stack.append(c)
        if not stack:
            return True
        else:
            return False

    #Time: O(n) Memory:O(n)
```
