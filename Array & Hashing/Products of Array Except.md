## Products of Array Except Self
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def productExceptSelf(self, nums: List[int]) -> List[int]:
            
            prod = 1
            n = len(nums)
            count_0 = 0

            for s in range(n):
                if nums[s] != 0:
                    prod = nums[s] * prod
                
                else:
                    count_0 += 1
                    k = s
            
            if count_0 == 1:
                return [prod if k == i else 0 for i in range(n) ]
            
            if count_0 > 1:
                return n * [0]
            
            new = []
            for j in range(n):
                val = int(prod / nums[j])
                new.append(val)
            return new

## Time Complexity: O(n)
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
| Brute Force    | O(n)          | O(1)             |
| Hashmap        | O(n)          | O(1)             |



<details>
<summary>Approach</summary>

    1) Hash approach - Here I found no. of letters for string1 irrespective of string2 and also I calculated no. of letters for string2 irrespective of string1
    2) Library approach - Here I just Imported Library and checked it(this library contiains the above approach code in it)
    
</details>


