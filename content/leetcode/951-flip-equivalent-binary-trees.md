---
title: 951-Flip-Equivalent-Binary-Trees
date: 2024-12-26
author: Your Name
cell_count: 6
score: 5
---

https://leetcode.com/problems/flip-equivalent-binary-trees


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
  def flipEquiv(self, root1: Optional[TreeNode], root2: Optional[TreeNode]) -> bool:
    if not root1:
      return not root2
    if not root2:
      return not root1
    if root1.val != root2.val:
      return False
    return self.flipEquiv(root1.left, root2.left) and self.flipEquiv(root1.right, root2.right) or \
        self.flipEquiv(root1.left, root2.right) and self.flipEquiv(
        root1.right, root2.left)
```


```
new Solution().flipEquiv()
```


---
**Score: 5**