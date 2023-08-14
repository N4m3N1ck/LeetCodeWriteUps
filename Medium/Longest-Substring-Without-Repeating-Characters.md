# Longest Substring Without Repeating Characters
# Slow Solution
Here is an intuitive solution to the problem. We will loop through each character in the string and check the substring starting from that element until the letter repeats. If this substring is longer than all the previous ones, we will store it in max_cur
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        if s =="":
            return 0
        max_cur = 1
        i = 0
        while i<len(s):
            visited = []
            j = 0
            while i+j<len(s):
                if s[i+j] in visited:
                    break
                else:
                    visited.append(s[i+j])
                    j+=1
            if j>max_cur:
                max_cur = j
            i+=1
        return max_cur
```
# Fast Solution
We can create two pointers: slow and fast. The fast pointer will be moving forward until it meets a repeating character in string [slow:fast]. We can store the characters in the count dictionary. We can then move the slow pointer forward until the string is valid and we can continue exploring the array. We will be storing max value after each step
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        if len(s)<=1:
            return len(s)
        slow = 0
        fast = 0
        count = {}
        max_v = 0
        while fast < len(s):
            if s[fast] not in count:
                count[s[fast]] = 1
                fast += 1
            elif count[s[fast]] == 0:
                count[s[fast]] = 1
                fast += 1
            else:
                count[s[fast]] += 1
                while count[s[fast]] > 1:
                    count[s[slow]] -= 1
                    slow += 1
                fast+=1
            if fast-slow > max_v:
                max_v = fast-slow
        return max_v
```
