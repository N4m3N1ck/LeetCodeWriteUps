# Merge Intervals
We can create array ```merged``` and add the first item of sorted intervals array. For each next item we will check if the start is before the last merged item end and merge them if it's true. We will merge them by choosing the max end point of the interval and substituting it into the merged array. If they are not intersecting, we will just add it to the merged array.   
```python
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        intervals.sort()
        merged = [intervals[0]]
        for i in range(1,len(intervals)):
            if merged[-1][1] >= intervals[i][0]:
                merged[-1][1] = max(merged[-1][1], intervals[i][1])
            else:
                merged.append(intervals[i])
        return merged
```
