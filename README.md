# Python-
# 1python是如何进行内存管理的
从三个方面来说
一是对象的引用计数机制 
  作用：首先，对每个对象都可以进行追踪，方便调用；对与固定的数据对象（数字或者字符串），解释器会在程序的不同部分共用内存，从而节省内存；
  sys.getrefcount()
二是垃圾回收机制
  当一个对象的引用技术归零时，就会被垃圾回收机制回收；
  循环检测器会定期筛查不可访问的对象循环，从而回收；
三是内存池机制
  内存池机制，对小于256字节的用过pymalloc分配，对与内存比较大的用系统的malloc函数进行分配；python中的对象都有单独的私有内存池；

# 2 random
random.random() #0-1
random.randint(a,b)#随机a-b之间整数
random.uniform(a,b)#随机a-b浮点数

# 3 pychecker和pylint
pychecker是对代码的bug进行检查的
pylint是对代码的标准进行检查

# 4 <.*> <.?>
贪婪匹配和满足匹配

# 5 re.match 和search()
print(re.match('zhangda','zhangdabusy'))

print(re.search('angda','zhangdabusy'))

<_sre.SRE_Match object; span=(0, 7), match='zhangda'>
<_sre.SRE_Match object; span=(2, 7), match='angda'>

# 6 [::]
c=b[::-1]
print(c)
d=b[::-3]
print(d)
edcba
eb

# 7python 中的迭代器和生成器
一个类用到迭代器需要iter()和next()方法
StopIteration 是迭代器结束的标志
迭代器是一种对象；用iter()定义，用next调动下一个迭代器；
生成器其实是一个包括了yeild返回的函数，保存的是上一个程序返回时候的结果


# 8继承 多态 方法重写
子类从左向右继承父类
super(Child,c).myMethod() #用子类对象调用父类已被覆盖的方法

# 9私有方法 私有变量
__ 只能在类中使用











