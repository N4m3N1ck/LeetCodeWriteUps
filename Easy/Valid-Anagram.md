# Valid Anagram
I decided to include multiple ways to solve the problem:
# 1. Goofy probability
We can create variable s1 which will hold the sum of ord of each character. But there might be collisions. For example: "bb" and "ac". ord("b")+ord("b") = 98+98 = 196. ord("a")+ord("c") = 97+99 = 196. To reduce the chance of a collision we could raise each number to some power. The smallest power that worked was 4.
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s)!=len(t):
            return False
        sum = 0
        for i in s:
            sum+=ord(i)**4
        for i in t:
            sum-=ord(i)**4
        return sum==0
```
# 2. Dictionary solution
While looping through s, we can create a dictionary which will keep the count of each letter. While looping through t, we can if each letter is in the dictionary, we will also check if there is the same amount of each letters by subtracting 1 from the letter in the dictionary. If it gets below zero, return False.
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s)!=len(t):
            return False
        dic = {}
        for i in s:
            if i not in dic:
                dic[i] = 1
            else:
                dic[i]+=1
        for i in t:
            if i not in dic:
                return False
            else:
                if dic[i] < 1:
                    return False
                dic[i] -= 1
        return True
```
We do not need to check if each item in the dictionary is zero, because we have compared the length of the strings in the beginning. So cases like "aaaaaaaa" and "aa" will reeturn False.
# 3. Sort
We can sort both strings and then compare them:
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s)==sorted(t)
```
# 4. Counter
We can use Counter in python, which will automatically count each character in the string. We can then compare two counters:
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return Counter(s) == Counter(t)
```
