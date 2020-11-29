![算法工程师日常](https://pic2.zhimg.com/80/9409dc7d3dde730a2d17533cd38403d2_720w.jpg?source=1940ef5c)
# Python 语法
设置后，notepad++运行python文件快捷键：Ctrl+Shift+Enter

## 缩进

* python中使用缩进不仅仅为了好看，用于指示代码块，空格数随意，但要统一，否则报错。
* 变量是在为其赋值时创建的，没有声明变量的命令。变量不需要使用任何特定类型声明，甚至可以在设置后更改其类型。
字符串变量可以使用单引号或双引号进行声明（必须）
* 注释以 ＃ 开头，Python 将其余部分作为注释呈现； <br> 多行注释：在代码中添加多行字符串（三引号），并在其中添加注释：

'''<br>
fdghcb
<br>'''
# 变量
* Python 变量命名规则：

1. 变量名必须以字母或下划线字符开头
2. 变量名称不能以数字开头
3. 变量名只能包含字母数字字符和下划线（A-z、0-9 和 _） **不包含小数点 \.**
4. 变量名称区分大小写（age、Age 和 AGE 是三个不同的变量）

* 允许您在一行中为多个变量赋值：x,y,z = 'bla', 'blab', 'blabla'<br>
允许连等，即可以在一行中为多个变量分配相同的值：x=y=z=100

* 如需结合文本和变量(类型应也为文本)，Python 使用 + 字符. 还可以使用 + 字符将变量与另一个变量相加储存为一个新的变量
<br> x='hello!', y='world',  z = x+y
* 对于数字，+ 字符用作数学运算符； + 字符 组合字符串和数字，报错。
* 全局变量<br>
在函数外部创建的变量称为全局变量。
全局变量可以被**函数内部和外部**的使用。如果在函数内部创建具有相同名称的变量，则该变量将是局部变量，并且只能在函数内部使用。具有相同名称的全局变量将保留原样，并拥有原始值。
* 要在函数<u>`内部创建全局变量`</u>，您可以使用 **`global 关键字`**。
如果您用了 global 关键字，则该变量属于全局范围：
```python 
def myfunc():
  global x
  x = "fantastic"

myfunc()

print("Python is " + x)
```
在函数内部更改全局变量，请使用 global 关键字,方法同上。（个人觉得这个命令少用，缺乏连贯性，救急的时候可用）
# 数据类型
* type() 函数获取任何对象的数据类型

|示例|数据类型|
|---|---|
|x = "Hello World"|	str	|
|x = 29	|int	|
|x = 29.5|	float|
|x = 1j	|complex	|
|x = ["apple", "banana", "cherry"]|	list|
|x = ("apple", "banana", "cherry")|	tuple|
|x = range(6)|	range|
|x = {"name" : "Bill", "age" : 63}|	dict|
|x = {"apple", "banana", "cherry"}	|set|
|x = frozenset({"apple", "banana", "cherry"})|	frozenset	|
|x = True|	bool	|
|x = b"Hello"	|bytes|
|x = bytearray(5)	|bytearray	|
|x = memoryview(bytes(5))	|memoryview	|

希望指定数据类型，则您可以使用以下构造函数：
 [网址链接](https://www.w3school.com.cn/python/python_datatypes.asp)
# 数字
* Python 中有三种数字类型：<br>
int,<br>
float,<br>
complex,~用 "j" 作为虚部编写  如:  2+3j<br>
类型转换：使用 int()、float() 和 complex() 函数从一种类型转换为另一种类型<br>
加一个转换为字符型的函数str() - 用各种数据类型**构造字符串**，包括字符串，整数字面量和浮点字面量
* Python 有一个名为 random 的内置模块，可用于生成随机数

# 字符串

* 可以使用三个引号将多行字符串赋值给变量：单双均可。 在结果中，效果中的换行符插入与代码中相
同的位置，相当于段落带格式复制

* Python 没有字符数据类型，单个字符就是长度为 1 的字符串。方括号可用于访问字符串的元素。
* 获取位置 1 处的字符（请记住第一个字符的位置为 0）, 这一点和C语言中数组一致
* 裁切
 <br>您可以使用裁切语法返回一定范围的字符。
 <br>指定开始索引和结束索引，以冒号分隔，以返回字符串的一部分。如 b[2:5]  左闭右开，即截取的位置用区间可表示为 [2,5)==[2,4]
*负的索引
 <br>使用负索引从字符串末尾开始切片：  最右位置为-1（猜测因为位置0已经有了上述自左头的定义，故不用0自右打头）
* 小结：左闭右开原则，自左向右取值原则（即使是负索引，左小右大）
* 获取字符串的长度~ len() 函数。此函数还可用于求列表（向量）的长度

# 运算

[网址链接](https://www.w3school.com.cn/python/python_operators.asp)

%	取模	x % y	试一试
**	幂	x ** y	试一试
//	地板除（向下取整除）	x // y	试一试

有符号十进制整数转换为二进制的步骤如下：
把十进制整数的绝对值转换为二进制数。
如果初始十进制数是负数，则在第 1 步的基础上，求该二进制数的补码。（补码：按位取反码，然后加1（二进制加法））
比如，十进制数 -43 转换为二进制的过程为：

1) 无符号数 43 的二进制表示为 0010 1011。

2) 由于初始数值是负数，因此，求出 0010 1011 的补码 1101 0101 这就是十进制数 -43 的二进制表示。

首位叫做符号位，为1则这个数为负数，为0则这个数为正数。


# Python 逻辑运算符
逻辑运算符用于组合条件语句：

运算符	描述	实例	试一试
and	如果两个语句都为真，则返回 True。	x > 3 and x < 10	试一试
or	如果其中一个语句为真，则返回 True。	x > 3 or x < 4	试一试
not	反转结果，如果结果为 true，则返回 False	not(x > 3 and x < 10)	试一试


# Python 身份运算符
身份运算符用于比较对象，不是比较它们是否相等，但如果它们实际上是同一个对象，则具有相同的内存位置：

运算符	描述	实例	试一试
is	如果两个变量是同一个对象，则返回 true。	x is y	试一试
is not	如果两个变量不是同一个对象，则返回 true。	x is not y	试一试


# Python 成员运算符
成员资格运算符用于测试序列是否在对象中出现：（sql中有此用法）

运算符	描述	实例	试一试
in	如果对象中存在具有指定值的序列，则返回 True。	x in y	试一试
not in	如果对象中不存在具有指定值的序列，则返回 True。	x not in y	试一试

# Python 位运算符
位运算符用于比较（二进制）数字：

运算符	描述	实例
&	AND	如果两个位均为 1，则将每个位设为 1。
|	OR	如果两位中的一位为 1，则将每个位设为 1。
^	XOR	如果两个位中只有一位为 1，则将每个位设为 1。
~	NOT	反转所有位。

<<	Zero fill left shift	通过从右侧推入零来向左移动，推掉最左边的位。

‘>>’	Signed right shift	通过从左侧推入最左边的位的副本向右移动，推掉最右边的位。

# Python 编程语言中有四种集合数据类型：

* 列表（List）是一种有序和可更改的集合。允许重复的成员。`[,]`
* 元组（Tuple）是一种有序且不可更改的集合。允许重复的成员。`(,)`
* 集合（Set）是一个无序和无索引的集合。没有重复的成员。 `{,}`
* 词典（Dictionary）是一个无序，可变和有索引的集合。没有重复的成员。`{:,}`

删除项目：  remove() 方法， pop() 方法， del, clear  

**删除和清空是有区别的，前者是删除对象，后者是将对象中的值清空（null）**

# 复制列表
您只能通过键入 list2 = list1 来复制列表，因为：list2 将只是对 list1 的引用，list1 中所做的更改也将自动在 list2 中进行。
也有一些内置方法来复制：copy()   list()     详见编程篇

# 合并两个列表
在 Python 中，有几种方法可以连接或串联两个或多个列表。

最简单的方法之一是使用 + 运算符。
```
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)
```

连接两个列表的另一种方法是将 list2 中的所有项一个接一个地追加（append）到 list1 中
```
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)
```

或者，您可以使用 extend() 方法，其目的是将一个列表中的元素添加到另一列表中：
```
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)
```
# list() 构造函数   感觉有点多此一举，应该是有大用场，只是暂时看不到罢了。
也可以使用 list() 构造函数创建一个新列表。

实例
使用 list() 构造函数创建列表：
```
thislist = list(("apple", "banana", "cherry")) # 请注意双括号
print(thislist)
```
# 列表方法
Python 有一组可以在列表上使用的内建方法。


|方法||描述|
|:---:||:---|
|[append()](https://www.w3school.com.cn/python/ref_list_append.asp)||在列表的末尾添加一个元素|
|[clear()](https://www.w3school.com.cn/python/ref_list_clear.asp)||删除列表中的所有元素|
|[copy()](https://www.w3school.com.cn/python/ref_list_copy.asp)	||返回列表的副本|
|[count()](https://www.w3school.com.cn/python/ref_list_count.asp)||	返回具有指定值的元素数量。|
|[extend()](https://www.w3school.com.cn/python/ref_list_extend.asp)||	将列表元素（或任何可迭代的元素）添加到当前列表的末尾|
|[index()](https://www.w3school.com.cn/python/ref_list_index.asp)	||返回具有指定值的第一个元素的索引|
|[insert()](https://www.w3school.com.cn/python/ref_list_insert.asp)	||在指定位置添加元素|
|[pop()](https://www.w3school.com.cn/python/ref_list_pop.asp)	||删除指定位置的元素|
|[remove()](https://www.w3school.com.cn/python/ref_list_remove.asp)	||删除具有指定值的项目|
|[reverse()](https://www.w3school.com.cn/python/ref_list_reverse.asp)	||颠倒列表的顺序|
|[sort()](https://www.w3school.com.cn/python/ref_list_sort.asp)	||对列表进行排序（**值得一看！**）|


# 更改元组值
创建元组后，您将无法更改其值。元组是不可变的，或者也称为恒定的。

但是有一种解决方法。您可以将元组转换为列表，更改列表，然后将列表转换回元组。

实例
把元组转换为列表即可进行更改：
```
x = ("apple", "banana", "cherry")
y = list(x)
y[1] = "kiwi"
x = tuple(y)

print(x)
```

# 删除项目
注释：您无法删除元组中的项目。

元组是不可更改的，因此您无法从中删除项目，但您可以完全删除元组：

实例
del 关键字可以完全删除元组：

thistuple = ("apple", "banana", "cherry")
del thistuple

print(thistuple) # 这会引发错误，因为元组已不存在。

# 合并两个元组
如需连接两个或多个元组，您可以使用 + 运算符

# tuple() 构造函数
也可以使用 tuple() 构造函数来创建元组。

实例
使用 tuple() 方法来创建元组：
```
thistuple = tuple(("apple", "banana", "cherry")) # 请注意双括号
#
print(thistuple)
```

# 对集合的操作函数有很多，很重要。
详见[这里](https://www.w3school.com.cn/python/python_sets.asp) 。

# 字典
字典是一个无序、可变和有索引的集合。在 Python 中，字典用花括号编写，拥有键和值。
您可以通过在方括号内引用其键名来访问字典的项目（字典本身是用花括号定义的）名为 get() 的方法。x = thisdict.get("model")
更改值
您可以通过引用其键名来更改特定项的值。thisdict["year"] = 2019 新值覆盖
循环遍历字典时，返回值是字典的键  for循环直接遍历

可以使用 values() 函数返回字典的值

[处理字典的函数](https://www.w3school.com.cn/python/python_dictionaries.asp)

# 语句
简写 If<br>
如果只有一条语句要执行，则可以将其与 if 语句放在同一行。

```if conditions: expression```


简写 If ... Else<br>
如果只有两条语句要执行，一条用于 if，另一条用于 else，则可以将它们全部放在同一行：

```expression.1 if conditions else expression.0```
<br>注：条件为真执行左边语句，反之执行右边语句。在R语言中的等价表述则更加简约：
<br>```ifelse(conditions,expression.1,expression.0)```


我们可以在同一行上使用多个 else 语句：

实例
单行 if else 语句，有三个条件：
```
a = 200
b = 66
print("A") if a > b else print("=") if a == b else print("B")
```
解构一下第三行语句：
print("A") if a > b else ##print("=") if a == b else print("B")##
<br>if else 语句的嵌套，事实上这类用法都可以由引入 elif 更好更清晰的表达，故几乎不用。


**and** 即R中的**&**  逻辑与

**or** 即R中的**|**   逻辑或

# pass 语句
if 语句不能为空，但是如果您处于某种原因写了无内容的 if 语句，请使用 pass 语句来避免错误。
实例：
```{python}
a = 66
b = 200

if b > a:
  pass
```

# while循环
使用continue, break 等语句前必须先设置索引变量的更新，如

**else 语句** 编程语言中独此一份

通过使用 else 语句，**当条件不再成立**时，我们可以运行一次代码块：

实例
条件为假时打印一条消息：
```
i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")
```
如需循环一组代码指定的次数，我们可以使用 range() 函数

# Range函数——生成列表（数组、向量）可用于for 循环的条件
注意：range(10) 不是 0 到 10 的值，而是值 0 到 9。

range() 函数默认 0 为起始值，不过可以通过添加参数来指定起始值：range(3, 10)，这意味着值为 3 到 10（但不包括 10）：

range() 函数默认将序列递增 1，但是可以通过添加第三个参数来指定增量值：range(2, 30, 3)：

**for 循环中的 else 关键字**指定循环结束时要执行的代码块：

pass 语句
for 语句不能为空，但是如果您处于某种原因写了无内容的 for 语句，请使用 pass 语句来避免错误。

关键字参数
您还可以使用 key = value 语法发送参数。

参数的顺序无关紧要。   但是当不适用关键字指明参数对应那个变量时，顺序变成了确定谁是谁的规则（按顺序一一对应）

# 任意参数——真的牛批
如果您不知道将传递给您的函数多少个参数，请在函数定义的参数名称前添加 *。

这样，函数将接收一个参数元组，并可以相应地访问各项：

实例
如果参数数目未知，请在参数名称前添加 *：
```
def my_function(*kids):
  print("The youngest child is " + kids[2])

my_function("Phoebe", "Jennifer", "Rory")
```
# pass 语句
函数定义不能为空，但是如果您出于某种原因写了无内容的函数定义，请使用 pass 语句来避免错误。

实例
```
def myfunction:
  pass
```

# lambda 函数(类似于MMA中的纯函数)
是一种小的匿名函数。lambda 函数可接受任意数量的参数，但只能有一个表达式。执行表达式并返回结果：
```
lambda arguments : expression
```
实例:
```
x = lambda a : a + 10
print(x(5))#调用——打印之
```
lambda 函数可接受任意数量的参数：

# __init__() 函数
上面的例子是最简单形式的类和对象，在实际应用程序中并不真正有用。

要理解类的含义，我们必须先了解内置的 `__init__()` 函数。

所有类都有一个名为` __init__()` 的函数，它始终在启动类时执行。

使用 `__init__()` 函数将值赋给对象属性，或者在创建对象时需要执行的其他操作：

实例
创建名为 Person 的类，**使用` __init__()` 函数为 name 和 age 赋值**：
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("Bill", 63)

print(p1.name)
print(p1.age)
```
注释：每次使用类创建新对象时，都会自动调用` __init__() `函数。


# 对象方法
对象也可以包含方法。对象中的方法是属于该对象的函数。

让我们在 Person 类中创建方法：

实例
插入一个打印问候语的函数，并在 p1 对象上执行它：
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)

p1 = Person("Bill", 63)
p1.myfunc()
```
运行实例
提示：**self 参数是对类的当前实例的引用，用于访问属于该类的变量**。

# self 参数
self 参数是<u>对类的当前实例的引用，用于访问属于该类的变量</u>。

它<u>不必被命名为 self，您可以随意调用它，但*它必须是类中任意函数的**首个参数***</u>：

实例
使用单词 mysillyobject 和 abc 代替 self：
```
class Person:
  def __init__(mysillyobject, name, age):
    mysillyobject.name = name
    mysillyobject.age = age

  def myfunc(abc):
    print("Hello my name is " + abc.name)

p1 = Person("Bill", 63)
p1.myfunc()
```
# 删除对象属性
您可以使用 del 关键字删除对象的属性：

实例
删除 p1 对象的 age 属性：
```
del p1.age
```
# 删除对象
使用 del 关键字删除对象：

实例
删除 p1 对象：
```
del p1
```
# pass 语句
类定义不能为空，但是如果您处于某种原因写了无内容的类定义语句，请使用 pass 语句来避免错误。

实例
class Person:
  pass

# 创建子类
要创建从其他类继承功能的类，请在创建子类时将父类作为参数发送：

实例
创建一个名为 Student 的类，它将从 Person 类继承属性和方法：
```
class Student(Person):
  pass
```
注释：如果您不想向该类添加任何其他属性或方法，请使用 pass 关键字。

# 使用 super() 函数
Python 还有一个 `super()` 函数，它会<u>使子类从其父继承所有方法和属性</u>：

实例
```
class Student(Person):
  def __init__(self, fname, lname):
    super().__init__(fname, lname)
```
运行实例
通过使用 super() 函数，您不必使用父元素的名称，它将自动从其父元素继承方法和属性。

# 添加方法
实例
把名为 welcome 的方法添加到 Student 类：
```
class Student(Person):
  def __init__(self, fname, lname, year):
    super().__init__(fname, lname)
    self.graduationyear = year

  def welcome(self):
    print("Welcome", self.firstname, self.lastname, "to the class of", self.graduationyear)
```

提示：如果您在子类中添加一个与父类中的函数同名的方法，则将**覆盖**父方法的继承。

# 迭代器（好像没什么用，有循环语句就够用了）

# 局部作用域
在函数内部创建的变量属于该函数的局部作用域，并且只能在该函数内部使用。
变量 x 在函数外部不可用，但对于函数内部的任何函数均可用：

# Global 关键字
如果您需要创建一个全局变量，但被卡在本地作用域内，则可以使用 global 关键字。

global 关键字**使变量成为全局变量。**

实例
如果使用 global 关键字，则该变量属于全局范围：
```
def myfunc():
  global x
  x = 100

myfunc()

print(x)
```
**在函数内部更改全局变量的值**，请使用 global 关键字引用该变量：

x = 100

def myfunc():
  global x
  x = 200

myfunc()

print(x)

# 什么是模块？
请思考与代码库类似的模块。

模块是包含一组函数的文件，希望在应用程序中引用。

创建模块
如需创建模块，只需将所需代码保存在文件扩展名为 .py 的文件中：(虽然不清楚调用模块的方法，但最好
将模块保存在相同的父文件夹中，方便管理和随时查看)


现在，我们就可以用 import 语句来使用我们刚刚创建的模块：

实例
导入名为 mymodule 的模块，并调用 greeting 函数：
```
import mymodule

mymodule.greeting("Bill")
```

注释：如果使用模块中的函数时，请使用以下语法：
```
module_name.function_name
```
*重命名模块*
您可以在导入模块时使用 as 关键字创建别名：
```
import mymodule as mx

a = mx.person1["age"]
print(a)
```
# 内建模块
Python 中有几个内建模块，您可以随时导入:  platform

# 使用 dir() 函数
有一个内置函数可以列出模块中的所有函数名（或变量名）。dir() 函数：
dir() 函数可用于所有模块，也可用于您自己创建的模块。

# 从模块导入 **from**
您可以使用 from 关键字选择仅从模块导入部件。
仅从模块导入 person1 字典：

```
from mymodule import person1

print (person1["age"])
```
提示：在使用 from 关键字导入时，请勿在引用模块中的元素时重复使用模块名称。
示例：person1["age"]，而不是 mymodule.person1["age"]。

# 日期
[日期数据的操作](https://www.w3school.com.cn/python/python_datetime.asp)

# JSON 
JSON 是用于存储和交换数据的语法。
JSON 是用 JavaScript 对象表示法（JavaScript object notation）编写的文本
[链接](https://www.w3school.com.cn/python/python_json.asp)

# ndjs

![本地图片](E:\\wallpapers\\Bing必应\\1600863125.bing.lylares.com.hd.jpg)

![本地图片1](E:\wallpapers\Bing必应\1600863125.bing.lylares.com.hd.jpg)

![ghvb](‪C:\Users\Samsung\Documents\GitHub\QinYeWoRuo.github.io\_posts\浓烈热情也不失天真.jpg)

![ghvb](‪C:\\Users\\Samsung\\Documents\\GitHub\\QinYeWoRuo.github.io\\_posts\\浓烈热情也不失天真.jpg)
