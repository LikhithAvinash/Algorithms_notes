## Minimum Stack

## ⚡ Efficent Solution

```python
    
    class Solution:
        def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
            n = len(nums)
            r = 0
            count = 0
            val = []
            maxi = float('-inf')
    
            if n < k:
                return nums
    
            for l in range(n-k+1):
                while count < k:
                    maxi = max(maxi,nums[r])
                    count += 1
                    r += 1
                    
                val.append(maxi)
                maxi = float('-inf')
                count -= count
                r = l + 1
            
            return val

                
# Time Complexity - O(1)
# Space Complexity - O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|     |
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

