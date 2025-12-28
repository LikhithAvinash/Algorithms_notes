## Minimum Stack

## ⚡ Efficent Solution

```python
    
    class MinStack:
        def __init__(self):
            self.stk = []
            self.min_stk = []
    
        def push(self, val: int) -> None:
            self.stk.append(val)
    
            if not self.min_stk:
                self.min_stk.append(val)
            elif self.min_stk[-1] < val:
                self.min_stk.append(self.min_stk[-1])
            else:
                self.min_stk.append(val)
    
        def pop(self) -> None:
            self.stk.pop()
            self.min_stk.pop()
    
        def top(self) -> int:
            return self.stk[-1]
    
        def getMin(self) -> int:
            return self.min_stk[-1]
        

                
# Time Complexity - O(1)
# Space Complexity - O(1)
```
| Approach       | Time Complexity | Space Complexity |  
|----------------|-----------------|------------------|       
| Efficent method| O(1)            | O(1)             |  

<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    
    1) I appended element for normal stack just buy using append but for minimum stack I did make sure the top of the element is minimum of previous element
    2) Here I appended(Pushed) in 3 different ways for minimum stack
    3) 1st way when there is no elemenet in the stack
    4) 2nd way when the element is more than previous element I append the previous element again(as in the next step I pop again)
    5) 3rd way when the element is when the previous element is small than previous element I append current element(val)
</details>

