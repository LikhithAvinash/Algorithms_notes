## Evaluate Reverse Polish Notation

## ⚡ Efficent Solution

```python
    class Solution:
        def evalRPN(self, tokens: List[str]) -> int:
            
            stack = []

            for token in tokens:

                if token in {'+','-','*','/'}:
                    b = stack.pop()
                    a = stack.pop()

                    if token == '+':
                        stack.append(a+b)
                    elif token == '-':
                        stack.append(a-b)
                    elif token == '*':
                        stack.append(a*b)
                    elif token == '/':
                        stack.append(int(a/b))

                else:
                    stack.append(int(token))

            return stack[0]


# Time Complexity - O(n)
# Space Complexity - O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|     |
| Sliding Window | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    
    1) In this I append every element other than those particular operators('+ o,'-','*','/')
    2) To be exactly..if I see those operators I pop out last 2 elements from the stack
    3) Initialize it as 'a' & 'b'
    4) Do all the arithmetic operations and append it to the stack
    5) I return the top of the stack[-1]---> This gives the result
</details>

