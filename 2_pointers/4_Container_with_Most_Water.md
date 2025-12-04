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

## Normal Solution
```python
        class Solution:
            def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
                
                all = []
                for j in strs:
                    freq = {}
                    for i in j:
                        if i not in freq:
                            freq[i] = 1
                        else:
                            freq[i] += 1
                    all.append(freq)

                new = []

                for m in range(len(all)):
                    sub = []
                    for n in range(len(all)):

                        if all[m] == all[n]:
                            sub.append(strs[n])
                        
                    new.append(sub)
                
                a = []
                for l in new:
                    if l not in a:
                        a.append(l)

                return a
Time Complexity: O(n)
Space Complexity: O(1)
```
## ⚡ Efficent Solution

```python
    
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n)            | O(n)             |
| Hashmap        | O(n)            | O(1)             |

<details>
<summary>Approach</summary>
    
    1) while iterating through for-loop always index will be first
    2) we then check if 'target-num' is in seen(initialize seen at the start)
    3) if it is then we return index of this one by 'idx' & that one by 'seen[target-num]' --> gives another index
    4) else we tell seen[num] = idx(here we assign 'idx' & 'num' to seen)[So, that 'idx' of seen && 'idx' of nums is always same]
    
</details>
