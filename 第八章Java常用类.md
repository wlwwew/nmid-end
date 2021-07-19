## 第八章Java常用类

 

### 第一节 java类库概述

JavaDoc技术，可以将注释抽取出来，形成了以HTML表现形式的API文档

Java.lang.*  java 编程语言的基本类库

 java.io.*  提供了通过数据流、对象序列以及文件系统实现的系统输入、输出。

 java.math.* 提供了简明的证书算术以及十进制算数的基本函数 

Java.text.*  包括以一种独立于自然语言的方式处理文本、日期、数字和消息的类和接口

Java.time.*  提供Java日期、时间类（Java8新增的包）

Java.util.* 包括集合类、时间处理模式、日期时间工具等常用工具包

 

### 第二节  数字相关类

##### Java数字类

整数  Short,Int,Long

浮点数Float，Double

大数类Biginterger（大整数），BigDecimal（大浮点数）

随机数类 Random

##### 工具类 Math

Java.math包 

Abs是绝对值函数

Max是比较函数

Pow是幂函数

Round是四舍五入函数

Ceil是向上取整

Floor是向下取整

 

### 第三节 Java常用类

##### String

使用频率高

是一个不可变对象，加减操作性能较差

charAt concat contains endsWith equals equals IgnoreCase hashCode indexOf 

length replace replaceAll split startsWith subString trim valueOf

 #####  可变字符串

StringBuffer(字符串加减，同步，性能好)

StringBuilder（字符串加减，不同步，性能更好）

Append insert delete replace substring

Length 字符串实际大小，capcity字符串占用空间大小

trimToSize（）：去除空隙，将字符串存储压缩到实际大小

如果有大量append，实现预估大小，在调用相应构造函数

 

### 第四节 时间相关类

Java.Util.Date

getTime()

java.sql.Date

Calendar 抽象类    

Calendar gc=Calendar.getInstance();

Calendar gc=new GregorianCalendar();

##### 简单工厂模式

Calendar

Get(Field)来获取时间中每个属性的值，注意月份0-11.要加一

GetTime（）返回相应的Date

GetTimeInMillis(),返回自1970.1.1以来的毫秒数

Set(Field)设置时间字段

Add(field,amount)根据指定字段增加/减少时间

Roll(field,amount)根据指定字段增加/减少时间，但不影响上一级的时间段

##### Java 8推出新的时间ApI

* Java.time 包

* 旧的设计不好（重名的类、线程不安全等）

* 新版本优点 ： 不变性，在多线程环境下

遵循设计模式，设计得更好，可扩展性强

Java8 java.time 包主要类

localDate:日期类

localTime:时间类（时分秒-纳秒）

LocalDateTime:LocalDate+LocalTime

Instant:时间戳

补充：很多程序语言都将1970-01-01 00：00作为一个起点（参照物）。

 

### 第五节  格式化相关类

 

Java.text 包java.text.Format的子类

NumberFormat：数字格式化，抽象类        3个数字一个“，“

MessageFormat：字符串格式化

DateFormat：日期、时间格式化，抽象类

Java.time.format包下

DateTimeFormatter

MessageFormat:字符串格式化

支持多个参数-值对位复制文本

支持变量的自定义格式

DateFormat：时间格式化，抽象类

Simple DateFormaat 工厂模式

Parse：将字符串格式花为时间对象

Format：将数据对象格式转化为字符串

 

Java.time.format.DateFormatter:时间格式化

Jdk8发布，线程安全

ofPattern：设定时间格式

parse:将字符串格式化为时间对象

format：将时间对象格式化为字符串