# Reverse Vowels Of A String
```python
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowel_indexes = []
        vowels = []
        non_vowel_indexes = []
        non_vowels = []
        result = [""]*len(s)
        for i in range(len(s)):
            if s[i].lower() in "aeiou":
                vowels.append(s[i])
                vowel_indexes.append(i)
            else:
                non_vowels.append(s[i])
                non_vowel_indexes.append(i)
        vowels = vowels[::-1]
        for i in range(len(vowel_indexes)):
            result[vowel_indexes[i]] = vowels[i]
        for i in range(len(non_vowel_indexes)):
            result[non_vowel_indexes[i]] = non_vowels[i]
        return "".join(result)
```
