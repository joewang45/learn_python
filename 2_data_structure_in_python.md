# 2. Python 中的数据结构 - 列表和元组
- Python 中最基本的数据结构是序列 Sequence
	+ 序列中的元素位置，称作索引
	+ 第一个索引是 0
- Python 中有 6 种内建序列
	+ 最常见的有
		* 列表： 可以进行修改，用于数据的操作 [1,2,3]
		* 元组： 不能进行修改，用于数据的储存 (1,2,3)
		* 字符串
	+ 在大部分情况下，列表都可以代替元组
- 定义序列
	``` python 
	edward = ["Edward Gumby",42]
	john = ["John Smith", 50]
	collegue = [edward, john]
	collegue
	``` 
- 对序列的操作
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
	+ 判断序列中是否存在某元素
		``` python
		name = input ("Whose status do you want to check? ")

		current_collegues = ["Konrad", "Niccolo", "Hendrik", "Ding", "Cong", "Anzhi", "Julian"]
		status = name in current_collegues
		if status == True:
			print (name + " is working with us.")
		else:
			print (name + " is not working with us.")
		```
	+ 调取序列长度，序列中最大值最小值
		``` python
		numbers = [1,2,3]
		len(numbers) # = 3
		max(numbers) # = 3
		min(numbers) # = 1
		```
- 对列表的操作
	+ 将字符串拆成字符列表
	```python
	letters = ("hello") 
	```
	+ 列表由于其可修改性，可以有一些特殊的赋值操作
		* 自动随元素个数的改变，改变列表本身大小
		```python
		original = [1,2,3,4,5]
		# 删除
		del original # 这是一个操作语句，不是一个函数
		# 赋值
		original[5:] = [6,7,8,9,10] # 赋值也是一个语句
		original[1:1] = [1.1, 1.2, 1.3] # 在第二个元素位置插入序列 = 把第二个元素及往后挤
		original[1:4] = [] # 删除刚才插入的序列
		```
	+ 但是 Python 是一门面向对象的语言，对对象的操作一般通过 *对象.方法(参数)* 的语句实现
	+ 一般来说“对对象的操作”要比“赋值”来的易读的多
	+ 以下是一些常见的 operations on objects
		* append: 在列表末尾追加一个新的元素
		```python
		numbers = [1,2,3]
		numbers.append(4)
		```
		* count: 计算某个元素在列表中出现的次数
		```python
		note = [1.0,1.3,1.3,1.7,1.7,1.7]
		note.count(1.3)
		```
		* extend: 扩展列表 = 在尾部增加新的列表
		```python
		a = [1,2,3]
		b = [4,5,6]
		a.extend(b) # 对对象的操作比重新赋值 a = a + b 要有效率
		```
		* index： 读取列表中某个元素的位置
		```python
		a = [1,2,3,4,5,6]
		a.index(4)
		```
		* insert: 在列表的某个位置插入某一个值
		```python
		a = [1,2,3,5,6]
		a.insert(3, 4)
		```
		* pop： 移除列表中的一个元素 （不给出，则默认为最后一个），并返回被移除的元素的值，完成了两步操作
		```python
		a = [1,2,3,4,5]
		b = a.pop(0)
		```
	
