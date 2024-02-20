# 用正则表达式查找文本模式
| 字符 | 含义 |
| ---- | ---- |
| \d | 表示一位数字字符 |
| () | 分组，一个括号括起来的正则表达式，就是一个组。（使用group([编号])获取那个组中的数据。如果想要获取全部组，使用groups()方法。） |
| \ | 转义字符‘\’用于转义下一个字符，使其不再具有特殊意义。例如：‘\.’匹配点而不是匹配任何字符。 |
| \| | ‘\|’称为管道符，用于表示“或”的关系。具体而言，`A\|B`表示匹配A或B |
| ？ | **零次或一次匹配（可选项）：** 在一个字符或一个括号表达式后面放置 `?`，表示该字符或表达式是可选的，即可以出现零次或一次。例如，`colou?r` 匹配 "color" 和 "colour"。 |
|  |  |
## 利用括号分组
```python
import re

phoneNumRegex = re.compile(r'(\d{3})-(\d{3}-\d{4})')
mo = phoneNumRegex.search('My number is 415-555-4242.')

# 输出整个匹配的电话号码
print(mo.group())  # 输出 "415-555-4242"

# 输出第一个分组，即区号
print(mo.group(1))  # 输出 "415"

# 输出第二个分组，即剩余的号码部分
print(mo.group(2))  # 输出 "555-4242"

# 输出所有分组的元组
print(mo.groups())  # 输出 ('415', '555-4242')
'''
程序在Pycharm中运行的结果为:
------------------------
415-555-4242
415
555-4242
('415', '555-4242')
------------------------
总结:
在这个例子中，`mo.groups()` 返回的是一个包含所有分组匹配结果的元组。
'''
```
## 利用管道匹配多个分组
```python
import re

heroRegex = re.compile(r'Batman|Tina Fey')

# 在 'Batman and Tina Fey.' 中匹配到了 Batman
mo1 = heroRegex.search('Batman and Tina Fey.')
print(mo1.group())  # 输出 "Batman"

# 在 'Tina Fey and Batman.' 中匹配到了 Tina Fey
mo2 = heroRegex.search('Tina Fey and Batman.')
print(mo2.group())  # 输出 "Tina Fey"

'''
程序在Pycharm中运行的结果为:
------------------------
Batman
Tina Fey
------------------------
总结:
正则表达式中的 `|` 表示“或”的关系，即匹配其中一个模式。在这里，它匹配字符串中的 `Batman` 或 `Tina Fey`。
'''
```
## 利用问号实现可选匹配
```python
import re

phoneRegex = re.compile(r'(\d{3}-)?\d{3}-\d{4}')

# 在 'My number is 415-555-4242' 中匹配到了完整的电话号码
mo1 = phoneRegex.search('My number is 415-555-4242')
print(mo1.group())  # 输出 "415-555-4242"

# 在 'My number is 555-4242' 中匹配到了没有区号的电话号码
mo2 = phoneRegex.search('My number is 555-4242')
print(mo2.group())  # 输出 "555-4242"

'''
程序在Pycharm中运行的结果为:
------------------------
415-555-4242
555-4242
------------------------
总结:
正则表达式 `(\d{3}-)?` 表示一个可选的区号部分，其中 `(\d{3}-)` 匹配三个数字加一个短横线，`?` 表示前面的组可以出现 0 次或 1 次。这样就允许匹配带区号和不带区号的电话号码。
'''
```
## 利用星号匹配零次或多次
```python
batRegex = re.compile(r'Bat(wo)*man')  
mo1 = batRegex.search('The Adventures of Batman')  
print(mo1.group())  
  
mo2 = batRegex.search('The Adventures of Batwoman')  
print(mo2.group())  
  
mo3 = batRegex.search('The Adventures of Batwowoman')  
print(mo3.group())

'''
程序在Pycharm中运行的结果为:
------------------------
Batman
Batwoman
Batwowoman
------------------------
总结:
'''
```