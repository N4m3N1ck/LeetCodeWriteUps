# Sort Characters By Frequency
We will count the frequency of each character using Counter, create an array of arrays, where each index represents the frequency, and the element at that index represents all the unique characters with that frequency. We will loop though the Counter and add each character to the corresponding frequency. After that we will loop the array backwards and add each character to the answer.
```python
class Solution:
    def frequencySort(self, s: str) -> str:
        counter = Counter(s)
        n = len(s)
        bucket = [[] for _ in range(n+1)]
        for char, freq in counter.items():
            bucket[freq].append(char)
        ans = []
        for i in range(n, 0, -1):
            for char in bucket[i]:
                ans.append(i*char)
        return "".join(ans)
```
