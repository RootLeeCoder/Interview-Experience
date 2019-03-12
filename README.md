# Interview-Experience_01

## 抽象类和接口的区别

- 抽象类是用来捕捉子类的通用特性的，它不能被实例化。抽象类是不完整的，它只能用作基类。抽象类主要用来进行类型隐藏和充当全局变量的角色。
- 接口是抽象方法的集合。如果一个类实现了某个接口，那么它就继承了这个接口的抽象方法。接口只是一种形式，接口自身不能做任何事情。

| **参数**           | **抽象类**                                                   | **接口**                                                     |
| ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 默认的方法实现     | 它可以有默认的方法实现                                       | 接口完全是抽象的。它根本不存在方法的实现                     |
| 实现               | 子类使用**extends**关键字来继承抽象类。如果子类不是抽象类的话，它需要提供抽象类中所有声明的方法的实现。 | 子类使用关键字**implements**来实现接口。它需要提供接口中所有声明的方法的实现 |
| 构造器             | 抽象类可以有构造器                                           | 接口不能有构造器                                             |
| 与正常Java类的区别 | 除了你不能实例化抽象类之外，它和普通Java类没有任何区别       | 接口是完全不同的类型                                         |
| 访问修饰符         | 抽象方法可以有**public**、**protected**和**default**这些修饰符 | 接口方法默认修饰符是**public**。你不可以使用其它修饰符。     |
| main方法           | 抽象方法可以有main方法并且我们可以运行它                     | 接口没有main方法，因此我们不能运行它。（java8以后接口可以有default和static方法，所以可以运行main方法） |
| 多继承             | 抽象方法可以继承一个类和实现多个接口                         | 接口只可以继承一个或多个其它接口                             |
| 速度               | 它比接口速度要快                                             | 接口是稍微有点慢的，因为它需要时间去寻找在类中实现的方法。   |
| 添加新方法         | 如果你往抽象类中添加新的方法，你可以给它提供默认的实现。因此你不需要改变你现在的代码。 | 如果你往接口中添加方法，那么你必须改变实现该接口的类。       |

## N条线程同时访问M个资源如何保证不死锁

使用多线程时，一种非常简单的避免死锁的方式就是：指定锁的顺序，并强制线程按照指定的顺序获取锁。

产生死锁的四个条件：

1. 互斥
2. 请求与保持
3. 不可剥夺
4. 循环等待

只要破坏其中任意一个条件，就可以避免死锁，其中最简单的就是破环循环等待条件。按同一顺序访问对象，加载锁，释放锁。

## 什么是Servlet？

Servlet（Server Applet）是Java Servlet的简称，称为小服务程序或服务连接器，用Java编写的服务器端程序

## 什么是单例模式

在它的核心结构中只包含一个被称为单例的特殊类。通过单例模式可以保证系统中，应用该模式的一个类只有一个实例。即一个类只有一个对象实例。

## SQL创建一个表，和设置主键

```sql
create table dept
(
    dept_id int primary key,
    dept_name nvarchar(100) not null,
    dept_address nvarchar(100)
)
```

## delete、truncate 和 drop的区别

- DELETE语句执行删除的过程是每次从表中删除一行，并且同时将该行的删除操作作为事务记录在日志中保存以便进行进行回滚操作
- TRUNCATE TABLE 则一次性地从表中删除所有的数据并不把单独的删除操作记录记入日志保存，删除行是不能恢复的。并且在删除的过程中不会激活与表有关的删除触发器。执行速度快。
-  DROP语句将表所占用的空间全释放掉

|           | DELETE | TRUNCATE | DROP               |
| --------- | ------ | -------- | ------------------ |
| 撤销/回滚 | 可以   | 不可以   | 不可以             |
| 触发器    | 会触发 | 不会     | 不会               |
| 删除      | 数据   | 数据     | 整个表(结构和数据) |
| 速度      | 慢     | 中       | 快                 |

## 迭代式开发

与传统的瀑布式开发相反，它弥补了传统开发方式中的一些弱点，具有更高的成功率和生产率。

**瀑布式开发(最传统)**，也就是从需求到设计，从设计到编码，从编码到测试，从测试到提交大概这样的流程，要求每一个开发阶段都要做到最好。
特别是前期阶段，设计的越完美，提交后的成本损失就越少。

**迭代式开发**，不要求每一个阶段的任务做的都是最完美的，而是明明知道还有很多不足的地方，却偏偏不去完善它，而是把主要功能先搭建起来为目的，以最短的时间，
最少的损失先完成一个“不完美的成果物”直至提交。然后再通过客户或用户的反馈信息，在这个“不完美的成果物”上逐步进行完善。

**螺旋开发**，很大程度上是一种风险驱动的方法体系，因为在每个阶段之前及经常发生的循环之前，都必须首先进行风险评估。

**敏捷开发**相比迭代式开发两者都强调在较短的开发周期提交软件，但是，敏捷开发的周期可能更短，并且更加强调队伍中的高度协作。
敏捷方法有时候被误认为是无计划性和纪律性的方法，实际上更确切的说法是敏捷方法强调适应性而非预见性。   
