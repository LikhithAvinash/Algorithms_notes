## Two Sum
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def twoSum(self, nums: list[int], target: int) -> list[int]:
            for i in range(len(nums)):
                for j in range(i+1,len(nums)):
                    if nums[i] + nums[j] == target:
                        return [i,j]
    sol = Solution()
    
    nums = [2,7,11,15]
    target = 9
    print(sol.twoSum(nums,target))

## Time Complexity: O(n**2)
## Space Complexity: O(n)
```
</details>

## ⚡ Efficent Solution

```python
    class Solution:
        def twoSum(self, nums: list[int], target: int) -> list[int]:
            seen = {}
            for i,num in enumerate(nums):
                if target - num in seen:
                    return [seen[target-num],i]
                seen[num] = i
    sol = Solution()
    
    nums = [2,7,11,15]
    target = 9
    print(sol.twoSum(nums,target))

## Time Complexity: O(n)
## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n²)           | O(1)             |
| Hashmap        | O(n)            | O(n)             |

