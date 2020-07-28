Concepts:
non local 
global
@property

# Intro to Python
Objects can have more linked objects, methods, or both. 

## Overview
1-Variables = Object
* Numbers. int, float
* Strings. str
* Booleans. bool

2-Data Structure = Object(Variable + Methods)
* List
* NumPy arrays
* Dictionary 
* Tuple
* Set

图片 声音 视频

3-Operations.  
> - [Part.1.E.2.values-and-their-operators（**值及其相应的运算**）](Part.1.E.2.values-and-their-operators.ipynb)

4-Condition. Use an if statement  
5-Loops. Write a for or while loop  
6-Functions. Write a function  
7-Classes and objects. Inheritance, encapsulation, Polymorfism. Define a class. Initialize an object  
8-Modules and packages  

File input/output  
try/except   

Run  
Debug  
Test  
Use libraries to build Algorithms. Algorithms to build Program, Software, Project.


```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
```


```python
# Python进阶. 微信
# decorator
# metaclass
```

## Import local packages


```python
import isolation
Board
```


```python
from custom.planning import Action
from custom.utils import Expr
```


```python
import platform
platform.python_version()
```




    '3.6.8'



## 所有数据结构都是关于创造 相互转换 增删查改


```python
number operations +,=,*,/,//,%,**. &,|,^,~,<<,>> 
logic operations ==,>,<, is, in
				 and, or, not
```

~ means revert every bit.  
Therefore, ~x means -x-1.  
An elegant (but confusing) way to choose the rightest element of the middle part.


```python
s // 10, s % 10
```


```python
s = 4
s >>= 1 # // 2
s

s & 1 == s % 2

d = 4
d <<= 1 # * 2
d
```




    2
    8



如果把 n 以二进制的形式展示的话，其实我们只需要判断最后一个二进制位是 1 还是 0 就行了，如果是 1 的话，代表是奇数，如果是 0 则代表是偶数，所以采用位运算的方式的话，


```python
2 and 4
```




    4




```python
2 or 4
```




    2



## Numbers


```python
help()
dir()
# print(‘{} is something'.format(variablename))
type(), raw_input(), float(), int()
round(1.68, 1) —> 1.7
max()
sorted()
```


```python
abs(-4)
```


```python
chr(3)
```


```python
ord('A')
```

### Decimal


```python
x = 1; y = 2

x, y = y, x

x = y
y = x

print(x, y)
```

    2 2


https://www.programiz.com/python-programming/numbers


```python
-7 / 2 # 5.0
-7 // 2 # 5
```




    -3.5






    -4




```python
round(-7 // 2)
```




    -4




```python
x = 3
y = complex(x)
x + y
```




    (6+0j)




```python
chr(65)
ord('a')
```




    'A'






    97




```python
chr(48)
ord('0')
```




    '0'






    48




```python
chr(127) # last item in ascii code
```




    '\x7f'




```python
from math import inf
max(-inf, 10)
```




    10




```python
import sys
_max = sys.maxsize
_min = -sys.maxsize - 1
```


```python
import math
math.log10(100)
```




    2.0




```python
import fractions as f
f.Fraction(1.5)

```

https://www.programiz.com/python-programming/modules/random


```python
import random

array = [0,1,2]

random.randint(0, 2) #0-2
random.randrange(0, 2) # 0-1
random.choice(array)
```




    2




```python
~2
```




    -3




```python
s = '110'
int(s)
```




    110



### Binary. Hexadecimal  
see EE course

1 unsigned int = 4 byte = 32 bits = ffffffff            
1 byte = 8 bits = 0000 0000 = ff 

& | ^ ~ << >> 都是对二进制数进行运算


```python
a = bin(4)
type(a)
a
int(a, 2)
```




    str






    '0b100'






    4




```python
x = 1
hex(id(x))
```




    '0x10891dbf0'




```python
x = [1,2]
y = x
hex(id(x))
hex(id(y))
```




    140354218507584






    140354218507584




```python
# 11 -> 1
3 >> 1

# 11 -> 6
3 << 1
```




    1






    6




```python
decimal_number = 255
"{:b}".format(decimal_number)
# '11111111'
```




    '11111111'




```python
# binary 0b or 0B
print("For 1010, int is:", int('1010', 2))
print("For 0b1010, int is:", int('0b1010', 2))

# octal 0o or 0O
print("For 12, int is:", int('12', 8))
print("For 0o12, int is:", int('0o12', 8))

# hexadecimal
print("For A, int is:", int('A', 16))
print("For 0xA, int is:", int('0xA', 16))
```

    For 1010, int is: 10
    For 0b1010, int is: 10
    For 12, int is: 10
    For 0o12, int is: 10
    For A, int is: 10
    For 0xA, int is: 10


https://www.ascii-code.com/

## String
https://www.programiz.com/python-programming/methods/string


```python
['.' * 3] * 3
```




    ['...', '...', '...']




```python
s = "I'm the iron man"
len(s)
```




    16




```python
s = "abba"
sorted(s)
```




    ['a', 'a', 'b', 'b']




```python
res = 'abcdef'
res[::2]
res[1::2]
```




    'bdf'




```python
s[::-1]
s.find('a') # return -1 if not found
s.index('a')
```




    "nam nori eht m'I"






    14






    14




```python
s= [0, 1]
if sum(s):
    print('yes')
```

    yes



```python
s.replace('iron','small')

song = 'Let it be, let it be, let it be, let it be'
'''only two occurences of 'let' is replaced'''
song.replace('let', "don't let", 2)
```




    'Mo3 nicaG el l22er'






    "only two occurences of 'let' is replaced"






    "Let it be, don't let it be, don't let it be, let it be"






    'Let it be, let it be, let it be, let it be'




```python
s = '...'
s.replace('.', 'Q')
```




    'QQQ'




```python
s.upper()
s.lower()
s.isuppper()
s.islower()
s.count('the')
```




    '.'






    '.'






    0




```python
s.startswith("I")
s.endswith('man')
text = "programming is easy"
result = text.startswith(('python', 'programming'))
```




    False






    False




```python
# List and strings
s = 'spam'
t = list(s)
t
```


```python
s2 = ' '.join(words)
s2
# Leading whitepsace are removed
s3 = ' xoxo love xoxo   '
s3.strip() # return new
```


```python
s = 'pining for the fjords'
t = s.split()
print(t) # ['pining', 'for', 'the', 'fjords']
print(t[2]) # the
print(t[::-1])
```


```python
s = 'spam-spam-spam'
s.split('-')
```




    ['spam', 'spam', 'spam']




```python
array = []
s = '43+22*33'
l = 0
r = 0
while r < len(s):
    if s[r] in '+-*/':
        array.append(s[l:r])
        r += 1
        l = r
    else:
        r += 1        
array.append(s[l:])

array
```




    ['43', '22', '33']




```python
# example string
string = 'cat'
width = 5
fillchar = '*'

# print left justified string
string.ljust(width, fillchar)
```


```python
s = "I'm the iron man"
a = s[len("I'm"):]

print(s, a, sep='\n')

x = list(enumerate(s))
x

b = []
b.append(s)
b
```

    I'm the iron man
     the iron man





    <enumerate at 0x10e135090>






    [(0, 'I'),
     (1, "'"),
     (2, 'm'),
     (3, ' '),
     (4, 't'),
     (5, 'h'),
     (6, 'e'),
     (7, ' '),
     (8, 'i'),
     (9, 'r'),
     (10, 'o'),
     (11, 'n'),
     (12, ' '),
     (13, 'm'),
     (14, 'a'),
     (15, 'n')]






    ["I'm the iron man"]




```python
m = [m]

def noman(m):
    if m != []:
        print('x')
noman(m)
```


```python
name = "Monica"
print(name.isalpha())

# contains whitespace
name = "Monica Geller"
print(name.isalpha())

# contains number
name = "Mo3nicaGell22er"
print(name.isalpha())
```


```python
s = "28212"
print(s.isdigit())

# contains alphabets and spaces
s = "Mo3 nicaG el l22er"
print(s.isdigit())
```

    True
    False



```python
s = '1242323'
print(s.isnumeric())
#s = '²3455'

s = '\u00B23455'
print(s.isnumeric())
# s = '½'

s = '\u00BD'
print(s.isnumeric())

s = 'python12'
print(s.isnumeric())
```

    True
    True
    True
    False



```python
name = "M234onica"
print(name.isalnum())

# contains whitespace
name = "M3onica Gell22er "
print(name.isalnum())

name = "Mo3nicaGell22er"
print(name.isalnum())

name = "133"
print(name.isalnum())
```


```python
s = "28212"
print(s.isdecimal())

# contains alphabets
s = "32ladk3"
print(s.isdecimal())

# contains alphabets and spaces
s = "Mo3 nicaG el l22er"
print(s.isdecimal())
```


```python
import random
random.randint(0,10)
```


```python
def containsSubstring(src, key):
    res = []
    for word in src:
        if key in word:
            res.append(word)
    return res
```


```python
s = "abc"
for i, c in enumerate(s):
    print(i, c)
```

    0 a
    1 b
    2 c



```python
s = "HNHAN"
"NHA" in s
```




    True




```python
arr = ["cha","r","act","ers"]
arr = [s for s in arr if len(s) == len(set(s))]
arr.sort(key=len, reverse=True)
arr
```




    ['cha', 'act', 'ers', 'r']




```python
s = "Let's go"
d = 'Let\'s go'
d
```




    "Let's go"




```python
s = '\nhello word\nhello word'
print(s)
```

    
    hello word
    hello word


## List

Learning python textbook

add, remove, select, modify, 


```python
l = [1,3,2,2,4,5,6]

# for n in l:
# for i in range(len(l))
# for i, n in enumerate(l)

l += 1, # fastest
l.append(1) # second fast
l += [1] # slowest
l

l * 2

a = [1, 2]
b = [3, 4]
a.extend(b) # equal to a += b
```




    [1, 3, 2, 2, 4, 5, 6, 1, 1, 1]






    [1, 3, 2, 2, 4, 5, 6, 1, 1, 1, 1, 3, 2, 2, 4, 5, 6, 1, 1, 1]






    'c'






    ['a', 'b']




```python

t = ['a', 'b', 'b', 'c']
t.pop() # = t.pop(-1)
t.remove('b')
# del t[1:2]
# t.clear()
t

a = [1,2,3]
del a[:]
a
```


```python
min(l)
max(l)
sum(l)
```


```python
s = [1,2,2]
s.index(2)
l.count(2)
```




    1






    2




```python
l = [1,3,2,2,4,5,6]
l.sort() # key, reverse 
l
sorted(l) # return a new sorted list.
sorted(l, reverse = True) 

l.reverse()
l
reversed(l)
for n in reversed(l):
    print(n)
    
l[::-1]
```




    [1, 2, 2, 3, 4, 5, 6]






    [1, 2, 2, 3, 4, 5, 6]






    [6, 5, 4, 3, 2, 2, 1]






    [6, 5, 4, 3, 2, 2, 1]






    <list_reverseiterator at 0x7fa6c3597df0>



    1
    2
    2
    3
    4
    5
    6





    [1, 2, 2, 3, 4, 5, 6]






    2




```python
l = [1,3,2,2,4,5,6]
l.reverse()
l
```




    [6, 5, 4, 2, 2, 3, 1]




```python
l = [(2, 2), (3, 4), (4, 1), (1, 3)]


l.sort(key = lambda x: x[1])
sorted(l, key = lambda x: x[1])

def takeSecond(elem):
    return elem[1]

l.sort(key=takeSecond)
l

sorted(l, key=takeSecond)
```


```python
b = a.copy()
b[0] = 0
print(b, a, sep='\n')

# same result
b = a[:]

s = [1,2,3]
s.insert(2,4) # [1,2,4,3]
s
```


```python
s = [1,2,3,4,5,6]
s[2:5:2]
s[2:5] = [0,0,0]
s
s[::-1]
```


```python
# List comprehensions 
nums = [0, 1, 2, 3, 4]
even_squares = [x ** 2 for x in nums if x % 2 == 0]
print(even_squares)  # Prints "[0, 4, 16]"
```


```python
# mixed list
list = ['cat', 0, 6.7]

# copying a list using slicing
# new_list = list[:]
new_list = list.copy()

# Adding element to the new list
new_list.append('dog')

# Printing new and old list
print('Old List: ', list)
print('New List: ', new_list)
```

    Old List:  ['cat', 0, 6.7]
    New List:  ['cat', 0, 6.7, 'dog']


数字可以用*，List必须用 for n in range()


```python
a = [0] * 6
a[0] = 1
a
```




    [1, 0, 0, 0, 0, 0]




```python
a = [[]] * 6
a[0].append(1)
a
```




    [[1], [1], [1], [1], [1], [1]]




```python
a = [[0] * 3] * 3

a[0].append(1)
print(a)
```

    [[0, 0, 0, 1], [0, 0, 0, 1], [0, 0, 0, 1]]



```python
a = [[0] * 3 for n in range(3)] 

a[0].append(1)
print(a)
```

    [[0, 0, 0, 1], [0, 0, 0], [0, 0, 0]]



```python
x = list(range(10, 100))

x[::2]
x[1::2]
x[10:40:6]
```




    [10,
     12,
     14,
     16,
     18,
     20,
     22,
     24,
     26,
     28,
     30,
     32,
     34,
     36,
     38,
     40,
     42,
     44,
     46,
     48,
     50,
     52,
     54,
     56,
     58,
     60,
     62,
     64,
     66,
     68,
     70,
     72,
     74,
     76,
     78,
     80,
     82,
     84,
     86,
     88,
     90,
     92,
     94,
     96,
     98]






    [11,
     13,
     15,
     17,
     19,
     21,
     23,
     25,
     27,
     29,
     31,
     33,
     35,
     37,
     39,
     41,
     43,
     45,
     47,
     49,
     51,
     53,
     55,
     57,
     59,
     61,
     63,
     65,
     67,
     69,
     71,
     73,
     75,
     77,
     79,
     81,
     83,
     85,
     87,
     89,
     91,
     93,
     95,
     97,
     99]






    [20, 26, 32, 38, 44]



## deque

https://docs.python.org/3/library/collections.html#collections.deque


```python
from collections import deque
x = deque([1,2,3])
x
x.append(4)
x.appendleft(5)
x.index(3)

# x = sorted(x)
# type(x)

```




    3




```python
x = [1,2,3,4,5]
x.index(2)
```




    1




```python
import collections

d = collections.deque(range(10))
print('Normal        :', d)

d = collections.deque(range(10))
d.rotate(2)
print('Right rotation:', d)

d = collections.deque(range(10))
d.rotate(-2)
print('Left rotation :', d)
```

    Normal        : deque([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
    Right rotation: deque([8, 9, 0, 1, 2, 3, 4, 5, 6, 7])
    Left rotation : deque([2, 3, 4, 5, 6, 7, 8, 9, 0, 1])


## Tuples


```python
# Tuples
t = ('a', 'b', 'c', 'd', 'e')
t[0]
t[1:3]
```


```python
list1 = [1,2,3]
list2 = [4,5,9]
list3 = [5,3,4]
x = zip(list1,list2,list3)
l = list(x)
l
    
a,b,c = zip(*l)
a
b
c

array = []
for row in zip(*l):
    print(type(row))
    array.append(row)
    
array
```




    [(1, 4, 5), (2, 5, 3), (3, 9, 4)]






    (1, 2, 3)






    (4, 5, 9)






    (5, 3, 4)



    <class 'tuple'>
    <class 'tuple'>
    <class 'tuple'>





    [(1, 2, 3), (4, 5, 9), (5, 3, 4)]




```python
def foo(bar, lee):
    print(bar, lee)

l = [1,2]

foo(*l)
# 1 2
```

    1 2


## Priority Queue


```python
from queue import PriorityQueue

q = PriorityQueue()
q.put(10)
q.put(1)
q.put(5)

q

while not q.empty():
	print(q.get())
```




    <queue.PriorityQueue at 0x10713bef0>



    1
    5
    10


## Heap


```python
import heapq #模块提供了如下几个函数：
heapq.heappush(heap, item) #把item添加到heap中（heap是一个列表）
heapq.heappop(heap) #把堆顶元素弹出，返回的就是堆顶
heapq.heappushpop(heap, item) #先把item加入到堆中，然后再pop，比heappush()再heappop()要快得多
heapq.heapreplace(heap, item) #先pop，然后再把item加入到堆中，比heappop()再heappush()要快得多
heapq.heapify(list) #将列表进行堆调整
heapq.merge(*iterables) #将多个列表合并，并进行堆调整，返回的是合并后的列表的迭代器
heapq.nlargest(n, iterable, key=None) #返回最大的n个元素（Top-K问题）
heapq.nsmallest(n, iterable, key=None) #返回最小的n个元素（Top-K问题）
```


```python
import heapq
heap = [1,3,6,4,8,7]
heapq.heappush(heap, 5)
heapq.heappop(heap)
heap

heapq.nsmallest(2, heap)

l = [14,5,6,2]
# heapq.heapify(l)
heapq.heappush(l, 4)
heapq.nlargest(2, l)
```




    [14, 6]




```python
heap = [7 ,6, 2, 4, 5, 3, 1]
heapq.heapify(heap)
heap

heapq.heappop(heap)
```




    [1, 4, 2, 6, 5, 3, 7]






    1



## Dictionary 

While values can be of any data type and can repeat, keys must be of immutable type (string, number or tuple with immutable elements) and must be unique.


```python
d = {'a':10, 
     'b':1, 
     'c':22}
len(d)

d.keys() # dict_keys(['a', 'b', 'c'])
d.values() # dict_values([10, 1, 22])
d.items() # dict_items([('a', 10), ('b', 1), ('c', 22)])

x = sorted(d.items()) 

for key in d: # = d.keys() Iterates just through the keys, ignoring the values
    print(key)
    
for value in d.values(): # Iterates just through value, ignoring the keys
    print(value)
    
for key, val in d.items():
    print(val, key)
```


```python
d = {'a':10, 
     'b':1, 
     'c':22}

for k in d:
    if d[k] == 22:
        print(k)
        
list(enumerate(d))
```

    c





    [(0, 'a'), (1, 'b'), (2, 'c')]




```python
d = {'a':10, 
     'b':1, 
     'c':22}
sorted(d.items(), key=lambda x: x[1])
```


```python
# empty dictionary
my_dict = {}

# dictionary with integer keys
my_dict = {1: 'apple', 
           2: 'ball'}
print(my_dict)

# dictionary with mixed keys
my_dict = {'name': 'John', 
           1: [2, 4, 3]}
print(my_dict)

# using dict()
my_dict = dict({1:'apple', 
                2:'ball'})
print(my_dict)

# from sequence having each item as a pair
my_dict = dict([(1,'apple'), (2,'ball')])
print(my_dict)
```


```python
dic = {1:2, 3:4}
type(dic.get(2))
```




    NoneType




```python
# Both are same 
d['a']
d.get('a', -1) # return 10
d.get('d', -1) # return -1 since 'd' is not in the dictionary

dic = {1:2}
dic[0] #keyerror
type(dic.get(0)) #None

counts = {'chuck' : 1 , 
          'annie' : 42, 
          'jan': 100}

x = counts.pop('jan')
counts['ss'] = x

counts.popitem() #return arbitraty key, value pair
        
print(counts)

# create a dictionary
squares = {1:1, 
           2:4, 
           3:9, 
           4:16, 
           5:25}  

# remove a particular item
print(squares.pop(4)) # Output: 16

print(squares) # Output: {1: 1, 2: 4, 3: 9, 5: 25}

# remove an arbitrary item
# print(squares.popitem()) # Output: (1, 1)

print(squares) # Output: {2: 4, 3: 9, 5: 25}

# delete a particular item
del squares[5]  

print(squares) # Output: {2: 4, 3: 9}

# remove all items
squares.clear()

print(squares) # Output: {}

# delete the dictionary itself
del squares


b = squares.copy()
```


```python
dic = {'ivan': 3,
       'pepe': 5}
dic.popitem()
```




    ('pepe', 5)




```python
europe['italy'] = 'rome'
data = dict(zip(list_with_keys, list_with_values)
```


```python
marks = dict.fromkeys(['Math','English','Science']) # Output: {'English': 0, 'Math': 0, 'Science': 0}
marks = {}.fromkeys(['Math','English','Science'], 0)
print(marks) # Output: {'English': 0, 'Math': 0, 'Science': 0}

for item in marks.items():
    print(item)

sorted(marks) # Output: ['English', 'Math', 'Science']
```


```python
squares = {x: x*x for x in range(6)}

print(squares) # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```


```python
# Dictionary comprehensions
nums = [0, 1, 2, 3, 4]
even_num_to_square = {x: x ** 2 for x in nums if x % 2 == 0}
print(even_num_to_square)  # Prints "{0: 0, 2: 4, 4: 16}"
```


```python
# The setdefault() method returns the value of a key (if the key is in dictionary). If not, it inserts key with a value to the dictionary.
count.setdefault('jan', 2)

person = {'name': 'Phill', 'age': 22}

age = person.setdefault('age')
print('Age = ',age)

# key is not in the dictionary
salary = person.setdefault('salary')
print('salary = ',salary)

# key is not in the dictionary
# default_value is provided
age = person.setdefault('height', 5)
print('person = ',person)
print('age = ',age)
```


```python
d = {1:2,
     2:3}
d[1] = 4
d
```




    {1: 4, 2: 3}




```python
s = 'abc'
dic = {}
for c in s:
    if c not in dic:
        dic[c] = 1
    else:
        dic[c] += 1
```

### Itertools

http://www.wklken.me/posts/2013/08/20/python-extra-itertools.html#itertoolsgroupbyiterable-key  
https://docs.python.org/2/library/itertools.html  
https://pymotw.com/2/itertools/


```python
from itertools import groupby

for key, group in groupby([1,1,1,1,5,1,1,1,1,4]):
    print(key, list(group))
```

    1 [1, 1, 1, 1]
    5 [5]
    1 [1, 1, 1, 1]
    4 [4]



```python
from itertools import combinations

array = [1,2,3,4]

for n in combinations(array, 3):
    print(n)
```

    (1, 2, 3)
    (1, 2, 4)
    (1, 3, 4)
    (2, 3, 4)



```python

```

### Counter


```python
from collections import Counter
```


```python
dic = Counter('gallahad') 
dic
for key, value in dic.items():
    print(key, value)

dic2 = Counter('dahallag')
dic2
for key, value in dic2.items():
    print(key, value)
    
dic == dic2

dic.most_common(2)
```




    Counter({'g': 1, 'a': 3, 'l': 2, 'h': 1, 'd': 1})



    g 1
    a 3
    l 2
    h 1
    d 1





    Counter({'d': 1, 'a': 3, 'h': 1, 'l': 2, 'g': 1})



    d 1
    a 3
    h 1
    l 2
    g 1





    True






    [('a', 3), ('l', 2)]




```python
dic = Counter()
for word in ['red', 'blue', 'red', 'green', 'blue', 'blue']:
     dic[word] += 1
dic
```


```python
word = ['red', 'blue', 'red', 'green', 'blue', 'blue']
dic = Counter(word)
dic
```




    Counter({'red': 2, 'blue': 3, 'green': 1})




```python
c = Counter(a=4, b=2, c=0, d=-2)
c
```


```python
dic = defaultdict(int)
for word in ['red', 'blue', 'red', 'green', 'blue', 'blue']:
     dic[word] += 1
dic
```


```python
from collections import Counter
dic = Counter()
dic[1] += 1
dic[1] -= 1
1 in dic
dic[1]
```




    0




```python
dic = Counter('ibfdgaeadiaefgbhbdghhhbgdfgeiccbiehhfcggchgghadhdhagfbahhddgghbdehidbibaeaagaeeigffcebfbaieggabcfbiiedcabfihchdfabifahcbhagccbdfifhghcadfiadeeaheeddddiecaicbgigccageicehfdhdgafaddhffadigfhhcaedcedecafeacbdacgfgfeeibgaiffdehigebhhehiaahfidibccdcdagifgaihacihadecgifihbebffebdfbchbgigeccahgihbcbcaggebaaafgfedbfgagfediddghdgbgehhhifhgcedechahidcbchebheihaadbbbiaiccededchdagfhccfdefigfibifabeiaccghcegfbcghaefifbachebaacbhbfgfddeceababbacgffbagidebeadfihaefefegbghgddbbgddeehgfbhafbccidebgehifafgbghafacgfdccgifdcbbbidfifhdaibgigebigaedeaaiadegfefbhacgddhchgcbgcaeaieiegiffchbgbebgbehbbfcebciiagacaiechdigbgbghefcahgbhfibhedaeeiffebdiabcifgccdefabccdghehfibfiifdaicfedagahhdcbhbicdgibgcedieihcichadgchgbdcdagaihebbabhibcihicadgadfcihdheefbhffiageddhgahaidfdhhdbgciiaciegchiiebfbcbhaeagccfhbfhaddagnfieihghfbaggiffbbfbecgaiiidccdceadbbdfgigibgcgchafccdchgifdeieicbaididhfcfdedbhaadedfageigfdehgcdaecaebebebfcieaecfagfdieaefdiedbcadchabhebgehiidfcgahcdhcdhgchhiiheffiifeegcfdgbdeffhgeghdfhbfbifgidcafbfcd')

dic.values()
```




    dict_values([111, 111, 111, 111, 111, 111, 111, 111, 111, 1])



### defaultdict (list, set, int)


```python
strs = ["eat", "tea", "tan", "ate", "nat", "bat"]
dic = {}
for s in strs:
    tmp = ''.join(sorted(list(s)))
    if tmp not in dic:
        dic[tmp] = [s]
    else:
        dic[tmp].append(s)
dic
```


```python
from collections import defaultdict
strs = ["eat", "tea", "tan", "ate", "nat", "bat"]
dic = defaultdict(list)
for s in strs:
    tmp = ''.join(sorted(list(s)))
    dic[tmp].append(s)

dic
```


```python
from collections import defaultdict
s = [('yellow', 1), ('blue', 2), ('yellow', 3), ('blue', 4), ('red', 1)]
dic = defaultdict(list)
for k, v in s:
    dic[k].append(v)

sorted(dic.items())
# [('blue', [2, 4]), ('red', [1]), ('yellow', [1, 3])]
```


```python
s = [('yellow', 1), ('blue', 2), ('yellow', 3), ('blue', 4), ('red', 1)]
dic = {}
for k, v in s:
    if k not in dic:
        dic[k] = [v]
    else:
        dic[k].append(v)
dic
```


```python
from collections import defaultdict

default_factory = (lambda: list(range(0,5))
d = defaultdict(default_factory)
                   
```


      File "<ipython-input-13-3410aa943885>", line 4
        d = defaultdict(default_factory)
        ^
    SyntaxError: invalid syntax




```python
from collections import defaultdict
dic = defaultdict(list)
s = 'aabbb'
for c in s:
    dic[c].append(c)
    
for key, value in dic.items():
    print(key, value)
```

    a ['a', 'a']
    b ['b', 'b', 'b']



```python
import itertools

s = 'aabbb'

for k, g in itertools.groupby(s):
    print(k, list(g))
```

    a ['a', 'a']
    b ['b', 'b', 'b']


### Ordered Dictionary


```python
from collections import OrderedDict
dic = OrderedDict.fromkeys('abcde')
dic
```




    OrderedDict([('a', None), ('b', None), ('c', None), ('d', None), ('e', None)])




```python
#Move an existing key to either end of an ordered dictionary. 
#The item is moved to the right end if last is true (the default)(Queue) or to the beginning if last is false (Stack).
dic.move_to_end('b')
dic
```


```python
# The popitem() method for ordered dictionaries returns and removes a (key, value) pair. 
# The pairs are returned in LIFO order if last is true (Queue) or FIFO order if false (Stack). 
dic.popitem(last=False)
dic
```


```python
dic['c']
```


```python
# regular unsorted dictionary
d = {'banana': 3, 'apple': 4, 'pear': 1, 'orange': 2}

# dictionary sorted by key
OrderedDict(sorted(d.items(), key=lambda t: t[0]))
#OrderedDict([('apple', 4), ('banana', 3), ('orange', 2), ('pear', 1)])

# dictionary sorted by value
OrderedDict(sorted(d.items(), key=lambda t: t[1]))
# OrderedDict([('pear', 1), ('orange', 2), ('banana', 3), ('apple', 4)])
```


```python
dic = OrderedDict()
dic['a'] = 1
dic['c'] = 4
dic['b'] = 2
dic.popitem(last=False)
dic
```




    OrderedDict([('c', 4), ('b', 2)])



## Set
https://www.programiz.com/python-programming/set


```python
x = {[1,2]:2}
if (2,1) in x:
    print('yes') 
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-13-d6a0f11a0ea6> in <module>
    ----> 1 x = {[1,2]:2}
          2 if (2,1) in x:
          3     print('yes')


    TypeError: unhashable type: 'list'



```python
seen = {2}

x = set()
x.add((1,2))
x.add((1,2))
x
```




    {(1, 2)}




```python
from collections import Counter
dic = Counter()
dic[(1,2)] += 1

dic
```




    Counter({(1, 2): 1})




```python
tuple([1,1,2])
```




    (1, 1, 2)




```python
# set do not have duplicates
# Output: {1, 2, 3, 4}
x = {1,2,3,4,3,2}
x

# set cannot have mutable items
# here [3, 4] is a mutable list
# If you uncomment line #12,
# this will cause an error.
# TypeError: unhashable type: 'list'

#my_set = {1, 2, [3, 4]}

# we can make set from a list
# Output: {1, 2, 3}
y = set([1,2,3,2])
y

a = {1,3}
a

# add an element
# Output: {1, 2, 3}
a.add(2)
a

# add multiple elements
# Output: {1, 2, 3, 4}
a.update([2,3,4])
a

# add list and set
# Output: {1, 2, 3, 4, 5, 6, 8}
a.update([4,5], {1,6,8})
a

b = a.copy()
```


```python
visited = set()
visited.add((1,2))
visited
```




    {(1, 2)}




```python
dic = {}
dic[(1,2)] = 2
dic
```




    {(1, 2): 2}




```python
(1,2) + (2,3)
```




    (1, 2, 2, 3)



A particular item can be removed from set using methods, discard() and remove().

The only difference between the two is that, while using discard() if the item does not exist in the set, it remains unchanged. But remove() will raise an error in such condition.

Set being unordered, there is no way of determining which item will be popped. It is completely arbitrary.


```python
# initialize my_set
my_set = {1, 3, 4, 5, 6}
print(my_set)

my_set.discard(4)
print(my_set) # Output: {1, 3, 5, 6}

# discard an element not present in my_set
my_set.discard(2)
print(my_set) # Output: {1, 3, 5}

my_set.remove(6)
print(my_set) # Output: {1, 3, 5}

# remove an element not present in my_set
#my_set.remove(2) # Output: KeyError: 2

my_set.clear()
print(my_set) #Output: set()
```


```python
# Set Union
# initialize A and B
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}

# use | operator
# Output: {1, 2, 3, 4, 5, 6, 7, 8}
print(A | B)
```


```python
# Set Intersection
# initialize A and B
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}

# use & operator
# Output: {4, 5}
print(A & B)
```


```python
# Set Difference
# initialize A and B
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}

# use - operator on A
# Output: {1, 2, 3}
print(A - B)
```


```python
# Set Symmetric Difference
# initialize A and B
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}

# use ^ operator
# Output: {1, 2, 3, 6, 7, 8}
print(A ^ B)
```
