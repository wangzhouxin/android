1.	内部类和静态内部类的区别
静态内部类可以有静态成员，非静态内部类不可以
静态内部类只能访问外部类的静态成员，非静态内部类可以访问外部类所有成员
静态内部类可由外部类进行创建，非静态内部类依赖于实例创建，
2.	如何使一个类不被继承
构造函数带private属性
加final关键字
设计为匿名类
3.	23种设计模式与常用的
创建型模式（5种）：工厂方法模式，抽象工厂模式，单例模式，建造者模式，原型模式。
结构型模式（7种）：适配器模式，装饰器模式，代理模式，外观模式，桥接模式，组合模式，享元模式。
行为型模式（11种）：策略模式、模板方法模式、观察者模式、迭代子模式、责任链模式、命令模式、备忘录模式、状态模式、访问者模式、中介者模式、解释器模式。
工厂模式 
抽象工厂模式
单例模式
Public class Singleton{
	private static Singleton singleton=new Singleton();
	private Singleton(){};
	public static Singleton getSin(){
		return singleton;
	}
}
建造者模式
原型模式
适配器模式
装饰模式
代理模式
外观模式
桥接模式
组合模式
享元模式
4.	数据库四大性质
事务是并发控制的基本单位，是一个操作序列，一个不可分割的工作单位
原子性：事务的操作要么全部成功，要么全部失败回滚，即对数据库不产生影响
一致性：最终的结果是否和设定的规则保持一致，例如转账前后两任的总金额之和相等
隔离性：多个并发事务之间相互隔离
持久性：一个事务一旦提交，对数据库的改变是永久的
持久性的问题：
脏读：一个事务读取了另一个事务未提交的数据
不可重复读：读取了前一事务提交的数据中的某个数据项
虚读：读取了前一事务提交的数据整体
5.	位运算符
1.	与：&000，010，100，111 2.或：|000，011，101，111 3.非：~10，01 
2.	4异或：…^000,011,101,110
6.	死锁的产生与避免
死锁：多个进程在运行过程中争夺资源形成一种僵局，使得所有进程都无法前进
原因：1.争夺不可剥夺资源（打印机、相机），竞争临时资源时通信顺序不当
	  2.进程间推进顺序非法
4个必要条件：互斥：资源在一段时间内的排他性、请求和保持：进程请求资源被阻塞时，不放弃已有资源、不剥夺：进程的资源不可被剥夺、环路等待：形成进程、资源的环形链
解决办法：
预防死锁：破坏请求条件：一次性分配所有资源，破坏保持条件：进程要不没资源要不全部资源都有、不可剥夺条件：进程资源可被剥夺、资源有序分配
避免死锁：
检测死锁：为进程和资源建立唯一的号码，建立资源分配和进程等待表
解除死锁：剥夺其他进程资源给死锁进程，撤销进程
7.	数组和链表的区别：
链表：单向、双向、循环
链表链式存储结构，数组顺序存储结构
通过指针连接元素，按次序依次排序
删除简单、不需要移动元素，且添加元素简单，但查找元素困难
寻找元素简单，删除、添加困难
8.	二叉排序树与查找时间复杂度
也叫二叉查找树，左子树及左子树的所有子树的节点值小于父节点的值，右子树反之
Logn,构造为平衡二叉树
9.	虚拟内存是什么
虚拟内存将主存看作一个磁盘的高速缓存，主存只保存活动区域，并在磁盘和主存之间来回传送数据
电脑运行程序过多占用内存很大，windows采用了虚拟内存技术，拿出一部分硬盘空间当内存使用，这部分空间被成为虚拟内存，优点：弥补物理内存不足的缺点，提高反应速度，缺点：占用了物理硬盘空间，设置不当会影响机器的稳定性与速度
10.	存储结构
易失存储器、非易失存储器
寄存器 SRAM高速缓存 DRAM主存 本地磁盘
11.	Cpu32位和64位区别，安卓cpu多少位
指的是通用寄存器的数据宽度，一次可以运行64bit数据，
64位拥有更大的寻址能力，更快的执行速度、更大的内存管理
12.	进程和线程的关系
一个application一般有一个进程和多个线程
进程是资源分配的基本单位，也是调度运行的基本单位
线程是进程中执行运算的最小单位
一个线程只属于一个进程，一个进程可有多个线程
资源分配给进程，进程中的线程共享进程的所有资源，每一个线程有自己的堆栈
13.	创建进程的方法
Runtime类的exec()方法
Proceebuilder创建
14.	创建线程的方法
继承thread类
使用匿名内部类创建线程
实现runnable接口
15.	Char是否可以存储汉字
在unicode编码中的汉字可以存储 
16.	Int的范围
Byte 1字节short 2字节 int 4字节 long 8字节 float 4字节1823 double 8字节11152 char 2字节
17.	equals和hashcode
equals()用来判断两个对象是否相同，最原始的equals是比较对象的地址是否相等，等价于“==”方法，意思是是否是同一个对象。一般重写equals，比较他们的内容是否相同
hashcode是获取哈希码，也叫散列码，哈希码的作用是确定对象在哈希表中的索引位置，散列表存储键值对
不会创建类对应的散列表，hashcod()和equals（）没有关系
会创建类对应的散列表，HashSet、HashTable、HashMap等，如果equals，hashcode也相等，但hashcode相等，equals不一定true
18.	String、StringBuilder、StringBuffer区别
运行速度：String builder>StringBuilder>String 原因：String是常量，每次改变都要回收然后新建，所以比较慢
StringBuiler线程不安全，StringBuffer线程安全，StringBuffer中很多方法有synchronnized，
String：少量字符串操作
StringBuilder：单线程下字符缓冲区大量操作
StringBuffer：多线程下字符缓冲区大量操作
19.	内存溢出out of memory和内存泄露memory leak
Oom：系统已经不能再分配你所需的空间了，分配的内存不足以放下数据项序列
ML：程序申请的内存空间，在使用完毕后未释放、一直占据内存单元
内存泄漏：常发性内存泄漏、偶发性内存泄漏、一次性内存泄漏、隐式内存泄漏
解决办法：1优先使用application的context，2不再需要使用的对象，将其赋值为null，3注意对象的生命周期，尤其单例、全局性集合、静态对象4handler使用弱应用
内存溢出：1加载数据量过于庞大2死循环或循环过多3对象引用为清空4参数内存设定值过小
解决办法：1检查数据库查询2检查死循环和递归代码3检查大循环4检查集合对象的清除
20.	强应用、软应用、弱应用、虚引用
强应用：最普遍的、不会被回收
软引用：内存空间不足时被回收：网页缓存、图片缓存
弱应用：扫描发现时回收
虚引用：任何时候都可能被回收
21.	ANR
输入事件5秒未被处理
广播接收器前台10秒、后台60秒违背处理
服务前台20秒、后台200秒未完成启动
内容提供其的publish在10秒内未被处理
产生原因：主线程在做耗时的工作、主线程被其他线程锁、CPU被其他进程占用
降低办法：1不要主线程读取数据2不在broadcast Receiver的onRecieve()中进行操作3各个组件的生命周期函数 不要有太耗时的操作4避免主线程被锁
22.	RecyclerView优化
1数据处理与视图绑定分离2数据优化 分页加载、局部刷新3布局优化 减少绘制4减少监听器创建5数据预取
23.	JVM、DVM、ART、JIT
Java virtual machine：本质是软件，计算机硬件的一层软件抽象，屏蔽了底层差异
					Java编译生成jvm字节码，字节码被jvm翻译为机器指令
Dalvik虚拟机 Android中使用的虚拟机，所有的安卓程序都运行在安卓系统中，每个进程对应一个Dvm实例
共同点：Dvm和Jvm都提供了生命周期管理、堆栈管理、线程管理、安全和异常管理、垃圾回收等机制
不同点：运行Java字节码和Dalvik字节码，Davlik字节码由Java字节码转化而来；生成class文件和Dex文件，每个class文件都有一个常量池，Dex文件共享一个常量池减少体积；基于栈结构和寄存器结构		
JIT：Just in time：即时编译技术 ，生成汇编代码
AOT：ahead of time，与编译技术，生成机器代码
DVM与ART
Dex字节码与本地机器码
每次打开都有jit编译器将dex翻译成机器码解释执行，每次直接执行
Art：系统性能提升、续航提升，更大的存储空间
24.	Jvm
Jvm存储、垃圾回收机制、类加载
25.	 
26.	 
27.	 
28.	 
29.	 
30.	 
31.	 
32.	 
33.	 
34.	 
35.	 Context
36.	 线程池
37.	 数据库索引
