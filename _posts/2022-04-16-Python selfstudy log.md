---
layout: post
title: Python Self-Study log. Updating....
date: 2022-04-16
Author: Ali
categories: 
tags: [Python]
comments: true
---




I realize that my IT skill may hit a plateau so here I make a plan for me to learn Python.

This page I use to push me to study and will continue to be updated for more than one month. 





### 16.April.2022     Chapter one

```python
#输入数字
print(111)
#输出字符
print("HELLO")
print('1+1')

#simple caculate
print(1+1)

#将数据输出到文件
#a+ 为定义创建模式，文件不存在既创建文件，存在就在内容后面追加
# file=定义名
shuchu=open('C:\\Users\ALI\Desktop\新建文件夹 (3)\\text.txt','a+')
print('hello',file=shuchu)
shuchu.close()



#不换行输出
print('HELLP','HELLO','YYDS')

#转义字符
print('HELLO\nworld')        #\n change line
print('helloooo\tworld')     #\t four world grap
print('HELLOoo\tworld')      #\t 前面内容不足4个字符时，\t会占据之前内容的空间
print('HELLO\rwor')          #\r 后面的内容全部向前覆盖，前面的内容会被完全覆盖
print('hello\b\b\bworld')    #\b 表示后面的内容前进覆盖一个单位，

#end表示输出后 不换行
print(40, '\t', end='')
print(50, '\t')

# \ 在命令中会被功能化过滤. 第一个会无效，第二个有效，第三个又会无效，第四个有效，依次类推
print("http：\\\\www.google.com ")    # \ 因为功能化 会被过滤，所以需要补充
print("")

# 在’‘作为输出命令时。\后+‘ ” 让'"失去功能作用，变为普通字符
print('question：What day today\nFirday')        
print('question：\'What day today\'\nFirday')    
print("")

# 在""作为输出命令时。不需要考虑,它会无视单个 \的存在
print("question：'What day today'\n‘Firday’")    
print("question：“What day today”\n‘Firday’")    
print("question：\“What day today\”\n‘Firday’")  
print("question：\'What day today\'\n‘Firday’")  
print("question：'What day today'\‘Firday’")     
print("")

#原字符：内容前+r  内容中的转义字符无效化.
print('Hello\nworld')
print(r'Hello\nworld')
print('Hello\nworld\\')
print("")

print(r"Hello\nworld")

print("")



#practice

secrite=open('C:\\Users\ALI\Desktop\secrite.txt','a+')
print('Click https:\\\\google.com\nThen type\nWho is Ali?',end="",file=secrite)
print('\t\tWhat he looks like?',file=secrite)
print(r'Does he know how to using \n in python?',file=secrite)
print('Sorry i forgot Mark\nDoes he know how to using','\'\\n\'','in python?',file=secrite)
secrite.close()

print('Can you tell me the relut of 991238*123123?','\n',991238*123123,)
print(991238*123123)
```









### 17.April.2022     Chapter Two

```python
#coding：gbk


'''
Nothing
over
here
多行注释
'''

#编码
print(chr(0b100111001011000))
print(ord('乘'))

#这些名字不能用坐变量
import keyword
print(keyword.kwlist)


#设置变量
name ='Ali'
print(name)
print('id',id(name))
print('type',type(name))
print('value',name)

#set变量改变，变量指向新的赋值，之前的赋值会丢弃
name ='Ali'
name='Alii'
print(name)



#数据类型：int整数(1234) ，float浮点（3.11xx），布尔类型：bool（True，False）, str 字符类型（my name is Ali）

#int整数(+-01234)     十进制 defult 二进制：0b， 八进：0o 十六：0x
i1=90
i2=11
print(i1,type(i1))
print(i2,type(i2))
#不同进制下打印118
print('二进制',0b01110110)
print('八进制',0o166)
print('十进',118)
print('十六进',0x76)

#float浮点（3.11xx）
f=3.14125
print(f,type(f))
#float浮点的计算在python会模糊，不准确。这是因为二进制的底层问题
f1=1.1
f2=2.2
print(f1+f2)
#调用decimal 来进行计算就能避免这个问题
from _decimal import Decimal
print(Decimal('1.1')+Decimal('2.2'))

#布尔类型：bool（True=1，False=0）
b1= True
b2= False
print(b1,type(b1))
print(b2,type(b2))
#布尔可以转换称整数计算
print(b1+1)
print(b2+1)

#str 字符类型
s1='ali'
s2="ali"
s3="""ali  
love python"""
#'"只能在一行使用，“”“可以换行继续写

print(s1,type(s1))
print(s2,type(s2))
print(s3,type(s3))


#数据转换
name1='Ali'
age=111
print(type(name),type(age))
print("my name",name1)
print('I am',age,'years old')
#将age的int转换城str
print("my name",name1,'\tI am',age,'years old')
print("my name "+name1+'\t\t'+'I am '+str(age)+' years old')

#-------------全部转换城str:   ali is 11 years old ,True------------
s11="ali"
i11=11
b11=True
print(s11+' is '+str(i11)+' years old,'+str(b11))
#------------全部转换城int:    -1+3+11+1.11------------------------
s12="11"
i12=-1
f12=1.11
b12=True
print(i12+int(b12*3)+int(s12)+f12)
#------------全部转换城float:   -1.1+2.1+3.1------------------------
s13="3.1"
i13=-1
f13=2.1
b13=True
print(int(b13)-f13+f13+float(s13))
#------------全部转换城bool:  True True False False------------------
s14='0'
i14=0
f14=1.0
b14=False
print(bool(s14),bool(f14),bool(i14),b14)
#string转成Bool时，只有为空才会转成false，其他任何内容都会转换城Ture
```











### 18.April.2022     Chapter Three

```python
#coding UTF-8

#输出函数input ，输入的value默认为str

'''''
whoareu=input('Are u Ali?')
print(whoareu,type(whoareu))
'''''

'''''
#输入2个数字，并计算和
a=input('number1')
b=input('number2')
print(int(a)+int(b))
#or
a=int(input('number1'))
b=int(input('number2'))
print(a+b)
'''''

#   运算符
#标准运算符
print(3+2)      # +
print(3-2)      # —
print(3*2)      # *
print(3/2)      # /
print(3//2)     # // 取整
print(3%2)      # %  取余
print(3**2)     # ** 幂

#一正一负的整数公式 向下取整(永远是选择更小的数)
print(9//5)     #=1   9/5=1.8      向下取整 1
print(9//-5)    #=-2  9/-5=-1.8    向下取整 -2
print(9//-4)    #=-3  9/-4=-2.2    向下取整 为-3
print(-9//4)    #=-3  -9/4=-2.2    向下取整 为-3

#一正一负的取余公式   余数=被除数-除数*（被除数//除数）
print(9%-5)
print(9-(-5)*(9//-5))

print(-9%4)
print((-9)-4*((-9)//4))



#赋值运算符 从右到左
aa=3+4
print(aa)

#链式赋值
bb=cc=dd=20
print(bb,id(bb))
print(cc,id(cc))
print(dd,id(dd))

#参数赋值
ee=10
ee+=30
print(ee)

ff=10
ff-=30
print(ff)

gg=10
gg*=30
print(gg,type(gg))

hh=10
hh/=30
print(hh,type(hh))

#解包赋值
ii,jj,kk=10,20,30
print(ii,jj,kk)


#交换两个变量的value
ll,mm=10,20
print(ll,mm)
ll,mm=mm,ll
print(ll,mm)


#比较运算符
nn,oo=10,20
print("Does nn > oo?\n",nn>oo)
print("Does nn < oo?\n",nn<oo)
print("Does nn <= oo?\n",nn<=oo)
print("Does nn >= oo?\n",nn>=oo)
print("Does nn == oo?\n",nn==oo)
print("Does nn != oo?\n",nn!=oo)

'''
= 和== 的区别
=为赋值运算符，==是比较运算符
==是比较value
is 用来比较标识
'''

## is 用来比较标识(id)
pp=10
qq=10
print(pp is qq)         #  a b have same id
print(pp == qq)         #  a b have same value
print(pp is not qq)

list1=[11,22,33,44]
list2=[11,22,33,44]
print(id(list1))
print(id(list2))
print(list1==list2)
print(list1 is list2)
print(list1 is not list2)
print()


#布尔运算符
# and
rr,ss=1,2
print(rr==1 and ss>2)
print(rr==1 and ss<2)
print(rr==1 and ss==2)
print(rr==1 and ss>=2)
print(rr==1 and ss<=2)
print(rr==1 and ss!=2)
print(rr!=1 and ss!=2)
print()
# or
print(rr==1 or ss>2)
print(rr==1 or ss<2)
print(rr==1 or ss==2)
print(rr==1 or ss>=2)
print(rr==1 or ss<=2)
print(rr==1 or ss!=2)
print(rr!=1 or ss!=2)
print()

# not 调换结果
print(not ss>2)
print()

# in 和not in
tt='Ali'
print('A'in tt)
print('B'in tt)
print('A'not in tt)
print('B'not in tt)
print()

#位运算符  数据转为二进制进行计算
# 4 的二进制为 0 0 0 0 0 1 0 0
# 8 的二进制为 0 0 0 0 1 0 0 0
#&  二进制对应位置都为1 结果为1.否则为0
print(4&8)      #0 0 0 0 0 0 0 0 =0

#|  二进制对应位置都为0 结果为0.否则为1
print(4|8)      #0 0 0 0 0 1 0 0 =12

#<< 二进制向左移动一个位置  高位舍弃，地位补零 公式：x<<y=x*（2^y）
print(4<<1)     #0 0 0 0 1 0 0 0 =8
print(4*2**1)

print(22<<4)
print(22*2**4)
print()

#>> 二进制向右移动一个位置  高位补零，地位舍弃 公式：x<<y=x//（2^y）
print(4>>1)      #0 0 0 0 0 0 1 0 =2
print(4/2**1)
print(22>>4)    #0001 0110      0000 0001
print(22//2**4)  #0001 0110      0000 0001
print(99>>4)    #0001 0110      0000 0001
print(99//2**4)  #0001 0110      0000 0001

#运算优先级：
# （）
# 幂运算
# 乘 除 取正 取余
# 加减
# >><<位移
# & |
# < > == >= <= !=
# and or 布尔运算 
# = 赋值
```
