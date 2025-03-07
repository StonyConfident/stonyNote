## 1.jdk8
这个不必多介绍，java代码想要跑起来，这个是必须的；虽然下面要介绍的集成开发工具idea会自带jdk，但还是推荐自己安装一下jdk，因为这样你可以通过java命令运用你的jar包，而不必打开重量级的集成开发界面；当然，最好也把idea上的默认jdk设置为你自己安装的那个，设置如下:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200321231747318.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0b255X0NvbmZpZGVudA==,size_16,color_FFFFFF,t_70)
- jdk下载地址,选mac版本，https://www.oracle.com/java/technologies/javase-jdk8-downloads.html
- 安装完后，jdk所在的home目录如下:/Library/Java/JavaVirtualMachines/jdk1.8.0_191.jdk/Contents/Home
- 修改.bash_profile或.zshrc文件，新增java相关的环境变量，如下，然后就可以直接使用java -jar xxx.jar包运行你的服务；

```bash
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_191.jdk/Contents/Home
export CLASSPATH=$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib/dt.jar:.
export PATH=$JAVA_HOME/bin:$PATH:.
```

## 2.IDEA
&#8194;&#8194;idea应该当前java后端开发最好的集成开发工具，功能非常完善齐全；下载地址:https://www.jetbrains.com/idea/，包括旗舰版和社区版；
idea是一款收费软件，免费activation code可通过http://idea.medeming.com/jets/获取
- idea自带的jvm目录: /Applications/IntelliJ IDEA.app/Contents/jbr/Contents/Home/，java11版本
- 自己下载的jvm目录: /Library/Java/JavaVirtualMachines/jdk1.8.0_191.jdk/Contents/Home，java8版本

## 3.maven
&#8194;&#8194;项目管理工具maven也是必需安装的工具之一，如果自己来维护项目的依赖包管理，肯定会非常头大，效率非常低；虽然在集成开发工具idea上也有自带的maven，但如果你想要通过命令行管理你的工程，有必要在系统上安装一个；
maven需要基于jdk环境运行;
- maven下载
- 设置环境变量,使用bash修改.bash_profile文件, 如果使用zsh修改.zshrc文件:
```bash
export MAVEN_HOME=/work/tools/apache-maven-3.6.2
export PATH=$PATH:$MAVEN_HOME/bin
```
- 相关配置
maven安装后，在用户目录\${user.home}/下会新建一个<font color=#ff0000>.m2</font>目录,包括<font color=#ff0000>repository</font>目录 和 <font color=#ff0000>settings.xml</font>文件;
	- repository表示本地仓库，maven的默认本地仓库为\${user.home}/.m2/repository；
	- setting.xml需要配置远程仓库地址，入职新公司后，可从同事那拷贝一份即可，默认为\${user.home}/.m2/settings.xml；
	- 如果是自己的开源项目，可以引入开源maven镜像库，比如maven阿里云中央仓库
	```xml
<mirrors>
   <mirror>
      <id>alimaven</id>
      <name>aliyun maven</name>
      <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
      <mirrorOf>central</mirrorOf>        
    </mirror>
</mirrors>

- idea相关配置
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200322152520886.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0b255X0NvbmZpZGVudA==,size_16,color_FFFFFF,t_70)
我们可以配置idea使用的maven为其自带的，但settings.xml和repository目录最好确保和我们自己安装的maven保持一致，也就是说二者共用一个配置和共用一个本地仓库；

## 4.IDEA好用的插件
	- Lombok,自动生成代码
	- Free Mybatis plugin，方便mapper.xml跳转
	- JRebel and XRebel for IntelliJ,本地热部署插件
	- Maven Helper,依赖分析，冲突解决插件
	- PlantUML integration,画图工具
