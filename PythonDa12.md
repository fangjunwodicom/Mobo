#  Python3 输入和输出

##  1.输出格式美化


- Python两种输出值的方式: 表达式语句和 print() 函数。
- 第三种方式是使用文件对象的 write() 方法，标准输出文件可以用 sys.stdout 引用。
- 如果你希望输出的形式更加多样，可以使用 str.format() 函数来格式化输出值。
- 如果你希望将输出的值转成字符串，可以使用 repr() 或 str() 函数来实现。
   - str()： 函数返回一个用户易读的表达形式。
   - repr()： 产生一个解释器易读的表达形式。


例如：

```
>>> s = 'Hello, Runoob'
>>> str(s)
'Hello, Runoob'
>>> repr(s)
"'Hello, Runoob'"
>>> str(1/7)
'0.14285714285714285'
>>> x = 10 * 3.25
>>> y = 200 * 200
>>> s = 'x 的值为： ' + repr(x) + ',  y 的值为：' + repr(y) + '...'
>>> print(s)
x 的值为： 32.5,  y 的值为：40000...
>>> #  repr() 函数可以转义字符串中的特殊字符
... hello = 'hello, runoob\n'
>>> hellos = repr(hello)
>>> print(hellos)
'hello, runoob\n'
>>> # repr() 的参数可以是 Python 的任何对象
... repr((x, y, ('Google', 'Runoob')))
"(32.5, 40000, ('Google', 'Runoob'))"

```


这里有两种方式输出一个平方与立方的表

```
>>> for x in range(1, 11):
...     print(repr(x).rjust(2), repr(x*x).rjust(3), end=' ')
...     # 注意前一行 'end' 的使用
...     print(repr(x*x*x).rjust(4))
...
 1   1    1
 2   4    8
 3   9   27
 4  16   64
 5  25  125
 6  36  216
 7  49  343
 8  64  512
 9  81  729
10 100 1000

>>> for x in range(1, 11):
...     print('{0:2d} {1:3d} {2:4d}'.format(x, x*x, x*x*x))
...
 1   1    1
 2   4    8
 3   9   27
 4  16   64
 5  25  125
 6  36  216
 7  49  343
 8  64  512
 9  81  729
10 100 1000

```

- 注意：在第一个例子中, 每列间的空格由 print() 添加。
- 这个例子展示了字符串对象的 rjust() 方法, 它可以将字符串靠右, 并在左边填充空格。
- 还有类似的方法, 如 ljust() 和 center()。 这些方法并不会写任何东西, 它们仅仅返回新的字符串。


另一个方法 zfill(), 它会在数字的左边填充 0，如下所示：

```
>>> '12'.zfill(5)
'00012'
>>> '-3.14'.zfill(7)
'-003.14'
>>> '3.14159265359'.zfill(5)
'3.14159265359'

```

###  2.旧式字符串格式化

- % 操作符也可以实现字符串格式化。 它将左边的参数作为类似 sprintf() 式的格式化字符串, 而将右边的代入, 然后返回格式化后的字符串. 例如:

```
>>> import math
>>> print('常量 PI 的值近似为：%5.3f。' % math.pi)
常量 PI 的值近似为：3.142。

```

- 因为 str.format() 比较新的函数， 大多数的 Python 代码仍然使用 % 操作符。但是因为这种旧式的格式化最终会从该语言中移除, 应该更多的使用 str.format().

###  3.读取键盘输入

- Python提供了 input() 置函数从标准输入读入一行文本，默认的标准输入是键盘。
- input 可以接收一个Python表达式作为输入，并将运算结果返回。


```
#!/usr/bin/python3

str = input("请输入：");
print ("你输入的内容是: ", str)

```

这会产生如下的对应着输入的结果：


```
请输入：菜鸟教程
你输入的内容是:  菜鸟教程

```


##  2.读和写文件

open() 将会返回一个 file 对象，基本语法格式如下:

`open(filename, mode)`

- filename：filename 变量是一个包含了你要访问的文件名称的字符串值。
- mode：mode决定了打开文件的模式：只读，写入，追加等。所有可取值见如下的完全列表。这个参数是非强制的，默认文件访问模式为只读(r)。

不同模式打开文件的完全列表：

<img src="./ppp/Pythonday12_1.jpg">


下图很好的总结了这几种模式：

<img src="./ppp/Pythonday12_2.jpg">


以下实例将字符串写入到文件 foo.txt 中：

```
#!/usr/bin/python3

# 打开一个文件
f = open("/tmp/foo.txt", "w")

f.write( "Python 是一个非常好的语言。\n是的，的确非常好!!\n" )

# 关闭打开的文件
f.close()

```

- 第一个参数为要打开的文件名。
- 第二个参数描述文件如何使用的字符。 mode 可以是 'r' 如果文件只读, 'w' 只用于写 (如果存在同名文件则将被删除), 和 'a' 用于追加文件内容; 所写的任何数据都会被自动增加到末尾. 'r+' 同时用于读写。 mode 参数是可选的; 'r' 将是默认值。


此时打开文件 foo.txt,显示如下：.

```
$ cat /tmp/foo.txt 
Python 是一个非常好的语言。
是的，的确非常好!!

```

##  3.文件对象的方法


###  1.pickle 模块

- python的pickle模块实现了基本的数  据序列和反序列化。
	- 通过pickle模块的序列化操作我们能够将程序中运行的对象信息保存到文件中去，永久存储。
	- 通过pickle模块的反序列化操作，我们能够从文件中创建上一次程序保存的对象。

基本接口：

`pickle.dump(obj, file, [,protocol])`

有了 pickle 这个对象, 就能对 file 以读取的形式打开:

`x = pickle.load(file)`

- 注解：从 file 中读取一个字符串，并将它重构为原来的python对象。
- file: 类文件对象，有read()和readline()接口。

实例:

```
#!/usr/bin/python3
import pickle

# 使用pickle模块将数据对象保存到文件
data1 = {'a': [1, 2.0, 3, 4+6j],
         'b': ('string', u'Unicode string'),
         'c': None}

selfref_list = [1, 2, 3]
selfref_list.append(selfref_list)

output = open('data.pkl', 'wb')

# Pickle dictionary using protocol 0.
pickle.dump(data1, output)

# Pickle the list using the highest protocol available.
pickle.dump(selfref_list, output, -1)

output.close()

```

