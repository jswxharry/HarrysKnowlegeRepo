> [!TIP]
> Explore more on [What is OSGi](https://www.osgi.org/resources/what-is-osgi/).

# What is OSGi ?
Simplest one sentence: A dynamic module system for Java
OSGi (Open Service Gateway Initiative) is a modular approach and specification that allows developers to create robust, highly decoupled and dynamic applications in Java.

Have following features:
- Modularity
- Dynamic Update
- Service-Oriented
- Isolated Classloaders

OSGi technology is successful because it provides a very mature, field proven, component system that works in a large number of environments. The OSGi component system is used to build any type of application ranging from **the simple to highly complex applications** like IDEs, application servers, email systems, content management systems, application frameworks, residential gateways and onboard telematics systems. 

# Why OSGi ?
- 解决“模块化失控“ 问题， 例如类路径冲突：不同jar包出现重名类， 依赖混乱等问题，框架通过声明对外暴露的包，和对内暴露的包来实现隔离。
- 更新难需要停机的问题。可以不用重启JVM 动态更新组件修复问题/升级 - 服务器重启导致服务中断；嵌入式设备（如工业控制器）重启可能引发生产事故；嵌入式设备（如工业控制器）重启可能引发生产事故； 框架定义了模块的生命周期的接口（更新，启动），以及发布注销等接口。
- 解决低效组件服用的问题。传统Java 需要通过依赖管理服用功能模块，在代码里实现功能实例，代码耦合度高。GSGi 可通过服务注册表发布服务，模块进行动态引用，无需关心实现类，面向接口编程。服务可用性监听，服务上线/下线触发回调，实现组件松耦合
- 易于集成老旧系统。基于实现模块对老的系统接口进行封装，新系统通过OSGi 服务调用，不用接触老系统代码。后续可拆分在新的模块重制老系统功能，进行渐进式替换，实现老系统淘汰。

# References
- [OSGi Specification Release 8](https://docs.osgi.org/specification/osgi.core/8.0.0/framework.introduction.html)



