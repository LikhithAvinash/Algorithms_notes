## Add Two Numbers
<details>
<summary>Brute Force Solution</summary>
  
```python
    class Solution:
        def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
            current = l1
            list_l1 = []
            while current is not None:
                list_l1.append(current.val)
                current = current.next
            
            curr = l2 
            list_l2 = []    
            while curr is not None:
                list_l2.append(curr.val)
                curr = curr.next
            
            new = []
    
            if len(list_l1) > len(list_l2):
                result = len(list_l1) - len(list_l2)
                while result > 0:
                    list_l2.append(0)
                    result -= 1
            
            if len(list_l2) > len(list_l1):
                result = len(list_l2) - len(list_l1)
                while result > 0:
                    list_l1.append(0)
                    result -= 1
    
            i,j = 0,0
            carry = 0
            while i != len(list_l1) or j != len(list_l2): #[7,0,8]
                total = list_l1[i] + list_l2[j] + carry
                if total > 9:
                    total = total % 10
                    carry = 1
                else:
                    carry = 0
    
                new.append(total)
                
                i += 1
                j += 1
            
            if carry > 0:
                new.append(carry)
    
            # New = new[::-1]
    
            # if not new:
            #     return [0]
            
            head = ListNode(new[0])
            curr = head
            for value in new[1:]:
                curr.next = ListNode(value)
                curr = curr.next
            return head
    
        sol = Solution()
        l1 = [2,4,3]
        l2 = [5,6,4]
        print(sol.twoSum(l1,l2))
```
</details>

## ⚡ Efficent Solution

```python
  class Solution:
      def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
          dummy_head = ListNode(0)
  
          curr = dummy_head
  
          carry = 0
  
          while l1 or l2 or carry:
              val1 = l1.val if l1 else 0
              val2 = l2.val if l2 else 0
  
              total_sum = val1 + val2 + carry
  
              carry = total_sum // 10
              new_digit = total_sum % 10
  
              curr.next = ListNode(new_digit)
              curr = curr.next
  
              if l1:
                  l1 = l1.next
              if l2:
                  l2 = l2.next
          
          return dummy_head.next
          
  sol = Solution()
  l1 = [2,4,3]
  l2 = [5,6,4]
  print(sol.twoSum(l1,l2))
  ```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n²)           | O(n)             |
| Hashmap        | O(n)            | O(n)             |

<details>
<summary>Approach</summary>

    1) First assign dummy_head(which will be none)
