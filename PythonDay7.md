#  Python3 条件控制

- Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。
- 可以通过下图来简单了解条件语句的执行过程:

<img src="./ppp/Pythonday7_1.jpg">

##  1.if语句

Python中if语句的一般形式如下所示:

```
if condition_1:
    statement_block_1
elif condition_2:
    statement_block_2
else:
    statement_block_3

```

+ Python 中用 elif 代替了 else if，所以if语句的关键字为：if – elif – else。

<strong>
+ 注意：
1、每个条件后面要使用冒号（:），表示接下来是满足条件后要执行的语句块。<br/>
2、使用缩进来划分语句块，相同缩进数的语句在一起组成一个语句块。<br/>
3、在Python中没有switch – case语句。
</strong>


以下为if中常用的操作运算符:

<img src="./ppp/Pythonday7_2.jpg">


实例：

```
#!/usr/bin/python3 
 
# 该实例演示了数字猜谜游戏
number = 7
guess = -1
print("数字猜谜游戏!")
while guess != number:
    guess = int(input("请输入你猜的数字："))
 
    if guess == number:
        print("恭喜，你猜对了！")
    elif guess < number:
        print("猜的数字小了...")
    elif guess > number:
        print("猜的数字大了...")

```

输出结果：

```
$ python3 high_low.py 
数字猜谜游戏!
请输入你猜的数字：1
猜的数字小了...
请输入你猜的数字：9
猜的数字大了...
请输入你猜的数字：7
恭喜，你猜对了！

```

##  2.if嵌套

在嵌套 if 语句中，可以把 if...elif...else 结构放在另外一个 if...elif...else 结构中。

```
# !/usr/bin/python3
 
num=int(input("输入一个数字："))
if num%2==0:
    if num%3==0:
        print ("你输入的数字可以整除 2 和 3")
    else:
        print ("你输入的数字可以整除 2，但不能整除 3")
else:
    if num%3==0:
        print ("你输入的数字可以整除 3，但不能整除 2")
    else:
        print  ("你输入的数字不能整除 2 和 3")

```

