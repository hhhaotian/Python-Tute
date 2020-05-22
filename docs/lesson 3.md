# Lesson 3
---

## 1. lambda表达

#### Lambda表达式定义

```python

	lambda parameters : expression

```

等价通过def定义的函数

```python

	def <lambda>(parameters):
		return expression

```
lambda函数本身不需要return来返回值，表达式结果本身就是返回值


和定义普通function一样，lambda表达式也能设置参数的默认值，例如：

```python

	lambda x=1, y=2 : x+y

	def plus(x=1, y=2):
		return x+y

```

#### Lambda函数调用

- 直接赋值给一个变量，然后再像一般函数一样调用

```python
	
	func = lambda x:x**2
	print(func(2))


```

- 直接传入参数

```python

	(lambda x:x**2)(2)

```

- 用于高阶函数中，例如sorted, map, filter


##### sorted

例如根据字典中的value进行排序

```python

	
	a = {'a':5, 'b':3, 'c':1}

	sorted(a.items(), key = lambda x:x[1])

	#等价于

	def item_value(item):
		return item[1]
	sorted(a.items(), key = item_value)


```

##### map

```python


	map(lambda x:x**2, range(1,101))
	

```

##### filter

```python

	filter(lambda x:x%3==0, range(10))

```



- 嵌套在函数中使用
```python

	def lambda_fun(n):
	    return lambda x : x + n

	f_5 = lambda_fun(5)   # lambda x:x+5
	print(f_5(1))

```


#### lambda表达式的优缺点

- 优点：
	- 代码简洁
	- 不用额外增加变量

- 缺点：
	- 牺牲了代码的可读性
	- 大部分lambda函数都可以被标准库里的函数代替
