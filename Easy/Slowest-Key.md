# Slowest Key
```python
class Solution:
    def slowestKey(self, releaseTimes: List[int], keysPressed: str) -> str:
        m = 0
        prev = 0
        m_key = ""
        for i in range(len(releaseTimes)):
            if (releaseTimes[i] - prev > m) or (releaseTimes[i] - prev == m and keysPressed[i] > m_key):
                m = releaseTimes[i] - prev
                m_key = keysPressed[i]
            prev = releaseTimes[i]
        return m_key
```
