---
title: 188-Best-Time-To-Buy-And-Sell-Stock-Iv
date: 2024-12-26
author: Your Name
cell_count: 6
score: 5
---

https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv


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
  def maxProfit(self, k: int, prices: List[int]) -> int:
    if k >= len(prices) // 2:
      sell = 0
      hold = -math.inf

      for price in prices:
        sell = max(sell, hold + price)
        hold = max(hold, sell - price)

      return sell

    sell = [0] * (k + 1)
    hold = [-math.inf] * (k + 1)

    for price in prices:
      for i in range(k, 0, -1):
        sell[i] = max(sell[i], hold[i] + price)
        hold[i] = max(hold[i], sell[i - 1] - price)

    return sell[k]
```


```
new Solution().maxProfit()
```


---
**Score: 5**