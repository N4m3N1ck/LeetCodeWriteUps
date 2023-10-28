# Group Anagrams
We can create a dictionary, in which the key is the count of each letter and the values is the array of corresponding anagrams
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        dic = {}
        for i in strs:
            c = [0]*26
            for j in i:
                c[ord(j) - 97] += 1
            if tuple(c) in dic:
                dic[tuple(c)].append(i)
            else:
                dic[tuple(c)] = [i]
        return dic.values()
```
