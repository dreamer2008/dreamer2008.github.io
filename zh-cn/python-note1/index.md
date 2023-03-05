# Python学习笔记1


![Python](http://www.kandasoft.com/wp-content/uploads/2014/02/Python-Programming-Language.png)

# Python入门
## Python简介
脚本语言。解释语言。动态语言。默认的解释器CPython。
Python之父—荷兰人Guido van Rossum。诞生于1989年。第一个公开发行版发行于1991年

## Python用途
1. 是网络应用，包括网站、后台服务等等；
2. 其次是许多日常需要的小工具，包括系统管理员需要的脚本任务等等；
3. 另外就是把其他语言开发的程序再包装起来，方便使用
4. 目前广泛应用于大数据和人工智能领域

## Python优缺点
* 性能差
* 源码不能加密

## 第一个Python程序
```
print('hello,world')
``` 
## 编程方式
### 交互式
### 脚本式
Python式和Shell式
# 基础语法
## 基本特点
* 大小写敏感
* 缩进（4个空格）而不是括号
* 注释：单行#，多行：'''或者""" 
* input()和print()

## 数据类型
### 整数
在整数除法中，除法（/）总是返回一个浮点数。，如果只想得到整数的结果，丢弃可能的分数部分，可以使用运算符//，称为地板除

### 浮点数

### 字符串
* Python中的字符串不能改变。在Python3中，所有的字符串都是Unicode字符串
* 字符串是以单引号'或双引号"括起来的任意文本，比如'abc'，"xyz"。多行字符串'''或""")
* 默认不转义。转义：\  不转义/自然字符串：通过在字符串前加r或R
* 反斜杠(\)可以作为续行符，表示下一行是上一行的延续。也可以使用 """...""" 或者 '''...''' 跨越多行
* 字符串可以用+运算符连接在一起，用*运算符重复
* Python中的字符串有两种索引方式，从左往右以0开始，从右往左以-1开始

```
str = 'Runoob'
 
print (str)          # 输出字符串
print (str[0:-1])    # 输出第一个到倒数第二个的所有字符
print (str[0])       # 输出字符串第一个字符
print (str[2:5])     # 输出从第三个开始到第五个的字符
print (str[2:])      # 输出从第三个开始的后的所有字符
print (str * 2)      # 输出字符串两次
print (str + "TEST") # 连接字符串
```
### List
* List（列表）是 Python 中使用最频繁的数据类型
* 列表是写在方括号([])之间、用逗号分隔开的元素列表
* list是一种有序的集合，列表中的元素是可以改变的
* 列表中元素的类型可以不相同，它支持数字，字符串甚至可以包含列表（所谓嵌套）
* 支持append,pop,insert

```
list = [ 'abcd', 786 , 2.23, 'runoob', 70.2 ]
tinylist = [123, 'runoob']
 
print (list)            # 输出完整列表
print (list[0])         # 输出列表第一个元素
print (list[1:3])       # 从第二个开始输出到第三个元素
print (list[2:])        # 输出从第三个元素开始的所有元素
print (tinylist * 2)    # 输出两次列表
print (list + tinylist) # 连接列表
```

### Tuple
* 元组（tuple）与列表类似，不同之处在于元组的元素不能修改。
* 元组写在小括号(())里。可以把字符串看作一种特殊的元组
* 虽然tuple的元素不可改变(“指向不变”)，但它可以包含可变的对象
* 构造包含 0 个或 1 个元素的元组比较特殊，所以有一些额外的语法规则：
```
tup1 = ()    # 空元组
tup2 = (20,) # 一个元素，需要在元素后添加逗号
```
* string、list和tuple都属于sequence（序列）

### Set

* 集合（set）是一个无序不重复元素的序列。
* 基本功能是进行成员关系测试和删除重复元素。
* 可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set()
* 操作：add,remove 集合运算

```
student = {'Tom', 'Jim', 'Mary', 'Tom', 'Jack', 'Rose'}
s = set([1, 2, 3])
```

### Dict
* 列表是有序的对象结合，字典是无序的对象集合。两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取
* 字典是一种映射类型，字典用"{ }"标识，它是一个无序的键(key) : 值(value)对集合。
* 键(key)必须使用不可变类型。
* 在同一个字典中，键(key)必须是唯一的。
* dict是用空间来换取时间的一种方法
要避免key不存在的错误，有两种办法，一是通过in判断key是否存在：

```
>>> 'Thomas' in d
False
```

二是通过dict提供的get方法，如果key不存在，可以返回None，或者自己指定的value：

```
>>> d.get('Thomas')
>>> d.get('Thomas', -1)
-1
```

### 布尔值
只有True和False两个值。可以参与and、or和not运算

### 复数
可以用a + bj,或者complex(a,b)表示， 复数的实部a和虚部b都是浮点型。如 1 + 2j、 1.1 + 2.2j

### 空值
空值是Python里一个特殊的值，用None表示。None不能理解为0，因为0是有意义的，而None是一个特殊的空值

### 类型判断
type()不会认为子类是一种父类类型。
isinstance()会认为子类是一种父类类型。

##变量
a, b, c = 1, 2, "runoob"
##常量
PI=3.14
## 数值运算与运算符

### 算术运算符
* 2**5 # 乘方
* 17 % 3 # 取余

### 比较运算符
!=

### 赋值运算符

### 位运算符

### 逻辑运算符
and or not

### 成员运算符
in, not in

```
a = 10
b = 20
list = [1, 2, 3, 4, 5 ];
 
if ( a in list ):
   print ("1 - 变量 a 在给定的列表中 list 中")
else:
   print ("1 - 变量 a 不在给定的列表中 list 中")
```

### 身份运算符
身份运算符用于比较两个对象的存储单元。类似于Java的==。
* is:x is y, 类似 id(x) == id(y)
* is not,x is not y ，类似 id(a) != id(b)
* is 与 == 区别：
is 用于判断两个变量引用对象是否为同一个， == 用于判断引用变量的值是否相等。
# 控制结构
## 条件判断
```
age = 3
if age >= 18:
    print('adult')
elif age >= 6:
    print('teenager')
else:
    print('kid')
```

## 循环

### for in
一种是for...in循环，经常用到range()函数。可以有else从句

```
names = ['Michael', 'Bob', 'Tracy']
for name in names:
    print(name)
```

```
sum = 0
for x in range(101):
    sum = sum + x
print(sum)
```

### while
第二种循环是while循环。可以有else从句

```
sum = 0
n = 99
while n > 0:
    sum = sum + n
    n = n - 2
print(sum)
```

### break
### continue
### end 关键字
关键字end可以用于将结果输出到同一行，或者在输出的末尾添加不同的字符

### 迭代器
* 迭代是Python最强大的功能之一，是访问集合元素的一种方式
* 迭代器是一个可以记住遍历的位置的对象
* 迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束。迭代器只能往前不会后退
* 迭代器有两个基本的方法：iter() 和 next()

## 再议不可变对象
对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的


# 参考资料
## Python 2.x vs 3.x
2008年, Python3发布。最大的变化是源码文件默认使用utf-8编码
- 更多区别：[Python3.x和Python2.x的区别](http://www.admin10000.com/document/144.html)
## 学习材料
* [廖雪峰Python3教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
* [Runoob Python3教程](http://www.runoob.com/python3/python3-tutorial.html)
* [PHPXS Python基础教程](http://www.phpxs.com/j/python)
