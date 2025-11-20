## Valid Anagram
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
    	def isAnagram(self, s: str, t: str) -> bool:
        
		freq = {}

		for i in s:
		    if i not in freq:
		        freq[i] = 1
		    else:
		        freq[i] += 1

		Freq = {}

		for j in t:
		    if j not in Freq:
		        Freq[j] = 1
		    else:
		        Freq[j] += 1
		
		if freq == Freq:
		    return True
		else:
		    return False
        
        

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
| Brute Force    | O(n+m)          | O(n)             |
| Hashmap        | O(n+m)          | O(n)             |



<details>
<summary>Approach</summary>

    1) Hash approach - Here I found no. of letters for string1 irrespective of string2 and also I calculated no. of letters for string2 irrespective of string1
    2) Library approach - Here I just Imported Library and checked it(this library contiains the above approach code in it)
    
</details>


