## search first and last letter's position in a specfic string
example:

```
IN：nums = [5,7,7,8,8,10], target = 8
OUT：[3,4]
```

### Thought process
INPUT: List, target value(assume a letter)

1. Iter this list.
2. Recording the first letter's position only once by setting a sentry.
3. Trying to find another letter's position.

```
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        L = nums
        start = end = -1
        start_sentry = 0
        for index in range(len(L)):
            val = L[index]
            if (not start_sentry) and (val == target):
                start = index
                start_sentry = 1
                continue
            if val == target:
                end = index
        return [start, end]
```
