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

## python 缺点

- 相较于C、C++、java，运行效率慢
- 有两个版本
- python核心团队计划在2020年停止支持python2
- python2.7 是最后一个2x版本

## 一个学习编程的经典误区

世界不只有Web，还有很多问题需要使用编程来解决。不要把思维局限在Web上，这只是编程的一个应用方向。

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
  - 文件开头加上`#!/usr/bin/python3`
  - 单行注释：`#`开头
  - 多行注释：`'''`或者`"""`
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
  - int a=10
  - float b=2.3
  - bool c=True
  - complx d=3 + 4j # 复数 j 复数单位
- String（字符串）
- List（列表）
- Tuple（元组）
- Sets（集合）
- Dictionary（字典）

多变量赋值：

- `a = b = c = 1`
- `a,b,c=1,2.3,"abc"`

运算符：

- 算术运算符：2 的 3 次方用`2 ** 3`表示。整除运算符`//`
- 比较（关系）运算符
- 赋值运算符
- 逻辑运算符：与或非，`and`, `or`, `not`
- 位运算符:`& | ^ ~ << >>`
- 成员运算符: `in`, `not in`
- 身份运算符: `is`, `is not`
- 运算符优先级: 指数运算 -》 位运算 -》 乘除取模取整 -》 加减法，优先级最低的是 逻辑运算，最高的是 括号。

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

3 33：36
