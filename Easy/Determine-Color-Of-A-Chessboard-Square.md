# Determine Color Of A Chessboard Square
If we number each letter, the black squares will be in places where the parity of the letter and the number are the same.
```python
class Solution:
    def squareIsWhite(self, coordinates: str) -> bool:
        return ord(coordinates[0]) % 2 != int(coordinates[1]) % 2
```
