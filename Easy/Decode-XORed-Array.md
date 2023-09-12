# Decode XORed Array
Xor operation is reversable. x^y = z z^y = x
```python
class Solution:
    def decode(self, encoded: List[int], first: int) -> List[int]:
        ar = [first]
        for i in encoded:
            ar.append(ar[-1] ^ i)
        return ar
```
