# Unique Morse Code Words
```python
class Solution:
    def uniqueMorseRepresentations(self, words: List[str]) -> int:
        dic = {'a': '.-', 'b': '-...', 'c': '-.-.', 'd': '-..', 'e': '.', 'f': '..-.', 'g': '--.', 'h': '....', 'i': '..', 'j': '.---', 'k': '-.-', 'l': '.-..', 'm': '--', 'n': '-.', 'o': '---', 'p': '.--.', 'q': '--.-', 'r': '.-.', 's': '...', 't': '-', 'u': '..-', 'v': '...-', 'w': '.--', 'x': '-..-', 'y': '-.--', 'z': '--..'}
        morse_words = []
        count = 0
        for word in words:
            morse_word = ""
            for letter in word:
                morse_word += dic[letter]
            if morse_word not in morse_words:
                morse_words.append(morse_word)
                count += 1
        return count
```
