### 学习目标

- 了解 Spring 的基本概念和优点
- 理解 Spring 中的 IoC 和 DI 思想
- 掌握 ApplicationContext 容器的使用
- 掌握属性 setter 方法注入的实现

Spring是当前十分流行的一个 Java Web 开发框架，它是为了解决企业应用开发的复杂性问题而存在的。

#### 1.Spring 概述

##### 1.1什么是 Spring

Spring 是一个分层的 Java SE/EE full-stack（一站式）轻量级开源框架，以 IoC 和 AOP 为内核，使用基本的 JavaBean 来完成以前只能由 EJB 完成的工作，取代了 EJB 的臃肿、低效的开发模式。

Spring 致力于 Java EE 应用各层的解决方案，在表现层它提供了 Spring MVC 和 Struts 框架的整合功能；在业务层可以管理实务、记录日记等；在持久层可以整合 MyBatis、Hibernate、JdbcTemplate 等技术。因此说 Spring 是一站式框架。

##### 1.2Spring 框架的优点

- 非侵入式设计
- 方便解耦、简化开发
- 支持 AOP
- 支持声明式事务处理
- 方便集成各种优秀的框架
- 降低 Java EE API 的使用难度

##### 1.3Spring 的体系结构

Spring 框架采用的是分层框架，它一系列的功能被分成20个模块，这些模块大体分为 Core Container、Data Access/Integration、Web、AOP、Instrumentation、Messaging 和 Test。

![体系结构](C:\Users\艾曼爷爷\Desktop\SSM框架学习笔记\day01\体系结构.png)

#### 2.Spring 的核心容器

Spring 框架的主要功能是通过其核心容器来实现，主要有两种核心容器，分别为 BeanFactory 和 ApplicationContext。

##### 2.1BeanFactory

##### 2.2ApplicationContext

#### 3.Spring 的入门程序

（1）在 Eclipse 中，创建一个名为 chapter01 的 Web项目,将 Spring 的4个基础包以及Commons-logging 的 JAR包复制到 lib 目录中 , 并发布到类路径下。

（2）在 src 目录下，创建一个 com.itheima.ioc 包，并在包中创建接口 UserDao，然后在接口中定义一个方法。

（3）在  com.itheima.ioc 包下，创建 UserDao 接口的实现类 UserDaoImpl,该类实现接口中 say()方法，并在该方法中编写一条输出语句。

（4）在 src 目录下，创建 Spring 的配置文件 applicationContext.xml, 并在配置文件中创建一个 id 为 userDao 的 Bean。

（5）在 com.itheima.ioc 包下，创建测试类 TestIoC , 并在类中编写 main() 方法。 在main（）方法中，需要初始化 Spring 容器，并加载配置文件，然后通过 Spring 容器获取 UserDao 实例，最后调用实例中的 sys()方法。

#### 4.依赖注入

##### 4.1依赖注入的概念

依赖注入与控制反转的含义相同，只不过这两个称呼是从两个角度描述的同一个概念。

在使用 Spring 框架后，对象的实例不再由调用者来创建，而是由 Spring 容器来创建，Spring 容器会负责控制程序之间的关系，而不是由调用者的程序代码直接控制。这样，控制权由应用代码转移到 Spring 容器，控制权发生了反转，这就是 Spring 的控制反转。

从 Spring 容器的角度来看， Spring 容器负责将被依赖对象赋值给调用者的成员变量，这相当于为调用者注入了它依赖的实例，这就是 Spring 的依赖注入。 

##### 4.2依赖注入的实现方式

依赖注入的作用就是在使用 Spring 框架创建对象时，动态地将其依赖的对象注入 Bean 组件中，通常有两种注入方式：一种是属性 setter 方法注入，另一种是构造方法注入。

- 属性 setter 方法注入：指 IoC 容器使用 setter 方法注入被依赖的实例。通过调用无参构造器或无参静态工厂方法实例化  Bean 后，调用该 Bean 的 setter 方法， 即可实现基于 setter 方法的依赖注入。
- 构造方法注入：指 IoC 容器使用构造函数注入被依赖的实例。基于构造方法的依赖注入通过调用带参的构造函数来实现，每一个参数代表一个依赖。

#### 5.小结

本小节学习了Spring框架的一些基础知识。Spring 框架的概念、作用、优点、体系结构以及如何下载和下载后的目录结构，还学习了 Spring 的两种核心容器。还通过一个入门程序来学习如何使用 Spring框架。最后学习了依赖注入和控制反转的概念，并通过依赖注入 setter 方法注入的实现。