## Two Sum
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        n = len(nums)
        seen = []
        
        for i in range(n):
            if nums[i] not in seen:
                seen.append(nums[i])
            else:
                return True
        
        return False

## Time Complexity: O(n**2)
## Space Complexity: O(n)
```
</details>

## ⚡ Efficent Solution

```python
    class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        n = len(nums)
        seen = set()
        
        for i in range(n):
            if nums[i] not in seen:
                seen.add(nums[i])
            else:
                return True
        
        return False

## Time Complexity: O(n)
## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n²)           | O(n)             |
| Hashmap        | O(n)            | O(n)             |



<details>
<summary>Approach</summary>

    1) List approach- I used list so it goes checks through the entire new list for every element - O(n)
    2) Hash approach- I used set so if any element I wanna check then simply it checks the hash value of it(if hash value exits then the element is present....if not then the element is not present(O(1))
    
</details>

