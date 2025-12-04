## Container with Most Water
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def maxArea(self, heights: List[int]) -> int:
            
            m = 0
            n = len(heights)
            count = n - 1 # 7
            val = 0

            for i in range(n):
                for j in range(i+1,n):
                    m = min(heights[i],heights[j])
                    b = j - i
                    val = max(val,m*b) 
                
            return val
                         
Time Complexity: O(n**2)
Space Complexity: O(1)

```
</details>

<details>
<summary>Method for Brute Force Approach</summary>
    
    1) Initiate val and count then write 2 for loops
    2) Here 1st get the minimum height of 2 heights one in 1st for loop(i) and the other one in 2nd for loop(j) --> m =  min(heights[i],heights[j])  
    3) Then put breadth which is b = i -j 
    4) so the val will be b * m -----> which gives the maximum area in a given array
    5) simply store the maximum value in a variable & return it
</details>

## ⚡ Efficent Solution

```python
    class Solution:
        def maxArea(self, heights: List[int]) -> int:
            
            n = len(heights)
    
            low,high = 0,n-1
            m = 0
            val = 0
    
            while low < high:
    
                m = min(heights[low],heights[high]) * (high - low)
                val = max(m,val)
    
                if heights[low] < heights[high]:
                    low += 1
                
                elif heights[high] < heights[low]:
                    high -= 1
                
                else:
                    low += 1
                    high -= 1
            
            return val

Time Complexity: O(n)
Space Complexity: O(1)

            
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n*2)          | O(1)             |
| 2 Pointers     | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    
    1) I approached this problem through 2 pointers approach.. one as `low` & the other one as `high`
    2) Here I wrote `while low < high`
    3) `m = min(heights[low],heights[high]) * (high - low)` where multiplying the minium number with the index difference between them
    4) The approach I didn't thought of above is `if heights[low] < height[high]` then increment low and decrement for high so this approach tries to find the maximum possible way &&& that is multiplied of index
    5) even if the 2 numbers are at the single side..side to each other it still works...not like n//2..where this checks only half but this while low < high... is gonna search the entire array(even if those are side to each other) ~ doesn't miss this kind of test case
    
</details>
