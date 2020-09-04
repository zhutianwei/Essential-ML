```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
```

## Control Flow


```python
l = [1,2,3,4]
for i in range(len(l)):
    print(i)
    
print()
    
for i in range(len(l)-1, -1, -1):
    print(i)
    
print()
```

    0
    1
    2
    3
    
    3
    2
    1
    0
    



```python
for n in l:
    print(n)
    
print()

for n in l[:len(l)-1][::-1]:
    print(n)
    
print()    
    
for i, n in enumerate(l):
    print(i, n)

print()
    
for i, n in list(enumerate(l))[::-1]:
    print(i, n)
    
list(enumerate(l))
```

    1
    2
    3
    4
    
    3
    2
    1
    
    0 1
    1 2
    2 3
    3 4
    
    3 4
    2 3
    1 2
    0 1





    [(0, 1), (1, 2), (2, 3), (3, 4)]




```python
l = [1,2,3,4]

i = 0
while i <= len(l) - 1:
    print(l[i])
    i += 1
```

    1
    2
    3
    4



```python
l1 = [1,2,3]
l2 = [4,5,6]
for n in l1:
    for x in l2:
        if n == 2:
            break
        print(n, x)
```

    1 4
    1 5
    1 6
    3 4
    3 5
    3 6



```python
i = 0
array = [1, 2, 3]
while i < len(array):
    if array[i] == 2:
        break
    

    print(array[i])      
    i += 1
```

    1



```python
i = 0
array = [1, 2, 3]
while i < len(array):
    if array[i] == 2:
        i += 1
    
    else:
        print(array[i])      
        i += 1
```

    1
    3



```python
l = [3,2,3]
for n in range(3):
    while l:
        if l[n] > 2:
#             l.pop(0)
            print(1)
        else:
            break
```


```python
l = [3,2,3]
for n in range(3):
    while l:
        if l[-1] > 2:
            l.pop()
            print(l)
        else:
            break
    print(n)
```


```python
s = [1, 2, 3, 4]

for i in range(len(s)):
    if s[i] == 2:
        
        
    print(s[i])
    
```

    1
    3
    3
    4



```python
s = [1, 2, 3, 4]
tmp = s.copy()

for i in range(len(s)-1, -1, -1):
    if s[i] % 2:
        s.pop(i)
    
print(s)
```




    3






    1



    [2, 4]



```python

```


```python
a = iter([1,2,3])
next(a)
a
next(a)
next(a)
next(a)
```




    1






    <list_iterator at 0x7fa6c3597040>






    2






    3




    ---------------------------------------------------------------------------

    StopIteration                             Traceback (most recent call last)

    <ipython-input-12-b4b40295aefa> in <module>
          4 next(a)
          5 next(a)
    ----> 6 next(a)
    

    StopIteration: 



```python
for element in iterable:
    # do something with element
    
    
# Same as above
# create an iterator object from that iterable
iter_obj = iter(iterable)

# infinite loop
while True:
    try:
        # get the next item
        element = next(iter_obj)
        # do something with element
    except StopIteration:
        # if StopIteration is raised, break from loop
        break
```

An interesting (and somewhat obscure) feature of Python is being able to attach an else block to a loop. The basic idea is that the code in the else block runs only if the loop completes without encountering a break statement


```python
for i in range(3):
    password = input('Enter password: ')
    if password == 'secret':
        print('You guessed the password!')
        break
else:
    print('3 incorrect password attempts')
```

    Enter password:  s
    Enter password:  s
    Enter password:  s


    3 incorrect password attempts


## 操作符
https://www.programiz.com/python-programming/operators/1

针对不同类型的数据，有各自专用的**操作符**。

### 数值操作符

针对数字进行计算的操作符有加减乘除商余幂：`+`、`-`、`*`、`/`、`//`、`%`、`**`。

其中 `+` 和 `-` 可以对单个值进行操作，`-3`；其它的操作符需要有两个值才能操作。

从优先级来看，这些操作符中：

> * 对两个值进行操作的 `+`、`-` 的优先级最低；
> * 稍高的是 `*`、`/`、`//`、`%`；
> * 更高的是对单个值进行操作的 `+`、`-`；
> * 优先级最高的是 `**`。

完整的操作符优先级列表，参见官方文档：

> https://docs.python.org/3/reference/expressions.html#operator-precedence



### 逻辑操作符

数值之间还可以使用逻辑操作符，`1 > 2` 返回布尔值 `False`。逻辑操作符有：`<`（小于）、`<=`（小于等于）、`>`（大于）、`>=`（大于等于）、`!=`（不等于）、`==`（等于）。

逻辑操作符的优先级，高于布尔值的操作符，低于数值计算的操作符。
即：数值计算的操作符优先级最高，其次是逻辑操作符，布尔值的操作符优先级最低。


```python
n = -95
n < 0 and (n + 1) % 2 == 0
```


```python
a = 3.5
b = 3.5

a + b == 7
```

### 布尔值操作符

针对布尔值，操作符有`与`、`或`、`非`：`and`、`or`、`not`。

它们之中，优先级最低的是或 `or`，然后是与 `and`, 优先级最高的是非 `not`：


```python
True and False or not True
```

最先操作的是 `not`，因为它优先级最高。所以，上面的表达式相当于 `True and False or (not True)`，即相当于 `True and False or False`；

然后是 `and`，所以，`True and False or False` 相当于是 `(True and False) or False`，即相当于 `False or False`；

于是，最终的值是 `False`。

### 字符串操作符

针对字符串，有三种操作：

> * 拼接：`+` 和 `' '`（后者是空格）
> * 拷贝：`*`
> * 逻辑运算：`in`、`not in`；以及，`<`、`<=`、`>`、`>=`、`!=`、`==` 


```python
'Awesome' + 'Python'
'Awesome' 'Python'
'Python, ' + 'Awesome! ' * 3
'o' in 'Awesome' and 'o' not in 'Python'
```

字符之间，字符串之间，除了 `==` 和 `!=` 之外，也都可以被逻辑操作符 `<`、`<=`、`>`、`>=` 运算：


```python
'a' < 'b'
```

这是因为字符对应着 Unicode 码，字符在被比较的时候，被比较的是对应的 Unicode 码。


```python
'A' > 'a'
ord('A')
ord('a')
```

当字符串被比较的时候，将从两个字符串各自的第一个字符开始逐个比较，“一旦决出胜负马上停止”：


```python
'PYTHON' > 'Python 3'
```

### 列表的操作符

数字和字符串（由字符构成的序列）是最基本的数据类型，而我们往往需要批量处理数字和字符串，这样的时候，我们需要**数组**（Array）。不过，在 Python 语言中，它提供了一个**容器**（Container）的概念，用来容纳批量的数据。

Python 的容器有很多种 —— 字符串，其实也是容器的一种，它的里面容纳着批量的字符。

我们先简单接触一下另外一种容器：**列表**（List）。

列表的标示，用方括号 `[]`；举例来说，`[1, 2, 3, 4, 5]` 和 `['ann', 'bob', 'cindy', 'dude', 'eric']`，或者 `['a', 2, 'b', 32, 22, 12]` 都是一个列表。

因为列表和字符串一样，都是*有序容器*（容器还有另外一种是无序容器），所以，它们可用的操作符其实相同：

> * 拼接：`+` 和 `' '`（后者是空格）
> * 拷贝：`*`
> * 逻辑运算：`in`、`not in`；以及，`<`、`<=`、`>`、`>=`、`!=`、`==`

两个列表在比较时（前提是两个列表中的数据元素类型相同），遵循的还是跟字符串比较相同的规则：“一旦决出胜负马上停止”。但实际上，由于列表中可以包含不同类型的元素，所以，通常情况下没有实际需求对他们进行 “大于、小于” 的比较。（比较时，类型不同会引发 `TypeError`……）


```python
a_list = [1, 2, 3, 4, 5]
b_list = [1, 2, 3, 5]
c_list = ['ann', 'bob', 'cindy', 'dude', 'eric']
a_list > b_list
10 not in a_list
'ann' in c_list
```

## 关于布尔值的补充

当你看到以下这样的表达式，而后再看看它的结果，你可能会多少有点迷惑：


```python
True or 'Python'
```


```python
a = 'abc'
b = 'abd'
a and b
a or b
'c' and 'd'
'c' or 'd'

c = []
d = [1,2,3]
c and d
c or d
```

这是因为 Python 将 `True` 定义为：

> By default, an object is considered true unless its class defines either a \_\_bool\_\_() method that returns `False` or a \_\_len\_\_() method that returns zero, when called with the object.
>
> https://docs.python.org/3/library/stdtypes.html#truth-value-testing

这一段文字，初学者是看不懂的。但下一段就好理解了：

> Here are most of the built-in objects considered `False`:
> 
> > * constants defined to be false: `None` and `False`.
> > * zero of any numeric type: `0`, `0.0`, `0j`, `Decimal(0)`, `Fraction(0, 1)`
> > * empty sequences and collections: `''`, `()`, `[]`, `{}`, `set()`, `range(0)`

所以，`'Python'` 是个非空的字符串，即，不属于是 `empty sequences`，所以它不被认为是 `False`，即，它的布尔值是 `True`

于是，这么理解就轻松了：

> 每个变量或者常量，除了它们的值之外，同时还相当于有一个对应的布尔值。



```python
if '' == True:
    print('yes')
else:
    print('no')
```


```python
if '' == False:
    print('yes')
else:
    print('no')
```


```python
'' != True
```


```python
'' == False
```

![image.png](attachment:image.png)

## Built-in functions

https://www.programiz.com/python-programming/methods/built-in


```python
print('I love {0} and {1}'.format('bread','butter'))
# Output: I love bread and butter

print('I love {1} and {0}'.format('bread','butter'))
# Output: I love butter and bread

print('Hello {name}, {greeting}'.format(greeting = 'Goodmorning', name = 'John'))
```


```python
name = 'Ann'
age = '22'
print(f'{name} is {age} years old.')
```


```python
print('hello world\nss', 2, sep='\n')
```

    hello world
    ss
    2



```python
x = 'spam'
y = 99
z = ['eggs']
print(x, y, z)
print(x, y, z, sep = '\n')
```

    spam 99 ['eggs']
    spam
    99
    ['eggs']



```python
print('hello\ngood')
```

    hello
    good



```python
a = input('Enter a Number: ')
a
```

    Enter a Number:  2





    '2'




```python
# filter(function, iterative)

# Program to filter out only the even items from a list

my_list = [1, 5, 4, 6, 8, 11, 3, 12]

new_list = list(filter(lambda x: (x%2 == 0) , my_list))

# Output: [4, 6, 8, 12]
print(new_list)
```


```python
# map(function, iterative, more iter...)

numbers = (1, 2, 3, 4)
result = list(map(lambda x: x*x, numbers))
print(result)     
```


```python
num1 = [4, 5, 6]
num2 = [5, 6, 7]

result = list(map(lambda n1, n2: n1+n2, num1, num2))
print(result)
```

    [9, 11, 13]



```python
# zip(*iterables)
# The zip() function take iterables (can be zero or more), makes iterator that aggregates elements 
# based on the iterables passed, and returns an iterator of tuples.
zip()
```


```python
arr1=[1, 2, 3, 4, 5]

reduce(lambda x, y: x+y, arr1)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-3-ba90527eb706> in <module>
          1 arr1=[1, 2, 3, 4, 5]
          2 
    ----> 3 reduce(lambda x, y: x+y, arr1)
    

    NameError: name 'reduce' is not defined



```python
array = [1,2,3]
# list(map(lambda x: str(x), array))

for i in range(len(array)):
    array[i] = str(array[i])
    
array
```




    ['1', '2', '3']



any() returns:

* True if at least one element of an iterable is true
* False if all elements are false or if an iterable is empty


```python
l = [1, 3, 4, 0]
print(any(l))

l = [0, False]
print(any(l))

l = [0, False, 5]
print(any(l))

l = []
print(any(l))
```

The all() method returns:

* True - If all elements in an iterable are true  
* False - If any element in an iterable is false


```python
# all values true
l = [1, 3, 4, 5]
print(all(l))

# all values false
l = [0, False]
print(all(l))

# one false value
l = [1, 3, 4, 0]
print(all(l))

# one true value
l = [0, False, 5]
print(all(l))

# empty iterable
l = []
print(all(l))
```

## Functions


```python
yield

keywords
```

yield()
https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do


```python
# Program to show the use of lambda functions

double = lambda x: x * 2

# Output: 10
print(double(5))
```


```python
def function(x, y = 1, z = 2): # default argument must behind non-default argument
    return x + y + z

function(x=3, z=5)
```




    9




```python
#The *args will give you all function parameters as a tuple
def foo(*args):
    for a in args:
        print(a)        

foo(1)
# 1

foo(1,2,3)
# 1
# 2
# 3
```


```python
#The **kwargs will give you all keyword arguments except for those corresponding to a formal parameter as a dictionary.
def bar(**kwargs):
    for a in kwargs:
        print(kwargs)
        print(a, kwargs[a])  

bar(name='one', age=27)
# age 27
# name one
```

    {'name': 'one', 'age': 27}
    name one
    {'name': 'one', 'age': 27}
    age 27



```python
def foo(a, b, c):
    print(a, b, c)

obj = {'a': 1, 'b':10, 'c':'lee'}

foo(**obj)
# 100 10 lee
```

    1 10 lee


## Class and Object


```python
class Main:
    def solution(self):
        print('a')
        
obj = Main()
obj.solution()
```

    a



```python
class Parrot:
    """
    hello
    """
    a = 10
    # instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)

# instantiate the object
blu = Parrot("Blu", 10)

# call our instance methods
print(blu.sing("'Happy'"))
print(blu.dance())
blu
blu.__doc__
```

    Blu sings 'Happy'
    Blu is now dancing





    <__main__.Parrot at 0x7f890759e880>






    '\n    hello\n    '




```python
class PartyAnimal:
    x = 0
    name = ''
    def __init__(self, nam):
        self.name = nam
        print(self.name,'constructed')

    def party(self) :
        self.x = self.x + 1
        print(self.name,'party count',self.x)

class CricketFan(PartyAnimal):
    points = 0
    def six(self):
        self.points = self.points + 6
        self.party()
        print(self.name,"points",self.points)

s = PartyAnimal("Sally")
s.party()
j = CricketFan("Jim")
j.party()
j.six()
print(dir(j))
type(s)
```


```python
class MyClass:
	"This is my second class"
	a = 10
	b = 2
	def func(self):
		print('Hello', self.a, self.b)

# create a new MyClass
ob = MyClass()

ob.func()
```

On the command del c1, this binding is removed and the name c1 is deleted from the corresponding namespace. The object however continues to exist in memory and if no other name is bound to it, it is later automatically destroyed.

This automatic destruction of unreferenced objects in Python is also called garbage collection.



### Inheritance


```python
# parent class
class Bird:
    
    def __init__(self):
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def swim(self):
        print("Swim faster")

# child class
class Penguin(Bird):

    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def run(self):
        print("Run faster")

peggy = Penguin()
peggy.whoisThis()
peggy.swim()
peggy.run()
```

    Bird is ready
    Penguin is ready
    Penguin
    Swim faster
    Run faster



```python
class Polygon:
    def __init__(self, no_of_sides):
        self.n = no_of_sides
        self.sides = [0 for i in range(no_of_sides)]

    def inputSides(self):
        self.sides = [float(input("Enter side "+str(i+1)+" : ")) for i in range(self.n)]

    def dispSides(self):
        for i in range(self.n):
            print("Side",i+1,"is",self.sides[i])
            
c = Polygon(3)
c.inputSides()
# c.dispSides()
```


```python
class Triangle(Polygon):
    def __init__(self):
        Polygon.__init__(self,3) # super().__init__(3)

    def findArea(self):
        a, b, c = self.sides
        # calculate the semi-perimeter
        s = (a + b + c) / 2
        area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
        print('The area of the triangle is %0.2f' %area)
```

### Encapsulation

Using OOP in Python, we can restrict access to methods and variables. This prevent data from direct modification which is called encapsulation. In Python, we denote private attribute using underscore as prefix i.e single “ _ “ or double “ __“.

In the above program, we defined a class Computer. We use ..init..() method to store the maximum selling price of computer. We tried to modify the price. However, we can’t change it because Python treats the __maxprice as private attributes. To change the value, we used a setter function i.e setMaxPrice() which takes price as parameter.


```python
class Computer:

    def __init__(self):
        self.__maxprice = 900

    def sell(self):
        print("Selling Price: {}".format(self.__maxprice))

    def setMaxPrice(self, price):
        self.__maxprice = price

c = Computer()
c.sell()

# change the price
c.__maxprice = 1000
c.sell()

# using setter function
c.setMaxPrice(1000)
c.sell()
```

#### Private variables


```python
class P:
    def __init__(self, name, alias):
        self.name = name       # public
        self.__alias = alias   # private

    def who(self):
        print('name  : ', self.name)
        print('alias : ', self.__alias)
    
    def iss(self):
        return self.__alias
    
x = P(name='Alex', alias='amen')
print(x._P__alias)
print(x.iss())

```


```python
class P:
    def __init__(self, name, alias):
        self.name = name       # public
        self._alias = alias   # nonpublic

    def who(self):
        print('name  : ', self.name)
        print('alias : ', self._alias)
    
    def iss(self):
        return self._alias
    
x = P(name='Alex', alias='amen')
print(x._alias)
print(x.iss())
```

    amen
    amen


### Polymorphism


```python
class Parrot:

    def fly(self):
        print("Parrot can fly")
    
    def swim(self):
        print("Parrot can't swim")

class Penguin:

    def fly(self):
        print("Penguin can't fly")
    
    def swim(self):
        print("Penguin can swim")

# common interface
def flying_test(bird):
    bird.fly()

#instantiate objects
blu = Parrot()
peggy = Penguin()

# passing the object
flying_test(blu)
flying_test(peggy)
```

We can see that, even though we did not define methods like **inputSides()** or **dispSides()** for class Triangle, we were able to use them.

If an attribute is not found in the class, search continues to the base class. This repeats recursively, if the base class is itself derived from other classes.

Generally when overriding a base method, we tend to extend the definition rather than simply replace it. The same is being done by calling the method in base class from the one in derived class (calling Polygon.__init__() from __init__() in Triangle).

A better option would be to use the built-in function **super()**. So, **super().__init__(3)** is equivalent to **Polygon.__init__(self,3)** and is preferred. You can learn more about the 

### Generator


```python
# mylist = [x*x for x in range(3)]
# for i in mylist:
#     print(i)
    

mygenerator = (x*x for x in range(3))
for i in mygenerator:
    print(i)
    
# def createGenerator():
#     mylist = range(3)
#     for i in mylist:
#         yield i*i

# mygenerator = createGenerator()
print(mygenerator)
# for i in mygenerator:
#     print(i)
    
    
[*range(3)]
```


```python
def x(n):
    n = 1
    print(n)
    return n

x(2)
# type(x(2))
```

### Decorators


```python
def inc(x):
    return x + 1

def dec(x):
    return x - 1

def operate(func, x):
    result = func(x)
    return result

operate(inc,3)
```




    4




```python
def make_pretty(func):
    def inner():
        print("I got decorated")
        func()
    return inner

def ordinary():
    print("I am ordinary")
    
# ordinary = make_pretty(ordinary)
# ordinary()

@make_pretty
def ordinary():
    print("I am ordinary")
    
# equivalent to 
# def ordinary():
#     print("I am ordinary")
# ordinary = make_pretty(ordinary)
    
ordinary()
```

    I got decorated
    I am ordinary



```python
def smart_divide(func):
    def inner(a,b):
        print("I am going to divide",a,"and",b)
        if b == 0:
            print("Whoops! cannot divide")
            return

        return func(a,b)
    return inner

@smart_divide
def divide(a,b):
    return a/b
```

*args (Non Keyword Arguments)
**kwargs (Keyword Arguments)


```python
def star(func):
    def inner(*args, **kwargs):
        print("*" * 30)
        func(*args, **kwargs)
        print("*" * 30)
    return inner

def percent(func):
    def inner(*args, **kwargs):
        print("%" * 30)
        func(*args, **kwargs)
        print("%" * 30)
    return inner

@star
@percent
def printer(msg):
    print(msg)
    
# equivalent to
# def printer(msg):
#     print(msg)
# printer = star(percent(printer))

printer("Hello")
```

### @property


```python
class Celsius:
    def __init__(self, temperature = 0):
        self.set_temperature(temperature)

    def to_fahrenheit(self):
        return (self.get_temperature() * 1.8) + 32

    # new update
    def get_temperature(self):
        return self._temperature

    def set_temperature(self, value):
        if value < -273:
            raise ValueError("Temperature below -273 is not possible")
        self._temperature = value
        
c = Celsius(37)
c.temperature = 23
c.get_temperature()
```


```python
class Celsius:
    def __init__(self, temperature = 0):
        self._temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    def get_temperature(self):
        print("Getting value")
        return self._temperature

    def set_temperature(self, value):
        if value < -273:
            raise ValueError("Temperature below -273 is not possible")
        print("Setting value")
        self._temperature = value

    temperature = property(get_temperature,set_temperature)
    
#     # make empty property
#     temperature = property()
#     # assign fget
#     temperature = temperature.getter(get_temperature)
#     # assign fset
#     temperature = temperature.setter(set_temperature)

c = Celsius()
# c.temperature
c.to_fahrenheit()
```

Which is also equivalent to below


```python
class Celsius:
    def __init__(self, temperature = 0):
        self._temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    @property
    def temperature(self):
        print("Getting value")
        return self._temperature

    @temperature.setter
    def temperature(self, value):
        if value < -273:
            raise ValueError("Temperature below -273 is not possible")
        print("Setting value")
        self._temperature = value
        
c = Celsius()
c.to_fahrenheit()
# c.temperature 
```


```python
class Person:
    def __init__(self, name): 
        self._name = name
    
    @property
    def name(self):
        print('fetch')
        return self._name
    
    @name.setter
    def name(self,value):
        print('change')
        self_name = value
        
    @name.deleter
    def name(self):
        print('remove')
        del self._name
        
bob = Person('Bob Smith')
print(bob.name)
```


```python
def intro(*d, **data):
    print("\nData type of argument:",type(data))
    print(data)
    print(d)
#     for key, value in data.items():
#         print("{} is {}".format(key,value))

intro(3,Firstname="Sita", Lastname="Sharma", Age=22, Phone=1234567890)
intro(Firstname="John", Lastname="Wood", Email="johnwood@nomail.com", Country="Wakanda", Age=25, Phone=9876543210)
```


```python
foo = 100
 
def hello():
    print("i am from my_module.py")

if __name__ == "__main__":
    print("Executing as main program")
    print("Value of __name__ is: ", __name__)
    hello()
```

## Keywords

https://www.programiz.com/python-programming/keyword-list#is

**is** is used in Python for testing object identity. While the == operator is used to test if two variables are equal or not, is is used to test if the two variables refer to the same object.

**Void functions** that do not return anything will return a None object automatically. None is also returned by functions in which the program flow does not encounter a return statement. 


```python
class Tree:
    def __init__(self, value):
        self.val = value
        self.next = None
        
a = Tree(3)
b = Tree(3)
a is b
```




    False



## Global, local, nonlocal

https://www.programiz.com/python-programming/global-local-nonlocal-variables

### Global


```python
c = 0 # global variable
def add():
    global c
    c = c + 2 # increment by 2
    print("Inside add():", c)

add()
print("In main:", c)
```

    Inside add(): 2
    In main: 2



```python
globvar = 10
def read1():
    print(globvar)
def write1():
    global globvar 
    globvar = 5
    return globvar
def write2():
    globvar = 15
    return globvar

write1()
```


```python
def outer():
    x = "local"
    
    def inner():
        nonlocal x
        x = "nonlocal"
        print("inner:", x)
    
    inner()
    print("outer:", x)

outer()
```

    inner: nonlocal
    outer: nonlocal


## os and sys

/Users/zhutianwei/Library/Mobile Documents/com~apple~CloudDocs/2. Tech Hacker/Essential-ML/  
/Volumes/Secomba/zhutianwei/Boxcryptor/iCloud Drive (Mac & PC only)/2. Tech Hacker/Essential-ML


```python
import os
import sys
```


```python
sys.version
```




    '3.7.2 (default, Dec 29 2018, 00:00:04) \n[Clang 4.0.1 (tags/RELEASE_401/final)]'




```python
os.path
# os.path.getsize()
# os.path.isdir(path)
# os.listdir(path)
# os.path.join(path, ﬁlename)
os.name
```




    <module 'posixpath' from '/Users/zhutianwei/anaconda/envs/ai/lib/python3.7/posixpath.py'>






    'posix'




```python
os.getcwd()
```




    '/Volumes/Secomba/zhutianwei/Boxcryptor/iCloud Drive (Mac & PC only)/2. Tech Hacker/笔记'




```python
!pwd
```

A string like that identifies a file is called a path. A relative path starts from the current directory; an absolute path starts from the topmost directory in the file system.


```python
os.path.exists('memo.txt')
```


```python
os.listdir(os.getcwd())
```


```python
os.chdir('/Users/zhutianwei/Library/Mobile Documents/com~apple~CloudDocs/2. Tech Hacker/Essential-ML/data')
```


```python
os.path.join('/Users/zhutianwei/Library/Mobile Documents/com~apple~CloudDocs/2. Tech Hacker/Essential-ML/data', 'housing.csv')
```


```python
os.path.isdir('/Users/zhutianwei/Library/Mobile Documents/com~apple~CloudDocs/2. Tech Hacker/Essential-ML/data/')
```


```python
os.makedirs(housing_path)
```


```python
module_path = os.path.abspath(os.path.join('/Users/zhutianwei/Library/Mobile\ Documents/com\~apple\~CloudDocs/2.\ Tech\ Hacker/2.\ AI/1.\ Artificial\ Intelligence/1.\ Projects/Project\ 2/AIND-Isolation/isolation'))
if module_path not in sys.path:
    sys.path.append(module_path)
```


```python
sys.path
```




    ['/Users/zhutianwei/anaconda/envs/IntroToTensorFlow/lib/python36.zip',
     '/Users/zhutianwei/anaconda/envs/IntroToTensorFlow/lib/python3.6',
     '/Users/zhutianwei/anaconda/envs/IntroToTensorFlow/lib/python3.6/lib-dynload',
     '',
     '/Users/zhutianwei/anaconda/envs/IntroToTensorFlow/lib/python3.6/site-packages',
     '/Users/zhutianwei/anaconda/envs/IntroToTensorFlow/lib/python3.6/site-packages/aeosa',
     '/Users/zhutianwei/anaconda/envs/IntroToTensorFlow/lib/python3.6/site-packages/IPython/extensions',
     '/Users/zhutianwei/.ipython']



https://www.tutorialsteacher.com/python/sys-module  
import sys 


## Regular Expression
https://www.programiz.com/python-programming/regex#python-regex


```python
'^a...s$'


```


```python
import re
A = ''
line = '.-.-....-.-...--.-...-....--...-.-...-.--.------..-...-..-.-.---...-..-..---..-......--..-.--.-...-.--......-.........-..-.----.-.....-....--.-.-.--.-..---..-......-...-..-.--.-.----......-.--.-----..-------.-.-..---.-.-.--..-.-...............--...--....--..-....-.-----.....-...-------.-......-.........-..-..--.-....-...--....-.--.-.....--..-.....--..-.---.--...-.-.-..-.-.....---.-.-.-.----....-..-.....--..----......-...-.--.-...--.....--.....-.......-....---..-..--...-------.--....---..---.....-.-.-....-.-...--..-....---..--.--...-.-.-..-.-.....---.-.-.-.----....-..-.....--..----.'
if re.search(A,line):
    print('yes')
```


```python
import re

pattern = '^a...s$'
test_string = 'abyss'
result = re.match(pattern, test_string)
print(result)

if result:
    print("Search successful.")
else:
    print("Search unsuccessful.")
```


```python
import re
string = 'hello 12 hi 89. Howdy 34'
pattern = '\d+'
result = re.findall(pattern, string) 
print(result)
```

    ['12', '89', '34']


## File I/O

https://www.programiz.com/python-programming/file-operation


```python
with open("test.txt",encoding = 'utf-8') as f:
   # perform file operations
```

## Error Handing

https://www.programiz.com/python-programming/exceptions


```python
try:
    a = int(input("Enter a positive integer: "))
    if a <= 0:
        raise ValueError("That is not a positive number!")
except ValueError as vs:
    print(vs)
  
```

    Enter a positive integer:  -1


    That is not a positive number!



```python
def reciprocal(num):
    try:
        r = 1/num
    except Exception:
        print('Exception caught')
        return None
    return r

print(reciprocal(10))
print(reciprocal(0))
```

    0.1
    Exception caught
    None



```python
try:
    print("No exception")
except:
    pass
else:
    print("Success") #The else clause runs when no exception occurs between try and except.
```

    No exception
    Success



```python
array = 1
 
if type(array) is not list:
    raise Exception('no')
    
else:
    print('ok')
```


    ---------------------------------------------------------------------------

    Exception                                 Traceback (most recent call last)

    <ipython-input-9-2904cc9cba4e> in <module>
          2 
          3 if type(array) is not list:
    ----> 4     raise Exception('no')
          5 
          6 else:


    Exception: no



```python
array = [1,2,3]

type(array) is list
isinstance(array, list)
```




    True




```python
num = {1:2}
type(num) == dict
```




    True



## Debug
Print()  
assert  
Divide  
debugger  

1. Do not use a “debugger.” A debugger is like doing a full-body scan on a sick person. You do not get any speciﬁc useful information, and you ﬁnd a whole lot of information that doesn’t help and is just confusing
2. The best way to debug a program is to use print to print out the values of variables at points in the program to see where they go wrong.
3. Make sure parts of your programs work as you work on them. Do not write massive ﬁle of code before you try to run them. Code a little, run a little, ﬁx a little.


```python
def avg(marks):
    assert len(marks) != 0
    return sum(marks)/len(marks)

mark1 = []
print("Average of mark1:", avg(mark1))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-1-f99d3eaaaacd> in <module>
          4 
          5 mark1 = []
    ----> 6 print("Average of mark1:", avg(mark1))
    

    <ipython-input-1-f99d3eaaaacd> in avg(marks)
          1 def avg(marks):
    ----> 2     assert len(marks) != 0
          3     return sum(marks)/len(marks)
          4 
          5 mark1 = []


    AssertionError: 


## Test


```python
# unittests
```


```python
assert sum([1, 2, 3]) == 5, "Should be 6"
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-12-670dd62afbd7> in <module>
    ----> 1 assert sum([1, 2, 3]) == 5, "Should be 6"
    

    AssertionError: Should be 6



```python
import unittest

class TestSum(unittest.TestCase):

    def test_sum(self):
        self.assertEqual(sum([1, 2, 3]), 6, "Should be 6")

    def test_sum_tuple(self):
        self.assertEqual(sum((1, 2, 2)), 6, "Should be 6")

# if __name__ == '__main__':
# unittest.main()
unittest.main(argv=['first-arg-is-ignored'], exit=False)
```

    F...F
    ======================================================================
    FAIL: test_float (__main__.TestDivision)
    ----------------------------------------------------------------------
    Traceback (most recent call last):
      File "<ipython-input-10-c5d43ca86633>", line 14, in test_float
        self.assertEqual(division_funtion(4.2, 3), 1.4)
    AssertionError: 1.4000000000000001 != 1.4
    
    ======================================================================
    FAIL: test_sum_tuple (__main__.TestSum)
    ----------------------------------------------------------------------
    Traceback (most recent call last):
      File "<ipython-input-14-b6758e2b821d>", line 9, in test_sum_tuple
        self.assertEqual(sum((1, 2, 2)), 6, "Should be 6")
    AssertionError: 5 != 6 : Should be 6
    
    ----------------------------------------------------------------------
    Ran 5 tests in 0.007s
    
    FAILED (failures=2)





    <unittest.main.TestProgram at 0x7f7f9d1a88e0>



https://stackoverflow.com/questions/37895781/unable-to-run-unittests-main-function-in-ipython-jupyter-notebook/38012249#38012249


```python
import unittest

def division_funtion(x, y):
    return x / y

class TestDivision(unittest.TestCase):
    def test_int(self):
        self.assertEqual(division_funtion(9, 3), 3)

    def test_int2(self):
        self.assertEqual(division_funtion(9, 4), 2.25)

    def test_float(self):
        self.assertEqual(division_funtion(4.2, 3), 1.4)

if __name__ == '__main__':
    unittest.main()
```

    E
    ======================================================================
    ERROR: /Users/zhutianwei/Library/Jupyter/runtime/kernel-161f2563-3832-493a-b78f-89a1c997a183 (unittest.loader._FailedTest)
    ----------------------------------------------------------------------
    AttributeError: module '__main__' has no attribute '/Users/zhutianwei/Library/Jupyter/runtime/kernel-161f2563-3832-493a-b78f-89a1c997a183'
    
    ----------------------------------------------------------------------
    Ran 1 test in 0.002s
    
    FAILED (errors=1)



    An exception has occurred, use %tb to see the full traceback.


    SystemExit: True



    /Users/zhutianwei/anaconda3/envs/random/lib/python3.8/site-packages/IPython/core/interactiveshell.py:3339: UserWarning: To exit: use 'exit', 'quit', or Ctrl-D.
      warn("To exit: use 'exit', 'quit', or Ctrl-D.", stacklevel=1)



```python
class example:
    def __init__(self,list1):
        self.list = list1
    def length():
        return self.list.length()
    
a = example([1,2])
a.length()
```


```python
a = dict()
a
```


```python
class NewList(list):
    pass
        
a = NewList()
print(a)
```


```python
import numpy as np
import scipy as sp
import math as m

# dir(np)
# help(np)

sp.special.factorial(5)
```

## Threading


```python
import threading

def test(x, y):
    for i in range(x, y):
        print(i)
        
thread1 = threading.Thread(name='t1', target=test, args=(1,10))
thread2 = threading.Thread(name='t2', target=test, args=(11,20))    
thread1.start()
thread2.start()

```

    111
    12
    13
    14
    15
    16
    17
    18
    19
    
    2
    3
    4
    5
    6
    7
    8
    9



```python
import json
```


```python
<str>    = json.dumps(<object>, ensure_ascii=True, indent=None)
<object> = json.loads(<str>)
```


```python
def read_json_file(filename):
    with open(filename, encoding='utf-8') as file:
        return json.load(file)
```


```python
def write_to_json_file(filename, an_object):
    with open(filename, 'w', encoding='utf-8') as file:
        json.dump(an_object, file, ensure_ascii=False, indent=2)
```
