# 239. Sliding Window Maximum
  
<br>**Problem:** https://leetcode.com/problems/sliding-window-maximum/<br>

**Difficulty:** Hard<br>
**Topics:** Array, Queue, Sliding Window, Heap (Priority Queue), Monotonic Queue, Range Minimum/Maximum Query<br>
**Language:** python<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-07 17:01 local time

**Runtime:** 305 ms (beats 17.380499999999923%)
**Memory:** 27.3 MB (beats 95.0765%)


<!-- leetgit:submissionId=2165225788 codeHash=4eb7219aa4b94c9d05daa620401a171c2ee79944a7779ebee1b95302f0640038 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python
class Solution(object):
    def maxSlidingWindow(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: List[int]
        """
        i,j=0,0
        lists=[]
        
        window=deque()
    
        while(j<len(nums)):
            while window and nums[window[-1]]<=nums[j]:
                window.pop()
            window.append(j)
            if(j-i+1==k):
                lists.append(nums[window[0]])
                if window[0]==i:
                    window.popleft()
                i+=1

            j+=1
        return lists

```
