# 2. Python 的列表和元组
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
	+ 将字符串或元组转成列表
	```python
	letters = ("hello") 
	a = list(letters)
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
		1. append: 在列表末尾追加一个新的元素，并返回该值
		```python
		numbers = [1,2,3]
		numbers.append(4)
		```
		2. remove: 移除列表中的某个名字的元素中的第一个，不返回任何值
		```python
		a = [1,2,1,2,1,2,1,2]
		a.remove(2)
		```
			* append 是在后面追加一个元素，pop 是移除最后面的一个元素，这样就定义了“栈”
			* “栈”就是这样一种“最后加入的被最先去除”的数据操作方式，这种操作方式被称为 LIFO： 后进先出
		3. count: 计算某个元素在列表中出现的次数，并返回该值
		```python
		note = [1.0,1.3,1.3,1.7,1.7,1.7]
		note.count(1.3)
		```
		4. extend: 扩展列表 = 在尾部增加新的列表，不返回任何值
		```python
		a = [1,2,3]
		b = [4,5,6]
		a.extend(b) # 对对象的操作比重新赋值 a = a + b 要有效率
		```
		5. index： 读取列表中某个名字元素的位置，并返回该值
		```python
		a = [1,2,3,4,5,6]
		a.index(4)
		```
		6. insert: 在列表的某个位置插入某一个值，不返回任何值
		```python
		a = [1,2,3,5,6]
		a.insert(3, 4)
		```
		7. pop： 移除列表中某个位置的元素 （不给出，则默认为最后一个），返回被移除的元素的值，完成了两步操作
		```python
		a = [1,2,3,4,5]
		b = a.pop(0)
		```
		8. reverse：将列表中的元素反向放置，不返回任何值
		```python
		a = [1,2,3,5,6]
		a.reverse()
		```
		9. sort：将列表中的元素进行从小到大的排序，不返回任何值
		```python
		x = [4,6,2,1,7,9]
		y = x[:] # 不能写成 y = x，否则只是让 y 和 x 指向同一个内存地址
		y.sort()
		```
			* 有一个类似的函数，可以经过一堆操作之后，返回新的排序后的列表，且不改变原列表的值
			```python
			y = sorted(x)
			```
			* sort 和 sorted 中可以提供两个参数, *key* 和 *reverse*
				- key 键：元素排序的依据，应该是一个函数，称作键函数；如此将对每个元素进行函数运算，并从小到大排序
				- reverse：一个布尔值，True 表示要进行反向排序
				```python
				x = [a,aaa,aa,aaaaaaa,aa,aa,aaa,a]
				x.sort(key=len, reverse=True)
				```

- 对元组的操作
	+ 将序列或字符串转成元组
	```python
	a = [1,2,3]
	b = tuple(a)
	```
	+ 创建只有一个元素的元组
	```python
	a = (1,) # 逗号说：“我从来没有这样重要过”
	```
	+ 元组的基本操作和列表几乎一样，除了 index 和 count 不能用
	+ 但是元组可以充当映射的键，列表则不行
	+ 元组也经常是内建函数的返回值
