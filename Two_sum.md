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
            for idx,num in enumerate(nums):
                if target - num in seen:
                    return [seen[target-num],idx]
                seen[num] = idx
    sol = Solution()
    
    nums = [2,7,11,15]
    target = 9
    print(sol.twoSum(nums,target))

## Time Complexity: O(n)
## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n²)           | O(n)             |
| Hashmap        | O(n)            | O(n)             |

### Approach
<approach>
    
    1) while iterating through for-loop always index will be first
    2) we then check if 'target-num' is in seen(initialize seen at the start)
    3) if it is then we return index of this one by 'idx' & that one by 'seen[target-num]' --> gives another index
    4) else we tell seen[num] = idx(here we assign 'idx' & 'num' to seen)[So, that 'idx' of seen && 'idx' of nums is always same]
    
</approach>
