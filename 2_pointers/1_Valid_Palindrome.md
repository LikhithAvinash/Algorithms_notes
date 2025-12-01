## Valid Palindrome
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def isPalindrome(self, s: str) -> bool:
            
            l = ""
            for i in s:
                if i.isalnum():
                    l += i.lower()

            n = len(l)//2

            for j in range(n):
                if l[j] != l[len(l)-1-j]:
                        return False
            
            return True
                
Time Complexity: O(n)
Space Complexity: O(n)

```
</details>

<details>
<summary>Brute Force Idea</summary>
    1) Here in this I created 'l' where this variable stores all the elements that aren't alpha numeric and also stores them as lowercase
    2) In the 2nd for loop I compare & decide
</details>

## ⚡ Efficent Solution
        
```python
    class Solution:
    def isPalindrome(self, s: str) -> bool:
        
        i, j = 0,len(s) -1
    
        while i < j:

            while i < j and not s[i].isalnum():
                i += 1
            while i < j and not s[j].isalnum():
                j -= 1
            
            if s[i].lower() != s[j].lower():
                return False
            
            i += 1
            j -= 1
            
        return True

Time Complexity: O(n)
Space Complexity: O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n)            | O(n)             |
| Hashmap        | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    1) Here in this I am directly checking whether the front & back side of the characters are not alpha numeric or not
    2) if they are then...I return False
    3) else they are been moved to next characther(for example i = 0 to i = 1 &&&& j = len(s) -1 to len(s) -2
    
</details>
