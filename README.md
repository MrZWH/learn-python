# python3 入门与进阶

<www.python.org>

- 基础语法，从最基本的变量到复杂的高阶函数
- 面向对象
- 常见误区
- Pythonic 高性能
- 总结经验
- 原生爬虫

## 认识python

- 人生苦短，我用python (Life is Simple，I Use Python)
- 作者 Guido van Rossum 在1989年的圣诞节为了打发时间写出了python
- 优雅、明确、简单是python的设计哲学
- python的设计目标之一是让代码具备高度的可阅读性
- python被广泛用于web程序、GUI开发、操作系统、科学计算、人工智能、游戏等领域

## python 特点

- 是一种动态语言
- 被设计成可扩充的
- 跨平台
- 语法简洁、开发效率高、维护成本低
- 易于学习，易于上手难于精通
- python 是面向对象的语言
- 简洁胜于复杂
- 做也许好过不做，但不假思索就动手还不如不做

### python 缺点：

- 相较于C、C++、java，运行效率慢
- 有两个版本
- python核心团队计划在2020年停止支持python2
- python2.7 是最后一个2x版本

## python 能做什么

- 爬虫
- 大数据与数据分析（Spark）
- 自动化运维与自动化测试
- web开发：Flask、Django
- 机器学习：Tensor Flow
- 胶水语言：混合其他如C++、Java等来编程。能够把用其他语言制作的各种模块（尤其是C/C++）很轻松地联结在一起

## Pythonic

如何交换两个变量？  

```python
x,y = y,x
```

python 高性能与优化：  

同样一个功能，可以有数个乃至数十种写法，但每种写法的性能与美观度是不同的。选择性能最高又易于理解的写法才是正确的。

## python 环境安装

- Windows 下一键环境安装包
  - 登录 <www.python.org> 在 Downloads 处下载，windows X86-64 executable installer
  - 选择自定义安装,勾选上 Add Python to PATH
  - 安装之后在 Windows 的搜索栏处搜索python 选择 IDLE 打开编辑器
- MacOS 下载 Mac OS X 64-bit/32-bit install
  - 在命令行下 直接敲 python 会调用默认安装的 2.x版本，需要输入 python3
- Linux
  - 第一个方法，需要编译源码安装，下载 XZ compressed source tarball
  - 第二个方法，centos 上使用 yum 安装，先引入一个安装源：`yum install epel-release`,然后`yum install python36`,命令行输入 python36 进入。
- python2.x 和 python3.x
- 退出 shell 需要输入`exit()`
- IDE：PyCharm

## python 快速入门

- 基本语法规则
  - 文件开头加上 `#!/usr/bin/python3`
  - 单行注释： `#`开头
  - 多行注释： `'''`或者`"""`
- 变量与字符串
- 函数与模块
- 流程控制
- 内置数据结构
- 类与面向对象
- 标准库
- 包管理器

## 什么是代码？什么是写代码

代码是现实世界事物在计算机世界中的映射  
写代码是将现实世界的事物用计算机语言来描述

## python 基本数据类型

- Number（数字）
  - 整型 int a=10
  - 浮点型 float b=2.3
  - 布尔型 bool c=True
  - 复数 complx d=3 + 4j # 复数 j 复数单位
- 组
  - 序列 
    - String（字符串）
    - List（列表）
    - Tuple（元组）
  - 集合 Sets
  - 字典 Dictionary

### Number：数字  

- 整数：int  
- 浮点数：float  
- bool 布尔类型：表示真`True`、假 `False`
  - `int(True) -> 1`，`bool(1) -> True`
  - 只要是非0的数值都表示bool真
- complex 复数
  
其它语言里的浮点数进一步划分：单精度（float），双精度（double）  
其它语言里的整数进一步划分：short、int、long  

查看数据类型：`type(1)`  
两个整数类型的数相除得到的数是float类型的。想得到int型可以如此：`type(2//2)`,`//`表示只保留整数。  

#### 进制表示

二进制：在开头加上`0b`  
八进制：在开头加上`0o`  
十六进制：在开头加上`0x`  

将十进制转换为二进制：`bin(10)` 输出为`0b1010`  
将其它进制转换为十进制：`int(0b111)`  
将其它进制转换为十六进制：`hex(0o111)`  
将其它进制转换为八进制：`oct(0x111)`  

### 字符串

python 中没有字符类型

```python
a = '21313'
b = "AAVA"
c = """
多行字符串
多行
多行
"""
```

只想更改字符串中某几个字符怎么做：

```python
str1 = "abcdefg"
print( str1[:3] + "123" + str1[3:] )
# 得到 abc123defg
```

冒号左边表示截取的起始位置，右边表示截取的结束位置，左边包含右边不包含。  

格式化字符串：

```python
print('ABCDEFG%d' %(12345))
# ->> ABCDEFG12345

# d 字母是根据后面的数据类型决定的，如果要加入字符串则变为 %s

# 要转变位 16进制数如下
print('%x' %(100))
# ->> 64

# 格式化复杂字符串
print("name: %s, age: %d" %("Tom", 21))
# ->> name: Tom, age: 21

```

## 变量与运算符
字母、数字、下划线，不能数字开头

多变量赋值：

- `a = b = c = 1`
- `a,b,c=1,2.3,"abc"`

int str tuple 值类型（不可变），list set dict（可变）引用类型。

显示变量再内存中的地址：`id(a)`。

对象的三个特征：id、value、type
判断变量类型：`isinstance(a,int)`、`isinstance(a,(int,str,float))`

### 运算符

- 算术运算符：2 的 3 次方用`2 ** 3`表示。整除运算符`//`
- 比较（关系）运算符
- 赋值运算符 =
- 逻辑运算符：与或非，`and`, `or`, `not`
- 位运算符（把数字当作二进制进行运算）:`& | ^ ~ << >>`
  - & 按位与
  - | 按位或
- 成员运算符: `in`, `not in`，字典的成员运算针对的是 key。
- 身份运算符: `is`, `is not`，不是比较值是否相等 而是身份 id。

```python
b=1
b+=b>=1
print(b) # -> 1+True ->c 2
```
运算符优先级: 指数运算 -》 位运算 -》 乘除取模取整 -》 加减法，优先级最低的是 逻辑运算，最高的是 括号。
not > and > or

`((not a) or ((b+2) == c))`

## 函数

```python
"""
def 函数名 (参数列表)：  
    函数体  
"""
def hello( str ):
  print("hello: %s" %(str))

hello("Tom")

def function01( a, b):
  return a + b

print(function01(3, 4))


def function01( a=0, b=0):
  return a * b
```

#### 变量作用域

- L（Local） 局部作用域
- E（Enclosing）闭包函数外的函数中
- G（Global）全局作用域
- B（Built-in）内建作用域

`x = int(32)` 内建作用域，作用域范围在小括号`()`内  
`g_a = 0` 全局作用域  

```python
def function03():
  o_c = 1 # 闭包函数外的函数中
  def function04():
    i_b = 3 # 局部作用域
```

在刚创建函数时，函数体内会有`pass`，表示占位，有内容时需去掉。

### 模块

模块是一个包含所有你定义的函数或变量的文件，其后缀名是 `.py`。  

python 中内置了很多模块，是 python 的标准库。  

```python
import sys

print(sys.path)

from module01 import test

# 查看模块提供了什么

dir(sys)
```

### 流程控制

- 条件控制
- 循环语句

```python
"""
if condition_1:
  statement_block_1
elif condition_2:
  statement_block_2
else:
  statement_block_3
"""

# while 循环语句
"""
while 判断条件:
  语句
"""

"""
n = 100
sum = 0
counter = 1
while counter <=n:
  sum = sum + counter
  couter += 1

print("sum: ", sum)

while True:
  mun = int(input("请输入一个数字："))
  print("输入的数字是：", mun)

print("循环结束！")
"""

counter = 0
while counter < 3:
  print("counter:", counter)
  counter += 1
else:
  print("counter", counter)


# for 循环语句
"""
for <variable> in <sequence>:
  <statement>
"""

"""
for a in [1,2,3,4,5,6,7]:
  print("a = ", a)
else:
  print("a>7!")
"""

"""
range()函数
"""
for a in range(0,5):
  print("a = ", a)
# -> a = 0
# -> a = 1
# -> a = 2
# -> a = 3
# -> a = 4
for a in range(3,5):
  print("a = ", a)
# -> a = 3
# -> a = 4

for a in range(1,5,2):
  print("a = ", a)
# -> a = 1
# -> a = 3
```

### 内置数据结构

- List（列表）
  - 可以看作是数据 `[var1, var2, var3]`
- Tuple（元组）
  - 和 List 相近，但其内部的值不可改变 `(var1, var2, var3)`
- Sets（集合）
  - `{var1, var2, var3}` 内部的元素不可重复
- Dictionary（字典）
  - `{key1:var1, key2:var2, key3:var3}`

```python
# List

list = ['abc', 123, 3.14, True]
print(list) # -> ['abc', 123, 3.14, True]
print(list[0]) # -> abc
print(list[3]) # -> True

list2 = ['list2str', 100]
print(list + list2) # -> ['abc', 123, 3.14, True, 'list2str', 100]

list[0] = "ABC"
list[1:3] = [321, 99.99]
print(list) # -> ['abc', 321, 99.99, True]

dir(list)

# Tuple

tuple = ("abc", 123, 3.14, True)
print(tuple) # -> ('abc', 123, 3.14, True)
print(tuple[2]) # -> 3.14
print(tuple[1:3]) # -> (123, 3.14)
print(tuple * 3) # 元组内容输出三次 -> ('abc', 123, 3.14, True,'abc', 123, 3.14, True,'abc', 123, 3.14, True)

"""
string 元组 列表 都属于序列
"""

for a in tuple
  print(a)

# Sets

set1 = {"Tom", "Marry", "Jack", "Rose", "Tom"}
set2 = set("abckde")
print(set1) # -> {"Tom", "Marry", "Jack", "Rose"}

if "Jack" in set1:
  print("Jack 在集合中")
else:
  print("not in")

set3 = set("1235abs")
print(set2)
print(set3)

print(set2 - set3) # 计算差集
print(set2 | set3) # 计算并集
print(set2 & set3) # 计算交集
print(set2 ^ set3) # 计算不同值存在的元素

len({1,2,3}) # -> 3

1 in {1,2,3}
1 not in {1,2,3}

set() # 定义空的集合

# 字典

dict = {}
dict['key1'] = 1
dict['key2'] = 200
dict[100] = "ABC"

print(dict) # -> {'key1':1, 'key2': 200, 100: 'ABC'}
print(dict['key1'])
print(dict[100])

## 字典中的 key 字符串的数字是不同的，不可变数据类型（int str set）可以当 key

```

## 实战壁纸爬虫

- 每天定时抓取Bing搜索的壁纸并保存在本地
  - 分析 Bing 搜索的页面结构
  - 分析Bing搜索的壁纸接口
  - 根据分析的结果编码实现壁纸爬虫

3 33：36
