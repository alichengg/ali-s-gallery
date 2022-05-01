---
layout: post
title: Python Self-Study log. Updating....
date: 2022-04-16
Author: Ali
categories: 
tags: [Python]
comments: true
---

This page I use to push me to study and will continue to be updated for more than one month. 











### 16.April.2022     Chapter one----- \n   \t    \t   \r  \b

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









### 17.April.2022     Chapter Two-----int ，float，bool, str 

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











### 18.April.2022     Chapter Three-----运算符

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


#range()的三个创建方式
#只有一个参数 默认从0开始 步长为一
r=range(10)
print(list(r))
#两个个参数 第一个数字为起始  步长默认为一
rr=range(1,10)
print(list(rr))
#三个个参数 第一个数字为起始  第三个数字为步长
rrr=range(1,10,2)
print(list(rrr))
#判断一个数字是否在序列中
print(11 in rrr)
print(1 in rrr)
print(11 not in rrr)
```





### 19.April.2022     Chapter Four-----顺序结构

```python
#coding utf-8

#程序组织的击结构

#顺序结构
print('open computer')
print('open pycharm')
print('coding')
print('test')

#对象布尔value为false的情况    false ,int =0 ,None, 空字符，空列表，空元组，空字典，空集合
print(bool(False))
print(bool(None))
print(bool(0))
print(bool())
print(bool(''))
print(bool(""))
print(bool((list())))
print(bool([]))
print(bool(set(())))

import sys

#---------------------------------选择结构---------------------
#----------单分支结构-----------
print('entry how much money u want to take')
money=100
s=int(input())
if money >= s:
    money= money-s
    print('sucess！you have',money,'left')
else:
    print('sorry,you dont have enogh money in ur account')


#-----------多分枝结构----------

print('Entry how much money left in ur accout')
money=int(input())
if money>=100000:
    print('you are rich')
elif money>=100 and money<=100000:
    print('you are  soso')
elif 100 >= money >= 10:
    print('you are poor')
elif money <= 10:
    print('really? Are u kindding me')



print('A Are you good at fight?')
a=input(str())
d='yes'
e='no'
if a==d :
    print('not bad')
elif a==e:
    print('you are rabbish..')

print('B Are you good at fight?')
b=input(str())
if b==d :
     print('not bad')
elif b==e:
    print('you are rabbish..')

print('Well')
if a==b==e:
    print('you guys are all rabbish')
elif a==b==d:
    print('you guys are all good fight')
else:
    print('OK')


#直接吧变量放入if 语句时，就会按照bool判断
age=int(input('How old are u?\n'))
if age:
    print(age)
else:
    print('Are u kidding? you are',age,'years old?')

    

#-------------------------循环结构 while----------------
a=1
while a<10:
    print(a)
    a+=1

#初始化变量
#条件判断
#条件执行模块
#改变变量

sum=0
a=0
while a<5:
    sum+=a
    a+=1
print(sum)

#1- 100的偶数合
sum=0
a=0
while a<=100:
    sum+=a
    a+=2
print(sum)


#--------------------------For in 循环-----------------
for item in  'Python':
    print(item)


for item1 in range(10):
    print(item1)


#for 可以在 执行循环中不需要变量，可以写作_
for _ in range(10):
    print("Python nuberone")

```









### 20.April.2022    Practice-----bank ATM System

```python
#Practice
m=moneyinbank=int(1000)
passwordinbank='123'

print('Welcome to Ali bank')
print('Plz insert ur bank card')
cardid='Acard'
a=input(str())
if a==cardid:
    print('wait a second..')
    print('PLZ entry ur password')
    list=[1,2,3]
    name=1
    for _ in range(3):
        password = str(input())
        if password==passwordinbank:
            for _ in range(6):
                print('how much moeny u want to take')
                money = int(input())
                if money > moneyinbank:
                    if money > moneyinbank:


                        for _ in range(3):

                            if money > moneyinbank:
                                print('Sorry, you dont have enogh money in here')
                                print('Type yes to contiue or type any to exit')

                                chic = input(str())
                                chic1 = 'yes'
                                chic2 = 'no'

                                if chic == chic1:
                                    break
                                else:
                                    sys.exit('OK!thanks for ur using')
                            else:
                                break
                    else:
                        continue
                elif money <= moneyinbank:
                    print('wait a second..')
                    print('Success! you still have $', moneyinbank - money, 'in your accout')
                    moneyinbank = moneyinbank - money
                    print('log out or transfer money again?')
                    for _ in range(100000):
                        chice=input(str())
                        chice1='log out'
                        chice2='again'
                        if chice == chice2:
                            print('ok')
                            break
                        elif chice==chice1:
                            sys.exit('thanks for ur using')
                        else:
                            print('???')
            else:
                sys.exit('Too Much operation,Plz try later')

        else:
            print('Wrong Password')

    else:
        print('Too Much wrong operation.pleaze try later')
else:
    print('Wrong card!plz using Acard')

```











### 21.April.2022     Chapter Five------list

```python
#UTP-8


#列表  列表相对一个 容器，可以储存多个元素，不同数据类型
list=['hello',98,False,0.0001]

#列表是有序排列的
print((list))

#列表通过索引获取  从左到右：0 1  2  3 ...分别对应列表里位置的value 从右到左：-1 -2 -3 .。。。
print(list[2])
print(list[-2])

#列表里的内容可以重复
list1=['hello',98,False,False]

#列表里的内容可以混

#列表会动态存储，会自动分配内存


#列表查询  如果列表里有相同的元素，只会回馈第一个
list2=['hello',98,False,0.0001,'hello',123123,123123,444123,11321]
print(list2.index('hello'))
print(list[0])
#指定位置列表查询      例如在3-10之间查询，
print(list2.index('hello',3,10))

#获取索引为0的元素
print(list[0])

#获取列表的多个元素    切片
#start（包括，默认为0）：stop（不包括）：step（默认为1）

list3=['hello',98,False,0.0001,'hello',123123,113,444123,11321]
#切片也可以拉出来单独使用
list4=list3[1:3:1]
print(list4)

#start（默认为0）：stop（默认为最后一个也包括最后一个）：step（默认为1）
list5=list3[:3:1]
print(list5)
list6=list3[1::1]
print(list6)
list7=list3[1:3:]
print(list7)

#数列中 会同时存在正负，step的-号要小心使用
list8=list3[-2:2:-2]
print(list8)

list9=list3[2:-2:2]
print(list9)

#查询是否存在   元素 in/not in 数列
list10=['hello',98,False,0.0001,'hello',123123,113,444123,11321]
print(98 in list10)
print(98 not in list10)

#遍历列表元素
for item in  list10:
    print(item)

#列表   增 删除

#向列表末尾添加一个元素
list11=['hello',98,False,0.0001,111]
print(list11,id(list11))
#append 添加一个元素
list11.append('Ali')
print(list11,id(list11))
#extend 添加一个列表
list12=['aliiii',123123,5555]
list11.extend(list12)
print(list11,id(list11))

#insert 在固定位置添加元素
list11.insert(1,'world')
print(list11,id(list11))

#insert 在固定位置添加切片

#添加切片
list13=[1,2]
list11.insert(1,list13)
print(list11)

#覆盖切片
list11[1::]=list13
print(list11)

#列表删除   重复的元素 只会删除第一个
list15=['aliiii',123123,5555,True,9999]
list15.remove('aliiii')
print(list15)

#根据索引删除   pop默认value是-1  只能删除单个
list15=['aliiii',123123,5555,True,9999]
list15.pop(-3)
print(list15)

#删除多个
list15=['aliiii',123123,5555,True,9999]
list15[1:2]=[]
print(list15)


#清除列表里的所有元素
list15=['aliiii',123123,5555,True,9999]
list15.clear()
print(list15)


#提取或者说截取切片
list15=['aliiii',123123,5555,True,9999]
newlist=list15[1:3:1]
print(list15,id(list15))
print(newlist,id(newlist))

#修改列表元素
#修改一个值
list15=['aliiii',123123,5555,True,9999]
list15[2]=100
print(list15)

#修改一个值
list15=['aliiii',123123,5555,True,9999]
list15[0:3]=[1,2,3]
print(list15)


#列表排序
#้升序排列
list16=[1123,235,2133,114,35,4444446]
print(list16)

list16.sort()
print(list16)

#降序排列
list16.sort(reverse=True)       #降序
print(list16)
list16.sort(reverse=False)      #升序
print(list16)

#内置函数sorted  列表id会改变

list16=[1123,235,2133,114,35,4444446]
print(list16)
newlist16=sorted(list16)
print(newlist16)


newlist16=sorted(list16,reverse=True)
print(newlist16)

#列表生成公式
#for i in range(1,10):
#    print(i)

listi=[i for i in range(1,10)]
print(listi)

#列表生成公式也可用算法
listi=[i+1 for i in range(1,10)]
print(listi)

listi=[i*2 for i in range(1,10)]
print(listi)
```







### 22.April.2022     Chapter Six------dict

```python
#

#字典  通常一对存在 ：键+值

#字典是无序的
#键会先经过Hash计算，来确定顺序

#python的字典 是根据key 查找 value所在的位置

#创建字典
scores={'Ali':20,'Alii':99,'Allllli':98}
print(scores)
#or
name1=dict(name='ali',age=20)
print(name1)
#空字典
scores={}
print(scores)

#获取字典中的value
scores={'Ali':20,'Alii':99,'Allllli':98}
print(scores['Ali'])
#print(scores['Aliasdasd'])    #会报错
#or
#get 只能通过key查询value
print(scores.get('Ali'))
print(scores.get('Aliasdasd')) #使用get不会保持，不存在时会直接回馈一个 None
print(scores.get('aliiie',99))     #如果用99查找‘aliiie’所对应的value不存在时，就输出99

#键的判断      可以用key 查询value，也可以用value 查询key
scores={'Ali':20,'Alii':99,'Allllli':98}
print('Ali' in  scores)
print('Ali' not in  scores)
print(20 not in  scores)


#删除 字典中的key-value pair
del scores['Allllli']
print(scores)
#清空字典
scores.clear()
print(scores)

#增加一个key-value pair
scores['alic']=1100
print(scores)

#修改一个key-value pair  用key去修改value ，不能用Value 去修改key
scores['alic']=11
print(scores)


#视图操作
scores={'Ali':20,'Alii':99,'Allllli':98}
#获取所有key
key1=scores.keys()
print(key1)
print(list(key1))

#获取所有value
value1=scores.values()
print(value1)
print(list(value1))

##获取所有key-value pair
items=scores.items()
print(items)
print(list(items))   #转换后的列表元素由元组组成

#字典元素的遍历
scores={'Ali':20,'Alii':99,'Allllli':98}
for item in scores:
    print(item,scores[item])

for item in scores:
    print(scores.get(item))   #

#字典里的key-value pair ，key不容许重复，但是value可以重复
#如果Key相同，后面的代替前面的
dicc={'math':10,'PE':99,'IT':11,'IT':12}
print(dicc)
#value可以重复
dicc={'math':10,'PE':99,'IIT':12,'IT':12}
print(dicc)

#字典对内存的浪费比较大
#字典生成式 zip
bankaccout1=['Ali','Bill','Cerry','Deinal']
moneyinaccout1=[100,200,300,400]

#A1=['A','B','C','D']
#B1=[1,2,3,4]
#  X={A:B for A,B in zip(A1,B1)}

dicccc={bankaccout:moneyinaccout for bankaccout,moneyinaccout in zip(bankaccout1,moneyinaccout1)}
print(dicccc)

#生成字典会按照顺序逐一配对，多余的会被忽略
```







### 23.April.2022     Chapter Serve------Tuple

```python
#元组

#不可变序列  没有增加 删除 改写的操作

#可变序列  列表，字典
list1=[1,2,3]
print(list1)
#不可变序列
s='hello'
s=s+'\tworld'
print(s)

#列表  l=[]
#字典  d={}
#元组  t=()

t=('hello',"my name",'Ali',199)
print(t)
print(type(t))
#or
t1=tuple(('hello','my name','Ali',12))
print(t1)
print(type(t1))
#or
t2='hello','my name','Ali',123
print(t2)
print(type(t2))

t3=tuple('Hello')
print(type(t3))

#如果元组里 只有一个元素 ，需要在加，用于辨别
t4='hello'
print(type(t4))

t5='hello',
print(type(t5))
#空元组
#空列表
list3=[]
dico={}

t6=(tuple())
print(t6)

#a 元组储存的都是不可变对象
t7=(1,[2,3],4,5)
print(t7)
#当您尝试像访问函数一样访问列表时，请确保使用方括号而不是大括号来访问或更改列表中的值。
print(t7[0],type(t7[0]),id(t7[0]))
print(t7[1],type(t7[1]),id(t7[1]))

#t7[1]=100
#print(t7)
#can add 元素 到元组的列表中
t7[1].append(6)
print(t7)

#元组遍历
t8=(1,2,4,3,5)
print(t8[0])
print(t8[2])
print()
#元组循环语句遍历
bl=-1
for _ in t8:
    bl = bl + 1
    if bl ==0:
        print(t8[bl])
    else:
        print(t8[bl])
#or
for _ in t8:
    print(_)
        
```





### 24.April.2022     Chapter Eight------Set

```python
#集合

#集合与字典一样，不过集合只有key 没有value

s={1,1,2,3,4,5,6}  #集合里的元素不能重复
print(s)
#or
s1=set(range(6))
print(s1)
#or 数列转集合
s2=set([1,2,3,4,5,6,7,7,7,7,7])
print(s2)
#or 元组转集合
s3=set((1,1,2,3,3,4,5,0))
print(s3)
#or 字典转集合
s5=set({1,2,3,4,4,4,5})
print(s5)

s4=set('I love python')
print(s4)
#空集合
s6=set()
print(s6)


####集合的相关操作
#集合里的元素判断  in or not in
s7={1,2,3,4,5}
print(1 in s7)
print(1 not in s7)
#集合元素增加  add+1     update+多个
s7.add(80)
print(s7)

s7.update({777,77723,222})
print(s7)

s7.update([74,7333,212])
print(s7)

s7.update((7772,123,778,1123))
print(s7)

#集合元素删除      remove 删除不存在的元素时会报错，但是discard 不会
s7.remove(74)
print(s7)

s7.discard(111)
print(s7)

#pop 随机删除一个元素，pop里不能赋予任何参数
s7.pop()
print(s7)
#pop 删除全部
s7.clear()
print(s7)


#-------------集合之间的关系-------------
s8={1,2,3,4,5}
s9={1,2,3,4,5}
s10={2,3,4,5,6}
s11={3,4,5,6}
s12={3,4,5,6}

print(s8==s9)
print(s10!=s9)

#子集     s11在不在s10中
print(s11.issubset(s10))
print(s12.issubset(s11))    #如果两个集合相同，那他们互为子集和超集
#超集     s10包含s11吗
print(s10.issuperset(s11))
print(s12.issuperset(s11))

#交集     isdisjoint意思没有交集    语句的意思是 s8和s11是否没有交集
#isdisjoint 返回false为有交集   返回True表示没有交集
print(s8.isdisjoint(s11))


#----------------集合的数学操作--------------------
#交集
s8={1,2,3,4,5}
s11={3,4,5,6}


print(s8.intersection(s11))
#or
print(s8 & s11)

# 并集
print(s8.union(s11))
#or
print(s8|s11)

# 差集
print(s8.difference(s11))
#or
print(s8-s11)

print(s11.difference(s8))

# 对称差集   排除都有的，剩下的就是对称差集
print(s8.symmetric_difference(s11))
#or
print(s8^s11)

#----------------集合生成公式--------------------

s20={i*i for i in range(6)}
print(s20)
```





### 30.April.2022     Chapter nine------字符串操作

```python
#------------字符串的驻留机制-------------
#优点：优化内存
a='python'
b="python"
c='''python'''
print(a,id(a))
print(b,id(b))
print(c,id(c))

#------------字符串查询操作-------------
#index()    查找字符串第一次出现的位置         查不到   value error
#rindex()   查找字符串最后一次出现的位置       查不到   value error
#find（）    查找字符串第一次出现的位置         查不到    返回-1
#rfind（）   查找字符串最后一次出现的位置       查不到    返回-1


d='hello,my name is Ali，hello'

print(d.index('hello'))
print(d.rindex('hello'))
print(d.rindex('my'))
print(d.find('name'))
print(d.rfind('Ali'))

#------------字符大小写转换-------------
#upper()        把所有字符串转成大写字母
#lower()        把所有字符串转成小写字母
#swapcase()     把字符串所有的大写字母转成小写字母，把所有的小写字母转成大写字母
#capitalize()   把第一个字符转换成大写，把其余字符转换成小写
#title()        把每个单词的第一个字符转换成大写，剩余的转成小写

e='hello,my name is Ali'
print(e,id(e))

f=e.upper()
print(f,id(f))

g=e.lower()
print(g,id(g))

i=e.swapcase()
print(i,id(i))

j=e.capitalize()
print(j,id(j))

k=e.title()
print(k,id(k))
#字符串转换后 id改变，产生了新的字符串对象

#------------字符串对齐-------------
#center(x,'y')       居中对其      Center函数中需要给与参数，x代表空间，表示字符在多大的空间中居中。‘y’用来填补居中后剩余的空间，默认为空格
#ljust(x,'y')        居左对其      ljust函数中需要给与参数，x代表空间，表示字符在多大的空间中居中。‘y’用来填补居中后剩余的空间，默认为空格
#rjust(x,'y')        居右对其      rjust函数中需要给与参数，x代表空间，表示字符在多大的空间中居中。‘y’用来填补居中后剩余的空间，默认为空格
#zfill(x)            居右对其      zfill函数会使用0进行填充，只能指定空间大小

e='hello,my name is Ali'

print(e.center(30,'!'))
print(e.center(30))     #默认为空格
print(e.center(5,'!'))  #当设定的空间小于字符串的长度时，会直接返回原字符

print(e.ljust(30,'!'))

print(e.rjust(30,'!'))

print(e.zfill(30))

#zfill函数会把 字符串首位的+和- 提到第一位，其余运算符都不会。
l='+a123sdds454'
print(l.zfill(30))

#------------字符串分割-------------
#split                          从字符串左开始分割，默认的 分割识别符 是空格，返回值为一个字符串列表
#split（sep='x'）                通过参数sep来指定 分割识别符,x可以为任意字符
#split（sep='x',maxsplit=y）     追加maxsplit来定义最大分割次数y，分割了y次后，剩余字符全部为一个部分

#rsplit                         定义用法都与split一样，只不过是从右边开始
#rsplit（sep='x'）
#rsplit（sep='x',maxsplit=y）

e='hello my name is Ali'
ee='hello,my,name,is,Ali'

print(e.split())
#or
list1=e.split()
print(list1)
print(ee.split(sep=','))
print(ee.split(sep=',',maxsplit=1))

print(e.rsplit())
print(ee.rsplit(sep=','))
print(ee.rsplit(sep=',',maxsplit=1))

#------------字符串的判断-------------
#isidentifier()                 判断指定的字符串是不是合法的标识符 （数字，字母和下划线）
#isspace()                      判断指定的字符串是不是全部右空白字符组队（回车，换行，水平制表符）
#isalpha()                      判断指定的字符是不是全部由字母组成
#isdecimal()                    判断指定的字符串是不是全部由十进制的数字组成
#isnumeric()                    判断指定的字符串是不是全部由数字组成
#isalnum()                      判断指定的字符串是不是由数字和字母组成

m='hello,my,name,is,Ali'

print('1.',m.isidentifier())
print('2.','ali_1'.isidentifier())
print('3.','ali_1'.isidentifier())
print('4.','Ⅰ'.isnumeric())     #罗马数字也是数字
print('4.','一'.isnumeric())     #中文数字也是数字

#------------字符串的替换合并-------------
#repale('x','y',z)                replace可以替换参数,'x'为被替换的参数，‘y’为替换参数，z定义换几次
#'x'.join()                       join将列表或元组合并，'x'为连接符

m='hello,my name is Ali'
print(m.replace('is','is not'))

mm='hello,hello,hello,my name is Ali'
print(mm.replace('hello','',2))

list1=['hello', 'my', 'name','is', 'Ali']
print('\t'.join(list1))

t=('hello', 'my', 'name','is', 'Ali')
print(' '.join(t))

print(' '.join('ALI'))

#------------字符串的比较-------------
#   >   >=     <    <=     ==  !=
#规则：逐一比较
#原理：比较 ordinal value(原始值)

#ord 查询字符的对应的原始值
print(ord('a'),ord('b'),ord('c'),ord('d'),ord('e'),ord('f'),ord('g'),ord('h'))
print(ord('1'),ord('2'),ord('3'),ord('4'),ord('5'),ord('6'),ord('7'),ord('8'))
print(ord('Ⅰ'),ord('Ⅱ'),ord('Ⅲ'),ord('Ⅳ'),ord('Ⅴ'))
print(ord('我'),ord('是'),ord('谁'),ord('啊'))
print(ord('の'))

#chr利用ordinal value查询对应的字符
print(chr(97),chr(98),chr(99),chr(100),chr(101),chr(102),chr(103))

#== 与 is 的区别
#   == 比较的是value
#   is 比较的是id


#------------字符串切片-------------
#字符串切片不具备增 删 改 操作
#切片后产生新的对象(id  改变)
# X[start:end:step]


m='hello,my,name,is,Ali'
s=m[:6]      #没有设定开始值
print(s)

t=m[6:]
print(t)

newone =s+t
print(newone)

u=m[1:11:2]
print(u)

v=m[-3::1]
print(v)


#------------字符串格式化-------------
#作用在格式文件， 按照一个模板来修改内容的情况下使用

#两种方式：
# 1.%作占位符
#       %s--字符串      %d---整数      %f---浮点数
#       'xxxxx:{0}，xxxx{1}'.%(x,y)
name='Ali'
age=11
print('Hello,My name is %s, I am %s years old'%(name,age))


# 2.{}作占位符
#       'xxxxx:{0}，xxxx{1}'.format(x,y)

print('Hello,My name is {0}, I am {1} years old'.format(name,age))

# 3.f-string
#       f'xxxxx:{x}，xxxx{y}'

print(f'Hello,My name is {name}, I am {age} years old')

#------------整数格式化-------------
# 整数：'%xd' %y          x为空间大小，y为内容，如果空间小于输入内容，则直接打印结果
print('%11d' %11123123)

# 浮点数：'%xf' %z                          x为空间大小，z为内容，默认浮点数最大会保留8位，多了四舍五入，少了用0补齐
# 浮点数：'%.yf' %z                         .y为保留小数点后的位数
# 浮点数：'%x.yf' %z                        x为空间大小，.y为保留小数点后的位数，z为内容
print('%11f' %1.11)
print('%.1f' %1.1123123)
print('%20.9f' %1.11231212312388232123763)
#or
# 浮点数：'{start:x.yf}'.format(z)        x为空间大小，.y为保留小数点后的位数，z为内容
print('{0:20.9f}'.format(1.11231212312388232123763))



#------------字符串编码转换------------
#计算直接传输时，需要把string转换位Unicode
#方法：
#       编码：将string转换位二进制（bytes）
#       解码：将（bytes）类型的数据转换位string

#在使用编码解码时，要确保编码方式和解码方式一致
#编码
w='你好，我叫Ali'    #Hello,my name is Ali
byte=w.encode(encoding='UTF-8')
print(byte)
# 解码
print(byte.decode(encoding='UTF-8'))
```



### 1.May.2022     Chapter Ten------Function

```python
#函数

#函数指的是 具有一个特定功能的一段代码
#为什么用函数
#重复的功能可以用函数来代替
#可以隐藏实现的细节
#可以提高可维护性，因为是调用，所以修改函数就可以全局更改
#便于调试

#---------------------函数的创建---------------------
def sum(a,b):           #a，b都是形式上的参数，它被用于定于
    c=a+b
    return c
#---------------------函数的调用---------------------
sumab=sum(1,2)          #1，2是实际上的参数，它被用于调用
print(sumab)

#---------------------函数的参数传递-------------------
def sum(a,b):
    c=a+b
    return c

sumab=sum(1,2)          #基于位置
print(sumab)
#or
def sum(a,b):
    c=a+b
    return c

sumab=sum(b=1,a=2)      #基于关键字
print(sumab)

#可变对象和不可变对象在参数传递后的变化规则

def fun1(a,b):
    a=100
    b.append(11)

numb1=11                #可变对象
numb2=[1,2,3]           #不可变对象

result=fun1(numb1,numb2)
print(numb1,numb2)

#why result is 11 [1, 2, 3, 11]？
#不可变对象不会受到传递参数的影响，在numb1=11传递到函数时，numb1只在函数内发生了变化，并不会受到实际的影响
#可变对象会受到函数的影响，


#---------------------函数的返回值-------------------
#区分奇数偶数
def re_odneven(num):
    odd=[]
    even=[]
    for i in num:
        if i%2:
            odd.append(i)
        else:
            even.append(i)
    return odd,even

print(re_odneven(range(1,20)))

#函数的返回值
#   1.如果函数没有返回值（函数执行完成后，不需要给调用处提供数据） return可以省略
def fun1():
    print('Hello, I am Ali')
    #return
print(fun1())

#   2.函数的返回值如果1个，直接返回原类型
def fun2():
    return 'Hello, I am Ali'
print(fun2())

#   3.函数的返回值如果多个，则返回一个元组
def fun3():
    return 'Hello','I','am','Ali'
print(fun3())

#是否需要写return 需要视情况而定


#---------------------函数的参数定义-------------------
#默认值参数
def func(a,b=11):      #b在函数数时，被赋予了一个值，这就意味着b的默认值为100
    c=a+b
    return c

print(func(90))         #a会被90代替，但由于没有第二数字，b就会使用函数里的默认值
print(func(90,70))

#-------------个数可变的位置参数     在函数定义中，只能定义一个个数可变的位置参数
#不确定 位置 实际参数的个数
#采用*定义
#返回结果会为一个元组
def funca(*args):
    print(args)

funca(1)
funca(1,2,3,4)
#------------个数可变的关键字形参     在函数定义中，只能定义一个个数可变的关键字形参
#不确定 关键字 实际参数的个数
#采用**定义
#返回结果会为一个字典
def funca(**args):
    print(args)

funca(a=1)
funca(a=1,b=2,c=3,d=4)

''''
#在函数定义中，只能定义一个个数可变的位置或关键字参数
def funca(*args,*a):
    print(args)

funca(1,2)
'''
#but 可变的位置和关键字参数 可以同时使用,但必须遵从顺序， 位置可变参数在前， 可变关键字参数在后，否则会报错
print()
def funca(*a,**b):
    print(a)
    print(b)
funca(1,b=2)

#---------------------函数的参数传递转化-------------------
def sum(a,b,c):
    d=a+b+c
    return d

list1=[1,2,3]
print(sum(*list1))      #*将列表里的每个元素都转换为位置实际参数

#or
def sum(a,b,c):
    d=a+b+c
    return d

dic1={'a':1,'b':2,'c':3}
print(sum(**dic1))      #*将字典里的每个key值对都转换为关键字实际参数


#函数定义形参时，可以同时采用位置和关键字参数，使用时用*号分割，但必须遵从顺序， 位置可变参数在前， 可变关键字参数在后，否则会报错
def sum(a,b,*,c):
    d=a+b+c
    return d

print(sum(1,2,c=99))

#组合方式

def sum(a,b,*c,**d):
    pass

def sum(*c,**d):
    pass

def sum(a,b=1,*c,**d):
    pass
```
