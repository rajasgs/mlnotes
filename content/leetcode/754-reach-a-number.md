---
title: 754-Reach-A-Number
date: 2024-12-26
author: Your Name
cell_count: 6
score: 5
---

https://leetcode.com/problems/reach-a-number


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
  def reachNumber(self, target: int) -> int:
    ans = 0
    pos = 0
    target = abs(target)

    while pos < target:
      ans += 1
      pos += ans

    while (pos - target) & 1:
      ans += 1
      pos += ans

    return ans
```


```
new Solution().reachNumber()
```


---
**Score: 5**