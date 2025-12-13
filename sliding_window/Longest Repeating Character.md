## Longest Repeating Character Replacement

## ⚡ Efficent Solution
Sliding Window algo approach
```python
    class Solution:
        def characterReplacement(self, s: str, k: int) -> int:
            
            n = len(s)
            l  = 0
            count = [0] * 26
            maxi = 0

            for r in range(n):
                count[ord(s[r])-65] += 1

                while (r-l+1) - max(count) > k:
                    count[ord(s[l])-65] -= 1
                    l += 1
                
                maxi = max(maxi,r-l+1)
            
            return maxi


```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|     
| Sliding Window | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    
    1) I am assuming left pointer as 'l',if I find any duplicate elements while adding it to the my set I will just remove it(this is under while loop)
    2) so the above thing will remove elements till it finds out that there is not such element in my set
    3) Also left pointer is incremented so that it assumes like the substring starts from that particular [l] index
    4) if I dont find any duplicate element(the element which is already in my set) then I will keep on adding the new one
    5) max_len variable gives me the updated max lenght of the substring
</details>

