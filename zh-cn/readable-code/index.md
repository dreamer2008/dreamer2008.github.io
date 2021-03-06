# 编写可读代码的艺术


<a alt="编写可读代码的艺术" href="http://item.jd.com/11020839.html" target="_blank"><img src="http://img14.360buyimg.com/n1/g5/M00/03/09/rBEDik_Zh6oIAAAAAAD30NgwDhkAAApCAC9qh0AAPfo079.jpg"></a>


# 引子
写代码是程序员的基本功。但是，程序员，你真的会写代码吗？今天，我们不谈什么高大上的“架构”，就谈谈怎么写代码。

作为程序员，你看过、写过、改过、删过的代码可能不计其数。然而，回头想想，真正让你感到赏心悦目、拍手称快的代码又有多少呢？要知道，你读代码的时间远远大于你实际写代码的时间。如果代码可读性不好，你的工作效率肯定会大打折扣。特别是，对于一个团队来说，如果没有良好的、统一的代码规范，协同工作效率必然很受影响，造成不必要的时间浪费。

《Clean Code》的作者Bob大叔认为“在代码阅读过程中人们说脏话的频率是衡量代码质量的唯一标准。” 哈哈。太TM经典了。

书的目录如下： ![目录](http://images.cnitblog.com/blog2015/449064/201505/141405470644668.jpg)（图片来源：[xingoo](http://www.cnblogs.com/xing901022/p/4503286.html)的博客）

# 内容简介
> 细节决定成败，思路清晰、言简意赅的代码让程序员一目了然；而格式凌乱、拖沓冗长的代码让程序员一头雾水。除了可以正确运行以外，优秀的代码必须具备良好的可读性，编写的代码要使其他人能在最短的时间内理解才行。本书旨在强调代码对人的友好性和可读性。

# 可读性为什么重要

## 书中观点
> 软件成本 = 开发成本 + 维护成本。往往，维护成本>>开发成本。这其中耗费的主要成本就是由于理解代码和修改代码造成的。
> 
> ——《Structured Design》

## 个人观点
> 可读性永远是第一位的。代码的可读性与效率、架构、易于测试一点也不冲突。
> 代码可读性好、bug少是对程序员的基本要求。

# 前言
> **本书旨在帮助你把代码写得更好** 。。。我们希望本书对你每天的编程工作有很多帮助，并且希望你把本书推荐给你团队中的每个人。

本文从命名、注释、代码布局、简化逻辑等方面阐述如何写出可读性高的代码

# 总结
## 第1章 代码应当易于理解
> 可读性基本定理
> 
> Code should be written to minimize the time it would take for someone else to understand it.
> 
> 代码的写法应当使别人理解它所需的时间最小化。

## 第一部分 表面层次的改进
1. 一定要让命名可以“自解释”，尽量具体形象。不要随便缩写，可读性比变量长短重要的多（当然也不要太长）
2. 不要用汉语拼音，不要使用有二义性的词，如filter
3. 注意代码的美观：缩进、分段、空格、空行、适当的对齐、顺序的一致性。在团队中，一致的风格比“正确”的风格重要。如，句尾的大括号
4. 好代码>坏代码+好注释。为缺陷加TODO注释。为特殊的地方写注释。写不同层次的注释。行级<方法级<文件级<包级
5. 使用明确、恰当、含义丰富的词精确描述函数的行为。注释中可以给出I/O的例子

## 第二部分 简化循环和逻辑
1. 形式上嵌套一般不超过2层，能return的尽早return。这个原则可以让你大大降低if-else的嵌套深度
2. 不要滥用三目运算符
3. 一定要做参数校验。对于不合法的参数：直接return、抛出异常、logging
4. 拆分过长或者过于复杂的表达式：解释变量、总结变量
5. 减少不必要的变量、合理控制变量的作用域

## 第三部分 重新组织代码
1. 抽出不相关的子问题，封装起来。如：各种工具类
2. 将通用代码和项目专有代码分开
3. 一次只做一件事情
4. 用自然语言描述问题，理清思路，能写出更好懂的代码
5. 质疑和拆分你的需求，消除不必要的功能
6. 保持代码库的轻量级，删除无用代码，尽量使用库函数

## 第四部分 精选话题
1. 测试代码的可读性与非测试代码的可读性同样重要
2. 对测试代码的使用者隐去不重要的细节，以便突出更重要的细节
3. 让错误信息具有更好的可读性
4. 又简单又能完成工作的测试值更好
5. 为测试函数起个好的名字。Test_类名_方法名_情形
6. 过犹不及：
7. 1）牺牲生产代码的可读性，只是为了方便测试
8. 2）顽固地追求100%的测试覆盖率
9. 3）让测试成为产品开发的主导和障碍










