# 387. First Unique Character in a String
  
<br>**Problem:** https://leetcode.com/problems/first-unique-character-in-a-string/<br>

**Difficulty:** Easy<br>
**Topics:** Hash Table, String, Queue, Counting<br>
**Language:** python<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-07 16:40 local time

**Runtime:** 125 ms (beats 23.062200000000022%)
**Memory:** 15.7 MB (beats 40.463400000000036%)


<!-- leetgit:submissionId=2165210390 codeHash=419b41eadd0af93de73697cc33b11e02e7b358cad16021e25c3bd70d1e505e85 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python
class Solution(object):
    def firstUniqChar(self, s):
        """
        :type s: str
        :rtype: int
        """
        map={}
        for c in s:
            map[c]=map.get(c,0)+1
        for i in range(len(s)):
            k=map.get(s[i],0)
            if k==1:
                return i
        return -1

        
```
