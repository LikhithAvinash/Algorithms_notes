## Sliding Window Maximum
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
            n = len(nums)
            r = 0
            count = 0
            val = []
            maxi = float('-inf')

            if n < k:
                return nums

            for l in range(n-k+1):
                while count < k:
                    maxi = max(maxi,nums[r])
                    count += 1
                    r += 1
                    
                val.append(maxi)
                maxi = float('-inf')
                count -= count
                r = l + 1
            
            return val
            

## Time Complexity: O(n*m)
## Space Complexity: O(1)
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
| Brute Force    | O(n*m)          | O(1)             |
| Sliding Window | O(n+m)          | O(n)             |


<details>
<summary>Approach</summary>

    1) Hash approach - Here I found no. of letters for string1 irrespective of string2 and also I calculated no. of letters for string2 irrespective of string1
    2) Library approach - Here I just Imported Library and checked it(this library contiains the above approach code in it)
    
</details>


