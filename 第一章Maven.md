## 第一章 Maven

#### 第一节  构建工具

##### 传统方法

* 优点：第三方库很强大

* 缺点：

> 1.搜索、确定版本、下载jar包，工作量大且不易 
>
> 2.需要手动把jar包添加到项目build path
>
> 3.代码拷贝到别人的机器，需要同样的配置路径



##### 构建工具的功能

> 自动帮程序员甄别和下载第三方库（jar）
>
> 完成整个项目编译（调用javac.exe)
>
> 完成整个项目单元测试流程（调用Junit工具）
>
> 完成项目打包（jar/war等格式，调用jar.exe)

##### 当前主要的java构建工具

> Maven,Gradle,Ivy,Buildr,Ant等

##### 总结

> 了解传统模式下使用第三方库的痛点
>
> 了解构建工具在项目开发中的作用
>
> 初步了解Maven的构建过程



#### 第二节  Maven基础概念和实战

##### 检查Maven安装  

>打开windos的运行界面，输入cmd
>
>然后输入mvn- v，出现配置的版本信息，安装成功

 ##### Maven基础概念

* Maven 开发流程
 >新建Maven项目
 >
 >在中央仓库查找第三方jar的依赖文本
 >
 >拷贝至依赖文本至项目的pom.xml
 >
 >执行maven build，编译/构建整个项目
* Maven是一个软件
* Maven也是有一个中心仓库
> 包含很多第三方软件
* Maven是一个构建工具，自动下载中心仓库的jar文件，存在本地管理，编译，测试，运行何打包发布java项目

##### Maven编译工作流程

> ![image-20210716123725705](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20210716123725705.png)

  ##### POM

* XML格式
* 包含了项目信息、依赖信息、构建信息
* 构建信息
 >groupId：组织
 >
 >artifactId：产品名称
 >
 >version：版本

````java
<dependency>
    <groupId>org.apache.commoons</goupId>
    <artifactId>commons-math3</artifactId>
    <version>3.6.1</version>
</dependency>
````

* Maven 仓库存放和管理各种构建

  > 本地仓库（本地用户的.m2文件夹
  >
  > 远程仓库

  * 中央仓库
  
  * 阿里云仓库
  
  * 谷歌仓库

* 基本目录结果

  —src

  * main
  
    —java/存放Java文件
  
    —resources/存放程序资源文
  
  * test/
  
    —java/存放测试程序
  
    —resources/存放测试程序资源文件
—pom.xml  

###### Maven构建生命周期

* 清理       编译    测试   打包    安装   部署
