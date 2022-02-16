## question

Write an efficient algorithm that searches for a value target in an m x n integer matrix matrix. This matrix has the following properties:

1. Integers in each row are sorted from left to right.
2. The first integer of each row is greater than the last integer of the previous row.

Constraints:

1. m == matrix.length
2. n == matrix[i].length
3. 1 <= m, n <= 100
4. -104 <= matrix[i][j], target <= 104

```
Input: matrix = [
    [1,3,5,7],
    [10,11,16,20],
    [23,30,34,60]
], target = 3
Output: true
```

### Thought process
INPUT: matrix, target value

1. Setting a specific list including the head value of every line.
2. Confirming the target value's line.
3. Iter this line's value and find weather target is exist.

```
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        L= []
        for lst in matrix:
            head = lst[0]
            L.append(head)

        target_line_index = -1

        for index in range(len(L)):
            head = L[index]
            INF = float('inf')
            if index + 1 < len(L):
                next_head = L[index+1]
            else:
                next_head = INF
            if head <= target < next_head:
                target_line_index = L.index(head)
                break
        if target_line_index == -1:
            return False
        print(L, target_line_index)
        target_line = matrix[target_line_index]
        for i in target_line:
            if i == target:
                return True
        return False
```
