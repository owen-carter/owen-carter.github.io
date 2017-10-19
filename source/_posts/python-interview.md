---
title: python面试题大全
date: 2017-10-15 15:11:06
tags: web manage
---

Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

+ Python的函数参数传递
  ```python
  a = 1
  def fun(a):
      a = 2
  fun(a)
  print a  # 1
  ```
  
  ```python
  a = []
  def fun(a):
      a.append(1)
  fun(a)
  print a  # [1]
  ```
  
  > 所有的变量都可以理解是内存中一个对象的“引用”，或者，也可以看似c中void*的感觉。
    这里记住的是类型是属于对象的，而不是变量。而对象有两种,“可更改”（mutable）与“不可更改”（immutable）对象。在python中，strings, tuples, 
    和numbers是不可更改的对象，而list,dict等则是可以修改的对象。(这就是这个问题的重点)
    当一个引用传递给函数的时候,函数自动复制一份引用,这个函数里的引用和外边的引用没有半毛关系了.所以第一个例子里函数把引用指向了一个不可变对象,
    当函数返回的时候,外面的引用没半毛感觉.而第二个例子就不一样了,函数内的引用指向的是可变对象,对它的操作就和定位了指针地址一样,在内存里进行修改.
    如果还不明白的话,这里有更好的解释: http://stackoverflow.com/questions/986006/how-do-i-pass-a-variable-by-reference


+ Python中的元类(metaclass)



+ @staticmethod和@classmethod
  ```python
  def foo(x):
      print "executing foo(%s)"%(x)
   
  class A(object):
      def foo(self,x):
          print "executing foo(%s,%s)"%(self,x)
   
      @classmethod
      def class_foo(cls,x):
          print "executing class_foo(%s,%s)"%(cls,x)
   
      @staticmethod
      def static_foo(x):
          print "executing static_foo(%s)"%x
   
  a=A()
  ```
  > 这里先理解下函数参数里面的self和cls.这个self和cls是对类或者实例的绑定,对于一般的函数来说我们可以这么调用foo(x),
    这个函数就是最常用的,它的工作跟任何东西(类,实例)无关.对于实例方法,我们知道在类里每次定义方法的时候都需要绑定这个实例,
    就是foo(self, x),为什么要这么做呢?因为实例方法的调用离不开实例,我们需要把实例自己传给函数,调用的时候是这样的a.foo(x)(其实是foo(a, x)).
    类方法一样,只不过它传递的是类而不是实例,A.class_foo(x).注意这里的self和cls可以替换别的参数,但是python的约定是这俩,还是不要改的好.
    对于静态方法其实和普通的方法一样,不需要对谁进行绑定,唯一的区别是调用的时候需要使用a.static_foo(x)或者A.static_foo(x)来调用.


+ 类变量和实例变量
  ```python
  class Person(object):
      name="aaa"
   
  p1=Person()
  p2=Person()
  p1.name="bbb"
  print p1.name  # bbb
  print p2.name  # aaa
  print Person.name  # aaa
  ```