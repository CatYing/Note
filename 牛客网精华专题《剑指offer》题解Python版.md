# 牛客网精华专题《剑指offer》题解Python版
Author: catying

1. 在一个二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

	* 从左下角开始查找，如果目标大于当前，则目标在当前右边；如果目标小于当前，则目标在当前上边

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
2. 替换空格

	* 请实现一个函数，将一个字符串中的空格替换成“%20”。例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。
	
	咳，如果你不怕被打的话，可以直接用python这么做
	
	```python
	# -*- coding:utf-8 -*-
	class Solution:
	    # s 源字符串
	    def replaceSpace(self, s):
	        # write code here
	        return s.replace(" ", "%20")
	```
	突如其来的骚，闪了老子的腰.jpg
	
	那么能不能稍微给力些呢
	
	```python
	# -*- coding:utf-8 -*-
	class Solution:
	    # s 源字符串
	    def replaceSpace(self, s):
	        # write code here
	        token_list = s.split(" ")
	        string = "%20".join(token_list)
	        return string
	
	```
	
	嗯…就酱！没毛病哦里给！
