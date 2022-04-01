# Python-
python
#### 
* 1python是如何进行内存管理的 
  从三个方面来说
  1. 是对象的引用计数机制 
  作用：首先，对每个对象都可以进行追踪，方便调用；对与固定的数据对象（数字或者字符串），解释器会在程序的不同部分共用内存，从而节省内存；
  sys.getrefcount()
  2. 是垃圾回收机制
  当一个对象的引用技术归零时，就会被垃圾回收机制回收；
  循环检测器会定期筛查不可访问的对象循环，从而回收；
  3. 是内存池机制
  内存池机制，对小于256字节的用过pymalloc分配，对与内存比较大的用系统的malloc函数进行分配；python中的对象都有单独的私有内存池；

* 2random
random.random() #0-1
random.randint(a,b)#随机a-b之间整数
random.uniform(a,b)#随机a-b浮点数

* 3pychecker和pylint
pychecker是对代码的bug进行检查的
pylint是对代码的标准进行检查

* 4<.*> <.?>
贪婪匹配和满足匹配

* 5.match 和search()
```
print(re.match('zhangda','zhangdabusy'))

print(re.search('angda','zhangdabusy'))

print('zzz'.replace('z','d'))
<_sre.SRE_Match object; span=(0, 7), match='zhangda'>
<_sre.SRE_Match object; span=(2, 7), match='angda'>
ddd
```

* 6[::]
```
c=b[::-1]
print(c)
d=b[::-3]
print(d)
edcba
eb
```

* 7python 中的迭代器和生成器
一个类用到迭代器需要iter()和next()方法
StopIteration 是迭代器结束的标志
迭代器是一种对象；用iter()定义，用next调动下一个迭代器；
生成器其实是一个包括了yeild返回的函数，保存的是上一个程序返回时候的结果


* 8继承 多态 方法重写
子类从左向右继承父类
super(Child,c).myMethod() #用子类对象调用父类已被覆盖的方法

* 9私有方法 私有变量
__ 只能在类中使用

* 10arg kwarg 
arg是输入的参数
kwarg是关键词参数
*arg 是元组
**kwarg 是dict{}

* 11os.path time

```
import os
import time

print(os.path.getatime(__file__))#access_time
print(os.path.getctime(__file__))#create_time
print(os.path.getmtime(__file__))#correct_time
#/home/dir/1.txt
print(os.path.dirname(__file__))#/home/dir
print(os.path.abspath(__file__))#\home\dir\1.txt
print(os.path.basename(__file__))#1.txt
print(time.gmtime( os.path.getmtime(__file__)) ) #time.struct_time(tm_year=2022, tm_mon=3, tm_mday=29, tm_hour=13, tm_min=8, tm_sec=23, tm_wday=1, tm_yday=88, tm_isdst=0)
print(os.path.getsize(__file__)) #byte
```

* 12sys.stdin sys.stdout
```
sys.stdin sys.stdout
import sys
st_input=sys.stdin.readline()
print(sys.stdout.write(st_input))
st_output=open("1.txt",'w')
sys.stdout=st_output
print("hello1")
```

* 13sys.path sys.modules
+sys.modules
存放已经缓存的模块
值是dict
+sys.path
搜索路径
值是list
+if __name__= __main__
可以看成python的程序入口，如果直接执行该.py文件，那么执行后面的代码，如果作为模块导入，则不执行后面的代码

* 14parser.parse_known_args()
```
import argparse
def basic_options():
    parser = argparse.ArgumentParser()
    parser.add_argument('--data_mode', type=str, default= 'unaligned', help='chooses how datasets are loaded')
    parser.add_argument('--mode', type=str, default='test', help='test mode')
    return parser

def data_options(parser):
    parser.add_argument('--lr', type=str, default='0.0001', help='learning rate')
    return parser

if __name__ == '__main__':
    parser = basic_options()
    opt, unparsed = parser.parse_known_args()
    print(opt)
    print(unparsed)
    parser = data_options(parser)
    opt = parser.parse_args()
    print(opt)
    print('{data_mode}_{mode}_{lr}'.format(**vars(opt)))
```
[简书](https://www.cnblogs.com/wanghui-garcia/p/11267160.html)

* 15package、module、__init__、__name__ 、__all__、__main__、 

[简书](https://www.jianshu.com/p/cb97d290c17f)
[python内置函数](https://segmentfault.com/a/1190000000494023)

* 16@property
@property
def age():
@age.setter()
def age()
property的单独使用
或者age=property(get_age,set_age())

* 17 @装饰器
```
def funA(fn):
    # 定义一个嵌套函数
    def say(*args,**kwargs):
        fn(*args,**kwargs)
    return say
@funA
def funB(arc):
    print("C语言中文网：",arc)
@funA
def other_funB(name,arc):
    print(name,arc)
funB("http://c.biancheng.net")
other_funB("Python教程：","http://c.biancheng.net/python")
```


