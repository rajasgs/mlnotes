---
title: 648-Replace-Words
date: 2024-12-26
author: Your Name
cell_count: 6
score: 5
---

https://leetcode.com/problems/replace-words


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
  def __init__(self):
    self.root = {}

  def insert(self, word: str) -> None:
    node = self.root
    for c in word:
      if c not in node:
        node[c] = {}
      node = node[c]
    node['word'] = word

  def search(self, word: str) -> str:
    node = self.root
    for c in word:
      if 'word' in node:
        return node['word']
      if c not in node:
        return word
      node = node[c]
    return word

  def replaceWords(self, dict: List[str], sentence: str) -> str:
    for word in dict:
      self.insert(word)

    words = sentence.split(' ')
    return ' '.join([self.search(word) for word in words])
```


```
new Solution().__init__()
```


---
**Score: 5**