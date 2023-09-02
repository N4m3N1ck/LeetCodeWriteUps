# Count Items Matching A Rule
```python
class Solution:
    def countMatches(self, items: List[List[str]], ruleKey: str, ruleValue: str) -> int:
        rules = ["type","color","name"]
        rule_index = rules.index(ruleKey)
        n = 0
        for i in items:
            if i[rule_index] == ruleValue:
                n += 1
        return n
```
