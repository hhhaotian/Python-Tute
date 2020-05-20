# Lesson 2

---
## 1. Itertor in Python

#### 1.1 迭代器

在python中，所有可以迭代的数据除了可以通过for循环或while循环一次遍历其中的子元素，还可以通过迭代iter()进行遍历

```python

	a_list = [1,2,3,4,5]

	#通过for循环
	for number in a_list:
		print(number)

	#通过iter()方法得到一个迭代对象
	iter_list = iter(a_list)

	#迭代对象可以通过for循环进行遍历
	for iter_element in iter_list：
		print(iter_element)

	#也可以通过next()方法进行遍历
	while True:
		try:
			print(next(iter_list))
		except StopIteration:
			print("stop iteration")

```

注意，每个迭代对象只能被遍历一遍，不可以重复遍历


#### 1.2 itertools - 排列组合迭代器



|迭代器 | 实参 | 结果 |
| ------ | ------ | ------ |
| product() | p, q, ... [repeat=1] | 笛卡尔积，相当于嵌套的for循环 |
| permutations() | p[, r] | 长度r元组，所有可能的排列，无重复元素 |
| combinations() | p, r | 长度r元组，有序，无重复元素 |
| combinations_with_replacement() | p, r | 长度r元组，有序，元素可重复 |









## 2. Image Processing


#### 2.1 下载pillow

	pillow是一个第三方图像处理包，想要在自己电脑上使用pillow库里的一系列工具首先需要安装pillow

```
	
	#通过pip安装pillow

	sudo pip3 install pillow

	#通过conda安装pillow

	conda install pillow

```


#### 2.2 加载图像

	可以通过Image里的load()方法加载已有图片，这个方法的参数是完整的文件名(要包括文件后缀)

```python

	from PIL import Image

	Image.open('example.png')

```

#### 2.3 创建新的图片

	通过Image里的new()方法可以创建三种不同类型的空白文件，

	- 第一个参数是mode（颜色模式）；
		- "1": 黑白图片
		- "L": 灰度图
		- "RGB": 彩色

	- 第二个参数是图片大小（size）；
		- (width * height)

	- 第三个参数是初始颜色（默认颜色是黑色）

		- 可以直接填入常用颜色的名称。如'red'
		- 也可以填入十六进制表示的颜色，如#FF0000表示红色。
		- 还能传入元组，比如(255, 0, 0, 255)或者(255， 0， 0)表示红色。

	新创建的图像文件可以使用new()方法储存到本地，new()方法的使用和load()方法类似


```python

	from PIL import Image

	#创建一个彩分辨率为100x100的红色图片
	Image.new('RGB', (100, 100), 'red')

```

#### 2.4 获取Image类信息有关的一些方法

```python

	#显示图像
	Image.show()

	#图像的模式
	Image.mode()

	#图像的大小
	Image.size()

	#图像的格式
	Image.format()


```

#### 2.5 获取某个像素点上的值

通过getpixel(position)方法获取图片上像素点的值，参数：有tuple组成的坐标

-  (x,y)
	- x: 到图像左边的距离 
	- y: 到图像顶边的距离

#### 2.6 设置图像上像素点的值

通过putpixel(position, color)方法设置图片某个像素点的值
- 第一个参数：像素点的位置，也是由tuple组成的坐标
- 第二个参数：设置的颜色，只能通过具体的值来设定

```python

	from PIL import Image

	#创建一个2*2颜色为黑色的黑白图片
	im1 = Image.new('1', (2, 2))
	#将(0,0)像素点设置成白色
	im1.putpixel((0, 0), 1)

	#创建一个2*2的黑色的彩色图片
	im2 = Image.new("RGB", (2, 2))
	#(0，0)像素点设置成红色
	im2.putpixel((0, 0), (255, 0, 0))

```

#### 2.7 图像缩放

通过resize()方法可以缩放图像

```python

	from PIL import Image

	im = Image.new('1', (10,10), 1)
	im.resize((100, 100))

```

