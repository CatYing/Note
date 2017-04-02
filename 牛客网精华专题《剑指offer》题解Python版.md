# 牛客网精华专题《剑指offer》题解Python版
Author: catying

1. 二维数组的查找

	* 在一个二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。
	
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

3. 从尾到头打印链表

	* 输入一个链表，从尾到头打印链表每个节点的值
		* 从头到尾遍历链表，存到列表中，反向输出
		
		```python
		# -*- coding:utf-8 -*-
		# class ListNode:
		#     def __init__(self, x):
		#         self.val = x
		#         self.next = None

		class Solution:
		    # 返回从尾部到头部的列表值序列，例如[1,2,3]
		    def printListFromTailToHead(self, listNode):
		        # write code here
		        result = []
		        if listNode is None:
		            return result
		        else:
		            while listNode.next is not None:
		                result.append(listNode.val)
		                listNode = listNode.next
		            result.append(listNode.val)
		            return result[::-1]
		```
		* 严重怀疑牛客网的评测系统有问题……同一份代码隔了十分钟提交就过了

4. 重建二叉树

	* 输入二叉树的前序和中序，输出该二叉树的根节点

	* 前序第一位是根节点，在中序中找到根节点，根节点左边即是左子树，右边即是右子树。

	```python
	# -*- coding:utf-8 -*-
	# class TreeNode:
	#     def __init__(self, x):
	#         self.val = x
	#         self.left = None
	#         self.right = None
	class Solution:
	    # 返回构造的TreeNode根节点
	    def reConstructBinaryTree(self, pre, tin):
	        # write code here
	        if len(pre) == 0:
	            return None
	        elif len(pre) == 1:
	            return TreeNode(pre[0])
	        else:
	            root = TreeNode(pre[0])
	            root.left = self.reConstructBinaryTree(pre=pre[1:tin.index(pre[0])+1], tin=tin[:tin.index(pre[0])])
	            root.right = self.reConstructBinaryTree(pre=pre[tin.index(pre[0])+1:], tin=tin[tin.index(pre[0])+1:])
	            return root
	```
	嗯……看着很吓人，其实思路很清晰对不对，而且题目也说了不会有重复数字，不用index函数真是浪费啊（逃
	


