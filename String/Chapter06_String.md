# 有用的字符串方法
## upper()和lower()
- upper()和 lower()字符串方法返回一个新字符串，其中原字符串的所有字母都被 相应地转换为大写或小写。字符串中非字母字符保持不变。
### upper()
```python
spam = 'Hello world!~'  
  
# upper()方法返回一个新字符串。  
# 该方法会将原字符串中的所有字符，转换为大写。  
# 字符串中非字母字符保持不变。  
free = spam.upper()  
print(free)  # HELLO WORLD!~  
print(spam)  # Hello world!~
```
### lower()
```python
print('How are you?')  
feeling = input()  
  
# lower()方法返回一个新字符串。  
# 该方法会将原字符串中的所有字符，转换为小写。  
# 字符串中非字母字符保持不变。  
if feeling.lower() in 'great':  
    print('I feel great too.')  
else:  
    print('I hope the rest of your day is good.')
```

## isupper()和islower()
- 字符串至少有一个字母，**并且所有字母都是大写或小写**。
- isupper()：如果所有字符都是大写，则返回True，否则返回False。
- islower()：如果所有字符都是小写，则返回True，否则返回False。
### isupper()
```python
>>> spam = 'Hello world!'
>>> spam.isupper()
False
>>> 'HELLO'.isupper()
True
>>> 'HELLO123'.isupper()
True
>>> '123'.isupper()
False
```
### islower()
```python
>>> spam = 'Hello world!'
>>> spam.islower()
False
>>> 'abc123'.islower()
True
>>> '123'.islower()
False
>>>
```
# isX字符串方法
- isalpha()返回True，如果字符串只包含字母，并且非空；
- isalnum()返回 True，如果字符串只包含字母和数字，并且非空；
- isdecimal()返回 True，如果字符串只包含数字字符，并且非空；
- isspace()返回True，如果字符串只包含空格、制表符和换行，并且非空；
- istitle()返回True，如果字符串仅包含以大写字母开头、后面都是小写字母的单词。
# startswith()和endswith()
- startswith()方法判断传入的字符串是否和字符串开始的字符一致。
- endswitch()方法判断传入的字符串是否和字符串结尾的字符一致。
```python
>>> 'Hello world!'.startswith('Hello')
True
>>> 'Hello world!'.endswith('world!')
True
>>> 'abc123'.startswith('abcd')
False
>>> 'Hello world!'.startswith('Hello world!')
True
>>> 'Hello world!'.endswith('Hello world!')
True
```
# join()和split()
- join()方法在一个字符串上调用，参数是一个字符串列表，返回一个 字符串。返回的字符串由传入的列表中每个字符串连接而成。
```python
>>> ','.join(['cats','rats','bats'])
'cats,rats,bats'
```
- split()方法，针对一个字符串调用，返回一个字符串列表。
```python
>>> 'My name is Simon'.split()
['My', 'name', 'is', 'Simon']
```
# strip()、rstrip()、lstrip()删除空白字符
- strip()字符串方法将返回一个新的字符串，它的开头或末尾都没有空白字符。 
```python
>>> spam = ' Hello World '
>>> spam.strip()
'Hello World'
```
- lstrip()和 rstrip()方法将相应删除左边或右边的空白字符。
```python
>>> spam.lstrip()
'Hello World '
>>> spam.rstrip()
' Hello World'
```