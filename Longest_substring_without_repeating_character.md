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
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n)            | O(n)             |
| Hashmap        | O(n)            | O(n)             |



<details>
<summary>Approach</summary>
    1) **Understanding**
    
</details>
