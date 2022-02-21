## question
Find Minimum in Rotated Sorted Array.
Suppose an array of length n sorted in ascending order is rotated between 1 and n times. For example, the array nums = [0,1,2,4,5,6,7] might become:
[4,5,6,7,0,1,2] if it was rotated 4 times.
[0,1,2,4,5,6,7] if it was rotated 7 times.
Notice that rotating an array [a[0], a[1], a[2], ..., a[n-1]] 1 time results in the array [a[n-1], a[0], a[1], a[2], ..., a[n-2]].
Given the sorted rotated array nums of unique elements, return the minimum element of this array.
You must write an algorithm that runs in O(log n) time.

Example 1:
Input: nums = [3,4,5,1,2]
Output: 1
Explanation: The original array was [1,2,3,4,5] rotated 3 times.
    
Example 2:
Input: nums = [4,5,6,7,0,1,2]
Output: 0
Explanation: The original array was [0,1,2,4,5,6,7] and it was rotated 4 times.

1. Integers in each row are sorted from left to right.
2. The first integer of each row is greater than the last integer of the previous row.

Constraints:

1. m == matrix.length
2. n == matrix[i].length
3. 1 <= m, n <= 100
4. -104 <= matrix[i][j], target <= 104


### Thought process
INPUT: matrix

1. Firstly, we can brief this question to a simple one - how to find minimum in a sequence consist of many ordered slices.
2. It is easy to find the main difference between different slices is the 'gap' - the head value in a slice is always the smallest. Besides, for accelerating the speed of the algorithm, we can compare the behand value and front value to judge that it is the right time met the 'gap'.
3. Iter the list and keep finding the smallest and recording it.

```
class Solution:
    def findMin(self, nums: List[int]) -> int:
        L = nums
        MIN = L[0]

        for i in range(len(L)):
            if i == 0:
                continue
            _n, n_ = L[i-1], L[i]
            if n_ > _n:
                continue
            else:
                if n_ < MIN:
                    MIN = n_

        return MIN
```
