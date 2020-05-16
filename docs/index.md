
# Lesson 1 


----
## 1. python的特性

- 简单易学，用途广泛
- 解释性语言 - 一边执行，一边编译
- 交互性 - 在python提示符后面直接执行
- 面向对象 - 可以用python分装对象
- 具有丰富的库


### Demo

展示几个之前用python做的project，帮助大家理解python的神通广大



## 2. python的输入输出

- input(参数：输入提示词)
	- 可以用于存储键盘输入
   	- 举个例子
```python

	name = input("pls input your name")
	print(name)

``` 

- print(参数：需要打印的内容)
	- 可以输出任何你想要输出的内容
	- 举个例子

```python

	string = "Hello World!"
	print(string)	#Hello World!

```

- 格式化输出

	- 占位符

	占位符|含义
	-- | --
	%d | 整数
 	%f | 浮点
 	%s | 字符
 	%x | 十六进制数


```python
 	
	print("the result of '%d + %d' is %d" %(1,1,2))  

	print("the price is %s%.2f" %('AU$' ,3)) 


```

## 3. python的数据类型


##### 3.1 整数型
- 任何正整数和负整数还有0
- int()方法：
	将字符串类型的数字转换成整数型

```python

	int('1')
	int('-1')
	...

```

##### 3.2 浮点型

- 表示任何小数
- 以及科学计数法
- float()方法：
	将字符串类型的小数转换成浮点型

```python
# 表示科学计数法

	print(1e9)	#1000000000.0
	print(1e-3)	#0.001
	...


# float()方法
	float('3.1415926') 
	float('Inf')	#正无穷
	float('-Inf') 	#负无穷
```

##### 3.3 字符串
- 可以用单引号，双引号，或者三引号包裹字符串
	- 三种引号在python中可以仍以应用，但是要注意字符串前后的引号必须是用一种

```python
	
	print('Hello World!')
	print("Hello World!")
	print("""Hello World!""")

```
	
 - 以上三种引号的作用结果虽然不同，但是每种又有略小的区别。
 分别使用有时候可以提高编程效率

 	- 单引号*' '*和双引号*" "*的使用大致相同，基本可以使用任意一种
 	- 因为引号已经被用来表示字符转，但是如果字符串本身就包含引号怎么办？例如: 'I'm Ok'，字符串里的单引号会和包裹字符串的两个引号冲突，为解决这个问题可以有两种方法解决
 		1. 使用转义符'\\'转义字符串中的引号，此时这个引号就可以不用代表字符的开始和结束
 		2. 可以混用引号来进行区分
 	- 因为python是一种解释型编程语言，系统会逐行进行读取和运算。一般情况下，每句完整的语句应该在同一行完成，但是当字符串很长的时候，使用三引号就可以跨行来编写字符串。

```python

 	print('I\'m Ok')
 	print("I'm Ok")
 	print("""
 		I'm
 		Ok
 		""")

```

- 转义符
	- 转义系统已经定义的负号
	- \n 换行符
	- \t 制表符


##### 字符串string有关的一些常用方法

1. 大小写转换

		upper()负责将指定字符串变为大写，可以单独使用，也可以放到print函数中

		lower()负责将指定字符串变为小写，可以单独使用，也可以放到print函数中

		title()将给定的字符串中所有单词的首字母大写，其他全部小写

		capitalize()将给定的字符串中首字母大写，其他小写


2. is判断函数

		isdigit()判断给定的字符是否是整数

		isdecimal()判断给定字符串是否全为数字

		isalpha()判断给定的字符串是否全为字母

		isalnum()判断给定的字符串是否只含有数字与字母

		isupper()判断给定的字符串是否全为大写

		islower()判断给定的字符串是否全为小写

		istitle()判断给定的字符串是否符合title()

		isspace()判断给定的字符串是否为空白符（空格、换行、制表符）

		isprintable()判断给定的字符串是否为可打印字符（只有空格可以，换行、制表符都不可以）

		isidentifier()判断给定的字符串是否符合命名规则（只能是字母或下划线开头、不能包含除数字、字母和下划线以外的任意字符。）


3. 字符串搜索

		字符串位置搜索count(target, start, end)
		参数：
			target - 目标子字符穿
			start - 起始点
			end - 结束点


4. 字符串位置锁定find与index函数

		find(target, start, end) 返回第一个子字符串的位置信息，若无则为-1

		index(target, start, end) 返回第一个子字符串的位置信息，若无则为报错

5. 字符串切割

		split(sep=None, maxsplit=-1) 切割字符串，第一个参数是切割的点，第二个表示切割次数，默认是全部切割

6. 可迭代的数据结合成字符串

		字符串string、列表list、元组tuple、字典dict、集合set这些数据通过join()方法，可将所有元素合并成一条字符串

7. 字符串修剪

		strip([chars])

		strip()是为移除指定字符串char，如果没传入参数则为移除空格、制表符、换行符

##### 3.5 布尔值

- True / False

	- 常用语逻辑判断以及逻辑运算 


## 4. list和tuple

##### 4.1 list

python中非常常用的列表，可以任意删除和添加元素

- 创建一个list

```python
	
	#最直接的方法就是在[]里直接设定list里的元素
	letters = ['a', 'b', 'c', 'd']

	#也可以用list()方法，将字符串或者tuple转成list

	letters = "abc"
	list(letters)

	#list可以存储不同数据类型的元素

	list_example = ['a', 'b', 1, 2, True]

	#数组里面的元素可以是数组

	matrix = [[1,2,3], [4,5,6], [7,8,9]]

```

- 读取list中的元素


```python
	
	letters = ['a', 'b', 'c', 'd']

	#读取数组的长度
	len(letters)

	#根据index直接读取list中特定的元素
	print(letters[0])	# 输出'a'
	print(letters[-1])	# 输出'd'

	#也可以读取数组中的某一段元素
	print(letters[1 : 3]) # 输出 'b', 'c'

	#查找某个元素在list中的index
	print(letters.index('a')) # 输出 0

```


- 操作list里的元素

```python

	letters = ['a', 'b', 'c', 'd']

	#添加一个新的元素

	letters.append('e') # 新元素被添加到letters里，现在这个list里有['a', 'b', 'c', 'd', 'e']5个元素

	#插入一个新元素得到指定位置

	letters.insert(0, 'z') #新元素被插入到letters列表中的第一个位置， ['z', a', 'b', 'c', 'd', 'e']

	#从list中取出一个元素

	letters.pop() # pop()方法没有传入参数的时候，默认list里最后一个元素被取出

	letters.pop(0) # 传入参数0，list里第一个元素被取出
	
	#从list里面删除一个指定的元素

	letters.remove('b') # 元素'b'被从list删除


```

- 两个list还可以直接合并

```python

	a = [1,2,3]
	b = [4,5,6]
	print(a+b) #[1, 2, 3, 4, 5, 6]

```


- 对list里的元素进行排序

	- list 中有默认的sort(key, reverse)方法可以对list排序
	- 参数：
		- key：主要是用来进行比较的元素，默认是空
		- reverse：用来设置升序还是降序，reverse默认是False(降序)

```python

	increase = [5, 4, 3, 2, 1]
	increase.sort()  #升序排序[1, 2, 3, 4, 5]

	decrease = [1, 2, 3, 4, 5]
	decrease.sort(True)	#降序排序 [5, 4, 3, 2, 1]

```

```python

	def takeSecond(elem):
	    return elem[1]
 
	random = [(2, 2), (3, 4), (4, 1), (1, 3)]
	 
	# 指定第二个元素排序
	random.sort(key=takeSecond)

```
以上例子输出
```

	[(4, 1), (2, 2), (1, 3), (3, 4)]

```

##### 4.2 tuple

tuple和list类似，但是tuple创建以后就不能修改


```python

	a = (1, 2, 3) #定义了一个tuple

	a = () # 定义可一个空的tuple

	a = (1,) #定义一个tuple只有一个元素时，需要在元素后加一个逗号(,), 因为()本身可以表示成数学负号，加一个逗号就是为了消除奇异


```



## 5. dict和set

##### 5.1 dict的使用


字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})

```

	d = {key1 : value1, key2 : value2 }

```


```python

	cards_value = {'A': 1, '0': 10, 'J' : 11}

```

以上是一个字典的例子，这个字典里面存了扑克牌里的字母和字母代表的值的对应关系。不同字母的对应关系就可以通过字典来实现，方便我们查找和维护。


- 查找字典中的值

```python

	print(cards_value['A']) # 输出 1

	print(cards_value['0']) # 输出 10

```

- 修改字典中的元素

```python

	#直接修改
	cards_value['Q'] = 12


	# 通过update()方法
	cards_value.update({'K' : 13})


```
以上两种方法可以添加元素，也可以直接修改key对应的value


- 删除元素

```python

	#del方法
	del[cards_value['K']]


	#pop()方法
	value = cards_value.pop('Q') #删除元素'Q':12, 并得到它的value
	print(value)  # 输出


	#clear()方法
	cards_value.clear()  # 字典cards_value被全部清空	


```

- dict的一些内置方法


	- dict.clear() - 删除字典内所有元素
	
	- dict.copy() - 返回一个字典的浅复制
	
	- dict.get(key, default=None) - 返回指定键的值，如果值不在字典中返回default值
	
	- dict.has_key(key)	- 如果键在字典dict里返回true，否则返回false
	
	- dict.items() - 以列表返回可遍历的(键, 值) 元组数组
	
	- dict.keys() - 以列表返回一个字典所有的键

	- dict.values() - 以列表返回字典中的所有值


##### 5.2 set

集合（set）是一个无序的不重复元素序列。

可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。

```pytho

	#直接使用大括号
	a_set = {1, 2, 3}

	#set()函数
	set(1)

```


- 添加一个新的元素

```python

	#可以直接用add()添加元素
	a_set.add(4)

	#update()方法也可以添加元素，且参数可以是列表，元组，字典等，语法格式如下：
	a_set.update([5,6])

```
因为set是一个元素不重复的集合，所以当重复添加元素的时候，set集合不会发生变化

- 删除一个元素

```python


	#remove()方法可将元素 x 从集合 s 中移除，如果元素不存在，则会发生错误。

	a_set.remove(6)


	#dicard()方法也可以移除集合中的元素，且如果元素不存在，不会发生错误。格式如下所示：

	a_set.discard(6)

