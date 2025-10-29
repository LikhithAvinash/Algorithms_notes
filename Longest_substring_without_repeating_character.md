## Longest Subtring without Repeating
<details>
<summary>Brute Force Solution</summary>
    
```python
class Solution:
  def lengthOfLongestSubstring(self, s: str) -> int:
      e = list(s)
      n = len(e)
      idx_1 = 0
      idx_2 = 0
      l = [] 
      total = []
      
      if len(s) == 0:
          return 0

      while idx_2 < n:
          if idx_1 == 0 and idx_2 == 0:
              p1 = e[idx_1]
              l.append(e[idx_2])
              idx_2 += 1

          elif e[idx_2] not in l:
              p2 = e[idx_2]
              l.append(p2)
              idx_2 += 1
          
          else:
              total.append(len(l))
              r = l.remove(e[idx_1]) # remove keyword works by passing in it a value
              idx_1 += 1
              
      total.append(len(l))
          
      m = 0    
      for j in range(len(total)):
          if total[j] > m:
              m = total[j]     
      return m

sol = Solution()
s = 'abcabcabc'
print(sol.lengthOfLongestSubstring(s))
```
</details>

## ⚡ Efficent Solution
Sliding Window algo approach
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        l = 0
        sett = set()
        max_len = 0
    
        for r in range(len(s)):
            while s[r] in sett:
                sett.remove(s[l])
                l += 1
            
            sett.add(s[r])
            max_len = max(max_len,r-l+1)
        
        return max_len
sol = Solution()
s = "abcabcabc"
print(sol.lengthOfLongestSubstring(s))
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n)            | O(n)             |
| Hashmap        | O(n)            | O(n)             |

<details>
<summary>Approach</summary>
    <b>Understanding</b> - I need to find the Longest substring that doesn't have any duplicate characters from the s(given parameter)
    1) I am assuming left pointer as 'l',if I find any duplicate elements while adding it to the my set I will just remove it(this is under while loop)
    2) so the above thing will remove elements till it finds out that there is not such element in my set
    3) Also left pointer is incremented so that it assumes like the substring starts from that particular [l] index
    4) if I dont find any duplicate element(the element which is already in my set) then I will keep on adding the new one
    5) max_len variable gives me the updated max lenght of the substring
</details>
