# 4 字典
- 对应关系，即 “映射 mapping”，是一个常用的数学概念
- 列表，本质是序号和数据的映射
  - 其最大的特点，是数据的排布具有顺序
- 字典，则是 “键 key” 和数据的映射
  - 键可以是数字、字符串和元组
  - 字典中的数据没有顺序
  - 键/数据的组合，又称作 “项”
- 字典的定义
  - 直接定义：使用花括号和冒号
  ```python
  phonebook = {"Anzhi":3369, "Ding":3378}
  tel_anzhi = phonebook ["Anzhi"]
  ```
  - 使用 dict 函数，将由 (键,值) 元组构成的序列转化为字典
  ```python
  items = [("name","Anzhi"),("age",29)]
  dict_items_1 = dict(items)
  dict_items_2 = dict (name = "Anzhi", age = 29)
  ```
  
