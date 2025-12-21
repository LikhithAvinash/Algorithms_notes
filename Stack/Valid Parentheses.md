## Valid Parentheses

## ⚡ Efficent Solution
Sliding Window algo approach
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
                
# Time Complexity - O(n)
# Space Complexity - O(1)
```
| Approach        | Time Complexity | Space Complexity |
|-----------------|-----------------|------------------|
| Efficent Method | O(n)            | O(1)             |


<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    
    1) I am assuming left pointer as 'l',if I find any duplicate elements while adding it to the my set I will just remove it(this is under while loop)
    2) so the above thing will remove elements till it finds out that there is not such element in my set
    3) Also left pointer is incremented so that it assumes like the substring starts from that particular [l] index
    4) if I dont find any duplicate element(the element which is already in my set) then I will keep on adding the new one
    5) max_len variable gives me the updated max lenght of the substring
</details>

