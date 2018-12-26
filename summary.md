
名词解释Summar
====
[TOC]
### spring
    核心是IOC（控制反转）和AOP（面向切面编程）
    控制反转：当应用了IoC，一个对象依赖的其它对象会通过被动的方式传递进来，而不是这个对象自己创建或者查找依赖对象。你可以认为IoC与JNDI相反——不是对象从容器中查找依赖，而是容器在对象初始化时不等对象请求就主动将依赖传递给它。
    面向切面编程：允许通过分离应用的业务逻辑与系统级服务（例如审计（auditing）和事务（transaction）管理）进行内聚性的开发。应用对象只实现它们应该做的——完成业务逻辑——仅此而已。它们并不负责（甚至是意识）其它的系统级关注点，例如日志或事务支持|符合高聚合松耦合和opc开发原则
### 容器
    包含并管理应用对象的配置和生命周期，在这个意义上它是一种容器，你可以配置你的每个bean如何被创建——基于一个可配置原型（prototype），你的bean可以创建一个单独的实例或者每次需要时都生成一个新的实例——以及它们是如何相互关联的
### springboot
[微框架](http://www.cnblogs.com/ityouknow/p/5662753.html "微框架")
### spring mvc
    是一个mvc框架，可以理解为Spring+Struts2，或者说是spring的一个子模块（同AOP，IOC一般），需运行在spring之上。
### javabean
    java里的一个可重用组件，是遵循特殊写法的类
    具体说来，javabean必须具有一个无参的构造函数、属性变量必须私有化（private）、私有变量可通过public getxxx setxxx函数被外部程序访问
    javabean在javaee中用于封装数据，其他程序可以通过反射实例化javabean对象，获取其属性，并调用其属性保存数据

### EBJ
    Enterprise（企业）javabean
    通俗理解：功能是将业务逻辑的计算机语言实现（类）打包并发布在服务器上
### JNDI
    java名称目录接口
    功能：将java对数据库的连接和配置交付给服务器端（与jdbc对比，并不是代替jdbc而是在数据库连接发生变动时，JNDI技术提供了一种更好的解决方式）
### JDBC
    java数据库连接是一个用于执行SQL语言的java API，由一组java类和接口组成，在其基础上可以设计更高级的工具和接口。
### 接口
    some抽象方法的集合，与类的定义方式类似，但是类描述对象的属性和方法，接口只包括抽象方法（说明实现接口的类需要实现哪些方法），除非该类为抽象类，否则必须实现其实现的接口定义的所有抽象方法。
### API
    应用程序编程接口（application programming interface）
### C/S 、 B/S
    C/S： client to server 
    B/S:  browser to server
### Git/Github
    学会了使用idea内置git与自安装git bash连接远程github仓库的方式  //还需实践练习
### SSM
    Spring+Spring MVc+Mybatis
<h3 id="1">SSH</h3>

    Spring+Structs+Hibernate
[SSH与SSM横向对比](https://www.cnblogs.com/justdoitba/p/8184122.html "SSH与SSM横向对比")
### maven
    java写的一个开源的项目管理工具
    项目配置依赖及其版本控制的一种描述方式，在pom.xml里添加dependency即可
### devtools(热部署)
    热部署，不用重启服务器即可完成部署。重新加载整个项目。会重新打包war，适用于生产环境，会清空内存
    热加载，不重启服务器，不重新打包，不清空内存，重新加载class（俗称开发者模式）
    devtools是spring提供的一个模块，来使springboot项目实现热部署
[详细对比](http://www.cnblogs.com/ptqueen/p/8384898.html "详细对比")
[devtools相关配置](https://www.cnblogs.com/TechSnail/p/7690829.html "devtools相关配置")
### thymeleaf
    一个模板引擎，可以代替jsp？？//感觉这个还得深入使用之后才能了解
    开箱即用，可以代替繁琐的jstl标签库
[thymyleaf](http://www.cnblogs.com/jiangbei/p/8462294.html "thymyleaf")
### 调试与正式部署
    个人理解调试也就是debug的过程，不止是代码本身的错误，也包括业务逻辑上特定情况下会出现的不可见的缺陷bug（在编译器中就是run和debug的区别）
    而在软件开发的整个过程中：需求、设计、编码、调试、维护。调试也是很重要的
### ORM框架（如Hibernate、mybatis）
    ORM是一种技术——对象关系映射，将软件工程（聚合，解耦，封装）发展而来的对象与从数学世界发展而来的关系型数据库之间建立关系
### 数据库连接池
    就是一组对不同数据库或一个数据库里不用用户的连接的集合

<h3 id="2"> 事务管理</h3>

    对数据库的一组sql操作命令的管理，spring框架支持编程式和声明式两种方式，前者直接将事务操作添加在业务逻辑处理中（类），而后者声明式事务管理建立在AOP之上的。其本质是对方法前后进行拦截，然后在目标方法开始之前创建或者加入一个事务，在执行完目标方法之后根据执行情况提交或者回滚事务。声明式事务最大的优点就是不需要通过编程的方式管理事务，只需在配置文件中做相关的事务规则声明(或通过基于@Transactional注解的方式)，便可以将事务规则应用到业务逻辑中。
    注意：声明式又分两种annotation（注解式）：@Transactional注解和使用使用tx/aop命名空间XML配置文件式的方式
[事务](https://blog.csdn.net/gloomy_114/article/details/62048335 "事务")
[基于tx/aop](https://blog.csdn.net/Or1n_559/article/details/52914752 "基于tx/aop")
### 持久化
    将数据存储到可永久存储介质上的过程
    是针对数据库增删改更新等的操作，DAO可以说是持久化的一种实现模式之一
### MVC框架（如Struts）
    model、view、controller
    总结：
    M：modle模型（包括：service、dao、entity（实体））
    V：view（做页面的展示，jsp、html……）
    C：controller（接受请求——调度模型处理请求——根据结果分发页面相应请求）
[springmvc工作原理](https://www.cnblogs.com/xiaoxi/p/6164383.html "springmvc工作原理")

[========]

![mvc](index_files/249993-20161212142542042-2117679195.jpg "mvc")


### 轻量级开发、重量级
    简单理解来说，根据使用的服务多少来划分，使用的服务越多，容器对java对象做的工作就越多，影响发布时间和运行性能
### mybatis（对比hibernate）
    一种持久层框架
详情滚回↑↑↑↑↑↑↑[ssh](#1)ヾ(ｏ･ω･)ﾉ

### POJO
    简单的java对象（plain ordinary java Object）就是普通的javabean为与EJB区分而起的名字
### JPA
    java持久层API，不同于JDBC，JPA是一种规范，是java程序访问ORM框架的规范，是我们可以用同一种方式操作不同的ORM框架
    个人理解：jdbc是一种最基础也最原生的一种java操作数据库的方式，整合各大数据库厂商提供的类和接口，使用sql语句。在其基础上加以JPA约束，有了更高级更方便的各种ORM框架工具
- 使用ORM框架的配置和操作还要熟悉
### tx
    见上事务管理第二条
[传送门](#2)
![层次](index_files/3bf33a87e950352adaa8264a5e43fbf2b3118ba2.jpg "层次")
### DAO
    数据访问对象（data assess object）
    是面向对象的一个数据库接口，DAO层包括接口和其实现类，主要是一些SQL语句（将对数据源的操作封装在一个公共的API中，是处于业务逻辑service和实体层entity之间的连接层）
### ocp开发原则
    开闭原则：一个软件实体（如类），应对扩展开放，对修改关闭
扩展：[敏捷开发的原则](https://blog.csdn.net/qq_16234613/article/details/54933742 "敏捷开发的原则")

[TOC]

>Q：系统为什么要分层？

>A:系统分层往往能达到高内聚低耦合的效果，易于维护和复用。且易于团队分工开发
