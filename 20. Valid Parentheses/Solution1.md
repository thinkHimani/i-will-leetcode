Question: https://leetcode.com/problems/valid-parentheses/
```python
class Solution(object):
    def isValid(self, s):
        stackopen = []
        output = False

        for ch in s:
            if (ch == '(') or (ch == '[') or (ch == '{'):
                stackopen.append(ch)
            elif ((ch == ')') or (ch == ']') or (ch == '}')) and len(stackopen)==0:
                output = False
                break
            elif ((ch == ')') or (ch == ']') or (ch == '}')) and len(stackopen)>0:
                st = stackopen.pop()
                if (ch == ')' and st == '(') or (ch == ']' and st == '[') or (ch == '}' and st == '{'):
                    output = True
                    continue
                else:
                    output = False
                    break
            else:
                output = False

        if len(stackopen)!=0:
                output = False
                
        return output
```
