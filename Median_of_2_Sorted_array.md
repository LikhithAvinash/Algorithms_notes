## ⚡ Efficent Solution
**Understanding** 

❌- find the median of 2 arrays and then add it and find median again
✅- find the median of 2 combined array and then find median
    * if odd then the **middle elemnent** is median
    * if even then **mean of all elements** is mean
    
  ```python
class Solution:
  def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:

      nums = sorted(nums1 + nums2) 
      n = len(nums)

      if n % 2 == 0:
          return (nums[n//2 - 1] + nums[n//2]) / 2
      else:
          return nums[n//2]

sol = Solution()
nums1 = [1,3]
nums2 = [2]
print(sol.findMedianSortedArray(nums1,nums2))

```
