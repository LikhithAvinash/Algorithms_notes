## Group Anagram
<details>
<summary>Brute Force Solution</summary>
    
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
                for n in range(m,len(all)-1):

                    if all[n] == all[n+1] and len(sub) == 0:
                        sub.append(all[n])
                        sub.append(all[n+1])

                    elif all[n] == all[n+1] and len(sub) != 0:
                        sub.append(all[n+1])
                    
                
                new.append(sub)

            return new
```
</details>

<details>
<summary>Reason for the Above Failed Approach</summary>
    
    1) Here in the 2nd nested loop I am checking the adjacent element but not the complete list So, it gives me wrong answer          
    2) In the 2nd for loop last element is not checked ~ Leads to inaccurate answer  
    3) I am appending freq dicts into it ~Leetcode don't get the expected and gives Error. 
    4) 4th Error is the below image shown from the chatgpt 

4) <img alt="Returns Empty List" src="../assets/Mistake_group_anagram.png" />

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
Time Complexity: O(n**2 * k)
Space Complexity: O(n**2)
```
## ⚡ Efficent Solution

```python
    
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n² * k)       | O(n²)            |
| Hashmap        | O(n)            | O(n)             |

<details>
<summary>Approach</summary>
    
    1) while iterating through for-loop always index will be first
    2) we then check if 'target-num' is in seen(initialize seen at the start)
    3) if it is then we return index of this one by 'idx' & that one by 'seen[target-num]' --> gives another index
    4) else we tell seen[num] = idx(here we assign 'idx' & 'num' to seen)[So, that 'idx' of seen && 'idx' of nums is always same]
    
</details>
