# Longest Palindromic Substring
We can solve this problem by checking if each substring is a palindrome, but the complexity will be O(n*n^2) or O(n^3), which is too slow. We can improve the complexity by making each character in the string the center of the possible palindrome, and checking if characters left to the center and right to the center are the same
# Solution 1: Long
```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        longest_left_ptr = 0
        longest_right_ptr = 0
        longest_length = 0
        for i in range(len(s)):
            l, r = i, i
            current_length = 1
            while l > 0 and r < len(s) - 1:
                if s[l - 1] == s[r + 1]:
                    l -= 1
                    r += 1
                    current_length += 2
                else:
                    break
            if current_length > longest_length:
                longest_length = current_length
                longest_left_ptr = l
                longest_right_ptr = r
            if i != len(s) - 1:
                l, r = i, i + 1
                current_length = 2
                if s[l] == s[r]:
                    while l > 0 and r < len(s) - 1:
                        if s[l - 1] == s[r + 1]:
                            l -= 1
                            r += 1
                            current_length += 2
                        else:
                            break
                    if current_length > longest_length:
                        longest_length = current_length
                        longest_left_ptr = l
                        longest_right_ptr = r
        return s[longest_left_ptr:longest_right_ptr+1]
```
