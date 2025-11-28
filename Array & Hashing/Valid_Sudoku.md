## Valid Sudoku
## ⚡Efficent Solution

```python

	class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        
        # Check rows
        for i in range(9):
            seen = set()
            for j in range(9):
                value = board[i][j]
                if value != '.':
                    if value in seen:
                        return False
                    seen.add(value)
        
        # Check Col
        for i in range(9):
            seen = set()
            for j in range(9):
                value = board[j][i]
                if value != '.':
                    if value in seen:
                        return False
                    seen.add(value)

        ## Check box

        box = [(0,0),(0,3),(0,6),(3,0),(3,3),(3,6),(6,0),(6,3),(6,6)]

        for i,j in box:
            Seen = set()
            for m in range(i,i+3):
                for n in range(j,j+3):
                    val = board[m][n]
                    if val != '.':
                        if val in Seen:
                            return False
                        Seen.add(val)
        return True
        
## Space Complexity: O(1)
## Time Complexity:  O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(1)            | O(1)             |

<details>
<summary>Approach</summary>

    1) I am iterating through the Horizontal rows in the first one & check any elements is repeated or not except '.'
    2) Again, I am iterating through the Vertical rows in the first one & check any elements is repeated or not except '.'
    3) In this I am checking the box..So I manually created this list by myself
    `box = [(0,0),(0,3),(0,6),(3,0),(3,3),(3,6),(6,0),(6,3),(6,6)]`
    4) I am iterating through the box and also through the i & j (example for (0,3) i represents 0 & j represents 3)
    5) checking whether it is repeated or not...if it did then I return `flase`
    6) If it didn't then after the entire loop I will return `true`
</details>


