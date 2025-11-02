## Longest Palindromic Substring
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
      def longestPalindrome(self, s: str) -> str:
        res = ""
        max_len = 0
        n = len(s)

        for i in range(n):
            for j in range(i,n):
                sub = s[i:j+1]
                if sub == sub[::-1]:
                    if len(sub) > len(res):
                        res = sub
        return res
    
    s = "babad"
    print(sol.twoSum(s))

## Time Complexity: O(n**3)
## Space Complexity: O(n)
```
</details>

## ⚡ Efficent Solution

```python
    class Solution:
   def longestPalindrome(self, s: str) -> str:
        res = ""
        max_len = 0

        ## odd length
        for i in range(len(s)):
            r,l = i,i
            while l >= 0 and r < len(s) and s[l] == s[r]:
                if max_len < (r - l + 1):
                    res = s[l:r+1]
                    max_len = r - l + 1
            
                l -= 1
                r += 1
        
        ## even length 
        
            r,l = i+1,i
            while l >= 0 and r < len(s) and s[l] == s[r]:
                if max_len < (r - l + 1):
                    res = s[l:r+1]
                    max_len = r - l + 1
                
                l -= 1
                r += 1
        
        return res

## Time Complexity: O(n*2)
## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n**3)         | O(n)             |
| Hashmap        | O(n*2)          | O(n)             |

<details>
  <summary>📊 Approach</summary>
  <img 
    src="https://github.com/LikhithAvinash/Algorithms_notes/blob/master/assets/prob5.png" 
    alt="Traditional vs Evolutionary Models" 
    width="675" 
    height="899" 
  />
</details>
