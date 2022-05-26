---
layout: post
title: Data Analysis--Python numpy&pandas
date: 2022-05-20
Author: Ali
categories: 
tags: [Python]
comments: true
---

```python
import random
import numpy as np

array1=np.array(object,dtype=None,copy=True,order=None,subok=False,ndmin=0)

#array(), you can add list,tuple ,range ect inside
#Object means 数组
#dtype means 改变数组类型
#copy means 数组是否可以被拷贝
#oder means 数组内存布局. C;行 F:列 A:默认 K：元素在内存中的出现顺序
#ndmin means 定义数组维度
#subok:

#------------------------------------创建数组-----------------------------------
list=np.array([1,2,3,4])
print(list)
print(type(list))

#tuple
tuple=np.array((1,2,3,4,5))
print(tuple)

rangee=np.array(range(10))
print(rangee)
print('--'*10)
#or
rangeee=np.arange(10)
print(rangeee)

#other
fun1=np.array(i**2 for i in range(10))
print(fun1)
#
list2=np.array(i for i in range(10) if i %2==0)
print(list2)

print('--'*20)
```



```python
#------------------------------------数组的类型-----------------------------------
#当数组里存在不同类型的数值时，python会选择内存占用最大的数值类型
import random
import pandas
import numpy as np

ar1=np.array([1,2,3,4,'1',1.9999,11,2333,12312312,124123123,1231,231])
print(ar1)
print(ar1.dtype)

ar2=np.array([1,2,12,2.11])
print(ar2)
print(ar2.dtype)

print('--'*20)


#---------------data type change---------------
ar3=np.array([1,2,3],dtype=float)
print(ar3)
print(ar3.dtype)
#to specifc type
ar4=np.array([1,2,3],dtype='float32')
print(ar4)
print(ar4.dtype)
#to int 8 bit
ar4=np.array([1,2,3],dtype='i1')
print(ar4)
print(ar4.dtype)

# to bool
ar5=np.array([1,0],dtype='bool')
print(ar5)
print(ar5.dtype)

#adjust data type
ar6=ar5.astype('int8')
print(ar6)
print(ar6.dtype)

print('--'*20)

#
ar7=np.array([random.random() for i in range(10)])
print(ar7)

ar8=np.around(ar7,2)                #保留2位小数
print(ar8)

```



```python
#----------------------------------data shape 数组维度--------------------------------

#1d data ,shape will show the number of data in
#(z,)  				组里z个元素
ar9=np.array([1,2,3,4])
print(ar9.shape)

#2d data,shape will show the number of list and line
#(y,z)  			y个数组，每组里z个元素

ar10=np.array([[1,2,3],('a','b','c')])
print(ar10.shape)

#3d
#(x,y,z)  			x组数据块，每块y个数组，每组里z个元素

ar11=np.array([[[1,2,3],[3,4,5],[5,2,1]],[[7,8,9],[10,11,12],[5,2,1]]])
ar111=np.array([[[1,2,3],[3,4,5],[5,2,1]],[[1,2,3],[3,4,5],[5,2,1]],[[7,8,9],[10,11,12],[5,2,1]]])

print(ar11)
print(ar11.shape)    

print(ar111)
print(ar111.shape)  

#------------------change data shape 数组维度---------------
print('--'*10)
#chang shape   the number of data must match with shape size

#1d data change to 2d data
ar12=np.arange(10)
ar13=ar12.reshape(5,2)
print(ar13)

#1d to 3d
ar14=np.arange(20)
ar15=ar14.reshape(2,2,5)
print(ar15)
print('--'*10)

#3d to 2d
#reshaper function have return,reshape will not change the origin shape
ar16=ar11.reshape(2,9)
print(ar16)
print(ar11)
```



```python
#-------------------------数组运算-------------------------
#数组运算采用广播原则
#相同维度下的运算规则
# (z,) 			一维之间运算时 需要保证z的值相同或一方为1
# (y,z) 		二维之间运算时 需要保证z的值相同或一方为1 且 y相同或者一方为1
# (x,y,z) 		三维之间运算时 需要保证z的值相同或一方为1 且 y相同或者一方为1 且 x相同或者一方为1

#add
ar17=np.array([[[1,2,2,1],[3,4,1,2]],[[2,1,1,2],[3,1,4,5]]])
ar18=np.array([[[6,7,3,1],[9,1,8,9]],[[2,1,3,4],[5,8,5,6]]])

print(ar17)
print('-------'*10)
print(ar18)
print('-------'*10)
print(ar18+ar17)

#数组乘法
print(ar17*2)

#数组相乘
print(ar18*ar17)

#------------------------不同维度的运算规则------------------
#不同维度的运算首先要保证 z的值时相同的，否则无法运算

ar17=np.array([[[1,2,2,1],[3,4,1,2]],[[2,1,1,2],[3,1,4,5]]])
ar20=np.array([[1,2,2,1],[2,1,1,2]])
ar19=np.array([1,2,3,4])

#一维与三维运算时，三维的每一组都要与一维进行计算
#二维与三维运算时,z值都必须相同，相同可以用一方为1代替

print(ar17-ar19)
print('-------'*10)

#二维与三维运算时，以二维为一组数据，三维为二组数据，三维的二组都与二维的一组运算
#二维与三维运算时,y和z值都必须相同，相同可以用一方为1代替
print(ar17-ar20)
print('-------'*10)

#二维与一维运算时，以二维为一组数据，三维为二组数据，三维的二组都与二维的一组运算
#二维与一维运算时，z值都必须相同，相同可以用一方为1代替
print(ar20-ar19)
print('-------'*10)

#-----------------列运算--------------
ar21=np.array([[[1],[4]],[[1],[3]]])
ar22=np.array([[1,2],[3,4]])
ar19=np.array([1,2,3,4])

print('-------'*10)
print('-------'*10)
print(ar21.shape)
print(ar22.shape)
print(ar19.shape)

print(ar21)
print(ar22-ar21)
print('-------'*10)

#一维与三维运算时，三维的每一组都要与一维进行计算
print(ar19-ar21)
print('-------'*10)


#二维和三维不能进行列运算
#print(ar22-ar19)
print('-------'*10)
```



```python
#------------------------数据读取------------------------

#np.loadtxt(frame,dtype=np.int,delimiter=None,skiprows==0,usecols=None,unpack=False)
#frame          file location
#dtype          data type
#delimiter      fenge zhifuchuan
#skiprows       jump x line
#usecols        read specific List index or Tuple
#unpack         line to list. list to line

us_file_path="./test.csv"
data1=np.loadtxt(us_file_path,delimiter=",",dtype='int')
#unpack chang line to list and change the list to line
data2=np.loadtxt(us_file_path,delimiter=",",dtype='int',unpack=True)
print(data1)
print(data2)
```



```python
#------------------------数组转置------------------------

#transpose

t1=np.arange(16).reshape((4,4))
print(t1)


t2=t1.transpose()
print(t2)
#or
t3=t1.T
print(t3)
#or
t4=t1.swapaxes(1,0)         #swpaxes defult setting is 0,1
print(t4)
```



```python
#------------------------numpy 索引和切片------------------------

us_file_path="./test.csv"
data1=np.loadtxt(us_file_path,delimiter=",",dtype='int')
print(data1)

#2维数据
#dataname[x,y]         x 为行, y 为列


#------取行			（取cvs第二行数据）
print(data1[1])

#------取连续多行   		（取cvs第二行数之后的所有行数据）
print(data1[1:])

#------取不连续的行
print(data1[[0,2,4]])

#完整写法
print(data1[1,:])
print(data1[1:,:])
print(data1[[0,2,4],:])


#------取列
print(data1[:,0])

#------取连续多列
print(data1[:,1:])

#------取不连续的列
print(data1[:,[0,2,4]])
print('**'*20)

#------取特定位置的一个值
print(data1[2,3])

#------取多个连续的行，多个连续的列

#例子：取CSV中 第2行到第4行，第2列到第4列
print(data1[1:4,1:4])


#------取多个不连续的值
# 2d data			   dataname[x,y]
# 取多个值				dataname[[x1,x2，..],[y1,y2,...]]
# [x1,x2],[y1,y2]对应的坐标就是[x1,y1]  [x2,y2]

print(data1[[0,0],[1,1]])

print(data1[[0,1,2],[0,1,2]])
```



```python
#------------------------数值修改------------------------

#------修改一个特定位置的值
data1[0,0]=999999
print(data1)

#------修改一个特定位置的值
data1[1:4,1:4]=0
print(data1)

#------bool 索引
#chang all data less than 1 to 2
data1[data1<1]=2
data1[data1>=3]=0
print(data1)

#------三元运算符
#np.where(条件,if True result change to ?,else change to ?)
d=np.where(data1<=0,1,3)
print(d)

#------numpy clip函数
#clip(x,y)    	Date value less than 21 change to 21, over than 43 change to 43

print(data2)
d2=data2.clip(21,43)
print(d2)


#------数组转换
print(data2)
#data2[0,0]=np.nan

data2=data2.astype(float)
data2[0,0]=np.nan
print(data2)

#------数组拼接

data3=np.arange(0,20).reshape(4,5)
data4=np.arange(20,40).reshape(4,5)

#------上下拼接
data34=np.vstack((data3,data4))
print(data34)

#------左右拼接
data34=np.hstack((data3,data4))
print(data34)

#------水平分割

#------竖直分隔
```





