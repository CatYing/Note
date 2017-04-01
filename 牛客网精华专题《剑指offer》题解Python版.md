# 牛客网精华专题《剑指offer》题解Python版
Author: catying

1. 在一个二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

从左下角开始查找，如果目标大于当前，则目标在当前右边；如果目标小于当前，则目标在当前上边

```python
# -*- coding:utf-8 -*-
class Solution:
    # array 二维列表
    def Find(self, target, array):
        # write code here
        row_count = array.__len__()
        col_count = array[0].__len__()
        i = row_count - 1
        j = 0
        while i>=0 and j < col_count:
            if target == array[i][j]:
                return True
            if target < array[i][j]:
                i -= 1
                continue
            if target > array[i][j]:
                j += 1
                continue
        return False

```