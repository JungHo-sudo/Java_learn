# 编译型和解释型语言 ：

## 编译型：

compile：一次性翻译程序，对环境要求低
缺点：实时更新。

## 解释型：

逐句解释，实时更新。
缺点：执行速度慢 ，对速度要求不高的情况。

---

## 总结：

java-编译器-class文件-JVM（类装载-字节码校验器-解释器）-操作系统平台。
`但目前来说随着科技发展，硬件性能提高，两者之间差别在逐渐缩小，java既有编译特征又有解释特征。`

---

# 快捷键：

  - 100.for
  - Fn + control + enter/command + N: 生成构造器
  - 层级树：control + h
  - command + D 复制行
- command option T 异常

# IDEA安装：

> 集成开发环境（IDE，Integrated Development Environment ）是用于提供程序开发环境的应用程序，一般包括代码编辑器、编译器、调试器和图形用户界面等工具。集成了代码编写功能、分析功能、编译功能、调试功能等一体化的开发软件服务套。所有具备这一特性的软件或者软件套（组）都可以叫集成开发环境。如微软的Visual Studio系列，Borland的C++ Builder、Delphi系列等。该程序可以独立运行，也可以和其它程序并用。IDE多被用于开发HTML应用软件。例如，许多人在设计网站时使用IDE（如HomeSite、DreamWeaver等），因为很多项任务会自动生成。

## 下载地址：

[官网下载地址](https://www.jetbrains.com/idea/)

---

## 创建工程：

1. Create New Project
2. java- Java版本(如果无则new按照路径寻找jdk安装地址)
3. 选择路径及工程名
4. 选择Src文件夹下Code
5. psvm可自动生成声明
6. sout自动生成system.out.println();
7. idea优化
8. 调整Project Structure SDK&language level（空工程需要）

---

# JAVA基础

## 01 注释：

Editor——Color Scheme——Java更改模版

```java
单行注释：//
多行注释：/* */
文档注释：
/**
*
*/
```

---

## 02 标识符和关键字：

### 关键字：

![关键字集合](https://img-blog.csdnimg.cn/c46a793f65a7491eb58c3531ee610516.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54y_5Lq65aS0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)

### 标识符：

Java标识符由数字，字母和下划线（_），美元符号（$）或人民币符号（￥）组成。
在Java中是区分大小写的，而且还要求首位不能是数字。
最重要的是，Java关键字不能当作Java标识符。 
下面的标识符是合法的： myName，My_name，Points，$points,_sys_ta，OK，_23b，_3_ 下面的标识符是非法的：
#name，25name，class，&time，if

---

## 03 数据类型：

- 强类型语言：==要求变量的使用要严格符合规定，所有变量必须先定义再使用。==
- 弱类型语言

### 基本类型（primitive type）

#### 数值类型：

##### 整数类型：

| 变量类型 | 所占内存 |
| -------- | -------- |
| byte     | 8位      |
| short    | 16位     |
| int      | 32位     |
| long     | 64位     |

long后面加上L。

##### 浮点类型：

| 变量类型 | 所占内存 |
| -------- | -------- |
| float    | 32位     |
| double   | 64位     |

float 加上F。

##### 字符类型：

| 变量类型 | 所占内存 |
| -------- | -------- |
| char     | 16位     |

==string不是关键字，是一个类。==

#### boolean类型：占1位

### 引用类型 （reference type） 

- 类：string
- 接口
- 数组

### 字节相关概念

位(bit):11001100 一个八位二进制数。
字节(byte)：基本单位，常用大写B表示。
1B = 8bit
字符：是指计算机中使用的字母 数字 字 符号
==电脑位数与寻址能力挂钩。==

---

### 扩展面试题：

**整数扩展：**
二进制 0b
十进制
八进制0
十六进制0x
**浮点数扩展：**
float 有限 离散 舍入误差 大约 接近但不等于
**最好完全避免浮点数进行==比较==**
Bigdecimal：数学工具class。
**字符扩展：**
强制转换sout((int)a)
==所有字符本质属于数字==
编码 unicode 处理各种语言文字，占2个字节 ，早些年最多表示65536，2的16次方 65536（excel）。
U0000-UFFFF
97 = a 
65 = A

```java
char a = '\u0061';
sout(a);
输出结果:a
```

**转义字符扩展**
\t 
\n

**布尔扩展**

```java
boolean flag = true;
if (flag == true){}
if (flag){}
// less is more
```

---

## 04 类型转换：

- 因为强类型 所以在不同数据类型时要遵循类型转换
- 优先级
- 低——高
- byte,short,char->int->long->float->double

```java
byte a = (byte)128 // 内存溢出
输出： -128
```

- 强制转换 高--低
- 自动转换 低--高

== 注意==

1. 不能对布尔转换
2. 不能把对象类型转换为不相干类型
3. 高容量至低容量强制转换
4. 转换中可能存在==内存溢出== 或是精度问题
5. jdk7新特性：数字之间可以用下划线分割

```java
int money = 10_0000_0000;
sout(money);
输出：1000000000
```

---

## 05 变量：

### 要素：变量名 变量类型 ==作用域==

```java
	String str = "hello world";	
	/*实例变量 在类里面，
	方法外面	从属对象	如果不进行初始化则默认值*/
	
psvm{
	static int allClicks = 0;		
	/* 类变量，加上static 随着类生命周期结束而结束*/
	
	public void method(){
		int i = 0;	// 局部变量，写在方法中
	}
}
//布尔值 默认：flase
//除了基本类型，其余都是null
```

### 常量

Constant ：initialize后不可改变。属于特殊的变量，一般规范大写字符。

```java
final PI = 3.14；
//修饰符不区分前后
```

==变量命名规范：==

![命名规范](https://img-blog.csdnimg.cn/a805a451701e40158d2e028f0dc830b1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54y_5Lq65aS0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)

## 06 运算符：

- 算术运算符：+ - * / % ++ --
- 赋值运算符：=
- 关系运算符：> < >= <= == !=	instanceof
- 逻辑运算符：&& 	||		|
- 位运算符：&	|	^	~	>>	<<	(*2 /2效率高) >>>
- 条件运算符：？：
- 扩展赋值运算符：+=		-=		*=	/=

---

## Package机制：

一般命名为公司域名倒置。

---

## JavaDoc生成文档：

JavaDos命令可自动生成API文档。

地址：javadoc -encoding UTF-8 -charset UTF-8 Doc.java

---

# Java流程控制

## 01 用户交互Scanner：

基本语法：

```java
Scanner s = new Scanner(System.in);
代码补全：option + enter
```

***通过Scanner类的next()与nextLine()方法获取输入的字符串，在读取前我们一般需要使用hasNext()与hasNextLine()判断是否还有输入的数据。***

```java
package XXX;
import java.util.Scanner;

public class demo1 {
    public static void main(String[] args) {
        //创建扫描器对象，用于接受键盘数据
        Scanner scanner = new Scanner(System.in);
        System.out.println("请以nextLine方式接收");


        //判断用户有没有输入字符串
        if(scanner.hasNextLine()){
            //以next方式接收
            String str = scanner.nextLine();
            System.out.println("输入的内容："+str);
        }
        // 凡事属于IO流的类如果不关闭会一直占用
        scanner.close();
    }
}

```

### Next():

- 一定要读到有效字符才结束输入
- 对输入有效字符之前遇到的空白自动去除
- 只有输入有效字符后才将其后面输入的==空白==作为分隔符或结束符
- ==next()不能得到带有空格的字符串==

### NextLine()：

- 以==Enter==为结束一就是说nextLine方法返回输入回车前的所有字符
- 可以获得空白

### 常规方法（无判断）：

```java
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

        System.out.println("请以nextLine方式接收");

        String str = scanner.nextLine();

        System.out.println("输入的内容："+str);
        
        scanner.close();
    }
```

## 02 Scanner的进阶：

==command+click = 跳转类源码==

---

## 03 顺序结构：

```java
    public static void main(String[] args) {

        System.out.println("hello1");
        System.out.println("hello2");
        System.out.println("hello3");
        System.out.println("hello4");
        System.out.println("hello5");
    }
```

---

## 04 选择结构：

### if单选择结构

### if双选择结构

### if 多选择结构

```java
if（布尔表达式1）{
}else if (布尔表达式2){
}else if (布尔表达式3){
}else{
}==
```

### 嵌套if结构

## 05 switch多选择结构

关键词：case穿透
==Java SE 7 以后支持 String==

```java
switch(expression){
	case value :
		break;// 可选
	case value :
		break;
	default :
}
```

### IDEA反编译方法：

Java --- class(字节码文件) --- 反编译(IDEA)

project Structure --- Project compiler output:
class files --- 在工程中 show in Explorer --- 拖拽至==文件管理器==
在项目中打开就是反编译后的文件。

---

## 06 While循环详解：

```java
while(布尔表达式){
	循环体
}
```

大多数情况下会让循环停止，我们需要用一个表达式失效的方式来结束循环。
少部分循环需要一直执行，比如服务器响应请求监听。
循环程序一直为True则成为死循环。

---

## 07 DoWhile循环：

```java
do {
		// 循环体
} while (布尔表达式/值);
```

---

## 08 ==For循环==：

```java
for (初始化;布尔表达式;更新){
	// 代码语句
}
```

 快捷键: 100.for

可初始化一个或多个循环控制变量，也可以是空语句。
初始化空前提 在循环体之外已经初始化。
三者皆空则死循环。

增强FOR循环：

```java
	int[] numbers = { 10, 20, 30, 40, 50 };
	for ( int x : numbers ){
		Sout(x);
	}
```

---

## 09 break，continue，goto:

break : 终止循环
continue ： 终止本次判断，开始下一次循环判定
goto : 已经被弃用

---

# Java方法

## 01 何为方法：

System . out . println () ;
  类			对象		方法

概念 ： 方法是语句集合，共同执行一个功能。

编写容量：==保持原子性==

----

## 02 方法的定义与调用：

```java
修饰符 返回值类型 方法名（参数类型 参数名）{
	...
	方法体
	...
	return 返回值;
}
```

关键词 ：
方法头 方法体
修饰符 返回值类型 方法名 returnValueType
参数类型 形式参数 实参
方法体

return 除了返回值 还有终止方法的作用。
值传递(Java)：对形式参数修改不会影响到实参
引用传递：对形式参数修改影响到实参

JVM中基本数据类型存放在栈中，而对象则存在堆中，对于基本数据类型的操作为同栈操作，复制为数据副本，操作结果对于两个数据互不影响。而操作对象则为栈指向堆操作，形式参数和实参都是对堆中对象操作，所以通过形参引用操作对象时显得实参改变，但本身并没有改变。

---

## 03 方法重载：

- 方法名一致
- 参数列表不同（个数、类型、参数排列顺序）
- 返回类型可以相同也可以不相同
- 仅仅返回类型不同不足以成为方法重载

**理论**：方法名称相同时，编译器会根据调用方法的参数个数、参数类型等去逐个匹配，以选择对应的方法，如果匹配失败则编译器会报错。

---

## 04 命令行传递参数：

在包路径——java——文件路径——参数

```java
  public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            System.out.println("args["+ i + "]:"+args[i]);

        }
    }
```

---

   ## 05 可变参数/不定项参数：

规则：

- JDK1.5开始 ， java支持传递同类型的可变参数给一个方法。
- 在方法声明中 ，在制定参数类型后加一个省略号(...)。
- 一个方法中只能指定一个可变参数，它必须是方法最后一个参数，任何普通的参数必须在他之前声明。

---

   ```java
   public class demo1 {
    public static void main(String[] args) {
        demo1 demo1 = new demo1();
        demo1.test(1,1,2,3,4,5);


    }

    public void test (int x , int ... i ){
        System.out.println(x);
        System.out.println(i[0]);
        System.out.println(i[1]);
        System.out.println(i[2]);
        System.out.println(i[3]);
        System.out.println(i[4]);

    }
}
输出：
1
1
2
3
4
5
   ```

---

## 06 ==递归==：

本身调用本身。

递归头：什么时候不调用自身方法。如果没有头则死循环。
递归体：什么时候需要调用自身方法。

```java
 public static void main(String[] args) {
        System.out.println(f(3));
    }

    // 3!
    // 3*f(2)
    // 2*f(1)
    // 1
    public static int f (int n){
        // 递归头
        if (n==1){
            return 1;
        }
        // 递归体
        else {
            return n*f(n-1);
        }
    }
```

---

# Java数组

## 01 数组声明 创建 ：

- 先声明
- dataType [ ]  arryRefVar ; // 首选方法
- dataType arrayRefVar [ ] ; // 效果相同，为C/C++易于学习
- 通过new 操作符 创建数组
- 数组长度 array.length

 ```java
   public static void main(String[] args) {
                
        int[] nums; // 声明

        nums = new int[10]; // 创建

        // 赋值
        nums[0] = 0;
        nums[1] = 1;
        nums[2] = 2;
        nums[3] = 3;
        nums[4] = 4;
        nums[5] = 5;
        nums[6] = 6;
        nums[7] = 7;
        nums[8] = 8;
        nums[9] = 9;

        for (int i = 0; i < nums.length; i++) {
            System.out.println(nums[i]);
        }

    }
 ```


----

## 02 三种初始化以及内存分析：

### 内存分析

![在这里插入图片描述](https://img-blog.csdnimg.cn/f823fc3b7a3147048598a69a1e50bf6f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54y_5Lq65aS0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/a380e27c89ae4dd7a1b058110964ad9c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54y_5Lq65aS0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)

### 三种初始化

- 静态初始化
- int [ ] a = { 1 ,2 ,3 } ;
- Man [ ] mans = { new Man (1 ,1 ), new Man (2 ,2 )};
- 动态初始化
- int [ ] a = new int [2];
- a [0] = 1;
- a [1] = 2;
- 数组的默认初始化
- 数组是引用类型 ， 他的元素相当于类的实例变量 ， 因此数组一经分配空间 ，  其中的每个元素也是按照实例变量同样的方式被隐式初始化。

---

## 03 下标越界及小结：

四个基本特点

- 长度确定，不允许更改。
- 元素类型相同，不允许混合类型。
- 数组中元素可以任何数据类型，包括基本类型和引用类型。
- 数组变量属于引用类型，数组也可以看成是对象，数组中的每个元素相当于该对象的成员变量。

 数组本身就是对象，java中对象是在堆中，因此数组无论保存原始类型还是其他对象类型，数组对象本身是在堆中。

---

## 04 数组的使用：

> 在java中，args是arguments的缩写，是指字符串变量名，属于引用变量，名字代号而已，只是一个默认名，可以自己取的，一般都习惯性照写。String[]
> args是main函数的形式参数，可以用来获取命令行用户输入进去的参数。


- For-Each 循环
  普通for循环和增强for循环（没有下标）。

- 数组作方法入参

```java
			// 打印数组元素 
 public static void printArray(int [] array){
        for (int i = 0; i < array.length; i++) {
            System.out.println(array[i]+" ");
        }
    }
 
```

- 数组作返回值

```java
    // 反转数组
    public static int[] reverse (int [] arrays) {
        int [] result = new int[arrays.length];
        
        // 反转的操作
        for (int i = 0, j = result.length; i < arrays.length; i++) {
            result[j]  = arrays[i];
        }
        
        return result;
    }
    
```


---

## 05 二维数组/多维数组：

二维数组：int a [ ][ ] = new int [ 2 ] [ 5 ] ; 
					int [ ] [ ] = {{1,2},{2,3},{3,4},{4,5}};
					

---

## 06 Arrays类：

toString: 返回该对象的字符串表示
sort

---

# 面向对象

## 01 什么是面向对象：

对宏观上分析，需要用面向对象思路分析整个系统，但是具体微观操作还是要用面向过程的思路。

面向对象编程：object- oriented programming，OPP）
本质：以类的方式组织代码，以对象的组织（封装）数据。

抽象

三大特性：封装、继承、多态

---

## 02 方法的回顾与加深：

### 方法的定义：

- 修饰符
- 返回类型
- break	return
- 方法名
- 参数列表
- 异常抛出

```java
// 类
public class demo1 {
        // main 方法
    public static void main(String[] args) {
        
        
    }
    
    /*
    修饰符 返回值类型   方法名（...）{
        //方法体
      }
     */
    
    public String sayhello(){
        return "hello,world!";
    }
    
    public int max(int a , int b){
        return  a>b?a:b;
    }
}
```


### 方法的调用：递归

- 静态方法
- 非静态方法
- 形参和实参
- 值传递和引用传递
- this关键字

主方法体：

```java
public class test {
    // 静态方法 static
    public static void main(String[] args) {
        //非静态方法
        //实例化这个类
        // 对象类型 对象名 =  对象值
        Student student = new Student();

        student.say();
        

    }
}
```


学生方法体（被调用）：

```java
public class Student {
    // 方法
    public void say(){
        System.out.println("学生说话了");
    }
}
```

二者都是static或非静态时可互相调用，
但 有二者不相同不可调用，
因为static 和类同时加载，
而 非静态方法则类实例化后才存在。

---

## 03 类与对象的创建：

        //类：抽象的 实例化
        // 类实例化后会返回一个自己的对象
        //student对象就是Student类的具体实例
       Student xh = new Student(); 


## 04 ==构造器详解==

构造器也称为构造方法，是在进行创建对象的时候必须要调用的。并且构造器有一下两个特点：

- 必须和类的名字相同
- 必须没有返回类型，也不能写void

作用：

  1. 使用new关键字，本质是在调用构造器，必须要有构造器。
  2. 初始化值

 注意：有参构造： 一旦定义了有参构造，无参必须显示定义。

 快捷键： ==Fn + control + enter/command + N==: 生成构造器

this.  			= 
当前类					参数传进来的值

---

## 05 创建对象内存分析：

![在这里插入图片描述](https://img-blog.csdnimg.cn/8f1e98b1dd7c499aa1497112cec7ea63.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54y_5Lq65aS0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


---

## 06 小结类与对象：

- 类与对象：类是一个模板：抽象；对象是一个具体的实例。
- 方法：定义，调用。
- 对应的引用：
- 引用类型 基本类型（8）
  对象是通过引用来操作的	 栈----->堆。

- 属性：字段 Field 成员变量
  默认初始化：
  数字： 0	，	0.0
  char：u0000
  boolean：false
  引用：null

修饰符 属性类型 属姓名 = 属性值

- 对象的创建和使用：

1. 必须使用new关键字创建对象， 构造器 Person tom = new Person（）；
2. 对象的属性：tom.name;
3. 对象的方法：tom.sleep();

- 类：
- 静态的属性： 属性
- 动态的行为： 方法


---

 ## 07 封装：

属性私有：get/set

封装（数据的隐藏）：通常应该禁止个对象中数据的实际表示，而应该通过操作接口来访问，这称之为==信息隐藏==。

### 意义：

1. 提高程序的安全性，保护数据；
2. 隐匿代码的实现细节；
3. 统一接口；
4. 增加系统可维护性；


### 看方法源码的方法： 

通过== command 加 鼠标点击 ==可以进入方法源码


主类：

```java
package app;

import app.opp.Student;

public class Applacation {
    public static void main(String[] args) {

        Student tim = new Student();

        tim.setName("tim");
        System.out.println(tim.getName());

        tim.setAge(999);
        System.out.println(tim.getAge());

    }
}
```

方法类：

```java
package app.opp;

public class Student {

    private String name;

    private int id;

    private char sex;

    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public char getSex() {
        return sex;
    }

    public void setSex(char sex) {
        this.sex = sex;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age>120 || age<0){
            this.age = 3;
        }else {
            this.age = age;
        }
    }
}
```


---

## 08 继承：

is a 关系。
子类是父类的扩展。
私有无法继承
一般属性是私有
只有单继承，没有多继承
只能有一个父类，可以间接继承多个

快捷键：==层级树：control + h==
派生类 = 子类

### object 类

所有的类都默认直接或者间接继承object类。


### super注意点：

隐藏代码：调用父类无参构造
空super();

---

![在这里插入图片描述](https://img-blog.csdnimg.cn/184211f10ef84e79b85e4b41741179c1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54y_5Lq65aS0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)



### 方法重写：

![在这里插入图片描述](https://img-blog.csdnimg.cn/9a2b255864fd4971a57032f0cf9d06ce.png#pic_center)
protected：包内以及子类可见。

---

## 09 多态：

同一个方法可以根据发送对象的不同而采用多种不同的行为模式；
一个对象的实际类型是确定的，但是可以指向对象的引用类型很多；

### 多态存在条件：

- 有继承关系；
- 子类重写父类方法；
- 父类引用指向子类对象 ；Father f1 = new son()；

### 注意：

- 多态是方法的多态，属性没有多态
- 父类和子类，有联系 类型转换异常 ClassCastException
  	

### 不能被重写的方法：

		1. static 方法，属于类，不属于实例；
		2. final常量；
		3. private方法；

![在这里插入图片描述](https://img-blog.csdnimg.cn/8dd8db4ac7ab4a6a94dfa6b073aa0981.png#pic_center)

---

### instanceof (类型转换) 引用类型：

判断两个对象之间是否有父子关系:

```java
 public static void main(String[] args) {

        Object object = new Student();

        System.out.println(object instanceof Student);
        System.out.println(object instanceof Person);
        System.out.println(object instanceof Object);
        System.out.println(object instanceof Teacher);
        System.out.println(object instanceof String);

        System.out.println("===========================");

        Person person = new Student();

        System.out.println(person instanceof Student);
        System.out.println(person instanceof Person);
        System.out.println(person instanceof Object);
        System.out.println(person instanceof Teacher);
        //System.out.println(person instanceof String); //编译报错

        System.out.println("===========================");

        Student student = new Student();

        System.out.println(student instanceof Student);
        System.out.println(student instanceof Person);
        System.out.println(student instanceof Object);
        // System.out.println(student instanceof Teacher); // 编译报错
        // System.out.println(student instanceof String); // 编译报错



    }
```


### 强制转换：

// 类型之间的转化：父——子；
// 子类转换为父类，可能会丢失自己本来的方法；
Eg1:
Student student = new Student();
student.go();
Person person = student;
person.go(); // 无法执行

Eg2：
Person obj = new Student();

// student将这个对象转换为Student类型，
就可以使用Student方法了

((Student)obj).go();

### new对象详解：

类名 对象名 = new 类的构造函数;

### 多态总结：

1. 父类引用指向子类对象；
   子类引用无法指向父类对象；
    Person person = student;
 2. 把子类对象转换为父类，向上转型，无需强制转换；
 3. 把父类转换为子类，向下转型，强制转化（不是很好，丢方法）；
 4. 方便方法的调用，减少重复代码，提升利用率，简洁；

### 开闭原则：

==不允许修改，允许扩展。==

---

## 10 static关键字详解：

### 静态导入包：

import static java.lang.Math.random;
直接写方法例如：random()；

Final是常量修饰符，通过Final修饰的类不能被继承，没有子类；


### 启动顺序：

静态（且只执行一次）
匿名代码块  {   } //常用来赋初始值
构造方法



---

## 11 抽象类：

### abstract ：

	public abstract class XXX
	抽象方法，只有方法名字，没有方法实现；
	public abstract void XXX();
	修饰方法为抽象方法；
	修饰类为抽象类；

### 注意：

- 抽象类可以没有抽象方法，但是有抽象方法的类一定要声明为抽象类；

- 抽象类，不能使用new关键字创建对象，它是用来让子类继承的；
- 抽象方法，只有方法的声明，没有方法的实现，它是用来让子类实现的：约束；

- 子类继承抽象类，则必须要实现抽象类没有实现的抽象方法，否则该子类也要声明为抽象类；

抽象类不常用，因为单继承，常用接口；

---

## 12 接口：

### 概念：

- 普通类：只有具体实现；
- 抽象类：具体实现和规范（抽象方法）都有；
- 接口：只有规范；约束和实现分离：面向接口编程；

- 接口就是规范，定义的是规则，体现“如果你是...则必须能...”的思想；
- 接口本质是契约，制订好人们遵守；
- OO的精髓，是对对象的抽象，最能体现这一点就是接口。为什么我们讨论设计模式都只对具备了抽象能力的语言（c++，java，c#）就是因为设计模式所研究的，实际就是如何合理的去抽象；

- 声明类的关键字是class，声明接口的关键字是interface；


---


### 作用：

- 约束；
- 定义一些方法，让不同的人实现 10个员工共同实现一个接口；
- public abstract；
- 常量 public static abstract；
- 接口不能实例化，没有构造方法；
- implements 可以实现多个接口；
- 必重写接口的方法；

---

UserService:

```java
package app.Service;

// interface定义的关键字,接口都需要有实现类

public interface UserService {
    // 接口中所有定义都是抽象 public abstract

    //常量
    // public static final int AGE = 99;
    // 一般不在接口中定义常量；

    int AGE = 99;

    void add(String name);
    void delete(String name);
    void update(String name);
    void query(String name);


}
```

---

TimeService:

```java
package app.Service;

public interface TImeService {
    void timer();
}
```

---

UserServiceImpl:

```java 
package app.Service;
/*
 实现类
 抽象类：extends
 类 可以实现接口 implements 接口（伪多继承）

 多继承 利用接口实现多继承
*/


public class UserServiceImpl implements UserService,TImeService{

    // command + N 快速实现方法

    @Override
    public void add(String name) {

    }

    @Override
    public void delete(String name) {

    }

    @Override
    public void update(String name) {

    }

    @Override
    public void query(String name) {

    }

    @Override
    public void timer() {

    }
}
```

---

## 13 内部类：

一个Java文件中只能有一个public 类，但是可以有多个class

### 概念：

在类中定义一个类；

- 成员内部类；

Outer：

```java
package app.InnerClass;

public class Outer {

    private int id = 10;
    public void out(){
        System.out.println("这是外部类的方法");
    }
    public class Inner{
        public void in(){
            System.out.println("这是内部类的方法");
        }
        // 获得外部类私有属性 私有方法；
        public void getID(){
            System.out.println(id);
        }
    }
}
```

Main:

```java
package app;

import app.InnerClass.Outer;

public class Applacation {
    public static void main(String[] args) {
        Outer outer = new Outer();

        //通过外部类来实例化内部类；

        Outer.Inner inner = outer.new Inner();
        inner.in();
        inner.getID();
    }
}
```

- 静态内部类；
  Outer:

```java 
public class Outer {

    private int id = 10;
    public void out(){
        System.out.println("这是外部类的方法");
    }
    public static class Inner{
        public void in(){
            System.out.println("这是内部类的方法");
        }

        } 
}
```

- 局部内部类；
  Outer:

```java
public class Outer {

        public void method(){
            class Inner{
                public void in(){

                }
            }
        }
}
```

- 匿名内部类；

```Java
package app.InnerClass;

public class test {
    public static void main(String[] args) {
        // 没有名字初始化类，不用讲实例保存到变量中；
        new Apple().eat();
        UserService userservice = new UserService(){

            @Override
            public void hello() {
                
            }
        };
                
    }
}

class Apple{
    public void eat(){
        System.out.println("1");
    }
}

interface UserService{
    void hello();
}

```

---

# 异常

## 01 Error和Exception：

### 三种类型异常：

- 检查性异常：用户错误或问题引发，例如打开不存在的文件；
- 运行性异常：可能呗程序员避免的异常。运行时异常可以在编译时被忽略，按照异常的状态运行程序；
- 错误：错误不是异常，而是脱离程序员控制的问题，错误在代码中通常被忽略。例如当栈溢出时，一个错误就发生了，它们在编译也检查不到；

---

### 异常体系结构：

定义一个基类java.lang.Throwable作为所有异常的超类；
![在这里插入图片描述](https://img-blog.csdnimg.cn/e4feb34288e24bd8aa978097851fffa2.png)![在这里插入图片描述](https://img-blog.csdnimg.cn/e84e61d5f72f4ad2baee49408cb6c822.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/5a86a37760114e09a1b88f4904584e8c.png)


## 02 捕获和抛出异常：

关键字：
try、catch、finally、throw、throws

```java
 public static void main(String[] args) {

        int a = 1;
        int b = 0;

        try{ // 监控区域
            System.out.println(a/b);
        }catch(ArithmeticException e){ // 参数想要捕获的异常类型，最高 Throwable； 
            System.out.println("程序出现异常，变量b不为0");
        }finally {
            // 无论是否出异常都会finally，善后工作；
            // finally可以不要，假设IO流，资源，关闭采用finally；
            System.out.println("finally");
        }

    }
    
```

catch小异常上，大异常下，层层递进；

```java
public class Test {
    public static void main(String[] args) {

        int a = 1;
        int b = 0;

        try{ // 监控区域
            System.out.println(a/b);
        }catch(Error e){
            System.out.println("Error");
        }catch (Exception e){
            System.out.println("Exception");
        }catch (Throwable t){
            System.out.println("Throwable");
        }finally {
            // 无论是否出异常都会finally，善后工作；
            // finally可以不要，假设IO流，资源，关闭采用finally；
            System.out.println("finally");
        }

    }
    public void a(){
        b();
    }
    public void b(){
        a();
    }
}
```

### 自动生成

快捷键：command option T

```java
public class testkey {
    public static void main(String[] args) {
        int a = 1;
        int b = 0;

        try {
            System.out.println(a/b);
        } catch (Exception e) {
            System.exit(1);
            e.printStackTrace();// 打印错误的栈信息
        } finally {
        }
    }


}
```

### 主动抛出异常：

try catch是遇到错误也能运行，throw和throws是运行时候抛出异常；

```java
package app.exception;

public class Test {
    public static void main(String[] args) {

        try {
            new Test().test(1,0);
        } catch (ArithmeticException e) {
            e.printStackTrace();
        }


    }

    // 假设这方法中，处理不了这个异常，方法上抛出异常

    public void test(int a , int b )throws ArithmeticException{
        if (b == 0){
           throw new ArithmeticException();
            // 主动抛出异常，一般在方法中使用
        }
        System.out.println("jk");
    }
}
```

---

## 03 自定义异常和总结：

### 简介：

Java内置异常类可以描述大部分异常，自定义异常类只需要继承Exception即可。

### 步骤：

- 创建自定义异常类；
- 在方法中通过throw关键字抛出异常对象；
- 如果在当前抛出异常的方法中处理异常，可以使用try-catch捕获并处理；否则在方法的声明处通过throws关键字指明要抛出给方法调用者的异常，继续进行下一步操作；
- 在出现异常方法的调用者中捕获并且处理异常；

快捷键：command + n：toString()添加注解

---

### 自定义异常类：

```java
package app.exception;

public class MyException extends Exception {
    //传递数字>10;
    private int detail;

    @Override
    public String toString() {
        return "MyException{" +
                "detail=" + detail +
                '}';
    }

    public MyException(int a){
        this.detail = a ;


    }


}
```

### 测试类：

```java
package app.exception;

public class Test {
        static void test(int a ) throws MyException {

            System.out.println("传递的参数为"+a);

            if (a > 10 ){
                throw new MyException(a);
            }
            System.out.println("ok");
        }

    public static void main(String[] args) {
        try {
            test(11);
        } catch (MyException e) {
            System.out.println("Myexception=>"+e);
        }

    }
}
```

---

### 实际应用中经验总结：

- 处理运行时异常时，采用逻辑去合理规避同时辅助try - catch处理，避免卡死；
- 在多重catch块后面，可以加上一个catch（最大Exception）来处理可能会被遗漏的异常；
- 对于不确定的代码，也可以加上try-catch，处理潜在的异常；
- 尽量去处理异常，切记只是简单调用printStackTrace（）去打印输出；
- 具体如何处理异常，要根据不同业务需求和异常类型去决定；
- 尽量添加finally语句块去释放占用的资源；
