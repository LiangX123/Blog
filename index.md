# 研究生个人学习总结





## Java技术总结

 

#### 目录 

### 一、Java基础

#### 1 Java简介
​		重要概念
​		环境搭建

​	2 数据类型

​		基本数据类型
​		引用数据类型
​		常量

​	3 命名规范

​	4 流程控制

​		语句
​		函数

​	5 类和对象

二 、java进阶

​	1 Java面向对象编程OOP

​	2 抽象类和接口

​	3 集合框架

​	4 异常处理

​	5 java IO

​	6 java多线程

​	7 JavaWeb

​		Web应用
​		Servlet
​		JSP

​	8 Java设计模式

***
## Java基础

### 一、Java简介

- 一种面向对象的语言；一种平台无关的语音；一种健壮的语言，吸收了C/C++的优点，但去掉了其影响程序健壮性的部分（如：指针、内存的申请与释放等）。

- 两种核心机制：Java虚拟机（Java Virtual Machine）、垃圾回收机制（Garbage Collection）。

- 源文件（.java文件）->Java编译器->字节码（.class文件）->类装载器->字节码校验器->解释器->操作平台。

- JDK(Java Development Kit)软件开发工具包，JRE（Java Runtime Environment）运行时环境。





### 二、数据类型

1.  **基本数据类型**


| 基本数据类型 |  分类  | 大小  |            取值范围             | 默认初始值 |
| :----------: | :----: | :---: | :-----------------------------: | :--------: |
|     byte     |  整型  | 1字节 |           [-128,127]            |     0      |
|     int      |  整型  | 4字节 |      [-2*10^31,2\*10^31-1]      |     0      |
|    short     |  整型  | 2字节 |      [-2*10^15,2\*10^15-1]      |     0      |
|     long     |  整型  | 8字节 |      [-2*10^63,2\*10^63-1]      |     0      |
|     char     | 字符型 | 2字节 |      [-2*10^31,2\*10^31-1]      |    null    |
|    float     | 浮点型 | 4字节 |  [3.402823e+38 ~ 1.401298e-45]  |    0.0     |
|    doubt     | 浮点型 | 8字节 | [1.797693e+308~ 4.9000000e-324] |    0.0     |
|   boolean    | 布尔型 | 1字节 |           true或false           |   false    |

2. **引用数据类型**

- 在Java中，引用类型的变量非常类似于C/C++的指针。引用类型指向一个对象，指向对象的变量是引用变量。这些变量在声明时被指定为一个特定的类型，比如 Employee、Student 等。变量一旦声明后，类型就不能被改变了。

- 对象、数组都是引用数据类型。

- 所有引用类型的默认值都是null。

- 一个引用变量可以用来引用任何与之兼容的类型。

  


 3. **常量**

- 常量在程序运行时是不能被修改的。
- 在 Java 中使用 final 关键字来修饰常量，声明方式和变量类似：

```java
final double PI = 3.1415927;
```






#####  三、命名规范

1.  **标识符的组成**：字母，数字，下划线，$，不能以数字开头，不能使用关键字和保留关键字。（关键字是指java中已经定义的具有特定功能的标识符，不能用作普通标识符）

2.  **包的命名**
   Java包的名字都是由小写单词组成。每一名Java程序员都可以编写属于自己的Java包，为了保障每个Java包命名的惟一性，最新的Java编程规范要求程序员在自己定义的包的名称之前加上惟一的前缀。由于互联网上的域名是不会重复的，所以程序员一般采用自己在互联网上的域名作为自己程序包的惟一前缀。例如：net.lx.study。

3.  **类的命名**
   类的名字必须由大写字母开头，一个单词中的其他字母均为小写。如果类名称由多个单词组成，则建议将每个单词的首字母均用大写，例如TestPage。如果类名称中包含单词缩写，则建议将这个词的每个字母均用大写，如：XMLExample。由于类是设计用来代表对象的，所以建议在命名类时应尽量选择名词。

4. **方法的命名**
   方法的名字的第1个单词应以小写字母开头，后面的单词则建议用大写字母开头(驼峰原则)。
   例如：sendMessge()。

5.  **常量的命名**
   常量的名字应该都使用大写字母，并且指出该常量完整含义。如果一个常量名称由多个单词组成，则建议用下划线来分割这些单词。
   例如：MAX_VALUE。

6.  **参数的命名（驼峰原则）**
   参数的命名规范和方法的命名规范相同，而且为了避免阅读程序时造成迷惑，请在尽量保证在参数名称为一个单词的情况下，参数的命名尽可能明确。**注意：**1、类的属性允许不进行初始化；2、方法内部的变量要进行初始化





##### 四、流程控制

- 语句：If switch do while while for

1. 当判断固定个数的值的时候，可以使用if，也可以使用switch。但是建议使用switch，效率相对较高。

```java
switch(变量){ 
   case 值:
        要执行的语句;
        break; 
   … 
  default:
        要执行的语句; 
  }
```

2. 当判断数据范围，获取判断运算结果boolean类型时，需要使用if。

3. 当某些语句需要执行很多次时，就用循环结构。 while和for可以进行互换。区别在于：如果需要定义变量控制循环次数。建议使用for。因为for循环完毕，变量在内存中释放。

4. break:作用于switch ，和循环语句，用于跳出，或者称为结束。break语句单独存在时，下面不要定义其他语句，因为执行不到，编译会失败。当循环嵌套时，break只跳出当前所在循环。要跳出嵌套中的外部循环，只要给循环起名字即可，这个名字称之为标号。

5. continue:只作用于循环结构，继续循环用的。作用：结束本次循环，继续下次循环。该语句单独存在时，下面不可以定义语句，执行不到。

   

- java函数定义：

  ```java
   修饰符 返回值类型 函数名(参数类型 形式参数1，参数类型 形式参数1，…){
        执行语句；
       return 返回值；
    }/*没有具体的返回值时，返回的返回值类型用void关键字表示。*/
  ```

- java函数重载：
  1. 重载的定义是：在一个类中，如果出现了两个或者两个以上的同名函数，只要它们的参数的个数，或者参数的类型不同，即可称之为该函数重载了。
  2. 如何区分重载：当函数同名时，只看参数列表。和返回值类型没关系。





##### 五、类和对象

- 成员变量、局部变量和全局变量

  成员变量：在类体的变量部分中定义的变量，也称为属性。
  局部变量：是指在程序中，定义在特定的方法或语句块的变量，是相对与全局变量而言的。

```java
public class Test{
　　int a=0; //全局变量
　　public static void main(String[] args){
　　int b =0；//局部变量
    }
}
```
- 区别：

1. 定义的位置不同：成员变量直接定义在类内部，局部变量是定义某个方法体内部；

2. 作用域不同：成员变量适用于整个类和与该类相关的类，局部变量只适用于该方法内部；

3. 初始值不同：成员变量可以不显式初始化它们可以由系统设定默认值，局部变量没有默认值，所以必须设定初始赋值；

4. 不同方法可以有重名的局部变量；5.如果类变量和局部变量重名，局部变量更有优先级；

- 实例变量和静态变量

```java
public class User
{ 
	String id; //实例变量 
	private String name; //实例变量 
	private int age; //实例变量 
	private static String department; //静态变量 
}
```

***

## Java进阶

##### 一、Java面向对象编程（OOP)

面向对象的编程优点：代码开发模块化，易于维护和理解，代码复用性，增强代码的可维护性和灵活性，

- **封装**：封装是指将一个计算机系统中的数据以及与这个数据相关的一切操作语言（即描述每一个对象的属性以及其行为的程序代码）组装到一起，一并封装在一个有机的实体中，把它们封装在一个“模块”中，也就是一个类中，为软件结构的相关部件所具有的模块性提供良好的基础。在面向对象技术的相关原理以及程序语言中，封装的最基本单位是对象，而使得软件结构的相关部件的实现“高内聚、低耦合”的“最佳状态”便是面向对象技术的封装性所需要实现的最基本的目标。对于用户来说，对象是如何对各种行为进行操作、运行、实现等细节是不需要刨根问底了解清楚的，用户只需要通过封装外的通道对计算机进行相关方面的操作即可。大大地简化了操作的步骤，使用户使用起计算机来更加高效、更加得心应手。

- **继承**：继承是面向对象技术中的另外一个重要特点，其主要指的是两种或者两种以上的类之间的联系与区别。继承，顾名思义，是后者延续前者的某些方面的特点，而在面向对象技术则是指一个对象针对于另一个对象的某些独有的特点、能力进行复制或者延续。如果按照继承源进行划分，则可以分为单继承（一个对象仅仅从另外一个对象中继承其相应的特点）与多继承（一个对象可以同时从另外两个或者两个以上的对象中继承所需要的特点与能力，并且不会发生冲突等现象）；如果从继承中包含的内容进行划分，则继承可以分为四类，分别为取代继承（一个对象在继承另一个对象的能力与特点之后将父对象进行取代）、包含继承（一个对象在将另一个对象的能力与特点进行完全的继承之后，又继承了其他对象所包含的相应内容，结果导致这个对象所具有的能力与特点大于等于父对象，实现了对于父对象的包含）、受限继承、特化继承。
  
  - 修饰类该类不能被继承，修饰方法该方法不能被覆盖，修饰属性该属性不能自动初始化，修饰变量该变量只能赋一次值。
  - java中继承的执行顺序：父类属性初始化–>父类构造方法–>子类属性初始化–>子类构造方法。
  
- **多态**：从宏观的角度来讲，多态性是指在面向对象技术中，当不同的多个对象同时接收到同一个完全相同的消息之后，所表现出来的动作是各不相同的，具有多种形态；从微观的角度来讲，多态性是指在一组对象的一个类中，面向对象技术可以使用相同的调用方式来对相同的函数名进行调用，即便这若干个具有相同函数名的函数所表示的函数是不同的。重用、重载、动态调用构成了多态。体现：子类生产父类对象。

  ```java
  Animal A = new Cat();
  ```





##### 二、抽象类和接口

1. **抽象类**
   - 抽象类（抽象类是约束子类必须拥有哪些方法，并不关注子类的实现）：
     包含抽象方法的类一定抽象类，定义了抽象类（abstract class A）不一定有抽象方法，抽象类中也可以定义普通方法；
   - 抽象类必须用public或protected修饰；
   - 抽象类不能用来创建对象；
   - 如果一个类继承了抽象类则子类必须实现父类的所有抽象方法方法。
   - 实例：

  ```java
  abstract class A{
      public abstract void doSomething();//定义抽象方法修饰符必须是public（缺省值）或protected
      
      public  void fun(){//抽象类中的非抽象方法
          System.out.println("I'm A.run(),Hello");
      }
  }
  class B extends A{
      public void doSomething() {//子类必须实现父类的抽象方法
          System.out.println("I'm B,doSomething!");
      }
      public  void fun(){
          System.out.println("I'm B.run(),Hello!");
      }
  }
  
  class C extends A{
      public void doSomething() {
          System.out.println("Im C,doSomething!");
      }
  }
  
  public class Test{
      public static void main(String[] args) {
          A a1 = new B();
          A a2 = new C();
          B b = new B();
          C c = new C();
          a1.fun();
          a2.fun();
          b.doSomething();
          c.doSomething();
      }
  }
  //结果//
  /*
  Im B.run(),Hello!
  Im A.run(),Hello
  Im B,doSomething!
  Im C,doSomething!
  */
  ```

2. **接口**
- 接口中的方法都是抽象方法；
  
- 一个类可以实现多个接口，一个非抽象的类实现了某个接口就必须实现接口中的所有方法（换
     句话说:对于遵循某个接口的抽象类，可以不实现该接口中的抽象方法）。
   
- 实例：

 ```java
     interface A{
         String s="sd";//接口中变量被隐式的指定为 publin static final
         public void doSomething();//接口中所有方法被隐式的指定为public abstract(抽象方法)，所以说接口中只有抽象方法
     }
     interface B{
         public void playSomething();
     }
     class C implements A,B{
         public void doSomething(){//实现类必须实现接口所有的方法
     
         }
         public void playSomething() {
     
         }
     }
 ```

​     

##### 三、集合框架

1. **java集合类**
   - Collection：是集合类的上级接口,继承于它的接口主要有Set 和List.
   - List：以特定次序来持有元素，可有重复元素；
   - Set:无法拥有重复元素,内部排序（无序）；
   - Map:键值对key–value，value可多值。
2. **集合类特性(几个常用类的区别)：**
   - ArrayList: 元素单个，效率高，多用于查询 Vector: 元素单个，线程安全，多用于查询 LinkedList: 元素单个，多用于插入和删除 HashMap: 元素成对，元素可为空。 
   - HashTable: 元素成对，线程安全，元素不可为空。
   - WeakHashMap: 是一种改进的HashMap，它对key实行“弱引用”，如果一个key不再被外部所引用，那么该key可以被GC回收。



##### 四、异常处理

1. **异常分类**

   - 可控式异常：在Java中把那些可以预知的错误，在程序编译时就能对程序中可能存在的错误进行处理，并给出具体的错误信息，这些错误称为可控式异常。
   - 运行时异常：在Java中不能被编译器检测到的错误称为运行时异常。

2. **处理异常**

   在Java中当程序出现异常时，可以使用try···catch、try···catch···finally或try···finally进行处理。
   
3. **抛出异常**

   对于程序中发生的异常，除了上面的try···catch语句处理之外，还可以使用throws声明或throws语句抛出异常。

```java
try {
  正常执行的语句
} catch(Exception e) {
  对异常进行处理的语句
}

try {
  正常执行的语句
} catch(Exception e) {
  对异常进行处理的语句
} finally {
  一定会被处理的语句
}

//throws用于方法声明，在声明方法时使用throws声明抛出异常，然后在调用该方法中对异常进行处理。
public void showInfo() throws Exception {    // 抛出Exception
  FileInputStream in = new FileInputStream("C://Record.txt");  // 创建IO对象 
}

//如果希望程序自行抛出异常，可以使用throw语句来实现。使用throw语句抛出的是异常类的实例，通常与if语句一起使用
if(x < 0) {
  throw new Exception("程序异常，x不能小于0。");
}
```






##### 五、java IO

1. **java IO 基本概念**

   - Java IO：即 Java 输入 / 输出系统。

   - 区分 Java 的输入和输出：把自己当成程序， 当你从外边读数据到自己这里就用输入（InputStream/Reader）， 向外边写数据就用输出（OutputStream/Writer）。

   - Stream：Java 中将数据的输入输出抽象为流，流是一组有顺序的，单向的，有起点和终点的数据集合，就像水流。按照流中的最小数据单元又分为字节流和字符流。

     （1）字节流：以 8 位（即 1 byte，8 bit）作为一个数据单元，数据流中最小的数据单元是字节。

     （2） 字符流：以 16 位（即 1 char，2 byte，16 bit）作为一个数据单元，数据流中最小的数据单元是字符， Java 中的字符是 Unicode 编码，一个字符占用两个字节。

2. **java IO主要包含的两个部分**

   - 流式部分：是 IO 的主体部分， 流式部分根据流向分为输入流（InputStream/Reader）和输出流（OutputStream/Writer）， 根据数据不同的操作单元，分为字节流（InputStream/OutputStream）和字符流（Reader/Writer），依据字节流和字符流，Java 定义了用来操作数据的抽象基类InputStream/OutputStream 和 Reader/Writer，再根据不同应用场景（或功能），在这两种抽象基类上基于数据载体或功能派上出很多子类，用来满足文件，网络，管道等不同场景的 IO 需求，从而形成了 Java 的基本 IO 体系。
   - 非流式部分：主要包含一些辅助流式部分的类，如： SerializablePermission 类、File 类、RandomAccessFile 类和 FileDescriptor 等；

3. **IO流分类**

   Java io 分类方式有很多，根据是否直接处理数据，Java io又分为节点流和处理流，节点流是真正直接处理数据的；处理流是装饰加工节点流的。

   - 节点流

     - 文件流：FileInputStream，FileOutputStrean，FileReader，FileWriter，它们都会直接操作文件，直接与 OS 底层交互。因此他们被称为节点流 ，注意：使用这几个流的对象之后，需要关闭流对象，因为 java 垃圾回收器不会主动回收。不过在 Java7 之后，可以在 try() 括号中打开流，最后程序会自动关闭流对象，不再需要显示地 close。

     - 数组流：ByteArrayInputStream，ByteArrayOutputStream，CharArrayReader，CharArrayWriter，对数组进行处理的节点流。

     - 字符串流：StringReader，StringWriter，其中 StringReader 能从 String 中读取数据并保存到 char 数组。

     - 管道流：PipedInputStream，PipedOutputStream，PipedReader，PipedWrite，对管道进行处理的节点流。

   - 处理流

     处理流是对一个已存在的流的连接和封装，通过所封装的流的功能调用实现数据读写。如 BufferedReader。

     处理流的构造方法总是要带一个其他的流对象做参数。

     常用处理流（通过关闭处理流里面的节点流来关闭处理流）

     - 缓冲流 ：BufferedImputStrean，BufferedOutputStream，BufferedReader ，BufferedWriter，需要父类作为参数构造，增加缓冲功能，避免频繁读写硬盘，可以初始化缓冲数据的大小，由于带了缓冲功能，所以就写数据的时候需要使用 flush 方法，另外，BufferedReader 提供一个 readLine( ) 方法可以读取一行，而 FileInputStream 和 FileReader 只能读取一个字节或者一个字符，因此 BufferedReader 也被称为行读取器。

     - 转换流：InputStreamReader，OutputStreamWriter，要 inputStream 或 OutputStream 作为参数，实现从字节流到字符流的转换，我们经常在读取键盘输入（System.in）或网络通信的时候，需要使用这两个类。

     - 数据流：DataInputStream，DataOutputStream，提供将基础数据类型写入到文件中，或者读取出来。

       ```java
        public static void readAndWriteByteToFile() throws IOException {
        	InputStream is =null;
       	OutputStream os = null;
        	try {
        	// 在try()中打开文件会在结尾自动关闭
        	is = new FileInputStream("D:/FileInputStreamTest.txt");
        	os = new FileOutputStream("D:/FileOutputStreamTest.txt");
        	byte[] buf = new byte[4];
        	int hasRead = 0;
        	while ((hasRead = is.read(buf)) > 0) {
        	os.write(buf, 0, hasRead);
        	}
        	System.out.println("write success");
        	} catch (Exception e) {
        	e.printStackTrace();
        	}finally{
        	os.close();
        	is.close();
        	}
        }
       ```

       



##### 六、java多线程

1. **进程与线程**

   - 进程：每一个进程都有独立的代码和数据空间（进程上下文）。进程间的切换会有较大的开销，一个进程包括1--n个线程。（进程是资源分配的最小单位）
   - 线程：同一类线程共享代码和数据空间，每一个线程有独立的执行栈和程序计数器(PC)，线程切换开销小。（线程是cpu调度的最小单位）

2. **java实现多线程方式**

   在java中要想实现多线程，一般有两种手段。一种是继续Thread类，第二种是实现Runable接口。

   ```java
   class Thread1 extends Thread{				
   	private String name;
       public Thread1(String name) {
          this.name=name;
       }
   	public void run() 												//结果
           for (int i = 0; i < 5; i++) {								//A执行  :  0
               System.out.println(name + "执行  :  " + i);	   		   //B执行  :  0
               try {													//A执行  :  1
                   sleep((int) Math.random() * 10);					//A执行  :  2
               } catch (InterruptedException e) {						//A执行  :  3
                   e.printStackTrace();								//A执行  :  4
               }														//B执行  :  1
           }															//B执行  :  2  																											//B执行  :  3 
   	}																//B执行  :  4 
   }															
   class Thread2 implements Runnable{
   	private String name;
   
   	public Thread2(String name) {
   		this.name=name;
   	}
   
   	@Override
   	public void run() {												//结果
   		  for (int i = 0; i < 5; i++) {								//输出：
   	            System.out.println(name + "执行  :  " + i);		   //C执行  :  0
   	            try {												//D执行  :  0
   	            	Thread.sleep((int) Math.random() * 10);			//D执行  :  1
   	            } catch (InterruptedException e) {					//C执行  :  1
   	                e.printStackTrace();							//D执行  :  2
   	            }													//C执行  :  2
   	        }														//D执行  :  3
   																	//C执行  :  3
   	}																//D执行  :  4
   																	//C执行  :  4
   }
   public class Main {
   	public static void main(String[] args) {			
   		Thread1 mTh1=new Thread1("A");
   		Thread1 mTh2=new Thread1("B");
   		mTh1.start();
   		mTh2.start();
   		new Thread(new Thread2("C")).start();
   		new Thread(new Thread2("D")).start();
   	}
   
   }
   ```

   实现Runnable接口比继承Thread类所具有的优势：

   1）：适合多个同样的程序代码的线程去处理同一个资源

   2）：能够避免java中的单继承的限制

   3）：添加程序的健壮性，代码能够被多个线程共享，代码和数据独立

   4）：线程池仅仅能放入实现Runable或callable类线程，不能直接放入继承Thread的类
   
3. **线程同步与互斥**

   - synchronized关键字

     - synchronized关键字的作用域有二种： 
       1）是某个对象实例内，synchronized aMethod(){}可以防止多个线程同时访问这个对象的synchronized方法（如果一个对象有多个synchronized方法，只要一个线程访问了其中的一个synchronized方法，其它线程不能同时访问这个对象中任何一个synchronized方法）。这时，不同的对象实例的synchronized方法是不相干扰的。也就是说，其它线程照样可以同时访问相同类的另一个对象实例中的synchronized方法； 
       2）是某个类的范围，synchronized static aStaticMethod{}防止多个线程同时访问这个类中的synchronized static 方法。它可以对类的所有对象实例起作用。 
     
     - 除了方法前用synchronized关键字，synchronized关键字还可以用于方法中的某个区块中，表示只对这个区块的资源实行互斥访问。用法是: synchronized(this){/*区块*/}，它的作用域是当前对象； 
     
     - synchronized关键字是不能继承的，也就是说，基类的方法synchronized f(){} 在继承类中并不自动是synchronized f(){}，而是变成了f(){}。继承类需要你显式的指定它的某个方法为synchronized方法； 
   
4. **守护线程（运行在后台，为其他前台线程服务）**

   - 特点：一旦所有的用户线程都结束运行，守护线程会随JVM一起结束工作
   - 应用：数据库连接池中的监测线程；JVM虚拟机启动后的监测线程
   - 最常见的守护线程：垃圾回收线程
   - 怎么设置守护线程：调用Thread类的setDaemon（true）方法来设置当前的线程为守护线程（注意事项：setDaemon（true）必须在
     start（）方法之前调用；守护线程中产生的新线程也是守护线程；并不是所有的任务都可以分配给守护线程来执行，比如读写操作和计算逻辑）





##### 七、JavaWeb

1. **WEB应用程序**

   - B/S ( browser/server ，浏览器/服务器）架构

   - 基于HTTP传输协议（超文本传输协议）

   - WEB程序必须要运行在web容器上，如Tomcat /Jboss/WebLogic等

     

2. **Servlet**

   - servlet是运行在服务端的小程序.是sun公司提供的一套规范,用来处理客户端请求,响应给浏览器的动态资源. servlet是javaWeb三大组件(sevlet,filter,listener)之一。

   -  servlet生命周期

     1. 创建: 用户第一次访问servlet创建servlet的实例。
     2. 销毁: 当项目从服务器移除,或服务器关闭的时候。
     
   - servletContext
   
     每次在服务器上部署一个项目时,系统会自动的创建一个ServletContext对象,这个对象时整个项目共同拥有。
   
     - 实现多个Servlet之间数据的数据的共享
     - 获取服务器上自定文件资源的信息
       a:可以获取服务器资源文件的绝对路径
       context.getRealPath(path);
       b:可以直接获取服务器上资源文件的字节流
       context.getResourceAsStream(path)
     - 获取Web项目web.xml中的初始化参数
   
   - cookie & session
   
     - cookie是一种会话技术,用来进行数据传递/数据共享
   
     - Session保存在服务器端：占用服务器内存，安全，数据量/保存数量无上限。
   
       
   
3. **JSP**

   - jsp九大内置对象
     request response exception page pageContext out session config application
     pageContext可以获得其他八个内置对象
     
   - el表达式
     简化java代码书写
     ${ }可以取出域对象的内容
     
   - jstl表达式
     JSP需要使用taglib指令导入对应标签库，某个JSP就可以使用JSTL标签
     常用标签`<c:if></c:if> <c:foreach></c:foreach>`
     
     

4. **filter & listener**

   - filter:一个实现了特殊接口的Java类.实现对请求资源的过滤的功能.过滤器是Servlet技术中最为实用的技术.

     - 作用:对目标资源进行过滤

     - 生命周期:创建服务器正常启动时，销毁服务器正常关闭时，每次执行过滤器,都会执行dofilter方法。

   - listener：Servlet规范中已经定义好了八个监听器接口，它们要监听的对象分别是request、session、servletContext对象，触发监听器的事件是这三个对象的创建与销毁，它们的域属性空间中属性的添加、删除、修改，及session的钝化与活化操作。

   

##### 八、 设计模式

1. **简介**

-  在 1994 年，由 Erich Gamma、Richard Helm、Ralph Johnson 和 John Vlissides 四人合著出版了一本名为 **Design Patterns - Elements of Reusable Object-Oriented Software（中文译名：设计模式 - 可复用的面向对象软件元素）** 的书，该书首次提到了软件开发中设计模式的概念。

   四位作者合称 **GOF（四人帮，全拼 Gang of Four）**。他们所提出的设计模式主要是基于以下的面向对象设计原则。

   - 对接口编程而不是对实现编程。
   - 优先使用对象组合而不是继承。

- 根据设计模式的参考书 **Design Patterns - Elements of Reusable Object-Oriented Software（中文译名：设计模式 - 可复用的面向对象软件元素）** 中所提到的，总共有 23 种设计模式。这些模式可以分为三大类：创建型模式（Creational Patterns）、结构型模式（Structural Patterns）、行为型模式（Behavioral Patterns）。



2. **设计模式的六大原则**

   - 开闭原则（Open Close Principle）

     开闭原则的意思是：**对扩展开放，对修改关闭**。在程序需要进行拓展的时候，不能去修改原有的代码，实现一个热插拔的效果。简言之，是为了使程序的扩展性好，易于维护和升级。想要达到这样的效果，我们需要使用接口和抽象类，后面的具体设计中我们会提到这点。

   - 里氏代换原则（Liskov Substitution Principle）

     里氏代换原则是面向对象设计的基本原则之一。 里氏代换原则中说，任何基类可以出现的地方，子类一定可以出现。LSP 是继承复用的基石，只有当派生类可以替换掉基类，且软件单位的功能不受到影响时，基类才能真正被复用，而派生类也能够在基类的基础上增加新的行为。里氏代换原则是对开闭原则的补充。实现开闭原则的关键步骤就是抽象化，而基类与子类的继承关系就是抽象化的具体实现，所以里氏代换原则是对实现抽象化的具体步骤的规范。

   - 依赖倒转原则（Dependence Inversion Principle）

     这个原则是开闭原则的基础，具体内容：针对接口编程，依赖于抽象而不依赖于具体。

   - 接口隔离原则（Interface Segregation Principle）

     这个原则的意思是：使用多个隔离的接口，比使用单个接口要好。它还有另外一个意思是：降低类之间的耦合度。由此可见，其实设计模式就是从大型软件架构出发、便于升级和维护的软件设计思想，它强调降低依赖，降低耦合。

   - 迪米特法则，又称最少知道原则（Demeter Principle）

     最少知道原则是指：一个实体应当尽量少地与其他实体之间发生相互作用，使得系统功能模块相对独立。

   - 合成复用原则（Composite Reuse Principle）

     合成复用原则是指：尽量使用合成/聚合的方式，而不是使用继承。
     
     

3. **观察者模式**

- 当对象间存在一对多关系时，则使用观察者模式（Observer Pattern）。比如，当一个对象被修改时，则会自动通知依赖它的对象。观察者模式属于行为型模式。
- 从现实角度来说，我们每一个人都是一个观察者，同时也是一个被观察者。作为被观察者，我们会发出一些信息，观察者在接收到这些信息后，会做出相应的反映；而作为观察者，我们是可以被“被观察者”所发出的信息影响的。一个被观察者，可能存在多个观察者。也就是说，一个被观察者所发出的信息，可能会影响到多个观察者。观察者设计模式，定义了一种一对多的关联关系。一个对象A与多个对象B、C、D之间建立“被观察与观察关系”。当对象A的状态发生改变时，通知所有观察者对象B、C、D。当观察者对象B、C、D在接收到A的通知后，根据自身实际情况，做出相应改变。当然，观察者与被观察者指的都是具有某一类功能的对象，所以这里的观察者与被观察者都是指的接口，而真正的观察者对象与被观察者对象，是指实现了这些接口的类的对象。



***
## Java项目介绍

#### 一、文件上传下载

- 本次文件下载指的是文件从服务器下载到浏览器后，浏览器并不直接解析，而是以附件的形式保存到客户端。文件上传是客户端向服务器上传文件。即将保存在客户端的文件上传至服务器中一个副本，保存到服务器中。
- 实现了多种上传下载方式，每种方式各有优劣。



##### 1. 文件上传
   - 文件上传要求客户端表单提交特殊的请求----multipart请求，即包含多部分数据的请求。所以文件上传表单对于表单数据的编码类型要求，必须为mutipart/form-data。即要为<form/>标签指定enctype属性值为“mutipart/form-data”。enctype，即encoding type，编码类型。
   - 由于客户端上传文件的大小是不确定的，所以HTTP协议规定，文件上传的数据要存放于请求正文中，而不能出现在URL的地址栏中。也就是说，文件上传的表单，必须提交POST请求，而不能提交GET请求。

1.1  服务端手工接收上传文件

- 服务端接收上传的文件，可以通过输入流来完成。而输入流可以通过HttpServletRequest的getInputStream()获取到。

```java
<form action="uploadServlet" method="POST" enctype="multipart/form-data"
```

```java
//定义UploadServlet
ServletInputStream is = request.getInputStream();//获取请求的输入流，该流中只存放了请求正文体数据

//读取输入流中的数据
byte[] buffer = new byte[1024];
int len = -1;
while(len = is.read(buffer) != -1){
    String str = new String(buffer,0,len);
    ou.print(str);
}
is.close();
```

1.2  使用第三方工具上传

- FileUpload工具存放在Apacher的Commons中。

  ```java
  public class UploadServlet extends HttpServlet {
  	protected void doPost(HttpServletRequest request，
                            HttpServletResponse response) 
          					throws ServletException,IoException {
  	try {
  		// 1.判断请求是否为Multipart请求
  		if( lserv1etFileUpload.isMuLt ipartContent(request)) {
  			throw new RuntimeException("该请求不能完成文件上传");
  		//2.创建文件项工厂
  		DiskFileItemFactory factory = new DiskFileItemFactory();
   		//3.创建文件上传核心组件
  	ServletFileUpload servletFileUpload = new ServletFileUpload(factory);
  		//4.解析Multipart请求,获哎所有请求体正文中的item
  		List<FileItem> fileItems = servletFileUpload.parseRequest(request);
  		//5、解析每个请求正文体中的item
          for (FileItem item : fileItems) {
            	if(item.isFormField()) {//若item为普通参数
                  String fie1dName = item.getFieldName(); //获取参数名
  				String fieldValue = item.getString();//获取参数值							
                  System.out.println(fieldName + " :" + fieldValue);
            }else {                             // 若item为普通参数
                String fileName = item.getName(); //获取文件名
  			  //获取输入流
                InputStream is = item.getInputStream();
                //创建输出流
  			   String path = this.getServletContext().getRealPath(" /images");
                File desFile = new File(path,fileName);
  			  FileOutputStream fos = new FileOutputStream(desFile);
  			  byte[]bytes = new byte[1024];
                int len = -1;
  			  while((len = is.read(bytes))l= -1){
  				fos.write(bytes, 0,len);
                }
  //关闭流
  				fos.close();
  				is.close();
  			}
          }  
     }catch (FileuploadException e) {
      e.printStackTrace();
  	}
    }
  }
  
  ```
  

1.3 使用第三方工具上传

- 文件由浏览器通过网络上传到服务器，并不是直接通过一条网络线路将所有请求数据发送到了服务器的。而是将这些数据分为了很多个数据包，这些数据包分别编号后，经由不同的网络线路最终发送到了同一台机器----服务器。这些数据包到达服务器的时间会根据不同的网络线路的情况不同，分别先后到达服务器，不一定是按照编号顺序到达的，或者是大多数情况下是不会按照编号顺序到达的。那么，服务器就会在其临时目录中，创建一个临时文件，将这些数据包进行拼接组装。

  ```java
  	//设置临时文件创建的临界值
      factory.setSizeThreshold(1024*1024* 2);
  	//设置临时文件目录
      String tempPath = this.getServletContext().getRealPath("/temp");
  	File tempFile = new File(tempPath);
  	factory.setRepository(tempFile);
  ```



1.4 参数名问题

- 解决普通参数的中文乱码问题，只需使用FileItem的带参getString(String  Encoding)方法获取参数名即可。
- 上传文件名的中文乱码问题，需要通过ServletFileUpload的方法setHeadEncoding()指定上传文件请求头部编码的方式解决。
- 为了解决浏览器向服务器发送文件名不同这个问题，需要使用String的substring()方法截取出文件名。因为文件名一定是最后一个”\”后面部分。
- 对于相同文件名的上传问题，只需要使保存在服务器端的文件名称唯一即可。例如，为原始文件名前添加一个当前系统时间System.currentTimeMillis()。



1.5 文件大小问题

- 对于上传文件的大小，可以通过ServletFileUpload的setFileSizeMax()与setSizeMax()方法进行控制。
- setFileSizeMax()用于设置单个文件上传的最大值，而setSizeMax()用于设置单次上传的最大值。即若一次上传多个文件，每个文件的大小边界值与所有文件加起来的最大小值。



##### 2. 文件下载

- 超链接下载：将下载资源作为超链接的链接目的文件出现。若浏览器可以解析该资源文件，则将在浏览器上直接显示文件内容；若浏览器不支持该文件的解析，则会弹出另存为对话框，要求用户保存。缺点：不同的浏览器，以及相同的浏览器所安装的插件不同，那么其对于资源的解析能力也就不同，其是否弹出另存为对话框的情况也就不一样。决定权由浏览器掌握。

```html
<body>
	<a href="$ipageContext.request.contextPath }/resources/aaa.exe">下载aaa.exe</a><br>
    <a href="${pageContext.request.contextPath j/resources/bbb.xmlL ">下裁bbb.xml</a><br>
    <a href="$ipageContext.request.contextPath }/resources/ccc.jpg">下载ccc.jpg</a><br>
    <a href="$ipageContext.request.contextPath j/resources/ddd. pdf">下载ddd.pdf</a><br>
    <a href= "${pageContext.request.contextPath }/resources/eee.rar">下数eee.rar</a><br>
</body>

```

- Servlet下载：若要使下载的文件以附件的形式出现在浏览器，则需要设置响应头的属性content-disposition的值为attachment，且需要指定浏览器下载后显示的文件名。即需要指定content-disposition的值为attachment;filename=文件名。

```java
// 设置响应头属性值，使文件以附件形式下载
response.setHeader("content-disposition","attachment;filename=test.jpg");
```

```java
// 解决中文乱码问题
fileName = new String(fileName.getBytes("UTF-8","ISO8859-1"));
```



#### 二、基于karaf的JavaWeb项目

##### 1.karaf简介

Karaf是Apache旗下的一个开源项目。Karaf同时也是一个基于OSGi的运行环境，Karaf提供了一个轻量级的OSGi容器，可以用于部署各种组件，应用程序。Karaf提供了很多特性用于帮助开发者和用户更加灵活的部署应用，例如：热部署、动态配置、几种日志处理系统、本地系统集成、可编程扩展控制台、ssh远程访问、内置安装认证机制等等。同时Karaf作为一款成熟而且优秀的OSGi运行环境以及容器已经被诸多Apache项目作为基础容器,例如：Apache Geronimo， ApacheServiceMix，Fuse ESB，由此可见Karaf在性能，功能和稳定性上都是个不错的选择。

##### 2.通过karaf部署项目

- karaf官网提供了多种部署项目的例子，本人主要是使用其中的启动器部署和feature部署。

- 两种部署都需要安装web控制台,在karaf控制台上运行：

  ```
  featrue:install webconsole
  ```

  
  
  ###### 2.1 通过启动器部署	
  
  - 通过启动器部署需要提供注册和注销的servlet名称。如：
  
  ```java
   httpService.registerServlet("/ApiServlet", new ApiServlet(), null, null);//注册servlet
   ((HttpService) service).unregister("/ApiServlet");//注销servlet
  ```
  
  
  
  - 在pom文件中需要指定打包方式为bundle，并提供相关插件。
  
    ```java
    <packaging>bundle</packaging>//设置打包方式为bundle
        
    //提供相关插件   
    <plugin>
    	<groupId>org.apache.felix</groupId>
    	<artifactId>maven-bundle-plugin</artifactId>
    	<version>${maven-bundle-plugin.version}</version>
    	<extensions>true</extensions>
    </plugin>
    ```
  
 
  
- 对项目进行打包后，在浏览器输入http://localhost:8181/system/console/bundles（初始用户名，密码都是karaf），进入web控制台。点击install/update按钮安装生成的jar文件。
  
  
  
  
  
  ![image-20210329102356712](C:\Users\LiangXin\AppData\Roaming\Typora\typora-user-images\image-20210329102356712.png)
  
  
  
  
  
  - 找到该bundle并启动。如无法启动，则单击进入详细页面查看pom文件的依赖是否能够解析。如果依赖报红，可以通过上一步的方法手动导入依赖并启动该依赖。



![image-20210329103808369](C:\Users\LiangXin\AppData\Roaming\Typora\typora-user-images\image-20210329103808369.png)



<img src="C:\Users\LiangXin\AppData\Roaming\Typora\typora-user-images\image-20210329103842061.png" alt="image-20210329103842061" style="zoom:200%;" />



​						

![image-20210329103750367](C:\Users\LiangXin\AppData\Roaming\Typora\typora-user-images\image-20210329103750367.png)



##### 3.通过feature部署项目

- 通过feature部署项目需要指定资源目录feature，并在该目录下创建feature.xml文件。通过feature.xml文件配置项目bundle相关参数。

  ```java
  <features name="${project.artifactId}-${project.version}" xmlns="http://karaf.apache.org/xmlns/features/v1.3.0">
  
      <feature name="Http-client" version="${project.version}">
          <bundle>mvn:cn.lx/Http-client/${project.version}</bundle>
      </feature>
  
      <feature name="Http-index" version="${project.version}">
          <bundle>webbundle:mvn:cn.lx/Http-index/${project.version}/war?Web-ContextPath=main</bundle>
      </feature>
  
  </features>
  ```

- 将项目打包后，通过feature:repo-add 将项目添加进来，最后通过feature:install安装指定的bundle

  ```
  feature:repo-add mvn:cn.lx/Http-feature/1.0-SNAPSHOT/xml
  feature:install Http-client
  feature:install Http-index
  ```



#### 三、Java调用第三方接口

- JDK的java.net包中提供了访问HTTP协议的基本功能的类：HttpURLConnection。

- URLConnection是个抽象类，它有两个直接子类分别是HttpURLConnection和JarURLConnection。另外一个重要的类是URL，通常URL可以通过传给构造器一个String类型的参数来生成一个指向特定地址的URL实例。

- HttpURLConnection是Java的标准类，它继承自URLConnection，可用于向指定网站发送GET请求、POST请求。它在URLConnection的基础上提供了如下便捷的方法：

  ```java
  int getResponseCode();        // 获取服务器的响应代码。
  String getResponseMessage();  // 获取服务器的响应消息。
  String getResponseMethod();   // 获取发送请求的方法。
  void setRequestMethod(String method); // 设置发送请求的方法。
  ```



##### 3.1 HttpURLConnection使用小结：

1.  HttpURLConnection的connect()函数，实际上只是建立了一个与服务器的tcp连接，并没有实际发送http请求。无论是post还是get，Http请求实际上直到HttpURLConnection的getInputStream()这个函数里面才正式发送出去。

2.  在用POST方式发送URL请求时，URL请求参数的设定顺序是重中之重， 对connection对象的一切配置（那一堆set函数） 都必须要在connect()函数执行之前完成。而对outputStream的写操作，又必须要在inputStream的读操作之前。  这些顺序实际上是由http请求的格式决定的。 如果inputStream读操作在outputStream的写操作之前，会抛出异常：

   ```java
     java.net.ProtocolException: Cannot write output after reading input....... 
   ```




3. http请求实际上由两部分组成， 一个是http头，所有关于此次http请求的配置都在http头里面定义， 一个是正文content。  connect()函数会根据HttpURLConnection对象的配置值生成http头部信息，因此在调用connect函数之前， 就必须把所有的配置准备好。 

   

4. 在http头后面紧跟着的是http请求的正文，正文的内容是通过outputStream流写入的，  实际上outputStream不是一个网络流，充其量是个字符串流，往里面写入的东西不会立即发送到网络， 而是存在于内存缓冲区中，待outputStream流关闭时，根据输入的内容生成http正文。 至此，http请求的东西已经全部准备就绪。在getInputStream()函数调用的时候，就会把准备好的http请求 正式发送到服务器了，然后返回一个输入流，用于读取服务器对于此次http请求的返回信息。由于http 请求在getInputStream的时候已经发送出去了（包括http头和正文），因此在getInputStream()函数  之后对connection对象进行设置（对http头的信息进行修改）或者写入outputStream（对正文进行修改） 都是没有意义的了，执行这些操作会导致异常的发生。 



##### 3.2 Servlet开发注意点：

1. 对于客户端发送的POST类型的HTTP请求，Servlet必须实现doPost方法，而不能用doGet方法。 

2. HttpURLConnection是基于HTTP协议的，其底层通过socket通信实现。如果不设置超时（timeout），在网络异常的情况下，可能会导致程序僵死而不继续往下执行。可以通过以下两个语句来设置相应的超时： 

   - System.setProperty("sun.net.client.defaultConnectTimeout", 超时毫秒数字符串); 

   - System.setProperty("sun.net.client.defaultReadTimeout", 超时毫秒数字符串); 
   
   ​       其中： sun.net.client.defaultConnectTimeout：连接主机的超时时间（单位：毫秒） sun.net.client.defaultReadTimeout：从主机读取数据的超时时间（单位：毫秒） 

   例如： 
   System.setProperty("sun.net.client.defaultConnectTimeout", "30000"); 
   System.setProperty("sun.net.client.defaultReadTime", "30000");



##### 3.3 代码实例：

- 示例代码如下： 

  ```java
  public class API {
      public static String sendPost(String url,String method) throws IOException {
          OutputStreamWriter out;
          BufferedReader in = null;
          String result = "";
          URL realUrl = new URL(url);
          // 打开和URL之间的连接
          HttpURLConnection conn = (HttpURLConnection) realUrl.openConnection();
          //设置超时时间
          conn.setConnectTimeout(50000);
          conn.setReadTimeout(150000);
          // 设置通用的请求属性
          conn.addRequestProperty("Content-Type", "application/x-www-form-urlencoded");
          conn.setRequestProperty("accept", "*/*");
          conn.setRequestProperty("connection", "Keep-Alive");
          conn.setRequestProperty("User-agent",
                  "Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1;SV1)");
          if (method.equals("PATCH")) {
              conn.setRequestProperty("X-HTTP-Method-Override", "PATCH");
              conn.setRequestMethod("POST");
          } else {
              conn.setRequestMethod(method);
          }
          conn.setRequestProperty("Authorization", "Bearer d66f5ff895bbe5baa3ed0426e92fd58c9e6f6cf4");
          // 发送POST请求必须设置如下两行
          /*  if(method.equals("POST"))
          {
              conn.setDoOutput(true);
          }*/
          conn.setDoOutput(false);
          conn.setDoInput(true);
          // 获取URLConnection对象对应的输出流
          /* out = new OutputStreamWriter(conn.getOutputStream(), "UTF-8");// utf-8编码*/
          // 发送请求参数
         /* out.write(body);
          // flush输出流的缓冲
          out.flush();*/
          // 定义BufferedReader输入流来读取URL的响应
          in = new BufferedReader(new InputStreamReader(conn.getInputStream(), "utf8"));
          String line;
          while ((line = in.readLine()) != null) {
              result += line;
          }
        /*  if (out != null) {
              out.close();
          }*/
          if (in != null) {
              in.close();
          }
          return  result;
      }
  }
       
  ```

  

