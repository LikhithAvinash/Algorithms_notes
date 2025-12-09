## Best_Time_to_buy_&_Sell_Stock
## ⚡Efficent Solution

```python
    class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        n = len(prices)

        mini = float('inf')
        idx = 0
        diff = 0
        maxi = 0

        for i in range(n):
            mini = min(prices[i],mini)
            diff = prices[i] - mini

            if diff > 0:
                maxi = max(diff,maxi)

        return maxi
        
        
## Space Complexity: O(n)
## Time Complexity:  O(1)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n)            | O(1)             |

<details>
<summary>Approach</summary>

   1) Here I am using for loop as it moves in order(bcz we want the stock price high at small index and sell at low price and high index)-------> simply follows the order
   2) I first need to find the minimum price so I initialized min(this constantly checks the minimum)
   3) I then did diff of mini and the current price
   4) If the diff is greater than all then that is been returned
</details>


