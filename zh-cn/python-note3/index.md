# Python学习笔记3


![Python](http://www.kandasoft.com/wp-content/uploads/2014/02/Python-Programming-Language.png)


# 面向对象
## 基本概念
Python中的类提供了面向对象编程的所有基本功能：类的继承机制允许多个基类，派生类可以覆盖基类中的任何方法，方法中可以调用基类中的同名方法。
对象可以包含任意数量和类型的数据。
OOP：属性(Property)和方法(Method)。
类（Class）和实例（Instance）

```
class Student(object):

    def __init__(self, name, score):
        self.name = name
        self.score = score
        #!/usr/bin/python3
 
class MyClass:
    """一个简单的类实例"""
    i = 12345
    def f(self):
        return 'hello world'
 
# 实例化类
x = MyClass()
 
# 访问类的属性和方法
print("MyClass 类的属性 i 为：", x.i)
print("MyClass 类的方法 f 输出为：", x.f())
```
##访问控制
```
class Student(object):
    ...

    def get_name(self):
        return self.__name

    def get_score(self):
        return self.__score
```
需要注意的是，在Python中，变量名类似__xxx__的，也就是以双下划线开头，并且以双下划线结尾的，是特殊变量，特殊变量是可以直接访问的，不是private变量，所以，不能用__name__、__score__这样的变量名。

有些时候，你会看到以一个下划线开头的实例变量名，比如_name，这样的实例变量外部是可以访问的，但是，按照约定俗成的规定，当你看到这样的变量时，意思就是，“虽然我可以被访问，但是，请把我视为私有变量，不要随意访问”。

## 继承和多态
动态语言的“鸭子类型”，它并不要求严格的继承体系，一个对象只要“看起来像鸭子，走起路来像鸭子”，那它就可以被看做是鸭子
## 获取对象信息
###使用type()
```
>>> type(fn)==types.FunctionType
True
```
###使用isinstance()
###使用dir()
类似__xxx__的属性和方法在Python中都是有特殊用途的，比如__len__方法返回长度。在Python中，如果你调用len()函数试图获取一个对象的长度，实际上，在len()函数内部，它自动去调用该对象的__len__()方法，所以，下面的代码是等价的：

```
>>> len('ABC')
3
>>> 'ABC'.__len__()
3
```
仅仅把属性和方法列出来是不够的，配合getattr()、setattr()以及hasattr()，我们可以直接操作一个对象的状态：

```
>>> class MyObject(object):
...     def __init__(self):
...         self.x = 9
...     def power(self):
...         return self.x * self.x
...
>>> obj = MyObject()
>>> def readImage(fp):
    if hasattr(fp, 'read'):
        return readData(fp)
    return None
```
###实例属性和类属性
类的方法与普通的函数只有一个特别的区别——它们必须有一个额外的第一个参数名称, 按照惯例它的名称是 self。self 的名字并不是规定死的，也可以使用 this，但是最好还是按照约定是用 self

### 类的私有属性和私有方法

# trouble shooting
## 异常捕获
Python的错误其实也是class，所有的错误类型都继承自BaseException

```
try:
    print('try...')
    r = 10 / int('2')
    print('result:', r)
except ValueError as e:
    print('ValueError:', e)
except ZeroDivisionError as e:
    print('ZeroDivisionError:', e)
else:
    print('no error!')
finally:
    print('finally...')
print('END')
```
### 用户自定义异常
```
>>> class MyError(Exception):
        def __init__(self, value):
            self.value = value
        def __str__(self):
            return repr(self.value)
```
## 断言
```
assert n != 0, 'n is zero!'
```
## logging
```
import logging
logging.basicConfig(level=logging.INFO)
```

## pdb
pdb.set_trace() # 运行到这里会自动暂停

# 参考资料
## Python 2.x vs 3.x
2008年, Python3发布。最大的变化是源码文件默认使用utf-8编码
- 更多区别：[Python3.x和Python2.x的区别](http://www.admin10000.com/document/144.html)
## 学习材料
* [廖雪峰Python3教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
* [Runoob Python3教程](http://www.runoob.com/python3/python3-tutorial.html)
* [PHPXS Python基础教程](http://www.phpxs.com/j/python)
