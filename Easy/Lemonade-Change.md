# Lemonade Change
```python
class Solution:
    def lemonadeChange(self, bills: List[int]) -> bool:
        fives = 0
        tens = 0
        for i in bills:
            if i == 5:
                fives += 1
            elif i == 10:
                fives -= 1
                tens += 1
            elif i == 20 and tens > 0:
                tens -= 1
                fives -= 1
            else:
                fives -= 3
            if fives < 0:
                return False
                
        return True
```
