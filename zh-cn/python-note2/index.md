# Python学习笔记2


![Python](http://www.kandasoft.com/wp-content/uploads/2014/02/Python-Programming-Language.png)


# 函数
函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段
## 参数传递

* 传不可变对象实例：在 python 中，strings, tuples, 和 numbers 是不可更改的对象
* 传可变对象实例：而 list,dict 等则是可以修改的对象

## 参数类型
* 必需参数
* 关键字参数：使用关键字参数允许函数调用时参数的顺序与声明时不一致
* 默认参数
* 变长参数

## 递归函数
## 匿名函数
lambda [arg1 [,arg2,.....argn]]:expression

```
sum = lambda arg1, arg2: arg1 + arg2;
 
# 调用sum函数
print ("相加后的值为 : ", sum( 10, 20 ))
print ("相加后的值为 : ", sum( 20, 20 ))
```

## 变量作用域
变量的作用域决定了在哪一部分程序可以访问哪个特定的变量名称。Python的作用域一共有4中，分别是：
L （Local） 局部作用域
E （Enclosing） 闭包函数外的函数中
G （Global） 全局作用域
B （Built-in） 内建作用域
以 L –> E –> G –>B 的规则查找，即：在局部找不到，便会去局部外的局部找（例如闭包），再找不到就会去全局找，再者去内建中找。
Python 中只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域，其它的代码块（如 if/elif/else/、try/except、for/while等）是不会引入新的作用域的，也就是说这这些语句内定义的变量，外部也可以访问

### global 和 nonlocal关键字

# 高级特性
## 切片
list,tuple,string都适用。有了切片操作，很多地方循环就不再需要了
```
L = list(range(100))
L[:10]
L[-10:]
L[:10:2]
(0, 1, 2, 3, 4, 5)[:3]
'ABCDEFG'[::2]
```
## 迭代
任何可迭代对象都可以作用于for循环，包括我们自定义的数据类型，只要符合迭代条件，就可以使用for循环
```
for i, value in enumerate(['A', 'B', 'C']):
for x, y in [(1, 1), (2, 4), (3, 9)]:
```

## 列表生成式（List Comprehensions）
```
>>> list(range(1, 11))
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
[x * x for x in range(1, 11) if x % 2 == 0]
[m + n for m in 'ABC' for n in 'XYZ']
```

##生成器（generator）
第一种方法很简单，只要把一个列表生成式的[]改成()，就创建了一个generator。
第二种：yield关键字

##迭代器
凡是可作用于for循环的对象都是Iterable类型；

凡是可作用于next()函数的对象都是Iterator类型，它们表示一个惰性计算的序列；迭代器有两个基本的方法：iter() 和 next()

集合数据类型如list、dict、str等是Iterable但不是Iterator，不过可以通过iter()函数获得一个Iterator对象

```
# 首先获得Iterator对象:
it = iter([1, 2, 3, 4, 5])
# 循环:
while True:
    try:
        # 获得下一个值:
        x = next(it)
    except StopIteration:
        # 遇到StopIteration就退出循环
        break
```
# 函数式编程
函数式编程的一个特点就是，允许把函数本身作为参数传入另一个函数，还允许返回一个函数！

Python对函数式编程提供部分支持。由于Python允许使用变量，因此，Python不是纯函数式编程语言

## 高阶函数
把函数作为参数传入，这样的函数称为高阶函数，函数式编程就是指这种高度抽象的编程范式。
###变量可以指向函数
###函数名也是变量
###传入函数

## map/reduce
map()函数接收两个参数，一个是函数，一个是Iterable，map将传入的函数依次作用到序列的每个元素，并把结果作为新的Iterator返回

```
def f(x):
    return x * x
r = map(f, [1, 2, 3, 4, 5, 6, 7, 8, 9])
list(r)
[1, 4, 9, 16, 25, 36, 49, 64, 81]
```

reduce把一个函数作用在一个序列[x1, x2, x3, ...]上，这个函数必须接收两个参数，reduce把结果继续和序列的下一个元素做累积计算，其效果就是：

```
reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```
##filter
和map()不同的是，filter()把传入的函数依次作用于每个元素，然后根据返回值是True还是False决定保留还是丢弃该元素

```
def is_odd(n):
    return n % 2 == 1

list(filter(is_odd, [1, 2, 4, 5, 6, 9, 10, 15]))
# 结果: [1, 5, 9, 15]
```

##sorted
sorted()函数也是一个高阶函数，它还可以接收一个key函数来实现自定义的排序，例如按绝对值大小排序：

```
sorted([36, 5, -12, 9, -21], key=abs)
[5, 9, -12, -21, 36]
```

##返回函数
一个函数可以返回一个计算结果，也可以返回一个函数。

返回一个函数时，牢记该函数并未执行，返回函数中不要引用任何可能会变化的变量
###函数作为返回值
```
def lazy_sum(*args):
    def sum():
        ax = 0
        for n in args:
            ax = ax + n
        return ax
    return sum
```

###闭包

## 装饰器
## 偏函数

```
>>> import functools
>>> int2 = functools.partial(int, base=2)
>>> int2('1000000')
64
>>> int2('1010101')
85

```

# 模块
一个.py文件就称之为一个模块（Module）
为了避免模块名冲突，Python又引入了按目录来组织模块的方法，称为包（Package）
##作用域
有的函数和变量我们希望仅仅在模块内部使用。在Python中，是通过_前缀来实现的
__name__属性

```
#!/usr/bin/python3
# Filename: using_name.py

if __name__ == '__main__':
   print('程序自身在运行')
else:
   print('我来自另一模块')
```

#三方模块
## 安装
pip install Pillow
### 导入
import x.y.z
from x.y import z/*

# 参考资料
## Python 2.x vs 3.x
2008年, Python3发布。最大的变化是源码文件默认使用utf-8编码
- 更多区别：[Python3.x和Python2.x的区别](http://www.admin10000.com/document/144.html)
## 学习材料
* [廖雪峰Python3教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
* [Runoob Python3教程](http://www.runoob.com/python3/python3-tutorial.html)
* [PHPXS Python基础教程](http://www.phpxs.com/j/python)
