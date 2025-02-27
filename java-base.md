## java注释

单行注释：//

多行注释：/**/

JavaDoc：文档注释

```java
/**
*@Description helloworld
*@Author st
*/
```



## java标识符

**关键字**

![image-20250211180700270](C:\Users\Linda\AppData\Roaming\Typora\typora-user-images\image-20250211180700270.png)



## 数据类型：强类型语言

```java
//基本类型——9种
int num1=10;
byte num2=20;
short num3=30;
long num4=30L;

float num5=50.1F;
double num6=3.14;

char name='t';
String name="ST";
boolean flag=true;

//引用类型
```



**拓展：**

```java
//整数拓展：二进制0b 十进制 八进制0 十六进制0x
//浮点数拓展：BigDecimal
//字符拓展：强制转换，所有的字符本质还是数字unicode
```



**类型转换**

```java
int i=128;
byte b=(byte)i;
//强制转换 高->低
//自动转换 低->高
//!!不能转换布尔值!!不能把对象转换成不相干的类型!!
//!!转换时可能会存在内存溢出或者精度问题!!
```



## 变量

实例变量：从属于对象，在方法外独立存在

局部变量：在方法中的变量

类变量：static



## 常量

不再变化的值，使用final关键字，修饰符不区分先后顺序



## 命名规范

类成员变量：首字母小写驼峰原则

局部变量：首字母小写驼峰原则

常量：大写字母下划线

类名：首字母大写驼峰原则

方法名：首字母小写驼峰原则



## 运算符

算数运算符：+ - * / % ++ --

赋值运算符：=

关系运算符：> < >= <= == != instanceof

逻辑运算符：|| && ！

位运算符：| ^ & ~ >> << >>>(按位右移补零)

扩展运算符：+= -= /= *=

*Math工具类*：Math.pow(3,2)3^2

**字符串连接+：**如果字符串在前，则进行字符串拼接，否则前面两个变量会默认进行运算

三元运算符：x?y:z



## 包机制

包的本质就是文件夹，**一般利用公司文件名倒置作为包名，如：com.baidu**

则package com.baidu.www

可使用import导入包以及各个包中的**类**



## JAVA Doc

```java
/**
* @author作者名
* @version版本号
* @since指明需要最早使用的jdk版本
* @param参数名
* @return返回值情况
* @throws异常抛出情况
*/
```

分为类注释和方法注释

通过命令javadoc [参数] java文件名可在命令行生成index.html



## java流程控制

### 输入输出

```java
Scanner scanner = new Scanner(System.in);
System.out.println();
//判断是否有输入字符串/行
scanner.hasNext();
scanner.hasNextLine();
//获取一个字符串/行，前者不带空格
String str = scanner.next();
String str = scanner.nextLine();
//关闭IO流
scanner.close();
//进阶
Scanner.hasNextInt()/hasNextFloat()...
Scanner.nextInt()/nextFloat()...
```



### 顺序结构

一句一句进行，很简单，略了^ ^



### 选择结构

**if选择结构**

- 与c/c++一样，if...else...等等
- 字符串的判断可以写.equals("string")做判断

**switch选择结构**

- 与c/c++一样，

- ```java
  switch(grade)
  {
      case value1:...
      case value2:...
  }
  ```

- 从java SE7开始，switch支持字符串的比较了

*可以在工程文件夹中找到class文件，在IDEA文件中打开，可以看到反编译代码，图标为01字符*



### 循环结构

**while循环**

- 与c/c++一样，不多说惹

**dowhile循环**

- 即使不满足条件，也要至少执行一次，即先执行后判断

**for循环**

- 与c/c++一样

```java
for(int i=0;i<n;i++)
{...}
//for-each
for(int x:nums)
{...}
```

**break&&continue**

continue中还有带标签的用法，类似goto，不推荐



## 方法

方法是语句的集合，实现一个功能，在程序中被创建，在其他地方中被引用，包含在类或对象中

**重载：**一个类有两个同名的方法，但方法的参数类型不同，是被允许的

*可使用命令行运行main方法*

**可变参数：**可以在方法的最后几个参数设置可变参数

```java
void test(int... numbers)
{
    if(numbers.length()==0)
        	System.out.println("No argument there");
    ...
}
```



## 数组

```java
int[] nums;//定义一个数组
nums=new int[10];//分配空间
//数组通过下标访问，与c/c++相同
nums[0]=1;
...
//获取数组的长度
nums.length
//类似的，引用类型
Woman[] w=new Woman[2];
//多维数组
int[][] array={{1,2},{2,3}...};
//for-each循环语句
for(int i:nums)
{...}
//打印一个数组
printArray(array[0]);
System.out.println(Arrays.toString(array[0]));
//数组进行排序
Arrays.sort(array[0]);
```

**稀疏数组压缩**

[0]记录行数列数即有效数字数n个

剩余的n行记录第i行第j列有数字x



## 面向对象编程

- **面向对象三大特性：封装、继承、多态**

- **静态方法（static）**可以直接引用，**非静态方法**需要先进行对象实例化（new）

- **static**和类一起加载，**非静态方法**在类实例化之后才存在

- java通常是**值传递**，通过传递对象可以进行**引用传递**

- **类实例化**后会返回一个自己的对象

- **构造方法**与类名相同，无返回值**（不能写void）**，可用于初始化信息
- 构造分为**有参构造**和**无参构造**，一旦定义了有参构造，则无参构造必须显示定义，空着不写即可。
- 构造器可用alt+insert生成默认框架

- 类中包含**属性**和**方法**。前者会进行默认的初始化：*数字：0/0.0，char u0000, boolean:false*,引用：null



### 封装

> **该露的露，该藏得藏**、**高内聚，低耦合**

- **public**属性可通过对象引用，**private**属性为对象的私有，外部不能使用、访问这种属性，一般会通过编写**get/set**方法实现私有属性的获取和修改



### 继承

使用修饰词**extends**实现继承：  

```jav
//Parent类
public class Person
{String name;}
//派生类
public class Teacher extends Person
{...}
public class Students extends Person
{...}
```

*private的属性和方法无法被继承*

*使用ctrl+h可以查看类的继承树*

*在java中，所有的类都默认直接或间接地继承自Object类*

*java中没有多继承，只有单继承*



:heavy_dollar_sign: **修饰符this、super**

**this**:当前类的

**super**:Parent类的

- *调用Parent类的构造器时必须是子类构造器的第一行，使用this时也必须在构造器的第一行*
- *子类默认使用Parent类的构造方法*
- *super只能出现在子类方法或者构造方法中，只有在有继承条件时才可以使用*



### 方法的重写

@Override 一种注释，表示重写

重写条件：需要有继承关系，public，子类重写Parent类的方法

- 方法名必须相同

- 参数列表必须相同

- 修饰符：范围可扩大，但不能缩小
- 抛出的异常：范围可以被缩小但不能被扩大



**Parent类的引用指向了子类是可以的，而静态方法的调用只和左侧定义的数据类型有关；**

**非静态：Parent类引用了子类则部分非静态方法将进行重写**



:thinking: **为什么重写？**

- 子类不一定需要Parent类的功能，或者不能满足子类需要
- Alt+insert:@Override



### 多态

一个对象的实际类型是确定的，但其指向的**引用类型**不确定：

```java
public class Student extends Person(){...}
...
Student s1=new Student();
Person s2=new Student();
```

对象能执行哪些方法，只看左边的定义类型，与右边的引用没什么关系

因此Parent类可以引用子类，但是不能调用子类独有的方法

**多态的前提是有继承关系**

**多态指方法的多态，属性没有多态**



**instanceof:**用于判断类之间的继承关系

```java
Object obj = new Student();
System.out.println(obj instanceof Student);//true
System.out.println(obj instanceof Object);//true
System.out.println(obj instanceof Teacher);//false
System.out.println(obj instanceof String);//false

Person per = new Student();
System.out.println(per instanceof Person);//true
System.out.println(per instanceof Teacher);//false
System.out.println(per instanceof String);//报错！
```

**能否通过？**

左侧的对象类型是否与右侧存在继承关系

**是否true?**

左侧的引用是否是右侧类型的子类



### static

**静态变量（类变量）**

```java
private static age;
...
Student.age...
```

**静态方法与非静态方法**

静态方法可以调用静态方法

静态方法不能调用非静态方法（静态方法与类一起加载）

非静态方法可以调用静态方法（非静态方法申请之后才会存在）

**静态代码块**只执行一次



### abstract

使用修饰词**abstract**定义抽象类、抽象方法

**抽象方法**只有名字，没有具体实现

**继承了抽象类的子类，必须实现抽象方法**

**抽象类不能new，只能靠子类实现**

**抽象方法必须在抽象类中，抽象类中可以写普通方法**



### 接口

**普通类**只有具体实现，**抽象类**既有具体实现也有规范的抽象方法，**接口**只有规范，实现约束和实现的分离

使用**interface**定义

```java
public interface UserService
{
    //接口中的所有定义都是抽象的public
    //默认为public abstract
    public abstract void run(String name);
}

//接口都需要实现类，一个类可以实现多个接口（接口可多继承）
public class UserServiceImpl implements UserService
{
    //实现一个接口，则需要实现接口中的所有方法
    public void run(String name)
    {...}
}
```

:thinking:**作用是？**

1.约束

2.定义一些方法，让不同的人实现

3.**接口不能实例化，因为其没有构造方法**



### 内部类

定义在一个类内部的类，还可以定义在一个方法里面

初始化类也可以没有名字，直接new，不用将实例保存到变量中



## 异常

**简单分类**

检查型异常

运行时异常

错误ERROR

![image-20250217201055512](C:\Users\Linda\AppData\Roaming\Typora\typora-user-images\image-20250217201055512.png)

**异常块try，捕获catch，无论是否有异常，最终都会执行finally（可以不要），其余的异常类型会在finally执行后报出**

**捕获多个异常可以并列写多个catch块，且需要从小到大进行捕获**

**ctrl+alt+t，可以进行快捷键生成异常块的框架**



**自定义异常：**

```java
public class MyException extends Exception
{
	private int detail;
    public MyException(int a)
    {
        this.detail=a;
    }
    @Override
    public String toString()
    {
        return "MyException{"+detail+'}';
    }
}

//测试类
static void Test(int a)
{
    if(a>10)
    {
        throw new MyException(a);//抛出异常
        System.out.println("OK");
    }
}

public static void main()
{
    int a=...;
    try{
        test(a);
    }
    catch(Exception e)
    {
        System.out.println("MyException=>"+e);
    }
}

```

