---
title: 609-Find-Duplicate-File-In-System
date: 2024-12-26
author: Your Name
cell_count: 6
score: 5
---

https://leetcode.com/problems/find-duplicate-file-in-system


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
  def findDuplicate(self, paths: List[str]) -> List[List[str]]:
    contentToPathFiles = defaultdict(list)

    for path in paths:
      words = path.split(' ')
      rootPath = words[0]  # "root/d1/d2/.../dm"
      for fileAndContent in words[1:]:  # "fn.txt(fn_content)"
        l = fileAndContent.find('(')
        r = fileAndContent.find(')')
        # "fn.txt"
        file = fileAndContent[:l]
        # "fn_content"
        content = fileAndContent[l + 1:r]
        # "root/d1/d2/.../dm/fn.txt"
        filePath = rootPath + '/' + file
        contentToPathFiles[content].append(filePath)

    return [filePath for filePath in contentToPathFiles.values() if len(filePath) > 1]
```


```
new Solution().findDuplicate()
```


---
**Score: 5**