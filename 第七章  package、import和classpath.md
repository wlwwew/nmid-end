## 第七章  package、import和classpath

### 第一节  package、import和classpath

 Package 必须和目录层次一样

Import类尽量准确

### 第二节 jar文件导出和导入

* jar文件：一种扩展名为jar的文件，是Java所持有的一种文件格式，用于可执行程序文件的传播
* jar文件实际上是一组class文件的压缩包

* jar文件优势
> jar文件可以包括多个class，比多目录更加简洁实用
>
> jar文件经过压缩，只有一个文件，在网络下载和传播方面，更具有优势
>
> jar文件只包括class，而没有包含java文件，在保护源文件知识版权方面，能够况云起到更好的作用
>
> 将多个class文件压缩成jar文件（只有一个文件），可以规定给以版本号，更容易进行版本控制
* 总结
> jar文件是一种有效传播Java程序的方法
> 可以通过jar.exe打包jar文件
### 第三节 package和import--命令行
* 总结
> 包名和类所在的目录必须严格一致
> 在命令行中，必须依靠classpath来指引所需要的类
> 编译需要文件的全路径，运行需要类的完整名字

### 第四节  Java 访问权限

* Private:私有的，只能比本类访问

* Default（通常不写）：同一个包内访问

* Protected：同一个包，子类均可以访问

* Public：公开的，所有类都可以访问

> 推荐：成员变量都是private

> 成员方法都是public

