## Top K Frequent Elements
<details>
<summary>Brute Force Solution</summary>
    
```python
    class Solution:
        def topKFrequent(self, nums: List[int], k: int) -> List[int]:
            
            freq = {}

            for i in nums:
                if i not in freq:
                    freq[i] = 1
                else:
                    freq[i] += 1
            
            sorted_items = sorted(freq.items(),key = lambda item:item[1],reverse = True)

            new = []
            for j in range(k):
                new.append(sorted_items[j][0])
            
            return new
            
## Time Complexity: O(nlogn)
## Space Complexity: O(n)
```
</details>

## ⚡ Efficent Solution

```python
    

## Time Complexity: O(n)
## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(nlogn)        | O(n)             |
| Hashmap        | O(n)            | O(n)             |



<details>
<summary>Approach</summary>

    1) Approach_1 = i) freq of each characther in a word ii) sort it based on the value in descending order iii) append elements to the list for the range in k
    2) 
    
</details>


