## 3Sum
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def threeSum(self, nums: List[int]) -> List[List[int]]:

            s = set()
            n = len(nums)
            res = []
            for i in range(n):

                for j in range(i+1,n):

                    for k in range(j+1,n):

                        if nums[i] + nums[j] + nums[k] == 0:

                            l = sorted([nums[i],nums[j],nums[k]])
            

                            if l not in res:
                                res.append(l)
            return res
                
Time Complexity: O(n**3)
Space Complexity: O(n)

```
</details>

<details>
<summary>Method of Brute Force Solution</summary>
    
    1) Here I used 3 for loops and iterated such that I am not iterating through element of same index
    2) So after 3 for loops checking if res[i] + res[j]+res[k] == 0 then append it(res=[])
    3) But there is a problem...res might have duplicate elements so I will like add only if this list isn't in the `res`
</details>

## ⚡ Efficent Solution

```python
    class Solution:
        def threeSum(self, nums: List[int]) -> List[List[int]]:
    
            nums.sort()
            n = len(nums)
            res = []
    
            for i in range(n):
                if i > 0 and nums[i] == nums[i-1]:
                    continue
                
                left,right = i + 1,n-1
    
                while left < right:
    
                    result = nums[left] + nums[right] + nums[i]
    
                    if result < 0:
                        left += 1
                    
                    elif result > 0:
                        right -= 1
                    
                    else:
                        res.append([nums[i],nums[left],nums[right]])
    
                        while left < right and nums[left] == nums[left+1]:
                            left += 1
                        
                        while left < right and nums[right] == nums[right-1]:
                            right -= 1
                        
                        left += 1
                        right -= 1
            return res
            
Time Complexity: O(n**2)
Space Complexity: O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n**3)          | O(n)             |
| Hashmap        | O(n**2)          | O(1)             |

<details>
<summary>Approach</summary>
    
    1) 
    2) Here I am checking if `result` is actually less than `0` then I need to make sure my I need to increment the nums(as it sorted incrementing it to the right side make sure the next element I get is bigger than the current element)
    3) Similarly for `result` greater than 0 I need to decrement my right index as decrement would give small number(In the sorted list)
    4) if this 2 weren't then it means that the result is correct. SO we append it to our main list
    5) Here Instead of checking the duplicate elements like `if result not in result: res.append(result)...O(n)... I am checking if there is a duplicate element on the left then increment till I don't have any duplicate
    6) for right also to not count duplicate I am decrementing countinuesly 
    7 Finally out of the loop I am return res...(which is all the elements that are appended to the res)
    
</details>
