---
title: Interview
categories: 技术
tags: Interview
date: 2018-03-05 15:58:41
---

### 记录
<!--more-->



#### 值传递和引用传递

#### JAVA的特性和你的理解

#### RESTFul API

#### 进程和线程的区别

#### 泛型

- [Java泛型详解](https://www.jianshu.com/p/463e0e4cbc89) 

- [Java 泛型 - 菜鸟教程](http://www.runoob.com/java/java-generics.html) 

  

#### static 关键字：

- [关键字 static](http://wiki.jikexueyuan.com/project/java-enhancement/java-seven.html) 

- [Java中的static关键字解析](https://www.cnblogs.com/dolphin0520/p/3799052.html) 



#### MySQL 的引擎：InnoDB... 区别

#### Integer与int的区别

- `int`是Java提供的8种`原始数据类型`之一。Java为每个原始数据类型提供的`封装类`。`Integer`是`int`的封装类。
- `int`的默认值为`0`，而`Integer`的默认值是`null`。
- 即，Integer可以区分出未赋值与值为0的区别；而int无法表达出未赋值的情况。
- 另外，Integer还提供了多个与整数相关的操作方法。

#### 静态变量和实例变量的区别？
- 语法定义上：静态变量前要加static关键字，而实例变量前不加。
- 程序运行上：
  - 静态变量不属于某个实例对象，属于类，所以也叫类变量。
  - 只要程序加载了类的字节码，静态变量就会被分配空间，就可以使用。不用创建任何实例变量。
  - 静态变量直接用类名来引用。
  - 实例变量属于某个实例对象的属性。
  - 必须创建了实例对象，其中的实例变量才会被分配空间，才能使用。
  - 实例变量通过其对象来引用。

```
public class variantTest {
  public static int staticVar = 0;
  public int instanceVar = 0;

  public VariantTest(){
    staticVar++;
    instanceVar++;
  }
}
// 上面的程序，无论创建了多少个类的实例对象，永远只分配一个静态变量staticVar。
// 并且每创建一个实例对象，staticVar都会累积加1。
// 但是，每创建一个实例对象，就会分配一个instanceVar。
// 每个instanceVar都只会自加一次。
```


#### 使用`final`关键字修饰一个变量时，是引用不能变，还是引用的对象不能变？
- 使用final关键字修饰一个变量时，是指引用不能变。
- 而引用的变量指向的对象中的内容是可以改变的。

```
final StringBuffer a = new StringBuffer("immutable");
a = new StringBuffer(""); //编译会报错！
a.append("broken!"); //是正确的！
```

#### Java中有没有`goto`?
- Java中有`goto`。
- 但是是Java中的**保留字**，现在**没有**在Java中使用。
- `保留字`的意思就是不排除以后会启用，变成关键字。

#### Java基本数据类型和引用数据类型

#### [Java 数组声明与初始化](https://echoguan.coding.me/2018/03/27/Java%E6%95%B0%E7%BB%84%E5%A3%B0%E6%98%8E%E4%B8%8E%E5%88%9D%E5%A7%8B%E5%8C%96/)

#### JDBC 流程 (7步)
  1. 加载驱动
  2. 建立数据库连接
  3. 创建JDBC statement 对象
  4. 设置SQL语句并传入参数
  5. 执行SQL语句，得到执行结果
  6. 对结果进行处理，返回数据
  7. 关闭资源


####  Spring
##### 为什么我们要使用Spring呢？
- `IOC` 依赖注入帮助我们解决对象的创建和依赖的管理，使得程序耦合降低。
- `AOP` 使得面向切面编程变得更加简单，使得切面逻辑与业务逻辑解耦。
- 创建对象默认是单例的，不需要再使用单例模式进行处理。

##### IOC
- IOC (Inversion of Controller) 控制反转，别名 DI (Dependency Injection) 依赖注入。
  - **所谓 IOC ，就是由 Spring IOC 容器来负责对象的生命周期和对象之间的关系（让别人为你服务）。**
  - IOC, 将对象的创建权交由Spring容器，由容器根据配置文件控制实例以及实例间的关系（创建、维护、销毁）。
  - DI, 在Spring容器创建Bean对象时，自动将依赖注入到对应的实例中。
- 运用了工厂模式。并且是通过反射机制实现的。并且默认是单例模式的。
  - 可以把IoC模式看做是工厂模式的升华。
  - 比工厂模式的优势在于，IOC的反射机制允许我们不用重新编译代码，因为对象都是动态生成的。
  - 通过配置文件管理实例。这个大工厂里要生成的对象都是在XML文件中给出定义的，然后利用Java 的反射，根据XML中给出的类名生成相应的对象。实现热插拔。
- 目的就是降低耦合度，提高灵活性和可维护性。
- IoC的灵活性是有代价的：设置步骤麻烦、生成对象的方式不直观、反射比正常生成对象在效率上慢一点。因此使用IoC要看有没有必要，我认为比较通用的判断方式是：用到工厂模式的地方都可以考虑用IoC模式。

##### AOP
- AOP:允许你把遍布应用各处的功能分离出来形成可重用的组件。
- 比方说，系统中的日志、事务管理、安全服务等。


####  [抽象类和接口的区别，具体使用场景](https://echoguan.coding.me/2018/03/06/%E6%8A%BD%E8%B1%A1%E7%B1%BB%E4%B8%8E%E6%8E%A5%E5%8F%A3/)

####  匿名内部类、静态嵌套类

#### static private ...
