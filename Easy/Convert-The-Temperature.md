# Convert the temperature
The solution is pretty much self explanatory:
```python
class Solution:
    def convertTemperature(self, celsius: float) -> List[float]:
        return [celsius+273.15, celsius*1.8+32]
```
