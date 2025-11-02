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
