---
title: 88-Merge-Sorted-Array
date: 2024-12-26
author: Your Name
cell_count: 6
score: 5
---

https://leetcode.com/problems/merge-sorted-array


```
import pyutil as pyu
pyu.get_local_pyinfo()
```


```
print(pyu.ps2("python-dotenv"))
```


```
from typing import List
```


```
class Solution:
  def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
    i = m - 1      # nums1's index (actual nums)
    j = n - 1      # nums2's index
    k = m + n - 1  # nums1's index (next filled position)

    while j >= 0:
      if i >= 0 and nums1[i] > nums2[j]:
        nums1[k] = nums1[i]
        k -= 1
        i -= 1
      else:
        nums1[k] = nums2[j]
        k -= 1
        j -= 1
```


```
new Solution().merge()
```


---
**Score: 5**