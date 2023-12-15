# Destination City
```python
class Solution:
    def destCity(self, paths: List[List[str]]) -> str:
        # Add all the start cities to A, and all the finish cities to B. The only city that is a finish city, but not a start city is the destination city
        A, B = map(set, zip(*paths))
        return (B - A).pop()
```
