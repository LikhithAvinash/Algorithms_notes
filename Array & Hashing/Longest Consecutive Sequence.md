## Longest Consecutive Sequence
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def longestConsecutive(self, nums: List[int]) -> int:

            a = set(nums)
            o = list(sorted(a))
            n = len(o)

            count = 0
            new = []
            i = 0

            if n == 0:
                return 0

            while i < n - 1:   
                if o[i+1] - o[i] == 1:
                    count += 1
                    val = True
                        
                else:
                    new.append(count)
                    count = 0
                i += 1

            new.append(count)

            return max(new) + 1
        
        
## Time Complexity: O(n**2)
## Space Complexity: O(n)
```
</details>

## ⚡ Efficent Solution

```python

	from collections import Counter
		class Solution:
		    def isAnagram(self, s: str, t: str) -> bool:
			if Counter(s) == Counter(t):
			    return True
			else:
			    return False
			    
## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(nlogn)        | O(n)             |
| Hashmap        | O(n)            | O(n)             |



<details>
<summary>Approach</summary>

    1) Hash approach - Here I found no. of letters for string1 irrespective of string2 and also I calculated no. of letters for string2 irrespective of string1
    2) Library approach - Here I just Imported Library and checked it(this library contiains the above approach code in it)
    
</details>
