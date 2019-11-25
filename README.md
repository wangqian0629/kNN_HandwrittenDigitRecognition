# kNN_HandwrittenDigitRecognition
KNN算法实现手写数字识别
# 算法步骤（瞎记）
## kNN classify0()
1. 4个参数
2. 计算输入向量inX与dataSet的欧式距离的数组distances
3. 对前k个距离的label统计数进行排序sortedClassCount
4. 返回sortedClassCount[0][0],即出现频率最高的分类

# 常见函数

## numpy.tile()

函数格式tile(A,reps)

```
import numpy as np
a = [1,2,3]
b = np.tile(a,[2,3])
print(b)
```
结果是
```
[[1 2 3 1 2 3 1 2 3]
 [1 2 3 1 2 3 1 2 3]]
```

## numpy.zeros()

用法：zeros(shape, dtype=float, order='C')

返回：返回来一个给定形状和类型的用0填充的数组；

参数：shape:形状

dtype:数据类型，可选参数，默认numpy.float64

例如：
``` 
zeros((1,1024))
```
生成1* 1024的全零矩阵

## numpy.shape()

功能是读取矩阵的长度，比如shape[0]就是读取矩阵第一维度的长度，一般指行数。


## read() readline() readlines() linecache
### read([size])
从文件当前位置起读取size个字节，若无参数size，则表示读取至文件结束为止，它范围为字符串对象。
### readline()
该方法每次读出一行内容，所以，读取时占用内存小，比较适合大文件，该方法返回一个字符串对象。
### readlines()
读取整个文件所有行，保存在一个列表(list)变量中，每行作为一个元素，但读取大文件会比较占内存。
### linecache模块
linecache.getline(),输出某个文件的第n行,对于大文件效率还可以。

## Python 获取字符串长度 len() 函数 
## Python 统计文件行数 len(fr.readlines())

## range()
range（5）等价于range（0， 5）
range（0， 5） 是[0, 1, 2, 3, 4]没有5

## argsort()

argsort()函数是将x中的元素从小到大排列，提取其对应的index(索引号)

## Python: sorted，operator.itemgetter的用法

Python]对容器内数据的排序有两种，一种是容器自己的sort函数，一种是内建的sorted函数。
sort函数和sorted函数唯一的不同是，sort是在容器内排序，sorted生成一个新的排好序的容器。
sorted(iterable, cmp=None, key=None, reverse=False) --> new sorted list
参数解释：

（1）iterable指定要排序的list或者iterable，不用多说；

（2）cmp为函数，指定排序时进行比较的函数，可以指定一个函数或者lambda函数，如：

       students为类对象的list，每个成员有三个域，用sorted进行比较时可以自己定cmp函数，例如这里要通过比较第三个数据成员来排序，代码可以这样写：
      students = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
       sorted(students, key=lambda student : student[2])
       
（3）key为函数，指定取待排序元素的哪一项进行排序，函数用上面的例子来说明，代码如下：
       sorted(students, key=lambda student : student[2]) 
       key指定的lambda函数功能是去元素student的第三个域（即：student[2]），因此sorted排序时，会以students所有元素的第三个域来进行排序。


## operator.itemgetter函数

operator模块提供的itemgetter函数用于获取对象的哪些维的数据

```
a = [1,2,3] 
b=operator.itemgetter(1)      //定义函数b，获取对象的第1个域的值> b(a) 
2 
```

## items()
```
>>> x = {'title':'python web site','url':'www.iplaypy.com'}
>>> x.items()
[('url', 'www.iplaypy.com'), ('title', 'python web site')]
```
items()方法是将字典中的每个项分别做为元组，添加到一个列表中，形成了一个新的列表容器。

## os.listdir()

os.listdir() 方法用于返回指定的文件夹包含的文件或文件夹的名字的列表。
