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


## 2. recursion 



递归需要保证每次递归的范围都逐渐缩小
还要设置边界条件，以确保递归可以结束


#### 使用recursion和while loop求斐波那契数列的第n项

斐波那契数列：0，1，1，2，3，5

```python
	
	#recursion
	def fib(n):
	    if n < 2:
	        return n
	    else:
	        return fib(n-2)+fib(n-1)

	# while loop
	def fib_loop(n):
	    a,b = 0,1
	    while n > 0:
	        a, b = b, a+b
	        n -= 1
	    return a


```

#### 通过recursion和while loop在list里查找元素n

numbers = [2,3,4,5,7,8,9]

```python

#通过二分法查找list里的元素
def find_number_recursion(numbers, n):
    if len(numbers) == 0:
        return None
    middle = len(numbers)//2
    if numbers[middle] == n:
        return n
    else:
        if numbers[middle] > n:
            return find_number_recursion(numbers[:middle],n)
        else:
            return find_number_recursion(numbers[middle+1:],n)



def find_number_by_loop(numbers,n):
    while True:
        middle = len(numbers)//2
        if len(numbers) == 0:
            return None
        if numbers[middle] == n:
            return n
        if numbers[middle] > n:
            numbers = numbers[:middle]
        else:
            numbers = numbers[middle+1:]

```


#### 通过recursion计算等差数列第n项

```python

def arithmetical_sequence(a_0, d, n):
    if n == 1:
        return a_0
    return arithmetical_sequence(a_0+d,d,n-1)

```


#### 通过recursion查找单词list里最长的单词

```python

def find_longest_words(words):
    if len(words) == 0:
        return None
    if len(words) == 1:
        return words[0]
    rest_words = find_longest_words(words[1:])
    if len(words[0]) >= len(rest_words):
        return words[0]
    else:
        return rest_words

```





