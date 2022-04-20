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





### 19.April.2022     Chapter Four

```python
#coding utf-8


#程序组织的击结构
'''''
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
'''''
import sys

'''''
#选择结构
#单分支结构
print('entry how much money u want to take')
money=100
s=int(input())
if money >= s:
    money= money-s
    print('sucess！you have',money,'left')
else:
    print('sorry,you dont have enogh money in ur account')
'''''
'''''

#多分枝结构

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
'''''

'''''
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


'''''


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







### 20.April.2022     Chapter Five

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
