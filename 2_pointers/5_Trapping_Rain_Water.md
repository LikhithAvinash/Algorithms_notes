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
    class Solution:
        def trap(self, height: List[int]) -> int:
            
            n = len(height)
            low,high = 0,n-1
            left_max, right_max = 0,0
            total = 0
    
            while low < high:
                if height[low] <= height[high]: # we are gonna take the min one
                    if height[low] >= left_max: # max of left values
                        left_max = height[low]
                    else:
                        total += left_max - height[low]
                
                    low += 1
    
                else:
                    if height[high] >= right_max:
                        right_max = height[high]
                    else:
                        total += right_max - height[high]
                    
                    high -= 1
            
            return total


```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| DP             | O(n)            | O(n)             |
| 2 pointers     | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    
    1) So here first checking the minimum element of height[low] & height[high]
    2) From there I comparing the maximum value of the previous iteration and with the height[left](In case of left), height[right](In case of right)
    3) Then I am doing max_left(left case), max_right(right case) - height[low](left case), height[right](right case)
    4) then adding it to the total value ----> total += of the point 3
    5) here I did the same approach as the brute force but in this I am not using any array(using variable to store single value) so the space complexity is gonna be O(1)
    
</details>
