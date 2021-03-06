学习一个语言的思想，设计初衷，为什么有这个特性而每那个特性。

### 好的东西 

1. interface，是个全新的抽象，感觉组织好go程序很重要的东西，类似鸭子类型，不需要接口和实现间的耦合，可以动态的调用方法。
1. 函数可以返回多个值，像python
1. 从字典里探测和取出item，一步完成，类似.net的tryparse模式，人性化的改进
1. 模块化，比C强多了，可以很好的组织代码。
1. 类型推导，介绍了不少枯燥无味的类型声明，类似csharp的var。
1. 数组切片，内置len等函数，对这些最常用功能的支持，感觉比较贴心，有python的感觉。
1. switch语句的增强，更有可读性，类似f#的模式匹配,很强大了。
1. 针对通道的select语句也很创新，在面向消息的并发模型下进行逻辑流同步，还能实现操作超时的功能。
1. 有map的概念，算是最常用的数据结构,而且还和json数据能互相的序列化和解序列化，这对数据表达和传输提供了极大的便利。
1. GC，与时俱进，最需要的东西，希望性能和功能能满足服务端程序的场景。
1. struct的初始化语法，很方便，像c#的数组和类型初始化语句。
1. defer语句类似try finally语句或类的析构函数，防止资源泄露
1. 协程的支持，好多多线程模型的问题不需要考虑了，而且随便的起逻辑流，很好的特性。

### 没有的东西

go故意不增加一些特性，让我们重新思考已经熟悉的一些语言特性的真正价值，很好。


1. 没有断言：单元测试用if语句和error来做，也够用了其实。
1. 没有类，没有类就不需要花时间去定义各种类的结构，关系了，没有类其实挺好的，有模块来划分组织函数就好了。
1. 没有泛型：go根本就没有完整的类型系统，所以go的世界里根本不需要泛型，而且泛型会增加运行时的负担。
1. 普通接口：go的思想不是普通的面相对象思想，没有类的概念，所以普通面向对象的接口在这里没意义。
1. 结构化异常处理：go认为异常被滥用了，导致代码逻辑混乱，其实感觉item, ok = func()的方式进行错误处理是个很新颖的实践
1. 只有数组，没有高级语言的list的概念，不能动态扩大数组，但用slice能很简单的封装一些类似list的操作。
1. 默认参数，没有这个，理由貌似是会让代码看起来不直观。
1. 方法重载和操作符重载：go连类型系统都没有，还重载啥呀，而且重载确实让代码可读性降低。

go没有增加的特性，大概的感觉就是因为

1. 加了很好，但是不加的话，写几行代码也能解决这个问题，所以就不加了，如泛型，list, 断言。
1. 不认可这些语言特性的价值，认为有更好的方式，如结构化异常处理, 函数的默认参数。
1. 为了保持语言精简，编译器编译速度更快，程序运行速度更快。

关于语言设计时的一些考虑和抉择，官方有文章回答了大多数的问题：[这里](http://golang.org/doc/faq#Design)
