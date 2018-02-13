# 4 字典
- 对应关系，即 “映射 mapping”，是一个常用的数学概念
- 列表，本质是序号和数据的映射
 + 其最大的特点，是数据的排布具有顺序
- 字典，则是 “键 key” 和数据的映射
 + 键可以是数字、字符串和元组，但是不能是序列，键不能随意变化
 + 字典中的数据（值）没有顺序
 + 键/值的组合，又称作 “项”
- 字典的定义
 + 直接定义：使用花括号和冒号
 ```python
 phonebook = {"Anzhi":3369, "Ding":3378}
 tel_anzhi = phonebook ["Anzhi"]
 ```
 + 使用 dict 函数，将由 (键,值) 元组构成的序列转化为字典
 ```python
 items = [("name","Anzhi"),("age",29)]
 dict_items_1 = dict (items)
 dict_items_2 = dict (name = "Anzhi", age = 29)
 ```
- 字典的基本操作，对字典 my_dict = {key1:value1", key2:value2}
 + len(my_dict)：返回字典中项的数量
 + my_dict[key1]：返回 key1 对应的值 value1
 + my_dict[key2] = value3：将 value3 赋予 key2 对应的值
 + my_dict[key3] = value3：直接在字典中定义出一个新的项，不需要像 list 一样使用 append 方法
 + del my_dict[key2]：删除键为 key2 的项
 + key1 in my_dict：判断 my_dict 中是否有键为 key1 的项，返回布尔值；注意是判断的是键，而不是值（跟 list 不同）
- 字典相对于序列的方便之处在于：比如你想在序列中放入值，你需要先定义出一个足够大的序列；而字典永远可以直接定义，不需要先创建一个空的容器
- 小代码：研究所人员的生日和电话
```python
mitarbeiter_stahlbau = {
 "Julian" : {  "Geburtstag" : "03.Jan",  "Telefon" : 3375 },
 "Angelika" : {  "Geburtstag" "17.Feb": ,   "Telefon" :  3370},
 "Hendrik" : {  "Geburtstag" : "25.Juni",  "Telefon" : 3368 },
 "Niccolo" : {  "Geburtstag" : "16.Juli",   "Telefon" : 3680 },
 "Ding" : {  "Geburtstag" : "10.Juli" , "Telefon" :  3378},
 "Nancy" : {   "Geburtstag" : "03.Juli" ,  "Telefon" :  3373},
 "Dechenthin" : {"Geburtstag" : "10.Aug", "Telefon" : 3358 },
 "Konrad": {"Geburtstag" : "10.Aug", "Telefon" : 3367 },
 "Reininghaus" : {"Geburtstag" : "18.Aug", "Telefon" : 3372 },
 "Sebastian" : {"Geburtstag" : "19.Aug", "Telefon" : 2512 }, 
 "Olaf" : {"Geburtstag" : "06.Dez", "Telefon" : 3360 },
 "Anzhi" : {"Geburtstag" : "10.Dez", "Telefon" : 3369 },
 "Cong" : {"Geburtstag" : "28.Dez", "Telefon" : 3335 }
}
name = input ("Wessen Informationen suchen Sie: ")

request = input ("Geburtstag (g) oder Telefon-Nr. (t):")
if request == "g": key = "Geburtstag", art = "Der"
else if request == "t": key = "Telefon", art = "Die"
else : print ("laden... \n")

if name in mitarbeiter_stahlbau : 
 print ("%s %s von %s ist %s." % (art, key, name, mitarbeiter_stahlbau[name][key]))
else:
 print ("%s arbeitet nicht im Institut für Stahlbau." % (name))
```
