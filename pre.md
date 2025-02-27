# 常用快捷键

ctrl+c 复制

ctrl+v 粘贴

ctrl+x 剪切

ctrl+z 撤销

ctrl+s 保存

alt+f4 关闭窗口

shift+delete 永久删除

win+e 我的电脑

ctrl+shift+esc 任务管理器



# DOS命令

### 打开方式

1.开始+系统+命令提示符

2.win+r输入cmd

3.在任意文件夹下shift+鼠标右键此处打开命令行

4.资源管理器地址栏前加上cmd



### 常用命令

```shell
#盘符切换
#dir 查看当前目录下的所有文件
#cd 切换目录
#cls 清除屏幕
#exit 退出终端
#ip config 查看电脑ip
#calc mspaint notepad 打开应用
#ping 命令
#md 创建文件夹
#cd>a.txt 创建文件
#del a.txt 删除文件
#rd 移出文件夹
```



# JAVA特性

简单、面向对象、可移植性、高性能、分布式、动态性、多线程、安全性、健壮性

***write once,run any where***



# JAVA三大版本

JavaSE:标准版，桌面程序&&控制台开发

JavaME:嵌入式开发

JavaEE:企业级开发，web端&&服务器开发



# JDK/JRE/JVM

JDK：Java开发者工具（一般包含JRE）

JRE：Java运行时环境

JVM：Java虚拟机


### 卸载JDK

1.删除java的安装目录

2.删除JAVA_HOME

3.删除path下关于java的目录

4.查看java -v


### 安装JDK

1.百度搜索JDK，找到下载地址

2.同意协议，下载电脑对应版本

3.双击安装JDK，记住安装路径

4.配置环境变量：（我的电脑->属性）JAVA_HOME

5.配置path变量



# 第一个程序-HelloWorld

```java
public class Hello
{
    public static void main(string[] args)
    {
        System.out.print("Hello,world!");
    }
}
```

**注意：文件名和类名要一致**



# JAVA程序运行机制

**编译型**：类似把书翻译成另一个版本（操作系统，常用c/c++）

**解释型**：用一下编译一下，类似随身的翻译员（网页，速度要求不高，使用java等)
