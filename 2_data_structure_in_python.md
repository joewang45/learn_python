# 2. Python 中的数据结构 - 列表和元组
- Python 中最基本的数据结构是序列 Sequence
	+ 序列中的元素位置，称作索引
	+ 第一个索引是 0
- Python 中有 6 种内建序列
	+ 最常见的有
		* 列表： 可以进行修改，用于数据的操作
		* 元组： 不能进行修改，用于数据的储存
		* 字符串
	+ 在大部分情况下，列表都可以代替元组
- 定义序列
``` python 
edward = ["Edward Gumby",42]
john = ["John Smith", 50]
collegue = [edward, john]
collegue
```
- 对序列的操作包括
	+ 序列单个元素的调取:
``` python
greeting = "Hello"
greeting[0] # 调取该字符串的第一个位置的元素
greeting[-1] # 调取该字符串从右边数第一个位置的元素
```
	+ 序列多个元素的调取
``` python
website = "http://www.python.org"
website[11:17] # 调取第12个位置到第17个位置的元素，组成新的序列，区间表达为左闭右开
website[-10:-5] # 调取从右边数第10个到第5个位置的元素，组成新序列
# website [-10:0] 不能调取元素，组成的是空序列
website [-10:] # 调取从右边数第10个到最后的所有元素，组成新序列
website [:] # 调取该序列中所有的元素，组成新序列
website [::2] # 在之后再加一个数字，定义调取的步长： 取第1个，取第1+2个...
website [::-2] # 从右开始： 取第-1个，取第-1-2个
```
	+ 序列加法和序列乘法
``` python
numbers_1 = [1,2,3]
numbers_2 = [4,5,6]
numbers_1 + numbers_2 # = [1,2,3,4,5,6]
# numbers_1 + "456" 是错误的语法，只有同类型的序列才能相加
numbers_1 * 2 # = [1,2,3,1,2,3] 
null = [None] * 10 # 创建一个包含十个位置的空序列
```
		* 代码： 字符显示框
``` python
screen_width = 80
box_text_dist = 5

output = input ("Sentence to display: ")
text_width = len (output)
box_width = text_width + 2 + box_text_dist * 2 
left_margin = (screen_width - box_width) // 2

print ()
print (" " * left_margin + "+" + "-" * (box_width -2) + "+")
print (" " * left_margin + "|" + " " * (box_width-2) + "|")
print (" " * left_margin + "|" + " " * box_text_dist + output + " "*box_text_dist + "|")
print (" " * left_margin + "|" + " " * (box_width-2) + "|")
print (" " * left_margin + "+" + "-" * (box_width -2) + "+")
print ()
```
	+ 检查
