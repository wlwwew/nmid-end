## 第十一章Java文件读写

### 第一节  文件系统及JAVA文件基本操作

文件系统是由OS（操作系体）管理

文件系统和JAVA进程是平行的，是两套系统

文件系统是由文件夹和文件递归组合而成

文件目录分隔符

Linux/Unix 用/隔开                    常见的字符转义

Windows 用\隔开，涉及到转义，在程序中需要/或[\\代替](file://代替)    \n 等价于换行

文件包括文件里面的内容和文件基本属性            \r等价于回车

文件基本属性：名称、大小、扩展名、修改时间等        \t等价于tab建

Java文件类File(java6)

Java.io.File是文件和目录的重要类

目录也可以File类进行表示

File类于OS无关，但会受到Oscar的权限限制

常用方法

createNewFile,delete,exists,getAbsolutePath,getName,

getParent,getPath,isDirectory,isFile,length,listFiles,mkdir,mkdirs

注意：File不涉及到具体的文件内容，只涉及属性 

exists 判断File对象是否存在        

 mkdir 创建一级（一层）目录

 mkdirs 创建多级（多层）目录

isDirectory 是否是目录

isFile 是否是文件

createNewFile创建新文件（非目录）

java NIO

java7提出的NIO包，提出新的文件系统类

Path，File，Directory Stream，FileVisitor，FileSystem

是java.io.File的有益补充

文件复制和移动

稳健性对路径

递归遍历目录

递归删除目录

 

### 第二节  java io包概述

文件系统和java是两套系统

Java读写文件，只能以（数据）流的形式进行读写

##### Java.io包(1)

节点类：直接对文件进行读写

包装类

转化类：字节/字符/数据类型的换化类

装饰类：装饰节点类

##### Java io包（2）

字节：byte,8bit,最基础的储存单位

字符：a，10000，我

数据类型：3，5.25，abcdef

文件是以字节保存，因此程序将变量保存到文件需要转化

##### Java io 包（3）

节点类：直接操作文件类

 InputStream，OutputStream（字节） InputStream：数据从文件读取到java里  

FileInputStream，FileOutputStream  OutputStream：数据从java输出到文件里

Reader，Writer（字符）

FileReader，FileWriter

###### Java io包（4）

转化类：字符到字节之间的转化

InputStreamReader：文件读取时字节，转化为Java能理解的字符

OutputStreamWriter：Java将字符转化为字节输入到文件中

装饰类：装饰节点类

DataInputStream，DataOutputStream：封装类数据流

BufferedInputStream，BufferOutputStreram：缓存字节流

BufferedReader，BufferedWriter：缓存字符流

### 第三节  文本文件读写

 ##### 文本文件读写（1）

 文件类型

   一般文本文件（若干行字符构成的文件），如txt等

   一般二进制文件，如数据文件dat

   带特殊格式的文本文件，如xml等

   文件时数据的一个容器（口袋）

   文件可以存放大量的数据

   文件很大，注定Java只能以流形式依次处理

从Java角度理解

输出：数据从Java到文件中，写操作

输入：数据从文件到Java中，读操作

文本文件读写

输出文本字符到文件中

从文件中读取文本字符串

写文件

先创建文件，写入数据，关闭文件

FileOutputStream，OutputStreamWriter，BufferedWriter

BufferWriter

Write

newLine

try-resoure语句、自动关闭资源

关闭最外层的数据流，将会把其上所有的数据流关闭

##### 文本文件读写（4）

读文件

先打开文件，逐行读入数据，关闭文件

File Output Stream，Output StreamWriter，Bufferedriter

BufferWriter

readLine

try-resource语句，自动关闭资源

关闭最外层的数据流，将会把其上所有的数据流关闭

##### 文本文件读写（5）

##### 总结

理解节点类、转换类和包装类的联合用法

尽量使用try-resource语句，自动关闭资源

### 第四节  二进制文件读写

##### 二进制文件读写（1）

二进制文件

狭义上说，采用字节编码，非字符编码的文件

广义上说，一切文件都是二进制文件

用记事本等无法打开/阅读

二进制文件读写

输出数据到文件中

从文件中读取数据

##### 二进制文件读写（2）

写文件

先创建文件，写入数据，关闭文件

File Output Stream，BufferedOutput Stream，DataOutputStream

DataOutputStream

flush

write/writeBoolean/writeBye/writeChars/writeDouble/writeInt/WriteUTF/…

try-resource语句，自动关闭资源

关闭最外层的数据流，将会把其上所有的数据流关闭

##### 二进制文件读写（3）

读文件

先打开文件，读入数据，关闭文件

File Input Stream，BufferedInputStream，DataInput Stream

DataInputStream

read/readBoolean/readChar/readDouble/readFloat/readInt/readUFT…

try-resource语句，自动关闭资源

关闭最外层的数据流，将会把其上所有的数据流关闭

##### 二进制文件读写（4）

##### 总结

理解节点类、转化类和包装类的联合用法

读取需要根据写入的规则进行读取，避免错位

尽量使用try-resource语句，自动关闭资源

### 第五节  Zip文件读写

Java zip包

Java zip包

压缩包：zip，rar，gz…

Java zip包支持zip和Gzip报的压缩和解压

Zip文件操作类：java.util.zip包中

Java.Io.InputStream,java.io.OutputStream的子类

ZipInputStream,ZipOutputStream压缩文件输入/输出流

ZipEntry压缩项

##### 压缩

单个/多个压缩

打开输出zip文件

添加一个ZipEntry

打开一个输入文件，读数据，向ZipEntry写数据，关闭输入文件

重复以上两个步骤，写入多个文件到zip文件中

关闭zip文件

##### 解压

单个/多个解压

打开输入的zip文件

获取下一个ZipEntry

新建一个目标文件，从ZipEntry读取数据，向目标文件写入数据

关闭目标文件

重复以上两个步骤，从zip包中读取数据到多目标文件

关闭zip文件

##### 总结

Java支持Zip和Gzip文件解压缩

重点在Entry和输入输出流向，无需关注压缩算法

 