# Reogranize String
Here is a nice video solution to the problem: https://www.youtube.com/watch?v=2g_b1aYTHeg
## Approach
Each step we can take the most common letter except the previous one and add it to the string. This will automatically minimize the number of repeating letters.
## Explanation
We can create a dictionary and create maxHeap out of the dictionary. We will make all the values negative, because python supports only minHeap. We can then on each iteration until the maxHeap is empty, take the largest(or negative lowest) value out, add one to it(because it's negative) and if it's more(less) than zero we store it in prev so that we can use it later without repeating it twice. After picking the max value, we will put prev back in the heap. If there is still prev left when heap is None, it means there will be characters repeating in the end of the string. We will return "" in this case.
## Script
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
