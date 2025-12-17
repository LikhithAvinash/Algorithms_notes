## Minimum Window Substring

## ⚡ Efficent Solution
Sliding Window algo approach
```python
    class Solution:
        def minWindow(self, s: str, t: str) -> str:
            
            if t == "":
                return ""
            
            count , window = {},{}

            for c in t:
                count[c] = 1 + count.get(c,0)
            
            have,need = 0,len(count)
            res,resLen = [-1,-1], float('inf')
            l = 0

            for r in range(len(s)):
                m = s[r]

                window[m] = 1 + window.get(m,0)

                if m in count and window[m] == count[m]:
                    have += 1
                
                while have == need:
                    if (r-l+1) < resLen:
                        res = [l,r]
                        resLen = r-l+1
                    
                    window[s[l]] -= 1
                    if s[l] in count and window[s[l]] < count[s[l]]:
                        have -= 1
                    l += 1
            
            l,r = res
            return s[l:r+1] if resLen != float('inf') else ""



# Time Complexity - O(n)
# Space Complexity - O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|     |
| Sliding Window | O(n)            | O(m)             |

<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    
    1) I am assuming left pointer as 'l',if I find any duplicate elements while adding it to the my set I will just remove it(this is under while loop)
    2) so the above thing will remove elements till it finds out that there is not such element in my set
    3) Also left pointer is incremented so that it assumes like the substring starts from that particular [l] index
    4) if I dont find any duplicate element(the element which is already in my set) then I will keep on adding the new one
    5) max_len variable gives me the updated max lenght of the substring
</details>

