# Python知识点总结(默认使用python3.x)

## python基础知识
* python的输入输出
```
# 1.输入
>>> a = input()             #python2.x中input()或raw_input()，input()方法只能输入数字，raw_input()方法返回str类型数据
sssdd
>>> print(a, type(a))       #返回的一个str类型数据
sssdd <class 'str'>
# 2.输出
print('Hello World!')       #python2.x中print 'Hello World!'或print('Hello World!')
```
* python导入一个模块
```
from A import B
import xx
```

## python常见的数据结构：
* 数字(Number)、字符串(Str)、列表(List)、元组(Tuple)、字典(Dict)、集合(Set)等

## 数字
```
python3支持int、float、bool、complex类型。
python3没有python2中的long类型
>>> a, b, c, d = 2, 2.2, True, 4+3j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
```

## 字符串
```
# 1.字符串连接
>>> s1 = 'abc'
>>> s2 = 'def'
>>> s1 += s2
>>> s1
'abcdef'
# 2.查找字符
>>> sS = 'c'
>>> s1.index(sS)        #返回该字符的位置
2
# 3.字符串格式化
>>> '%s is %s years old!!' % ('lbw', 20)
'lbw is 20 years old!!'
# 4.字段宽度和精度
>>> from math import pi
>>> pi
3.141592653589793
>>> 'Pi: %10f' % pi
'Pi:   3.141593'
>>> 'Pi:%.2f' % pi
'Pi:3.14'
# 5.find方法可以在一个较长的字符串中查找子字符串。并返回子串所在位置的最左端索引。
>>> title = "monty python's Flying Circus"
>>> title.find('monty')
0
>>> title.find('python')
6
# 6.join方法是非常重要的字符串方法，它是split方法的逆方法，用来在队列中添加元素
>>> seq = [1,2,3,4,5]
>>> sep = '+'
>>> sep.join(seq)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: sequence item 0: expected str instance, int found
>>> seq = ['1','2','3','4','5']
>>> sep.join(seq)
'1+2+3+4+5'
>>> '/'.join(seq)
'1/2/3/4/5'
# 7.lower方法返回字符串的小写字母版
>>> 'Treandheim Heardeer Dance'.lower()
'treandheim heardeer dance'
# 8.replace方法返回某字符串的所有匹配项均被替换之后得到的字符串
>>> 'Treandheim Heardeer Dance'.replace('r','ss')
'Tsseandheim Heassdeess Dance'
# 9.split方法是join的逆方法，用来将字符串分割成序列
>>> '1+2+3+4+5'.split('+')
['1', '2', '3', '4', '5']
# 10.strip方法返回去除两侧空格的字符串
>>> '  insert into afds, dsf    '.strip()
'insert into afds, dsf'
```

## 列表
* 列表是可变类型的(mutable)----可以改变列表的内容
```
# 1.列表长度、最大值和最小值。使用内建函数len、max和min。
>>> alist = [1,2,3,4,5]
>>> len(alist)
5
>>> max(alist)
5
>>> min(alist)
1
# 2.元素赋值
>>> alist[1] = 1
>>> alist
[1, 1, 3, 4, 5]
# 3.删除元素
>>> del alist[1]
>>> alist
[1, 3, 4, 5]
# 4.索引
>>> alist[0]                    
1
>>> alist[-1]
5
# 5.切片
>>> alist[:3]                   
[1, 3, 4]
>>> alist[:]
[1, 3, 4, 5] 
>>> alist[0:4:2]            #步长为2
[1, 4]
>>> alist[4:] = [6,7,8]     #切片赋值
>>> alist
[1, 3, 4, 5, 6, 7, 8]
>>> alist[1:1] = [2]
>>> alist
[1, 2, 3, 4, 5, 6, 7, 8]
# 6.append方法用于在列表末尾追加新的对象
>>> alist.append(6)
>>> alist
[1, 2, 3, 4, 5, 6, 7, 8, 6]
# 7.count方法统计某个元素在列表中出现的次数
>>> alist.count(6)
2
>>> alist.count(3)
1
# 8.extend方法可以
>>> a = [2,2]
>>> alist.extend(a)
>>> alist
[1, 2, 3, 4, 5, 6, 7, 8, 6, 2, 2]
# 9.index方法用于从列表中找出某个值第一个匹配项的索引位置
>>> alist.index(6)
5
# 10.insert方法用于将对象插入到列表中
>>> alist.insert(3, 'four')
>>> alist
[1, 2, 3, 'four', 4, 5, 6, 7, 8, 6, 2, 2]
# 11.pop方法会移除列表中的一个元素(默认是最后一个)，并返回该元素的值
>>> alist.pop()
2
>>> alist.pop()
2
>>> alist
[1, 2, 3, 'four', 4, 5, 6, 7, 8, 6]
# 12.remove方法用于移除列表中某个值的第一个匹配项
>>> alist.remove(6)
>>> alist
[1, 2, 3, 'four', 4, 5, 7, 8, 6]
>>> alist.remove(8)
>>> alist
[1, 2, 3, 'four', 4, 5, 7, 6]
# 13.reverse方法将列表中的元素反向存放
>>> alist.reverse()
>>> alist
[6, 7, 5, 4, 'four', 3, 2, 1]
# 14.sort方法用于在原位置对列表进行排序
>>> alist.remove('four')                    #str和int之间不能排序，先移除'four'字符串
>>> alist.sort()
>>> alist
[1, 2, 3, 4, 5, 6, 7]
>>> x = ['aardvark', 'abalone', 'acme', 'add', 'aerate']
>>> x.sort()
>>> x
['aardvark', 'abalone', 'acme', 'add', 'aerate']
>>> x.sort(key=len)                         #sort方法有另外两个可选参数--key和reverse
>>> x
['add', 'acme', 'aerate', 'abalone', 'aardvark']
# 15.list()方法将其他数据类型转换成list类型
>>> a = list('12345')
>>> a
['1', '2', '3', '4', '5']
>>> type(a)
<class 'list'>
```

## 元组
* 元组是不可变类型的()
```
# 1.len()、max()、min()方法分别返回元组元素的个数，元组中元素最大值、最小值
>>> len(a)
3
>>> max(a)
3
>>> min(a)
1
# 2.count()方法查找元组中某元素出现的次数
>>> a.count(1)
1
# 3.index()方法查找元组中某元素第一个索引值
>>> a.index(3)
2
# 4.tuple()返回一个元组
>>> seq = ['a','b','c']
>>> seq[1]
'b'
>>> tuple(seq)
('a', 'b', 'c')
```

## 字典
* 字典是Python中唯一内建的映射类型。字典中的值并没有特殊的顺序，但是都存储在一个特定的键(Key)里。
键可以是数字、字符串甚至是元组。
* 创建和使用字典:
    - phonebook = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}
* 字典由多个键及与其对应的值构成的对组成。字典中的键是唯一的。
```
# 1.dict函数
>>> items = [('name', 'Gumby'), ('age', 42)]
>>> d = dict(items)
>>> d
{'name': 'Gumby', 'age': 42}
>>> d['name']
'Gumby'
# 2.返回字典键值对的数量
>>> len(d)
2
# 3.d[k]返回关联到键k上的值
>>> d['age']
42
# 4.d[k] = v将值v关联到键k上
>>> d['home'] = 'China'
>>> d
{'name': 'Gumby', 'age': 42, 'home': 'China'}
# 5.del d[k]删除键为k的项
>>> del d['home']
>>> d
{'name': 'Gumby', 'age': 42}
# 6.k in d检查字典中是否含有键为k的项
>>> 'name' in d
True
>>> 'aaa' in d
False
# 7.clear方法清除字典中所有的项。这是原地操作(类似于list.sort)
>>> d.clear()
>>> d
{}
# 8.copy方法返回一个具有相同键值对的新字典(这个方法实现的是浅复制)
>>> x = {'username': 'admin', 'machines': ['foo','bar','baz']}
>>> y = x.copy()
>>> y
{'username': 'admin', 'machines': ['foo', 'bar', 'baz']}
>>> x['username'] = 'root'
>>> x['machines'].remove('foo')
>>> x
{'username': 'root', 'machines': ['bar', 'baz']}
>>> y
{'username': 'admin', 'machines': ['bar', 'baz']}
# 3.fromkeys方法使用给定的键建立新的字典，每个键默认对应的值为None
>>> dict.fromkeys(a)
{1: None, 2: None, 3: None}
>>> dict.fromkeys(a, 'unknown')                 #指定默认值
{1: 'unknown', 2: 'unknown', 3: 'unknown'}
# 4.get方法是个更宽松的访问字典项的方法
>>> b = {1: 'unknown', 2: 'unknown', 3: 'unknown'}
>>> print(b.get(4))                             #get访问一个不存在的键时，没有任何异常，得到了None值。
None
>>> print(b.get(3))
unknown
# 5.has_key方法可以检查字典中是否含有给出的键。表达式d.has_key(k)相当于表达式k in d。python3.x没有这个函数
# 6.items方法返回一个迭代器对象。python2.x中items方法将所有的字典项以列表方式返回，iteritems方法相当于python3.x中的items方法
>>> d = {'title': 'Python Web Site', 'url': 'http://www.python.org', 'spam': 0}
>>> d.items()
dict_items([('spam', 0), ('title', 'Python Web Site'), ('url', 'http://www.python.org')])
# 7.keys方法将字典中的键以列表形式返回
>>> d.keys()
dict_keys(['spam', 'title', 'url'])
# 8.pop方法用来获得对应于给定键的值，然后将这个键值对从字典中删除
>>> d
{'spam': 0, 'title': 'Python Web Site', 'url': 'http://www.python.org'}
>>> d.pop('spam')
0
>>> d
{'title': 'Python Web Site', 'url': 'http://www.python.org'}
# 9.popitem方法类似于list.pop，不过popitem弹出随机的项，list.pop弹出列表最后一个元素。
>>> d.popitem()
('title', 'Python Web Site')
# 10.setdefault方法在某种程度上类似于get方法，就是能够获得与给定键相关联的值，除此之外，还能在字典
# 中不含有给定键的情况下设定相应的键值。
>>> d.setdefault('url')
'http://www.python.org'
>>> d.setdefault('name','N/A')
'N/A'
>>> d
{'name': 'N/A', 'url': 'http://www.python.org'}
# 11.update方法可以利用一个字典项更新另外一个字典
>>> d = {'title': ' Python Web Site', 'url': 'http://www.python.org', 'changed': 'Mar 22:02:21 2017'}
>>> x = {'title': 'Python Language Website'}
>>> d.update(x)
>>> d
{'changed': 'Mar 22:02:21 2017', 'title': 'Python Language Website', 'url': 'http://www.python.org'}
# 12.values方法以列表的形式返回值的迭代器。python2.x中values方法返回字典中的值，itervalues方法相当于python3.x中values方法。
>>> d.values()
dict_values(['Mar 22:02:21 2017', 'Python Language Website', 'http://www.python.org'])
```

## 集合
```
# 集合set是Python中一种基本数据类型，它分为可变集合(set)和不可变集合(frozenset)两种。类似于其他语言，集合是一个无序不
# 重复元素集，包括集合set、向集合中添加元素、删除集合中的元素、求集合的交集、并集、差集等操作。
# 1.set创建集合。set集合类需要的参数必须是迭代器类型的。如：序列、字典等，然后转换成无序不重复的元素集。
>>> ss = set([])                    #创建空集合
>>> ss
set()
>>> st = set(())
>>> st
set()
>>> s = set('createSet')            #创建非空集合
>>> s
{'c', 'a', 't', 'S', 'e', 'r'}
>>> s1 = set([1,2,3,4,5,6,7])
>>> s1
{1, 2, 3, 4, 5, 6, 7}
# 2.集合添加
>>> s1.add('f')                     #add方法把要传入的元素作为一个整体添加到集合中
>>> s1
{1, 2, 3, 4, 5, 6, 7, 'f'}
>>> s1.update('8910')               #update把要传入的元素拆分成单个字符，存入集合中，并去掉重复的字符
>>> s1
{1, 2, 3, 4, 5, 6, 7, '8', '9', '0', 'f', '1'}
# 3.集合删除
>>> s1.remove(4)
>>> s1
{1, 2, 3, 5, 6, 7, '8', '9', '0', 'f', '1'}
# 4.集合的遍历
>>> for i in s1:                    #集合的遍历跟序列的遍历方法完全一样
...     print(i, end=' ')
... 
1 2 3 5 6 7 8 9 0 f 1
# 5.pop()方法删除并返回一个元素
>>> s1.pop()
1
>>> s1
{2, 3, 5, 6, 7, '8', '9', '0', 'f', '1'}
>>> s1.pop()
2
>>> s1
{3, 5, 6, 7, '8', '9', '0', 'f', '1'}
>>> s1.pop()
3
# 6.交集
>>> st1 = set('python')
>>> st2 = set('php')
>>> st1 & st2
{'p', 'h'}
# 7.并集
>>> st3 = set('html')
>>> st1 | st3
{'m', 'h', 't', 'y', 'l', 'o', 'n', 'p'}
# 8.差集
>>> st1 - st2
{'o', 't', 'y', 'n'}
>>> st1 - st3
{'o', 'n', 'y', 'p'}
```

## range()和xrange()
* python3.x：range()函数与python2.x中的xrange()一样，返回的是一个生成器。
* python2.x：range()生成一个列表，xrange()返回一个生成器，用法和range()一样。
```
>>> range(2,10)
range(2, 10)
>>> type(_)
<class 'range'>
>>> list(range(2,10,2))
[2, 4, 6, 8]
>>> for i in range(0,10,2):
...     print(i, end=' ')
... 
0 2 4 6 8 
```

## 条件、循环和其他语句
* 略。。。和其他语言没有太大差异

## python内置函数
* abs()函数获取绝对值
```
>>> abs(-10)
10
>>> a = -10
>>> a.__abs__()
10
```
* bin(),oct(),hex()三个函数将十进制分别转换为2/8/16进制
* bool()函数测试一个对象是True还是False
```
>>> bool(1)
True
>>> bool(1 == 2)
False
```
* bytes()函数将一个字符串转换成字节类型
```
>>> s = 'python'
>>> x = bytes(s, encoding='utf8')
>>> x
b'python'
>>> a = '湖北'
>>> y = bytes(a, encoding='utf8')
>>> y
b'\xe6\xb9\x96\xe5\x8c\x97'
```
* str()函数将字符类型/数值类型等转换为字符串类型
```
>>> str(b'\xe6\xb9\x96\xe5\x8c\x97', encoding='utf8')
'湖北'
>>> str(222)
'222'
```
* callables()函数判断对象是否可以被调用，能被调用的对象就是一个callables对象。
```
>>> callable([1,2,3])
False
>>> callable(abs)
True
>>> callable(max)
True
>>> callable(str)
True
>>> callable('str')
False
```
* chr(),ord()函数查看十进制数对应的ASCII字符和查看某个ASCII对应的十进制数
```
>>> chr(66)
'B'
>>> ord('B')
66
```
* complex()复数函数
* delattr()删除对象的熟悉
* eval()将一串基本数据类型的字符串，转化成基本数据类型
```
>>> alist = "[1,2,3,4]"
>>> l = eval(alist)
>>> l
[1, 2, 3, 4]
```
* dir()查看某个类型下的所有方法
```
>>> l = [1,2,3]
>>> dir(l)
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__',
 '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__',
  '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', 
  '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', 
  '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop',
   'remove', 'reverse', 'sort']
```
* divmod()获取两个数相除后的商和余数
```
>>> divmod(5,2)
(2, 1)
```
* max(),min(),sum()分别获取某个可迭代对象的最大值，最小值，和。
* pow(a,b)获取a的b次方
```
>>> pow(3,3)
27
```
* type()查看数据类型
```
>>> type('aaa')
<class 'str'>
>>> type([1,1,1])
<class 'list'>
>>> type({1:2})
<class 'dict'>
```
* filter()将一个可迭代对象按某种特定方式过滤，生成一个新的可迭代对象
```
>>> for i in f:
...     print(i, end=',')
... 
6,7,8,9,
```
* sorted()将一个可迭代序列排序，与list.sort不同的是，sorted()将返回一个排序后的副本，而不是原地排序。
```
>>> a = [4,2,6,1,3]
>>> sorted(a)
[1, 2, 3, 4, 6]
>>> a
[4, 2, 6, 1, 3]
```
* zip()将两个或多个列表拼接成一个元组列表
```
>>> list1 = [1,2,3,4]
>>> list2 = ['a','b','c','d']
>>> z = zip(list1, list2)
>>> z
<zip object at 0x102975a88>
>>> for i in z:
...     print(i)
... 
(1, 'a')
(2, 'b')
(3, 'c')
(4, 'd')
```
* map()函数包含两个参数，第一个是一个函数，第二个是序列。
```
def f(x):
    return x * x

print(map(f, [1,2,3,4,5,6,7,8,9]))
输出结果：<map object at 0x1005a1a20>        
python2.x中输出结果：[1, 4, 9, 10, 25, 36, 49, 64, 81]
```


## 正则表达式
* 正则表达式为高级的文本模式匹配、抽取、或文本形式的搜索和替换功能提供基础。简单的说，正则表达式(regex)是一些由字符和特殊符号
组成的字符串，它们描述了模式的重复或者表述多个字符，于是正则表达式能按照某种模式匹配系列有相似特征的字符串。
* python通过标准库中的re模块来支持正则表达式。
### 特殊符号和字符
* 使用择一匹配符配多个正则表达式模式
   - 表示择一匹配的管道符号(|)，表示一个'从多个模式中选择其一'的操作。它用于分割不同的正则表达式。
   ```
   正则表达式模式              匹配的字符串
   at | home                 at、home
   r2de | c3po               r2d2、c3po
   bat | bet | bit           bat、bet、bit   
   ```
* 匹配任意单个字符
   - 点号或者句点(.)符号匹配除了换行符\n以外的任何字符()。
   ```
   正则表达式模式              匹配的字符串
   f.o                       匹配在字母"f"和"o"之间的任意一个字符：例如fao、fco、foo、f#o等 
   ..                        任意两个字符
   ```
* 从字符串起始或结尾或单词边界匹配
   - 有些符号和相关的特殊字符用于在字符串的起始和结尾部分指定用于搜索的模式。
   ```
   正则表达式模式              匹配的字符串
   ^From                     任何以From开头的字符串
   /bin/tcsh$                任何以/bin/tcsh结尾的字符串
   ^Subject:hi$              任何由单独的字符串Subject:hi构成的字符串
   ```
* 创建字符集
   - 匹配方括号中包含的任何字符。
   ```
   正则表达式模式              匹配的字符串
   b[aeiu]t                  bat、bet、bit、but
   [cr][23]                  c2、c3、r2、r3   
   ```
* 限定范围和否定
   - 方括号中两个符号之间用连字符(-)连接，用于指定一个字符的范围。
   ```
   正则表达式模式              匹配的字符串
   z.[0-9]                   字母'z'后面跟着任何一个字符，然后跟着一个数字
   [a-z]                     一个小写字母  
   ```
* 实现存在性和频数匹配
   - '+'操作符将匹配一次或者多次出现的正则表达式
   - '?'操作符将匹配零次或者一次出现的正则表达式
   - '*'操作符将匹配其左边正则表达式出现零次或者多次的情况
* 表示字符集的特殊字符
   - 使用\d表示匹配任何的十进制数字相当于[0-9]；使用\w能够用于表示全部字母数字的字符集，相当于[A-Za-z0-9]。
* 使用圆括号指定分组
   - (\w+)-(\d+)
### re模块：核心函数和方法
* 匹配对象以及group()和groups()方法
    - group()要么返回整个匹配对象，要么根据要求返回特定子组。groups()则仅返回一个包含唯一或者全部子组的元组。    
* 使用match()方法匹配字符串
```
# match()函数试图从字符串的起始部分对模式进行匹配。如果匹配成功，就返回一个匹配对象。匹配失败则返回None。匹配对象的
# group()方法能够用于显示那个成功的匹配。
>>> import re
>>> m = re.match('foo', 'foo')
>>> if m is not None:
...     m.group()
... 
'foo'
>>> m
<_sre.SRE_Match object; span=(0, 3), match='foo'>
>>> m = re.match('foo', 'far')                      #如果匹配失败，则返回None
>>> if m is not None:
...     m.group()
... 
>>> m = re.match('foo', 'food on the table')        #匹配成功。只要模式从字符串的起始部分开始匹配，即使字符串比模式
                                                    #长，匹配也仍然能够成功
>>> m.group()
'foo'
```
* 使用search()在一个字符串中查找模式(搜索与匹配的对象)。search()会用它的字符串参数，在任意位置对给定正则表达式模式搜索
第一次出现的匹配情况。
```
>>> m = re.match('foo', 'seafoo')                   #如果使用match()方法，它会从字符串起始位置开始匹配模式，即'f'
>>> if m is not None: m.group()                     #将匹配到字符串的首字母's'上，故匹配失败
... 
>>> m = re.search('foo', 'seafoo')                  #search()函数不但会搜索模式在字符串中第一次出现的位置，而且会
>>> if m is not None: m.group()                     #严格地对字符串从左到右搜索。故匹配成功
... 
'foo'
```
* 匹配多个字符串
```
>>> bt = 'bat|bet|bit'                              #正则表达式模式：bat、bet、bit
>>> m = re.match(bt, 'bat')                         #'bat'是一个匹配
>>> if m is not None: m.group()
... 
'bat'
>>> m = re.match(bt, 'blt')                         #'blt'没有匹配成功
>>> if m is not None: m.group()
... 
>>> m = re.match(bt, 'He bit me!')                  #不能匹配字符串
>>> if m is not None: m.group()
... 
>>> m = re.search(bt, 'He bit me!')                 #通过搜索查找'bit'
>>> if m is not None: m.group()
... 
'bit'
```
* 匹配任何单个字符
```
>>> anyend = '.end'
>>> m = re.match(anyend, 'bend')                    #点号匹配'b'
>>> if m is not None: m.group()
... 
'bend'
>>> m = re.match(anyend, '\nend')                   #除了\n之外的任何字符
>>> if m is not None: m.group()
... 
>>> m = re.search(anyend, 'The end')                #在搜索中匹配' '
>>> if m is not None: m.group()
... 
' end'
```
* 创建字符集
```
>>> m = re.match('[cr][23][dp][o2]', 'c3po')        #匹配'c3po'
>>> if m is not None: m.group()
... 
'c3po'
>>> m = re.match('[cr][23][dp][o2]', 'c2do')        #匹配'c2do'
>>> if m is not None: m.group()
... 
'c2do'
>>> m = re.match('[cr][23][dp][o2]', 'ccdo')        #不匹配'ccdo'
>>> if m is not None: m.group()
... 
```
* 重复、特殊字符以及分组
```
>>> patt = '\w+@(\w+\.)?\w+\.com'                   #'(\w+\.)?\w+'匹配主机名,包含0个或1个子域名
>>> re.match(patt, 'nobody@xxx.com').group()
'nobody@xxx.com'
>>> re.match(patt, 'nobody@xxx.yyy.com').group()
'nobody@xxx.yyy.com'
>>> patt = '\w+@(\w+\.)*\w+\.com'
>>> re.match(patt, 'nobody@xx.yy.zz.aa.com').group()    #允许任意数量的中间子域名存在
'nobody@xx.yy.zz.aa.com'
>>> m = re.match('(\w\w\w)-(\d\d\d)', 'abc-123')        #匹配分组
>>> m.group()                                           #完整匹配
'abc-123'
>>> m.group(1)                                          #子组1
'abc'
>>> m.group(2)                                          #子组2
'123'
>>> m.groups()                                          #全部子组
('abc', '123')
```
* 使用findall()和finditer()查找每一次出现的位置
    - findall()查询字符串中某个正则表达式模式全部的非重复出现情况。总是返回一个列表，如果匹配失败则返回空列表。
    ```
    >>> re.findall('car','car')
    ['car']
    >>> re.findall('car','scary')
    ['car']
    >>> re.findall('car','carry my team the barcardi to the car')
    ['car', 'car', 'car']
    ```
    - finditer()函数完成的所有额外工作都旨在获取它的输出来匹配findall()的输出。
* 使用sub()和subn()搜索与替换
    - subn()和sub()都是将某字符串中所有匹配正则表达式的部分进行某种形式的替换。subn()和sub()一样，但subn()
    还返回一个表示替换的总数，与替换后的字符串作为元组返回。
    ```
    >>> re.sub('X', 'liuhui', 'My name is X,X niubi!')
    'My name is liuhui,liuhui niubi!'
    >>> re.sub('[ae]', 'XX', 'abcedfg')
    'XXbcXXdfg'
    >>> re.subn('[ae]', 'XX', 'abcedfg')
    ('XXbcXXdfg', 2)
    ```
* 在限定模式上使用split()分隔字符串
    - 如果给定分隔符不是使用特殊符号来匹配多重模式的正则表达式，那么re.split()与str.split()工作方式相同。
    ```
    >>> re.split(':', 'str1:str2:str3')
    ['str1', 'str2', 'str3']
    ```
    - 更复杂的处理
    ```
    >>> DATA = (
    ...     'Mountain View, CA 94040',
    ...     'Sunnyvale, CA',
    ...     'Los Altos, 94023',
    ...     'Cupertino 95014',
    ...     'Palo Alto CA',
    ... )
    >>> for datum in DATA:
    ...     print(re.split(', |(?= (?:\d{5}|[A-Z]{2})) ', datum))
    ... 
    ['Mountain View', 'CA', '94040']
    ['Sunnyvale', 'CA']
    ['Los Altos', '94023']
    ['Cupertino', '95014']
    ['Palo Alto', 'CA']
    ```
* 正则表达式应用示例
```
#创建编写rewho.py程序
import re

f = open('whodata.txt', 'r')
for eachLine in f:
    print(re.split(r'\s\s+', eachLine))
f.close()

#将who命令结果输出到whodata.txt文件中
$ who > whodata.txt
$ python rewho.py                           #执行rewho.py
['liuhui', 'console', 'Dec 12 17:33']
['liuhui', 'ttys000', 'Dec 14 19:45']
['liuhui', 'ttys002', 'Dec 18 15:46']

#创建编写rewho2.py。在不手动创建whodata.txt文件情况下，使用os.popen方法获取命令结果。
import os
import re

with os.popen('who', 'r') as f:
    for eachLine in f:
        print(re.split(r'\s\s+|\t', eachLine.strip()))

$ python rewho2.py 
['liuhui', 'console', 'Dec 12 17:33']
['liuhui', 'ttys000', 'Dec 14 19:45']
['liuhui', 'ttys002', 'Dec 18 15:46']
```


## 网络编程
### 套接字(Socket)
* 套接字地址：主机-端口号
* 面向连接的套接字：面向连接的通信提供序列化的、可靠的和不重复的数据交付，而没有记录边界。
* 无连接的套接字


## python监控Linux系统
### 多功能系统资源统计工具dstat
* dstat是一个用Python语言实现的多功能系统资源统计工具，用来取代Linux下的vmstat、iostat、netstat和ifstat等命令。
* dstat功能特性：
    - 综合了vmstat、iostat、ifstat、netstat等监控工具的功能，并且提供了更多的监控信息；
    - 实时显示监控数据；
    - 在问题分析和故障排查时，可以监视最重要的计数器，也可以对计数器进行排序；
    - 模块化设计；
    - 使用Python语言编写，更方便扩展现有的工作任务；
    - 容易扩展，便于添加自定义的计数器；
    - 包含许多扩展插件；
    - 可以分组统计块设备/网络设备，并给出汇总信息；
    - 可以显示每台设备中断信息；
    - 非常准确的时间精度，即便是系统负荷较高也不会延迟显示；
    - 准确显示单位，限制转换误差范围；
    - 用不同的颜色显示不同的单位，增加可读性；
    - 支持CSV格式输出，便于将监控信息导入Gnumeric和Excel以生成图形。
* 安装使用dstat（这里使用Centos7）
```angular2html
$ yum install dstat
dstat --version         # 除了显示dstat的版本之外，还会显示操作系统的版本、Python语言的版本、cpu的个数，
                        # 以及dstat支持的插件列表等详细信息。
Dstat 0.7.2
...

Platform posix/linux2
Kernel 3.10.0-514.21.1.el7.x86_64
Python 2.7.5 (default, Nov  6 2016, 00:28:07) 
[GCC 4.8.5 20150623 (Red Hat 4.8.5-11)]

Terminal type: xterm-256color (color support)
Terminal size: 24 lines, 80 columns
...

$ dstat --list            # 使用dstat命令的 --list选项获取dstat的插件列表
internal:
	aio, cpu, cpu24, disk, disk24, disk24old, epoch, fs, int, int24, io, 
	ipc, load, lock, mem, net, page, page24, proc, raw, socket, swap, 
	swapold, sys, tcp, time, udp, unix, vm
/usr/share/dstat:
	battery, battery-remain, cpufreq, dbus, disk-tps, disk-util, dstat, 
	dstat-cpu, dstat-ctxt, dstat-mem, fan, freespace, gpfs, gpfs-ops, 
	...
	
# 直接在终端输入dstat命令，dstat将以默认参数运行。默认情况下，dstat会收集cpu、磁盘、网络、
# 换页和系统信息，并以一秒钟一次的频率进行输出，直到我们按ctrl+c结束。
            
```
* dstat常用选项
    - -c：显示cpu的使用情况。显示了cpu时间花费在各类操作的百分比，包括执行用户代码(usr)、执行系统代码(sys)、空闲(idl)和
    等待IO(wai)。如果usr的值较高，说明当前系统钟cpu负载较大；如果wai长期处于较大值，说明IO等待比较严重；
    - -d：显示磁盘的读写情况，在进行性能测试时可以使用该字段观察当前的磁盘负载；
    - -n：网络设备发送和接收的数据，这一栏显示网络收发数据的总数；
    - -g：表示换页活动；
    - -y：系统统计。这一项显示的是中断(int)和上下文切换(csw)；
    - -t：显示统计系统的当前时间；
    - -l、--load：统计系统负载情况，包括1分钟、5分钟、15分钟平均值；
    - -p、--proc：统计进程信息，包括runnable、blocked和new的进程数量；
    - --tcp：显示常用的TCP统计；
    - --fs：统计文件打开数和inodes数。
    ```angular2html
    $ dstat -tlp --tcp --fs
    ----system---- ---load-avg--- ---procs--- ----tcp-sockets---- --filesystem-
     time     | 1m   5m  15m |run blk new|lis act syn tim clo|files  inodes
    16-01 00:15:07|   0 0.01 0.05|0.0   0 0.8|  8   1   0   0   0| 1216  12282 
    16-01 00:15:08|   0 0.01 0.05|  0   0   0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:09|   0 0.01 0.05|  0   0 1.0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:10|   0 0.01 0.05|  0   0   0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:11|   0 0.01 0.05|  0   0   0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:12|   0 0.01 0.05|  0   0   0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:13|   0 0.01 0.05|  0   0   0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:14|   0 0.01 0.05|  0   0 1.0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:15|   0 0.01 0.05|  0   0 1.0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:16|   0 0.01 0.05|  0   0   0|  8   1   0   0   0| 1216  12282 
    16-01 00:15:17|   0 0.01 0.05|  0   0 1.0|  8   1   0   0   0| 1216  12282
    ...
    # dstat还可以像vmstat和iostat一样使用参数控制报告的时间间隔，或者同时指定时间间隔与报告次数。
    $ dstat 2 10              # 以默认选项运行dstat，每两秒输出一条监控信息，并在输出10条监控信息后自动退出dstat
    You did not select any stats, using -cdngy by default.
    ----total-cpu-usage---- -dsk/total- -net/total- ---paging-- ---system--
    usr sys idl wai hiq siq| read  writ| recv  send|  in   out | int   csw 
      0   0  99   0   0   0| 393B   15k|   0     0 |   0     0 |  49    94 
      0   0 100   0   0   0|   0    96k| 539B 1276B|   0     0 |  72    93 
      1   0 100   0   0   0|   0     0 | 594B 1002B|   0     0 |  56   100 
      0   1  99   0   0   0|   0     0 | 539B  999B|   0     0 |  65   120 
      0   0  99   0   0   0|   0    16k| 176B  434B|   0     0 |  44    78 
      0   0 100   0   0   0|   0     0 | 539B 1140B|   0     0 |  58   108 
      1   0 100   0   0   0|   0     0 | 901B 1492B|   0     0 |  66   129 
      0   0  99   0   0   0|   0    40k| 901B 1909B|   0     0 |  81   136 
      0   0 100   0   0   0|   0     0 | 539B  952B|   0     0 |  57   115 
      0   0 100   0   0   0|   0     0 | 176B  430B|   0     0 |  43    76 
      1   0  98   2   0   0|   0    18k| 176B  452B|   0     0 |  44    71 
    ```
* dstat高级用法
    - dstat的强大之处不仅仅是因为它聚合了多种工具的监控结果，还因为它能通过附带的插件实现一些高级功能，如找出占用资源最高的进程和
    用户。dstat的--top-(io|bio|cpu|cputime|cputime-avg|mem)这几个选项可以看到是哪个用户和哪个进程占用了相关系统资源，对系统
    调优非常有效。如查看当前占用I/O、cpu、内存等最高的进程信息可以使用--top-mem --top-io --top-cpu选项。
    ```angular2html
    $ dstat --top-io                  # 占用io最多的进程
    ----most-expensive----
       i/o process      
    systemd      10k 1370B
    sshd: root@ 146B  180B
    barad_agent 823B  991B
    sshd: root@  78B  116B
    barad_agent1450B 1032B
    sshd: root@  78B  116B
    sshd: root@  78B  116B
    ...
    $ dstat --top-mem --top-io --top-cpu 2 5          # 多个选项连用
    --most-expensive- ----most-expensive---- -most-expensive-
      memory process |     i/o process      |  cpu process   
    uwsgi       49.0M|systemd      10k 1370B|barad_agent  0.0
    uwsgi       49.0M|barad_agent1818B  516B|                
    uwsgi       49.0M|barad_agent 412B  488B|                
    uwsgi       49.0M|barad_agent 725B  470B|barad_agent  1.0
    uwsgi       49.0M|sshd: root@ 153B  192B|                
    uwsgi       49.0M|sshd: root@ 149B  188B|
    $ dstat --top-cpu --top-mem --top-io --output dstat_output.csv        # 将监控信息保存到csv文件中
    $ cat dstat_output.csv 
    "Dstat 0.7.2 CSV output"
    "Author:","Dag Wieers dag@wieers.com>",,,,"URL:","http://dag.wieers.com/home-made/dstat/"
    "Host:","VM_19_199_redhat",,,,"User:","root"
    "Cmdline:","dstat --top-cpu --top-mem --top-io --output dstat_output.csv",,,,"Date:","16 Jan 2018 00:46:41 CST"

    "most expensive","most expensive","most expensive"
    "cpu process","memory process","i/o process"
    barad_agent / 0%,uwsgi / 51769344%,systemd / 10082:1369
    barad_agent / 1%,uwsgi / 51769344%,barad_agent / 2582:5688
    sgagent / 0%,uwsgi / 51769344%,barad_agent / 22:449
    barad_agent / 1%,uwsgi / 51769344%,barad_agent / 0:942
    sgagent / 0%,uwsgi / 51769344%,barad_agent / 3635:1032
    barad_agent / 1%,uwsgi / 51769344%,barad_agent / 143033:2248
    sgagent / 0%,uwsgi / 51769344%,barad_agent / 823:976
    ```

### 使用Python打造自己的监控工具
* Linux系统的/proc目录介绍，/proc是一个位于内存中的伪文件系统。该目录下保存的不是真正的文件和目录，而是一些'运行时'的信息，如
系统内存、磁盘io、设备挂载信息和硬件配置信息等。/proc也是内核提供给我们的查询中心，用户可以通过这些文件查看有关系统硬件及当前
正在运行进程的信息。在Linux系统中，许多工具的数据来源正是proc目录中的内容，例如，lsmod命令是cat /proc/modules命令的别名，
lspci命令是cat /proc/pci命令的别名。
* proc目录被称作虚拟文件系统。
```angular2html
$ ll /proc
...
dr-xr-xr-x  9 root           root                         0 Dec  9 14:59 7
dr-xr-xr-x  9 root           root                         0 Dec  9 14:59 8
dr-xr-xr-x  9 rpc            rpc                          0 Dec  9 15:55 8134
dr-xr-xr-x  9 root           root                         0 Dec  9 14:59 9
dr-xr-xr-x  9 root           root                         0 Dec  9 14:59 96
dr-xr-xr-x  2 root           root                         0 Jan 16 00:52 acpi
-r--r--r--  1 root           root                         0 Jan 16 00:52 buddyinfo
dr-xr-xr-x  4 root           root                         0 Jan 16 00:52 bus
-r--r--r--  1 root           root                         0 Jan 16 00:52 cgroups
-r--r--r--  1 root           root                         0 Jan 16 00:52 cmdline
-r--r--r--  1 root           root                         0 Jan 16 00:52 consoles
-r--r--r--  1 root           root                         0 Jan 16 00:52 cpuinfo
-r--r--r--  1 root           root                         0 Jan 16 00:52 crypto
-r--r--r--  1 root           root                         0 Jan 16 00:52 devices
-r--r--r--  1 root           root                         0 Jan 16 00:52 diskstats
-r--r--r--  1 root           root                         0 Jan 16 00:52 dma
... 
```
* proc目录下常用文件介绍，在编写Linux的监控系统时，最基本的监控包括cpu、内存、磁盘和网络等信息，可以从下面几个文件中获取：
    - /proc/loadavg：保存了系统负载的平均值，其前三列分别表示最近1分钟、5分钟、15分钟的平均负载。反应系统的繁忙情况；
    - /proc/meminfo：一般由free命令统计当前内存使用信息，可以使用文件查看命令直接读取此文件；
    - /proc/diskstats：磁盘设备的磁盘I/O统计信息列表；
    - /proc/cmdline：启动时传递给kernel的参数信息；
    - /proc/filesystems：内核当前支持的文件系统类型；
    - /proc/net/dev：网络流入流出的统计信息，包括接收包的数量、发送包的数量，发送数据包时的错误和冲突情况等；
    - /proc/cpuinfo：查看cpu的详细信息；
    - /proc/devices：系统已经加载的所有块设备和字符设备的信息；
    - /proc/mounts：系统中当前挂载的所有文件系统；
    - /proc/uptime：系统上次启动以来的运行时间；
    - /proc/version：当前系统运行的内核版本号；
    - /proc/vmstat：当前系统虚拟内存的统计数据；
* 使用shell脚本监控Linux
```
$ vim monitor.sh
cpu_idle=$(top -n2 | grep 'Cpu' | tail -n 1 | awk '{ print $8 }')
cpu_usage=$(echo "100 - $cpu_idle" | bc)

mem_free=$(free -m | awk '/Mem:/{ print $4 + $6 + $7 }')
mem_total=$(free -m | awk '/Mem:/{ print $2 }')
mem_used=$(echo "$mem_total - $mem_free" | bc)
mem_rate=$(echo "$mem_used * 100 / $mem_total" | bc)

disk_usage=$(df -h / | tail -n 1 | awk '{ print $5 }')
disk_used=$(df -h / | tail -n 1 | awk '{ print $3 }')  

echo "cpu利用率：$cpu_usage %"
echo "内存使用量：$mem_used M"
echo "内存利用率：$mem_rate %"
echo "磁盘空间使用量：$disk_used"
echo "磁盘空间利用率：$disk_usage"

$ bash monitor.sh
cpu利用率：.3 %
内存使用量：-459 M
内存利用率：-46 %
磁盘空间使用量：7.0G
磁盘空间利用率：15%
```
* 使用Python监控Linux
    - 在Python语言中，对于cpu利用率、内存利用率、磁盘使用量等监控项，可以参考shell脚本中获取监控的方式实现。
    - 磁盘的详细监控信息位于/proc/diskstats文件中。获取监控信息的难点在于该文件具有较多的字段，每个字段具有不同的含义。在Python语言中，
    可以定义一个类来表示磁盘的监控项。这里我们可以使用命名元组(namedtuple)。/proc/diskstats文件的每一行都保存了一块磁盘的io统计信息，
    并且在/proc/diskstats文件中，每一行都有相同个数的字段，字段的个数和顺序也非常明确。因此我们可以考虑使用namedtuple来保存diskstats
    文件中的字段，在读取时，可以使用更加具有可读性的名称来引用diskstats文件中的字段。
    ```angular2html
    $ vim diskstats.py
    #!/usr/bin/python
    # -*- coding:utf-8 -*-
    from __future__ import print_function
    from collections import namedtuple

    Disk = namedtuple('Disk', 'major_number minor_number device_name'
	    		' read_count read_merged_count read_sections'
		    	' time_spent_reading write_count write_merged_count'
			    ' write_sections time_spent_write io_requests'
			    ' time_spent_doing_io weighted_time_spent_doing_io')

    def get_disk_info(device):
        """
        从/proc/diskstats中读取磁盘的IO信息
        $ cat /proc/diskstats
        253       0 vda 98877 206 2588650 2158459 7278514 4373679 98199576 181448662 0 9450886 183606505
        253       1 vda1 98786 206 2587058 2158317 7265510 4373679 98199576 181423679 0 9427899 183581400
        """
        with open("/proc/diskstats") as f:
	        for line in f:
	            if line.split()[2] == device:
		            return Disk(*(line.split()))
        raise RuntimeError("device {{0}} not found !".format(device))


    def main():
        disk_info = get_disk_info('vda')
        print(disk_info)
    
        print("磁盘写次数：{0}".format(disk_info.write_count))
        print("磁盘写字节数：{0}".format(long(disk_info.write_sections) * 512))
        print("磁盘写延时：{0}".format(disk_info.time_spent_write))


    if __name__ == '__main__':
        main()
      
    $ python diskstats.py
    Disk(major_number='253', minor_number='0', device_name='vda', read_count='102905', read_merged_count='213', 
    read_sections='2747130', time_spent_reading='2260147', write_count='7284766', write_merged_count='4415573',
    write_sections='98603312', time_spent_write='185154980', io_requests='0', time_spent_doing_io='9509921', 
    weighted_time_spent_doing_io='187414508')
    磁盘写次数：7284766
    磁盘写字节数：50484895744
    磁盘写延时：185154980
    ```

### 开源库监控Linux(psutil)
* psutil是一个开源且跨平台的库，其提供了便利的函数用来获取操作系统的信息，如cpu、内存、磁盘、网络等信息。psutil还可以用来进行进程
管理，包括判断进程是否存在、获取进程列表、获取进程的详细信息等。psutil还提供了许多命令行工具提供的功能，包括ps、top、lsof、netstat、
ifconfig、who、df、free、kill、nice、iostat、uptime等。
* psutil是一个跨平台的库，支持Linux、Windows、OSX、FreeBSD等操作系统。psutil支持Python2.6到Python3.6之间所有的python版本。
* psutil是一个第三方的开源项目，可直接用pip安装：
    ```
    $ pip install psutil
    ```
#### psutil提供的功能函数
* cpu
    - cpu_count默认返回逻辑cpu的个数，也可以指定logical=False获取物理cpu的个数。
    ```
    In [1]: import psutil

    In [2]: psutil.cpu_count()
    Out[2]: 4

    In [3]: psutil.cpu_count(logical=False)
    Out[3]: 2
    ```
    - cpu_percent返回cpu的利用率，可以通过interval参数阻塞式地获取interval时间范围内的cpu利用率，可以使用percpu参数指定获取
    每个cpu的利用率，默认获取整体的cpu利用率。
    ```
    In [4]: psutil.cpu_percent()
    Out[4]: 5.4

    In [5]: psutil.cpu_percent(percpu=True)
    Out[5]: [11.4, 1.3, 7.3, 1.3]
    
    In [6]: psutil.cpu_percent(interval=2, percpu=True)
    Out[6]: [13.6, 2.0, 6.5, 2.0]
    ```
    - cpu_times以命名元组的形式返回cpu的时间花费，也可以通过percpu参数指定获取每个cpu的统计时间。
    ```
    In [7]: psutil.cpu_times()
    Out[7]: scputimes(user=6359.04, nice=6.53, system=3114.38, idle=3392720.36, iowait=9148.34, irq=0.0, 
    softirq=122.57, steal=0.0, guest=0.0, guest_nice=0.0)
    ```
    - cpu_times_percent与cpu_times类似，但是返回的是耗费时间的比例。
    ```
    In [8]: psutil.cpu_times_percent()
    Out[8]: scputimes(user=0.2, nice=0.3, system=0.7, idle=95.9, iowait=2.9, irq=0.0, softirq=0.0, steal=0.0, 
    guest=0.0, guest_nice=0.0)
    ```
    - cpu_stats以命名元组返回cpu的统计信息，包括上下文切换、中断、软中断和系统调用的次数。
    ```
    In [9]: psutil.cpu_stats()
    Out[9]: scpustats(ctx_switches=321304066, interrupts=166722235, soft_interrupts=119965657, syscalls=0)
    ```
* 内存
    - virtual_memory以命名元组的形式返回内存使用情况，包括总内存、可用内存、内存利用率、buffer和cached等。除了内存利用率，其他
    字段都以字节为单位返回。
    ```
    In [1]: import psutil
    
    In [2]: psutil.virtual_memory()
    Out[2]: svmem(total=1040912384, available=642895872, percent=38.2, used=217673728, free=78962688, 
    active=499863552, inactive=321830912, buffers=106143744, cached=638132224, shared=1503232)
    In [3]: def bytes2human(n):
       ...:     symbols = ('K', 'M', 'G', 'T', 'P', 'E', 'Z', 'Y')
       ...:     prefix = {}
       ...:     for i, s in enumerate(symbols):
       ...:         prefix[s] = 1 << (i + 1) * 10
       ...:     for s in reversed(symbols):
       ...:         if n >= prefix[s]:
       ...:             value = float(n) / prefix[s]
       ...:             return '%.1f%s' % (value, s)
       ...:     return "%sB" % n
       ...: 
    
    In [4]: bytes2human(psutil.virtual_memory().total)
    Out[4]: '992.7M'  
    ```
    - swap_memory以命名元组的形式返回swap memory的使用情况，显然，对swap memory的统计包含了页的换入与换出。
    ```
    In [5]: psutil.swap_memory()
    Out[5]: sswap(total=0, used=0, free=0, percent=0.0, sin=0, sout=0)
    ```
* 磁盘
    - disk_partitions返回所有已经挂载的磁盘，以命名元组的形式返回。命名元组包含磁盘名称、挂载点、文件系统类型等信息。
    ```
    In [1]: import psutil

    In [2]: psutil.disk_partitions()
    Out[2]: [sdiskpart(device='/dev/vda1', mountpoint='/', fstype='ext3', opts='rw,noatime,data=ordered')]
    
    In [3]: def get_disk_via_mountpoint(mountpoint):
       ...:     disk = [item for item in psutil.disk_partitions() if item.mountpoint == mountpoint]
       ...:     return disk[0].device
       ...: 

    In [4]: get_disk_via_mountpoint('/')
    Out[4]: '/dev/vda1'
    ```
    - disk_usage获取磁盘的使用情况以命令元组返回，包括磁盘的容量，已经使用的磁盘容量、磁盘的空间利用率等。类似于Linux下的df命令。
    ```
    In [5]: psutil.disk_usage('/')
    Out[5]: sdiskusage(total=52709421056, used=9939668992, free=40085475328, percent=19.9)

    In [6]: psutil.disk_usage('/').percent
    Out[6]: 19.9
    
    In [7]: type(psutil.disk_usage('/').percent)
    Out[7]: float
    ```
    - disk_io_counters以命名元组的形式返回磁盘io统计信息，包括读的次数、写的次数、读字节数、写字节数等。
    ```
    In [8]: psutil.disk_io_counters()
    Out[8]: sdiskio(read_count=159050, write_count=7854072, read_bytes=2481423360, write_bytes=57169477632,
     read_time=3582659, write_time=285442557, read_merged_count=292, write_merged_count=5336543, busy_time=11337707)

    In [9]: psutil.disk_io_counters(perdisk=True)
    Out[9]: {'vda1': sdiskio(read_count=159050, write_count=7854104, read_bytes=2481423360,
     write_bytes=57169760256, read_time=3582659, write_time=285442725, read_merged_count=292, 
     write_merged_count=5336583, busy_time=11337797)}
    ```
* 网络
    - net_io_counters返回当前系统中网络io统计信息是监控系统中最需要关注的网络信息。net_io_counters函数以命名元组返回每块网卡的网络
    io统计信息，包括收发字节数、收发包的数量、出错情况和删包情况。使用net_io_counters函数与解析/proc/net/dev文件内容实现功能相同。
    ```
    In [1]: import psutil

    In [2]: psutil.net_io_counters()
    Out[2]: snetio(bytes_sent=2522047413, bytes_recv=2792065242, packets_sent=15997213, packets_recv=17443836,
     errin=0, errout=0, dropin=0, dropout=0)

    In [3]: psutil.net_io_counters(pernic=True)
    Out[3]: 
    {'eth0': snetio(bytes_sent=2317606811, bytes_recv=2587624905, packets_sent=15950616, packets_recv=17397280, 
    errin=0, errout=0, dropin=0, dropout=0),
    'lo': snetio(bytes_sent=204453785, bytes_recv=204453785, packets_sent=46707, packets_recv=46707, errin=0,
     errout=0, dropin=0, dropout=0)}
    ```
    - net_connections以列表的形式返回每个网络连接的详细信息，可以使用该函数查看网络连接状态，统计连接数以及处于待定状态的连接数。
    ```
    In [4]: psutil.net_connections()
    Out[4]: 
    [sconn(fd=-1, family=2, type=1, laddr=addr(ip='127.0.0.1', port=46515), raddr=(), status='LISTEN', pid=None),
    ...
    
    In [5]: conns = psutil.net_connections()
    
    In [6]: len([conn for conn in conns if conn.status == 'TIME_WAIT'])
    Out[6]: 0

    In [7]: len([conn for conn in conns if conn.status == 'LISTEN'])
    Out[7]: 8
    ```
    - net_if_addrs以字典形式返回网卡的配置信息，包括ip地址或mac地址、子网掩码和广播地址。
    ```
    In [8]: psutil.net_if_addrs()
    Out[8]: 
    {'eth0': [snic(family=2, address='10.154.19.199', netmask='255.255.192.0', broadcast='10.154.63.255', ptp=None),
    snic(family=17, address='52:54:00:34:b6:31', netmask=None, broadcast='ff:ff:ff:ff:ff:ff', ptp=None)],
    'lo': [snic(family=2, address='127.0.0.1', netmask='255.0.0.0', broadcast=None, ptp=None),
    snic(family=17, address='00:00:00:00:00:00', netmask=None, broadcast=None, ptp=None)]}
    ```
    - net_if_stats返回网卡的详细信息，包括是否启动、通信类型、传输速度与mtu。
    ```
    In [9]: psutil.net_if_stats()
    Out[9]: 
    {'eth0': snicstats(isup=True, duplex=0, speed=0, mtu=1500),
    'lo': snicstats(isup=True, duplex=0, speed=0, mtu=65536)}
    ```
* 其他
    - users以命名元组的方式返回当前登陆用户的信息，包括用户名、登陆时间、终端与主机信息。
    ```
    In [10]: psutil.users()
    Out[10]: [suser(name='liuhui', terminal='pts/1', host='101.130.54.76', started=1516298240.0, pid=9114)]
    ```
    - boot_time以时间戳的形式返回系统的启动时间。
    ```
    In [11]: import datetime

    In [12]: psutil.boot_time()
    Out[12]: 1512802687.0

    In [13]: datetime.datetime.fromtimestamp(psutil.boot_time()).strftime("%Y-%m-%d %H:%M:%S")
    Out[13]: '2017-12-09 14:58:07'
    ```

#### 使用psutil实现监控程序
* 使用psutil收集cpu的信息、开机时间、内存信息以及磁盘空间等信息。监控程序不同函数收集不同纬度的监控信息以字典形式返回。
```
$ vim monitor.py                        # 编辑monitor.py收集监控信息
#!/usr/bin/python
# -*- coding: utf-8 -*-
from __future__ import unicode_literals
import os
import socket
from datetime import datetime

import jinja2
import yagmail
import psutil


EMAIL_USER = 'xxxxxx@163.com'
EMAIL_PASSWORD = 'xxxxxx'
RECIPIENTS = ['xxxxxx@qq.com']

def render(tpl_path, **kwargs):
    path, filename = os.path.split(tpl_path)
    return jinja2.Environment(
        loader=jinja2.FileSystemLoader(path or './')
    ).get_template(filename).render(**kwargs)

def bytes2human(n):
    symbols = ('K', 'M', 'G', 'T', 'P', 'E', 'Z', 'Y')
    prefix = {}
    for i,s in enumerate(symbols):
        prefix[s] = 1 << (i + 1) * 10
    for s in reversed(symbols):
        if n >= prefix[s]:
            value = float(n) / prefix[s]
            return '%.1f%s' % (value, s)
    return "%sB" % n

def get_cpu_info():
    cpu_count = psutil.cpu_count()
    cpu_percent = psutil.cpu_percent(interval=1)
    return dict(cpu_count=cpu_count, cpu_percent=cpu_percent)

def get_memory_info():
    virtual_mem = psutil.virtual_memory()
    mem_total = bytes2human(virtual_mem.total)
    mem_percent = virtual_mem.percent
    mem_free = bytes2human(virtual_mem.free + virtual_mem.buffers + virtual_mem.cached)
    mem_used = bytes2human(virtual_mem.total * virtual_mem.percent)
    return dict(mem_total=mem_total, mem_percent=mem_percent, mem_free=mem_free, mem_used=mem_used)


def get_disk_info():
    disk_usage = psutil.disk_usage('/')
    disk_total = bytes2human(disk_usage.total)
    disk_percent = disk_usage.percent
    disk_free = bytes2human(disk_usage.free)
    disk_used = bytes2human(disk_usage.used)
    return dict(disk_total=disk_total, disk_percent=disk_percent, disk_free=disk_free, disk_used=disk_used)

def get_boot_info():
    boot_time = datetime.fromtimestamp(psutil.boot_time()).strftime("%Y-%m-%d %H:%M:%S")
    return dict(boot_time=boot_time)

def collect_monitor_data():
    data = {}
    data.update(get_boot_info())
    data.update(get_cpu_info())
    data.update(get_memory_info())
    data.update(get_disk_info())
    return data

def main():
    hostname = socket.gethostname()
    data = collect_monitor_data()

    data.update(dict(hostname=hostname))
    print(data)
    content = render('index.html', **data)

    with yagmail.SMTP(user=EMAIL_USER, password=EMAIL_PASSWORD, host='smtp.163.com', port=25) as yag:
        for recipient in RECIPIENTS:
        yag.send(recipient, "监控信息".encode('utf-8'), content.encode('utf-8'))


if __name__ == "__main__":
    main()
```
* 前端模版获取监控信息
```
$ vim index.html
<html>
<head>
    <title>监控信息</title>
</head>
<body>
    <table border='1'>
        <tr><td>服务器名称</td><td>{{ hostname }}</td></tr>
        <tr><td>开机时间</td><td>{{ boot_time }}</td></tr>

        <tr><td>cpu个数</td><td>{{ cpu_count }}</td></tr>
        <tr><td>cpu利用率</td><td>{{ cpu_percent }}</td></tr>

        <tr><td>内存总量</td><td>{{ mem_percent }}</td></tr>
        <tr><td>内存利用率</td><td>{{ mem_total }}</td></tr>
        <tr><td>内存已用空间</td><td>{{ mem_used }}</td></tr>
        <tr><td>内存可用空间</td><td>{{ mem_free }}</td></tr>

        <tr><td>磁盘空间总量</td><td>{{ disk_total }}</td></tr>
        <tr><td>磁盘空间利用率</td><td>{{ disk_percent }}</td></tr>
        <tr><td>磁盘已用空间</td><td>{{ disk_used }}</td></tr>
        <tr><td>磁盘可用空间</td><td>{{ disk_free }}</td></tr>
    </table>
</body>
</html>
```

## python网络分析
### 列出网络上所有活跃的主机
* 使用ping命令判断主机是否活跃
```
$ ping www.baidu.com    # ping命令使用互联网控制协议(ICMP)中的ECHO_REQUEST数据报，网络设备收到会做出回应。
PING www.a.shifen.com (220.181.112.244) 56(84) bytes of data.
64 bytes from 220.181.112.244 (220.181.112.244): icmp_seq=1 ttl=249 time=34.6 ms
64 bytes from 220.181.112.244 (220.181.112.244): icmp_seq=2 ttl=249 time=34.7 ms
64 bytes from 220.181.112.244 (220.181.112.244): icmp_seq=3 ttl=249 time=34.6 ms

$ ping -c 2 www.baidu.com                   # ping命令发送了2个ECHO_REQUEST数据报就停止发送。
PING www.a.shifen.com (14.215.177.39) 56(84) bytes of data.
64 bytes from 14.215.177.39 (14.215.177.39): icmp_seq=1 ttl=52 time=32.2 ms
64 bytes from 14.215.177.39 (14.215.177.39): icmp_seq=2 ttl=52 time=32.4 ms

--- www.a.shifen.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1001ms
rtt min/avg/max/mdev = 32.286/32.371/32.456/0.085 ms

# 编辑test-ping.sh通过ping命令的返回码判断主机是否可达，当主机活跃时，ping命令的返回码为0，当主机不可达时，ping
# 命令返回码非0。
$ vim test-ping.sh
#!/bin/bash

for ip in `cat ips.txt`
do
    if ping $ip -c 2 &> /dev/null
    then
        echo "$ip is alive"
    else
        echo "$ip is unreachable"
    fi
done
$ vim ips.txt                   # 编辑ips.txt写入几个ip供test-ping.sh脚本使用
127.0.0.1
192.168.61.1
10.154.19.199
$ bash test-ping.sh             # 执行脚本
127.0.0.1 is alive
192.168.61.1 is unreachable
10.154.19.199 is alive
```
* 使用Python判断主机是否活跃
```
# 使用前面的shell脚本由于每执行一次ping命令都要经历一段时间延迟，所以，要检查大量主机是否处于活跃状态时需要很长的
# 时间。这里，我们可以使用Python语言编程并发的程序，以此加快程序的执行。
#!/usr/bin/python
# -*- coding:utf-8 -*-
from __future__ import print_function

import subprocess
import threading

def is_reacheable(ip):
    if subprocess.call(["ping", "-c", "1", ip]) == 0:
        print("{0} is alive".format(ip))
    else:
        print("{0} is unreacheable".format(ip))

def main():
    with open('ips.txt') as f:
        lines = f.readlines()
        threads = []
        print(lines)
        for line in lines:
            thr = threading.Thread(target=is_reacheable, args=(line,))
            thr.start()
            threads.append(thr)
        for thr in threads:
            thr.join()

if __name__ == "__main__":
    main()
```
* 使用生产者消费者模型减少线程的数量
```
#!/usr/bin/python
# -*- coding:utf-8 -*-
from __future__ import print_function

import subprocess
import threading
from Queue import Queue
from Queue import Empty

def call_ping(ip):
    if subprocess.call(["ping", "-c", "1", ip]) == 0:
        print("{0} is alive".format(ip))
    else:
        print("{0} is unreacheable".format(ip))

def is_reacheable(q):
    try:
        while True:
            ip = q.get_nowait()
            call_ping(ip)
    except Empty:
        pass

def main():
    q = Queue()
    with open('ips.txt') as f:
        for line in f:
            q.put(line)

    threads = []
    for i in range(10):
        thr = threading.Thread(target=is_reacheable, args=(q,))
        thr.start()
        threads.append(thr)
    for thr in threads:
        thr.join()

if __name__ == "__main__":
    main()
```

### 端口扫描 
* 使用Python语言编写一个端口扫描器
```
# 在Python代码中可以调用telnet命令判断一个端口是否打开，但是telnet命令存在一个问题，当我们telnet一个不可达的端口
# 时，telnet需要很久才能超时返回。这里我们使用socket模块来编写一个端口扫描器。
$ vim port-scan1.py                     # 编辑脚本port-scan1.py
#!/usr/bin/python
# -*- coding:utf-8 -*-
from __future__ import print_function
from socket import socket, AF_INET, SOCK_STREAM

def conn_scan(host, port):
    conn = socket(AF_INET, SOCK_STREAM)
    try:
        conn.connect((host, port))
        print(host, port, 'is avaliable')
    except:
        print(host, port, 'is not avaliable')
    finally:
        conn.close()

def main():
    host = '127.0.0.1'
    for port in range(20, 5000):
        conn_scan(host, port)

if __name__ == "__main__":
    main()
    
$ python port-scan1.py              # 执行脚本
127.0.0.1 20 is not avaliable
127.0.0.1 21 is not avaliable
127.0.0.1 22 is avaliable
127.0.0.1 23 is not avaliable
127.0.0.1 24 is not avaliable
127.0.0.1 25 is avaliable
127.0.0.1 26 is not avaliable
127.0.0.1 27 is not avaliable
127.0.0.1 28 is not avaliable
127.0.0.1 29 is not avaliable
127.0.0.1 30 is not avaliable
...
```
* 使用nmap扫描端口。nmap(Network Mapper)是知名的网络探测和安全扫描程序，nmap可以进行主机发现(Host Discovery)、
端口扫描(Port Scanning)、版本侦测(Version Detection)、操作系统侦测(Operating System Detection)。
```
$ sudo yum install nmap                       # 安装nmap
# nmap具有非常灵活的方式指定需要扫描的主机，我们可以使用nmap命令的-sL选项来进行测试。-sL选项仅仅打印IP列表。
$ nmap -sL 127.0.0.1/30

Starting Nmap 6.40 ( http://nmap.org ) at 2018-01-21 01:08 CST
Nmap scan report for 127.0.0.0
Nmap scan report for localhost (127.0.0.1)
Nmap scan report for 127.0.0.2
Nmap scan report for 127.0.0.3
Nmap done: 4 IP addresses (0 hosts up) scanned in 0.00 seconds

$ nmap -sL 10.154.19.199 127.0.0.1          # 指定多个主机

Starting Nmap 6.40 ( http://nmap.org ) at 2018-01-21 01:10 CST
Nmap scan report for 10.154.19.199
Nmap scan report for localhost (127.0.0.1)
Nmap done: 2 IP addresses (0 hosts up) scanned in 0.00 seconds

$ nmap -iL ips.txt                  # -iL选项读取文件中的IP地址

Starting Nmap 6.40 ( http://nmap.org ) at 2018-01-21 01:12 CST
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00024s latency).
Not shown: 995 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
25/tcp   open  smtp
80/tcp   open  http
111/tcp  open  rpcbind
8080/tcp open  http-proxy

Nmap scan report for 10.154.19.199
Host is up (0.00025s latency).
Not shown: 997 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
111/tcp open  rpcbind

Nmap done: 3 IP addresses (2 hosts up) scanned in 1.27 seconds
```
* 主机发现。使用-sP或-sn选项可以仅仅判断主机是否可达，不进行端口扫描。
```
nmap -sP 10.154.19.199

Starting Nmap 6.40 ( http://nmap.org ) at 2018-01-21 01:15 CST
Nmap scan report for 10.154.19.199
Host is up (0.000038s latency).
Nmap done: 1 IP address (1 host up) scanned in 0.00 seconds
```
* 端口扫描。不添加任何参数便是对主机进行端口扫描，默认情况下，nmap将会扫描1000个最常用的端口和。
```
$ nmap 10.154.19.199

Starting Nmap 6.40 ( http://nmap.org ) at 2018-01-21 01:17 CST
Nmap scan report for 10.154.19.199
Host is up (0.00025s latency).
Not shown: 997 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
111/tcp open  rpcbind

Nmap done: 1 IP address (1 host up) scanned in 0.04 seconds

# 在进行端口扫描时，nmap提供了大量的参数控制端口扫描。包括端口扫描协议、端口扫描类型、扫描的端口号。
# 端口扫描协议：T(TCP)、U(UDP)、S(SCTP)、P(IP)；
# 端口扫描类型：-sS/sT/sA/sW/sM:TCP SYN/Connect()/ACK/Window/Maimon scans；
# 扫描的端口号：-p 80,443；
# nmap通过探测将端口划分为6个状态：
# open              端口是开放的
# closed            端口是关闭的
# filtered          端口被防火墙IDS/IPS屏蔽，无法确定其状态
# unfiltered        端口没有被屏蔽，但是否开放需要进一步确定
# open/filtered     端口是开放的或被屏蔽
# closed/filtered   端口是关闭的或被屏蔽

# 在端口扫描时，可以使用不同的端口扫描类型。常见的端口扫描类型如下：
# TCP SYNC SCAN：半开放扫描。这种扫描为发送一个SYN包，启动一个TCP会话，并等待响应的数据包。如果收到的是一个reset
                包，表明端口是关闭的；如果收到的是一个SYNC/ACK包，则表示端口是打开的。
# TCP NULL SCAN：NULL扫描把TCP头中的所有标志位都设置为NULL。如果收到是RST包，则表示相应的端口是关闭的。
# TCP FIN SCAN：TCP FIN扫描发送一个表示结束一个活跃的TCP连接的FIN包，让对方关闭连接。如果收到RST包则端口是关闭的。
# TCP XMAS SCAN：TCP XMAS扫描发送PSH、FIN、URG和TCP标志位被设置为1的数据包，如果收到一个RST包则端口是关闭的。
```
* 版本侦测。版本侦测功能用于确定开放端口上运行的应用程序及版本信息。
```
$ nmap -sV 127.0.0.1
```
* 使用python-nmap进行端口扫描。python-nmap仅仅是对nmap的封装，python-nmap将nmap的输出结果保存到字典之中，我们只
需要通过python的字典就可以获取到nmap的输出信息。
```
$ sudo pip install python-nmap              # 安装python-nmap
# python-nmap的使用非常简单，我们只需要创建一个PortScanner对象，并调用对象的scan方法就能够完成基本的nmap端口扫描。
In [1]: import nmap

In [2]: nm = nmap.PortScanner()

In [3]: nm.scan('10.154.19.199', '22-1000')
Out[3]: 
{'nmap': {'command_line': 'nmap -oX - -p 22-1000 -sV 10.154.19.199',
  'scaninfo': {'tcp': {'method': 'connect', 'services': '22-1000'}},
  'scanstats': {'downhosts': '0',
   ...
   
In [4]: nm.command_line()               # 获取命令行参数
Out[4]: 'nmap -oX - -p 22-1000 -sV 10.154.19.199'

In [5]: nm.scaninfo()                   # 获取扫描的方法
Out[5]: {'tcp': {'method': 'connect', 'services': '22-1000'}}

In [6]: nm.all_hosts()                  # 获取主机列表
Out[6]: ['10.154.19.199']

# python-nmap还提供了以主机地址为键，获取单台主机的详细信息。包括获取主机网络状态、所有的协议、所有打开的端口号、
# 端口号对应的服务等。
In [7]: nm['10.154.19.199'].state()
Out[7]: 'up'

In [8]: nm['10.154.19.199'].all_protocols()
Out[8]: ['tcp']

In [9]: nm['10.154.19.199']['tcp'].keys()
Out[9]: [80, 22, 111]

In [10]: nm['10.154.19.199']['tcp'][111]
Out[10]: 
{'conf': '10',
 'cpe': '',
 'extrainfo': 'RPC #100000',
 'name': 'rpcbind',
 'product': '',
 'reason': 'syn-ack',
 'state': 'open',
 'version': '2-4'}
```

## Python自动化管理
### SSH协议的Python实现paramiko
* SSH是一个协议，OpenSSH是其中一个开源实现。paramiko是一个python的库，该库支持Python2.6+和Python3.3+版本，实现
了SSHv2协议。有了paramiko后，我们可以在Python代码中直接使用SSH协议对远程服务器执行操作，而不是调用ssh命令。
* paramiko的安装。直接使用pip安装。
    ```
    $ sudo pip install paramiko
    $ python -c 'import paramiko'
    ```
* SSHClient类与SFTPClient类。paramiko包含两个核心组件，分别是SSHClient和SFTPClient，前者的作用类似与Linux下的
ssh命令，后者的作用类似于Linux下的sftp命令。SSHClient类是对SSH会话的封装，该类封装了传输(transport)、通道(channel)
及SFTPClient类建立的方法(open_sftp)，通常用于执行远程命令。SFTPClient类是对SFTP客户端的封装，用以实现远程文件操作，
如文件上传、下载、修改文件权限等操作。
    ```
    # SSHClient类常用的几个方法：
    # 1）connect：connect方法实现远程服务器连接与认证，对于该方法，只有hostname是必传传输。
    connect(self, hostname, port=22, username=None, password=None,
            pkey=None, key_filename=None, timeout=None,
            allow_agent=True, look_for_keys=True, compress=False)
    # 2）set_missing_host_key_policy：设置远程服务器没有在know_hosts文件中记录时的应对策略。目前支持三种策略，分别是AutoAddPolicy、
    RejectPolicy（默认策略）与WarningPolicy，分别表示自动添加服务器到know_hosts文件、拒绝本次连接、警告并将服务器添加到know_hosts中。
    # 3）exec_command：在远程服务器执行Linux命令。
    # 4）open_sftp：在当前ssh会话的基础上创建一个sftp会话。该方法会返回一个SFTPClient对象。
    SFTPClient类常用的几个方法：
    put：上传本地文件到远程服务器；
    get：从远程服务器下载文件到本地；
    mkdir：在远程服务器上创建目录；
    remove：删除远程服务器中的文件；
    rmdir：删除远程服务器中的目录；
    rename：重命名远程服务器中的文件与目录；
    stat：获取远程服务器中文件的详细信息；
    listdir：列出远程服务器中指定目录下的内容。
    ```
* paramiko的基本使用
    - 使用密码认证
        ```
        import paramiko
        ssh = paramiko.SSHClient()
        ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
        ssh.connect("ip", port, 'username', 'password')
        ```
    - 使用密钥认证    
        ```
        import paramiko
        ssh = paramiko.SSHClient()
        ssh.connect('IP', port, 'username', key_filename='私钥')
        ```
    - 在建立SSH连接以后，可以通过SSHClient.exec_command方法执行Shell命令。执行Shell命令后不会直接打印输出，而是返回几个Channel。每个
    Channel都类似于Python的文件对象，可以调用Channel的readlines方法读取输出结果。
        ```
        In [1]: import paramiko
        
        In [2]: client = paramiko.SSHClient()

        In [3]: client.set_missing_host_key_policy(paramiko.AutoAddPolicy())

        In [4]: client.connect('ip', port, 'username', 'password')

        In [5]: stdin, stdout, stderr = client.exec_command('hostname')

        In [6]: print(stdout.readlines())
        ['VM_19_199_redhat\n']

        In [7]: stdin, stdout, stderr = client.exec_command('lssa')

        In [8]: stderr.readlines()
        Out[8]: ['bash: lssa: command not found\n']
        ```
    - SFTPClient将会复用SSHClient的认证信息。复用的方式很简单，直接使用SSHClient的open_sftp方法即可。SFTPClient提供了大量的文件操作
    的API，可以进行文件上传、文件下载、修改文件权限、修改文件所有者等。
        ```
        In [9]: sftp = client.open_sftp()

        In [10]: sftp.put('website.txt', 'website.txt')
        Out[10]: <SFTPAttributes: [ size=1059 uid=0 gid=0 mode=0o100644 atime=1516476267 mtime=1516476267 ]>

        In [11]: sftp.stat('website.txt')    
        Out[11]: <SFTPAttributes: [ size=1059 uid=0 gid=0 mode=0o100644 atime=1516476267 mtime=1516476267 ]>

        In [12]: sftp.rename('website.txt', 'website.py')
        ```
* 使用paramiko部署监控程序。将本地文件的monitor.py文件上传远程服务器，通过SFTPClient的chmod方法修改monitor.py文件的权限。
    ```
    #!/usr/bin/python
    # -*- coding:utf-8 -*-
    from __future__ import print_function

    import paramiko

    def deploy_monitor(ip):

        with paramiko.SSHClient() as client:
            client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
            client.connect(ip, 22, 'liuhui', 'aixocm')

            stdin, stdout, stderr = client.exec_command('ls -l')
            print(stdout.readlines())

            with client.open_sftp() as sftp:
                sftp.put('monitor.py', 'monitor.py')
                sftp.chmod('monitor.py', 0o755)


    def main():
        with open('ips.txt') as f:
            for line in f:
                deploy_monitor(line.strip())

    if __name__ == '__main__':
        main()
    ```


    
    