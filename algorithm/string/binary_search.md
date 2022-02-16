# binary search

### Thought process
INPUT: List, target value

1. Spliting List to 2 sub lists(L1, L2), and find the middle value.
2. Comparing the middle value and the target value. If find, finish.
3. If not find, recurring, trying to find the target in the sub list(L1, L2).

```
List = list
def recursion(L, target):
    LEN = len(L)
    mid_index = ceil(LEN/2)
    if LEN != 1:
        mid = L[mid_index]
    else:
        mid = L[0]
    if target == mid:
        #print('find', M, target)
        return M[target]
    elif target > mid:
        L = L[mid_index:]
    else:
        L = L[:mid_index]
    if LEN == 1:
        #print('-1')
        return -1
    return recursion(L, target)

def binarySearch(L, target):
    global M
    M = {L[i]:i for i in range(len(L))}
    return recursion(L, target)

class Solution:
    def search(self, nums: List[int], target: int) -> int:
        return binarySearch(nums, target)

L = nums = [-1,0,3,5,9,12]
target = 9
s = Solution()
res = s.search(L, target)
print(res)
```

