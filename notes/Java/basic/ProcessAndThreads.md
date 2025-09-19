

Process & Program

Process
- Program Block (Code)
- Data Block （Memory）
- Prgram Control Bock (PCB)
    * Process Description - Process ID/Name
    * process coodination details. start of program, first command address, conunication info
    * Pocess resouce information: memoery, I/O, handles
    * process context. process environment 

线程是指“进程代码段”的一次的顺序执行流程。线程是CPU调度的最小单位。一个进程可以有一个或多个线程，各个线程之间共享进程的内存空间、系统资源，进程仍然是操作系统资源分配的最小单位。

一个标准的线程主要由三部分组成，即**线程描述信息**、**程序计数器（Program Counter，PC）**和**栈内存**
程序计数器很重要，它记录着线程下一条指令的代码段内存地址。
栈内存是代码段中局部变量的存储空间，为线程所独立拥有，在线程之间不共享

进程与线程的区别
1）线程是“进程代码段”的一次的顺序执行流程。一个进程由一个或多个线程组成；一个进
程至少有一个线程。
2）线程是CPU调度的最小单位，进程是操作系统分配资源的最小单位。线程的划分尺度小于
进程，使得多线程程序的并发性高。
3）线程是出于高并发的调度诉求从进程内部演进而来的。线程的出现既充分发挥CPU的计算
性能，又弥补了进程调度过于笨重的问题。
4）进程之间是相互独立的，但进程内部各个线程之间并不完全独立。各个线程之间共享进程
的方法区内存、堆内存、系统资源（文件句柄、系统信号等）。
5）切换速度不同，线程上下文切换比进程上下文切换要快得多。所以，有时线程也称为轻量
级进程。

创建线程的 4 种方法
Thread.currentThread()静态方法就是其中之一，该方法的作用是取得当前CPU内核上正在
运行的线程实例。
虽然一个进程有很多个线程，但是在一个CPU内核上，同一时刻只能有一个线
程是正在执行的，该线程也被叫作当前线程。
Java线程优先级的最大值为10，最小值为1，默认值为5
三个类常量如下：
``` Java
public static final int MIN_PRIORITY = 1;
public static final int NORM_PRIORITY = 5;
public static final int MAX_PRIORITY = 10;
```

是否为守护线程 daemon
什么是守护线程呢？
守护线程是在进程运行时提供某种后台服务的线程，比如垃圾回收（GC）线程。

start()，用来启动一个线程，当调用start()方法后，JVM才会开启一个新的
线程来执行用户定义的线程代码逻辑，在这个过程中会为相应的线程分配需要的资源。
run()，作为线程代码逻辑的入口方法。run()方法不是由用户程序来调用的，
当调用start()方法启动一个线程之后，只要线程获得了CPU执行时间，便进入run()方法去执行具体
的用户线程代码。

线程创建方法一：继承 Thread 类创建线程类
线程创建方法二：实现 Runnable 接口创建线程目标类

通过继承Thread类的方式创建的线程类，可以在子类中直接调用Thread父类的方法访问当前线
程的名称、状态等信息。这也是使用Runnable实现异步执行与继承Thread方法实现异步执行的不同
的地方。

``` Java
thread = new Thread(new RunTarget(), "name" + threadNo++);
```

优雅创建 Runnable 线程目标类的两种方式
1）通过匿名类优雅创建Runnable线程目标类。
``` Java
thread = new Thread(new Runnable() { //①匿名实例
@Override
public void run() { //②异步执行的业务逻辑
for (int j = 1; j < MAX_TURN; j++) {
Print.cfo(getCurThreadName() + ", 轮次：" + j);
} Print.cfo(getCurThreadName() +"运行结束.");
}
}, "RunnableThread" + threadNo++);
thread.start();
```

2）使用Lambda表达式优雅创建Runnable线程目标类。

在Java中，“函数式接口”是有且仅有一个抽象方法的接口。
@FunctionalInterface注解不是必需的，只要一个接口符合“函数式接口”的定义，
使用时加不加@FunctionalInterface注解都没有影响，都可以当作“函数式接口”来使用。

Runnable接口是一个函数式接口，在接口实现时可以使用Lambda表达式提供匿名实现

``` Java
thread = new Thread( ()-> { //①Lambda表达式
for (int j = 1; j < MAX_TURN; j++) {
Print.cfo(getCurThreadName() + ", 轮次：" + j);
} Print.cfo(getCurThreadName() +"运行结束.");
}, "RunnableThread" + threadNo++);
thread.start();
```

经过对比可以发现：使用Lambda表达式创建target执行目标实例，代码已经做到极致的简化。

Runnable接口的方式创建线程目标类 - 缺点：
1) 需要把runable 实例传入线程构造器， 才能创建线程
2) run 方法无法直接访问和控制当前线程。必须通过Thread.currentThread()获取当前线程实例

Runnable接口的方式创建线程目标类 - 优点：
1) 可以避免由于Java单继承带来的局限性。如果异步逻辑所在类已经继承了一个基类，就没有办法再继承Thread类。可通过实现runable接口。
2) 实现Runnable接口的方法创建多线程更加适合同一个资源被多段业务逻辑并行处理的场景。通过实现
Runnable接口的方式设计多个target执行目标类可以更加方便、清晰地将执行逻辑和数据存储分离

继承 Thread 类 vs 使用Runnable接口对比
* 继承Thread类实现多线程能更好地做到多个线程并发地完成各自的任务，访问各自的数据资源。
* 通过实现Runnable接口实现多线程能更好地做到多个线程并发地完成同一个任务，访问同一份数据资源。可以将线程逻辑和业务数据进行有效的分离。
* 通过实现Runnable接口实现多线程时， 需要对共享资源实现线程同步控制，或者使用原子类型（i.e.AtomicIntetger）

在大多数情况下，偏向于用实现Runnable接口来实现线程执行目标类， 异步执行任务在大多数情况下是通过线程池去提交
的，而很少通过创建一个新的线程去提交

线程创建方法三：使用 Callable 和 FutureTask 创建线程
继承Thread类或者实现Runnable接口这两种方式来创建线程类，但是这两种方式都有一个共同的缺陷：不能获取异步执行的结果。run()方法是不支持返回值。 after Java 1.5
