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
                        
                else:
                    new.append(count)
                    count = 0
                i += 1

            new.append(count)

            return max(new) + 1
        
        
## Time Complexity: O(nlogn)
## Space Complexity: O(n) at worst case
```
</details>

## ⚡ Efficent Solution

```python

	class Solution:
	    def longestConsecutive(self, nums: List[int]) -> int:
	
	        num_set = set(nums)
	        longest = 0
	
	        for num in num_set:
	            if num - 1 not in num_set:
	                curr = num
	                count = 1
	            
	                while curr + 1 in num_set:
	                    count += 1
	                    curr += 1
	            
	                longest = max(longest,count)
	        
	        return longest

## Time Complexity: O(n)
## Space Complexity: O(n) at worst case
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(nlogn)        | O(n)             |
| Hashmap        | O(n)            | O(n)             |


<details>
<summary>Approach</summary>

    1) Approach_1 : First remove duplicate elements by using `set` keyword...then sort them[if we do it in reverse way then it won't be sorted --> sort and then set]
	2) In Approach_1 sorted function alone takes time complexity of O(logn)
	3) Approach_2: Through the hash I am checking whether the element is there or not -- O(1)
	4) So in this approach I will first check the element that is sequentially less... and also take number less than that sequentially less..so technically that number won't be in list (curr)
	5) but in the `while loop I will check curr + 1 and update the longest for every increase or not increase in the count && return the longest
    
</details>
