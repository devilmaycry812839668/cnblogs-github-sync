---

title: python的debug—pdb的使用笔记
 
description: 

#多个标签请使用英文逗号分隔或使用数组语法

tags: 杂谈

#多个分类请使用英文逗号分隔或使用数组语法，暂不支持多级分类

---

相关：

[【python】来学学debugger吧，不能只会用print调试呀！](https://www.youtube.com/watch?v=oyIJOCSgTM0)

<br/>

虽然写了这么多年的代码，不论是C++还是python，我几乎都没有使用过debug，当然这并不是说我写的代码从来不出问题，而是我几乎都是用print的方法，或者直接头脑风暴，但是我并不是不认为debug没有用，而是我一直没有遇到需要debug的代码，当然这可能和自己的代码量和任务类型有关，但是我依然认为写代码还是应该需要掌握debug的技术。

<br/>

修改源码的方式进行debug：

源码中加入       breakpoint()



<br/>

p  打印变量；

w  打印当前栈；

l    打印当前行附近代码(连续输入l代表向下再显示一定的行数)；

l.   回到当前函数；

ll   显示当前函数的所有代码；

u   切换到上一帧；

d   切换到下一帧；

n    向下运行一行程序（跳出方式，跳出调用的函数）；

s     向下运行一行程序(step方式，进入调用的函数)；

until   运行到比当前行的行数大的行，跳出循环所常用的方法；

until+数字   运行到指定行；

r       运行到函数的返回处（运行到所在函数的return处，return）；

retval   上一个调用函数的返回值；

c        跳出当前调试，接着运行；

clear+数字    删除指定号的断点，b显示断点情况，打印断点号，再使用clear清除掉指定的断点；    

<br/>



不修改源码的方式debug：

python -m pdb   example.py  

<br/>

b        设置断点（b   5    在第5行设置断点），不加数字表示打印出所有断点的位置；

b        b+函数名，断点设置为运行到某函数，停留在这个还是的return处；

<br/>

**PS:**

自己写的代码或许不用debug，但是如果是review其他人写的代码，估计还是要用到debug的。

<br/>

<br/>

**个人github博客地址：**
[https://devilmaycry812839668.github.io/](https://devilmaycry812839668.github.io/ "https://devilmaycry812839668.github.io/")