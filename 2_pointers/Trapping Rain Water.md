## Trapping Rain Water
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def trap(self, height: List[int]) -> int:
            
            n = len(height)

            left = 0
            left_res = [0] * n
            left_res[0] = height[0]

            for i in range(1,n):
                left_res[i] = max(left_res[i-1],height[i])
            
            right = n-1
            right_res = [0] * n
            right_res[n-1] = height[n-1]

            for j in range(n-2,-1,-1):
                right_res[j] = max(right_res[j+1],height[j])
            
            total = 0

            for k in range(n):
                m = min(right_res[k],left_res[k])

                diff = m - height[k]

                if diff > 0:
                    total += diff
            
            return total
                
Time Complexity: O(n)
Space Complexity: O(n)

```
</details>

<details>
<summary>Brute Force Approach</summary>

    1) Here I created left array and from the height_array I replaced with the maximum values comparing with the previous iteration
    2) Here I done the same but in reverse direction so we can assume this as right array
    3) Then I found the minimum of m = left_array[k],right_array[k] and then I subtracted  m - height[k](the actual array) which I stored as diff
    4) Here If I found that diff > 0 then I did total += diff and returned it
</details>


## ⚡ Efficent Solution

```python
    
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n)            | O(n)             |
| Hashmap        | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    
    1) 
    
</details>
