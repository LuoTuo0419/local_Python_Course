Variable
# 变量快速入门

## 代码举例

```python
# 定义了一个变量，变量的名称是 a ，变量的值为 10 ，变量的类型为 int
a = 10

# 定义了一个变量，变量的名称是 b ,变量的值为 20，变量的类型为 int
b = 20

# 将变量b的值修改为 8
b = 8

print("a 的值为 ", a, " a的类型为 ", type(a))
print("b 的值为 ", b, "  b的类型为 ", type(b))
```

### 代码在内存中的样子

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/14d1fe5c-747c-4456-b9a2-2101e9eddd56/1ca07660-9c1c-433c-8f56-11a8b161e915/Untitled.png)

# 格式化输出

## 代码举例

```python
# 格式化输出案例

# 定义变量
name = 'jack'
age = 20
gender = 'man'
score = 90.5

# %操作符输出
print("个人信息：%s %d %s %.2f" % (name, age, gender, score))

# format操作符输出
print("个人信息：{} {} {} {}".format(name, age, gender, score))

# f-string操作符输出
print(f"个人信息：{name} {age} {gender} {score}")
```

## 程序中+号的使用

1. 当左右两边都是数值型时，则做加法运算。
2. 当左右两边都是字符串时，则做拼接运算。

### 代码举例

```python
# + 号的使用案例

name = 'jack'
score = 60.7

print(score + 50)    # 110.7
print(name + 'Hi')   # jackHi
print("100" + "98")  # 10098
print(34.5 + 100)    # 134.5

# TypeError: can only concatenate str (not "int") to str
# 字符串只能和字符串拼接，不可以和整数拼接
print('number ：' + 34) #报错
```

# 数据类型

## 基本数据类型

|类型|描述|
|---|---|
|整型 int|1，-1，200|
|浮点型 float|1.1，-4.5|
|字符串string|Python中用成对的单引号或双引号括起来|
|布尔值bool|True，False|

## type()函数查看数据类型

### type()基本使用

- 语法：type(object)
- object就是你要查看类型的数据，可以是一个具体的数据（即：字面值），也可以是变量（也就是查看该变量指向的数据的类型）

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/14d1fe5c-747c-4456-b9a2-2101e9eddd56/9f1f97bb-ca82-4b5f-b442-081adf7e132a/Untitled.png)

### 代码举例

```python
# type() 函数的使用

name = 'tom'
age = 20
score = 90.4
gender = 'man'
is_pass = True

print(f"name 的类型为：{type(name)}")
print(f"age  的类型为：{type(age)}")
print(f"score 的类型为：{type(score)}")
print(f"gender 的类型为：{type(gender)}")
print(f"is_pass 的类型为：{type(is_pass)}")

'''
程序在Pycharm中运行的结果为:
------------------------
name    的类型为：<class 'str'>
age     的类型为：<class 'int'>
score   的类型为：<class 'float'>
gender  的类型为：<class 'str'>
is_pass 的类型为：<class 'bool'>
------------------------
总结:
'''
```

# 整型的使用细节

## 整型可以存放的最大数

```python
# int类型可以存放的最大数值测试

n1 = 2 ** 99999
# 报错
# ValueError: Exceeds the limit (4300 digits) for integer string conversion;
# use sys.set_int_max_str_digits() to increase the limit
print(f"n1的类型为：{type(n1)} n1的值为：{n1}")

'''
程序在Pycharm中运行的结果为:
------------------------
    print(f"n1的类型为：{type(n1)} n1的值为：{n1}")
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
ValueError: Exceeds the limit (4300 digits) for integer string conversion; use sys.set_int_max_str_digits() to increase the limit
------------------------
总结:
'''
```

## 整型占多少个字节

- 字节(Byte)：计算机中基本存储单位
- 位(bit)：计算机中的最小存储单位
- 1 byte = 8 bit

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/14d1fe5c-747c-4456-b9a2-2101e9eddd56/a5239cc0-aa03-43d3-b2e1-44ff25f85ba6/Untitled.png)

1. 字节数随着数字增大而增大（即：python整型是变长的）
2. 每次的增量是4个字节

```python
# int类型存放数据，如果要存放的数字大于了要存放空间的大小，会按每4个字节增量。
# sys.getsizeof 可以查看变量在内存中所占的字节数。

n1 = 0
n2 = 1
n3 = 2
n4 = 2 ** 10
n5 = 2 ** 20
n6 = 2 ** 30
n7 = 2 ** 40

# sys.getsizeof(object[, default])
# 返回对象的大小（以字节为单位）。该对象可以是任何类型。所有内建对象返回的结果都是正确的，但对于第三方扩展不一定正确，因为这与具体实现有关。
print(f"n1 = {n1} n1在内存中所占的字节数为：{sys.getsizeof(n1)}")
print(f"n2 = {n1} n2在内存中所占的字节数为：{sys.getsizeof(n2)}")
print(f"n3 = {n3} n3在内存中所占的字节数为：{sys.getsizeof(n3)}")
print(f"n4 = {n4} n4在内存中所占的字节数为：{sys.getsizeof(n4)}")
print(f"n5 = {n5} n5在内存中所占的字节数为：{sys.getsizeof(n5)}")
print(f"n6 = {n6} n6在内存中所占的字节数为：{sys.getsizeof(n6)}")
print(f"n7 = {n7} n7在内存中所占的字节数为：{sys.getsizeof(n7)}")

'''
程序在Pycharm中运行的结果为:
------------------------
n1 = 0 n1在内存中所占的字节数为：28
n2 = 0 n2在内存中所占的字节数为：28
n3 = 2 n3在内存中所占的字节数为：28
n4 = 1024 n4在内存中所占的字节数为：28
n5 = 1048576 n5在内存中所占的字节数为：28
n6 = 1073741824 n6在内存中所占的字节数为：32
n7 = 1099511627776 n7在内存中所占的字节数为：32
------------------------
总结:
1. 计算 数据类型在内存中所在的字节数，可以用 sys.getsizeof()方法实现。
'''
```

# 浮点数类型

## 浮点数类型的使用细节

### 浮点数表示形式

1. 十进制数形式：5.12、.512（必须有小数点）
2. 科学计数法形式：5.12E2、5.12E-2

### 浮点类型的精度问题

- 浮点类型计算后，存在精度的损失，可以使用Decimal类进行精确计算。

```python
# 正确结果：2.7 输出结果：2.6999999999999997
print(f"8.1 / 3 = {8.1 / 3}")

# 解决办法：使用Decimal类进行精确计算
# 导入 Decimal类
from decimal import Decimal

print(f"Decimal('8.1') / Decimal('3') = {Decimal('8.1') / Decimal('3')}")

'''
程序在Pycharm中运行的结果为:
------------------------
8.1 / 3 = 2.6999999999999997
Decimal('8.1') / Decimal('3') = 2.7
------------------------
总结:
'''
```

# 布尔类型

## 基本介绍

1. 布尔类型也叫bool类型，取值True和False。
2. True和False都是关键字，表示布尔值。
3. bool类型适用于逻辑运算，一般用于程序流程控制。

## 案例演示

```python
# bool类型的基本使用

num1 = 100
num2 = 200

if num1 > num2:
    print("num1 > num2")

# 将 num1 > num2 比较的结果 赋值给 result 变量
result = num1 > num2

print(f"result 类型的变量值为：{result}")

print(f"result 类型的变量类型为：{type(result)}")

'''
程序在Pycharm中运行的结果为:
------------------------
result 类型的变量值为：False
result 类型的变量类型为：<class 'bool'>
------------------------
总结:
'''
```

## 布尔类型使用细节

1. 布尔类型只有两个值，True和False。
2. 布尔类型可以和其他数据类型进行比较，比如：数字、字符串等。在比较时，Python会将True视为1，False视为0。
3. 在Python中，非0被视为真值，0值被视为假值。

```python
b1 = True
b2 = False

# 将布尔类型和整型进行计算
print(b1 + 10)
print(b2 + 10)

# 将布尔类型和整型进行比较
if b1 == 1:
    print("True")

if b2 == 0:
    print("False")

'''
程序在Pycharm中运行的结果为:
------------------------
11
10
True
False
------------------------
总结:
'''
```

# 字符串类型

## 基本介绍

1. 字符串是 Python 中很常用的数据类型，通俗来说，字符串就是字符组成的一串内容。
    
2. 使用引号(’ 或 “)包括起来，创建字符串。
    
3. str就是string的缩写，在使用type()查看数据类型时，字符串类型显示的是str。
    
    ```python
    print(type("hello")) # <class 'str'>
    ```
    
4. 通过加号可以连接字符串。
    

## 字符串使用注意事项

1. Python 不支持单字符类型，单字符在Python中也是作为一个字符串使用。
    
2. 用三个单引号 ‘’’内容’’’ ，三个双引号 ”””内容””” 可以使字符串内容保持原样输出，在输出格式复杂的内容是比较有用的，比如输出一段代码。
    
    ```python
    print('''if b1 == 1:
        print("True")
    
    if b2 == 0:
        print("False")
    
    print(type("hello"))''')
    
    '''
    程序在Pycharm中运行的结果为:
    ------------------------
    if b1 == 1:
        print("True")
    
    if b2 == 0:
        print("False")
    
    print(type("hello"))
    ------------------------
    总结:
    '''
    ```
    
3. 在字符串前面加’r’可以使整个字符串不会被转义。
    
    ```python
    print(r'luotuo \\t man \\t 20') # luotuo \\t man \\t 20
    ```
    

## 字符串驻留机制

### 什么是字符串驻留机制

Python仅保存一份相同且不可变字符串，不同的值被存放在字符串的驻留池中，Python的驻流机制对相同的字符串只保留一份拷贝，后续创建相同字符串时，不会开辟新空间，而是把该字符串地址赋给新创建的变量。

![[字符串驻留机制.png]]

### 驻留机制几种情况讨论（注意：需要在交互模式下 win + R → Python）

1. 字符串是由26个英文字母大小写，0-9，_ 组成
    
    ```python
    # 变量指向同一块内存空间
    >>> a = 'abc123_'
    >>> b = 'abc123_'
    >>> id(a)
    2428627749488
    >>> id(b)
    2428627749488
    
    # 变量没有指向同一块内存空间
    >>> a = 'abc123#'
    >>> b = 'abc123#'
    >>> id(a)
    2428627761200
    >>> id(b)
    2428629220720
    ```
    
2. 字符串长度为0或1
    
3. 字符串在编译时进行驻留，而非运行时
    
    ```python
    >>> a = 'abc'
    >>> b = ''.join(['a','b','c'])
    >>> a
    'abc'
    >>> b
    'abc'
    >>> id(a)
    140736142118688
    >>> id(b)
    2428627749488
    ```
    
4. [-5,256]的整数数字
    
    ```python
    >>> a = -5
    >>> b = -5
    >>> id(a)
    140736143483496
    >>> id(b)
    140736143483496
    
    >>> a = 256
    >>> b = 256
    >>> id(a)
    140736143491848
    >>> id(b)
    140736143491848
    
    >>> a = -6
    >>> b = -6
    >>> id(a)
    2428625665328
    >>> id(b)
    2428628152976
    
    >>> a = 257
    >>> b = 257
    >>> id(a)
    2428628152080
    >>> id(b)
    2428628149264
    ```
    
### PyCharm对字符串进行了优化处理
* Pycharm编译器对上面的情况做了优化。
    ```python
    a = 'abc123#'
    b = 'abc123#'
    
    print(id(a))
    print(id(b))
    
    '''
    程序在Pycharm中运行的结果为:
    ------------------------
    1680558952816
    1680558952816
    ------------------------
    总结:
    '''
    ```
# 数据类型转换
## 隐式类型转换
- python变量的类型不是固定的，是根据变量当前值在运行时决定的，可以通过内置函数type(变量)来查看其类型，这种方式就是隐式转换。
	```python
	a = 10  
	b = 1.1  
	  
	var1 = a + b  
	print(f'var1 = {var1} var1的类型：{type(var1)}')  
	var2 = a + 0.1  
	print(f'var2 = {var2} var2的类型：{type(var2)}')
	
	'''
	程序在Pycharm中运行的结果为:
	------------------------
	var1 = 11.1 var1的类型：<class 'float'>
	var2 = 10.1 var2的类型：<class 'float'>
	------------------------
	总结:
	'''
	```
## 显示类型转换
- int()、float()、str()
### 显示类型转换的注意事项
1. 不管值是int，float等等，都可以转换成str，str(x)将对象x转换为字符串。
	```python
	a = 1  
	b = 1.1  
	  
	print(f"a 的类型为 {type(a)} ,使用 str()函数转换后的类型为 {type(str(a))}")  
	print(f"b 的类型为 {type(b)} ,使用 str()函数转换后的类型为 {type(str(b))}")
	
	'''
	程序在Pycharm中运行的结果为:
	------------------------
	a 的类型为 <class 'int'>   ,使用 str()函数转换后的类型为 <class 'str'>
	b 的类型为 <class 'float'> ,使用 str()函数转换后的类型为 <class 'str'>
	------------------------
	总结:
	'''
	```
2. int转换成float时，会增加小数部分，比如 123 -> 123.0。float转成int时，会去掉小数部分，比如 123.65 -> 123
	```python
	a = 1  
	b = 1.1  
	  
	print(f"a的值为：{a} ")  
	print(f"b的值为：{b} ")  
	a = float(a)  
	b = float(b)  
	print(f"a 的类型为 {type(a)} ,使用 float()函数转换后的类型为 {type(a)} a转换后的值为：{a}")  
	print(f"b 的类型为 {type(b)} ,使用 float()函数转换后的类型为 {type(b)} b转换后的值为：{b}")
	
	'''
	程序在Pycharm中运行的结果为:
	------------------------
	a的值为：1 
	b的值为：1.1 
	a 的类型为 <class 'float'> ,使用 float()函数转换后的类型为 <class 'float'> a转换后的值为：1.0
	b 的类型为 <class 'float'> ,使用 float()函数转换后的类型为 <class 'float'> b转换后的值为：1.1
	------------------------
	总结:
	'''

	```
3. 在将str类型转成基本数据类型时，要确保str值能够转成有效的数据，比如 我们可以把"123"，转成一个整数，但是不能把"hello"转换成一个整数，如果格式不正确，程序会报 ValueError，程序就会终止。
4. 对一个变量进行强制转换，会返回一个数据/值，注意，强制转换后，并不会影响原变量的数据类型(即：不会影响原变量指向的数据/值的数据类型)
	```python
	i = 10  
	j = float(i)  
	  
	print(f"i 的值为 {i} i 的类型为 {type(i)}")  
	print(f"j 的值为 {j} j 的类型为 {type(j)}")
	
	'''
	程序在Pycharm中运行的结果为:
	------------------------
	i 的值为 10 i 的类型为 <class 'int'>
	j 的值为 10.0 j 的类型为 <class 'float'>
	------------------------
	总结:
	'''
	```
	