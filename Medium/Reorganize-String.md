# Reogranize String
https://www.youtube.com/watch?v=2g_b1aYTHeg
```python
class Solution:
    def reorganizeString(self, s: str) -> str:
        counter = {}
        for i in s:
            if i not in counter:
                counter[i] = -1
            else:
                counter[i] -= 1
        maxHeap = [[cnt,char] for char,cnt in counter.items()]
        heapq.heapify(maxHeap)
        prev = None
        ans = ""
        while maxHeap or prev:
            if prev and not maxHeap:
                return ""
            cnt, char = heapq.heappop(maxHeap)
            ans += char
            cnt += 1
            if prev:
                heapq.heappush(maxHeap,prev)
                prev = None
            if cnt != 0:
                prev = [cnt,char]
        return ans
```
