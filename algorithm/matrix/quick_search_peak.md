## question
A peak element is an element that is strictly greater than its neighbors.
Given an integer array nums, find a peak element, and return its index. If the array contains multiple peaks, return the index to any of the peaks.
You may imagine that nums[-1] = nums[n] = -∞.
You must write an algorithm that runs in O(log n) time.

Example 1:
Input: nums = [1,2,3,1]
Output: 2
Explanation: 3 is a peak element and your function should return the index number 2.

Example 2:
Input: nums = [1,2,1,3,5,6,4]
Output: 5
Explanation: Your function can return either index number 1 where the peak element is 2, or index number 5 where the peak element is 6.

Constraints:

1 <= nums.length <= 1000
-231 <= nums[i] <= 231 - 1
nums[i] != nums[i + 1] for all valid i.

### Thought process
INPUT: matrix

1. O(log n), Let me think about binary search. We can use the mid-value to compare the front and behind value, if found, that's done

Tips:
1. Flag is used to stop recurse.
2. Top list is used to save the target index value.
```
TOP = [None]
FLAG = [False]

def recursion(NL):
    if FLAG[0]:
        return
    LEN = len(NL) 
    mid_index = LEN//2
    mid = NL[mid_index][0]
    if LEN == 4:
        NL = NL[3:] + NL[1:]
    elif LEN == 5:
        print(NL)
        NL = NL[3:] + NL[2:]
    if LEN < 3:
        return
    _n, n_ = NL[mid_index-1][0], NL[mid_index+1][0]
    if _n < mid > n_: 
        index = NL[mid_index][1]
        TOP[0] = index
        FLAG[0] = True
        return
    recursion(NL[:mid_index])
    recursion(NL[mid_index:])

class Solution:
    def findPeakElement(self, nums: List[int]) -> int:
        L = nums
        NL = [(L[index], index) for index in range(len(L))]
        recursion(NL)
        return TOP[0]
```
