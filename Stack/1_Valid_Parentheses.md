## Valid Parentheses

## ⚡ Efficent Solution
Sliding Window algo approach
```python
    
    class Solution:
        def isValid(self, s: str) -> bool:
            stack = []
            hashmap = {')':'(','}':'{',']':'['}
    
            for c in s:
                if c in hashmap:
                    if stack and stack[-1] == hashmap[c]:
                        stack.pop()
                    else:
                        return False
                else:
                    stack.append(c)
    
            return True if not stack else False
                
# Time Complexity - O(n)
# Space Complexity - O(1)
```
| Approach        | Time Complexity | Space Complexity |  
|-----------------|-----------------|------------------|  
| Efficent Method | O(n)            | O(1)             |  


<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    
    1) I initialized stack = [] to store open parenthesis && I created hashmap list ok key contining closed of different types of brackets
    2) So here if the element is not in hashmap(sees key which contain closed) then append it to the stack 
    3) if the element is hashmap then compare the previous element(stack[-1]) and current element value(by hashmpa[c])  if those are equal I will  pop the open parenthesis from stack
    4) if stack is empty it means but there is element that is still left out that means that open parthensis or closed paranthesis are more or unequal so I return False
</details>

