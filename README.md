gradle-hello-world-demo
======

#1.安装Intellij IDEA
---

#2.通过Intellij IDEA中Gradle创建Java项目
----

![Create New Project](http://upload-images.jianshu.io/upload_images/2437769-ac560dee70b0fead.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


- ##选择Java项目,Next:
![Gradle-Java](http://upload-images.jianshu.io/upload_images/2437769-308ba980e1dc5efd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ##GroupId、ArtifactId和Version和Maven一样。填写GroupId和ArtifactId，Next：
![GroupId & ArtifactId](http://upload-images.jianshu.io/upload_images/2437769-c31891d4151205ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ##Use auto-import和Create directories for empty content roots automatically这两个选项勾上，Next：
![...](http://upload-images.jianshu.io/upload_images/2437769-7765950a77d454d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ##Finish
![](http://upload-images.jianshu.io/upload_images/2437769-2727c2e24f632cb5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#3.项目目录结构
----

![gradle-hello-world-demo](http://upload-images.jianshu.io/upload_images/2437769-476164894e5ba6cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- .gradle，gradle的相关支持文件，不用管
- .idea，IntelliJ IDEA的相关文件，不用管
- build，构建生成物，存放项目构建中生成的class和jar包
- gradle，一个gradle的包装程序，貌似直接用gradle不太好，得再包一层，这个其实我们也不用管
- src，我们写代码的地方，不用说了吧
- build.gradle，gradle的构建配置，这是我们要关心的，相当于Maven的pom.xml
- GradleLearn.iml，IntelliJ IDEA的项目文件
- gradlew，一段gradle wrapper的运行脚本，For *nix
- gradlew.bat，一段gradle wrapper的运行脚本，For Windows

#4.创建Hello.java
----
>代码写在: `src/main/java/`

![Hello.java](http://upload-images.jianshu.io/upload_images/2437769-0db5afc3b474d56f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```java
public class Hello {   
      public String hello(String name) {        
            return "Hello:" + name;   
      }
}
```
#5.创建Junit测试
----
>快捷键：cmd+shift+T (Mac)

![cmd+shift+T](http://upload-images.jianshu.io/upload_images/2437769-4ad479f6d0dcb5fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ##勾选hello
![Create Test](http://upload-images.jianshu.io/upload_images/2437769-1feea67553610d86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ##测试文件位置
>测试文件位置: `src/test/java/`

![HelloTest](http://upload-images.jianshu.io/upload_images/2437769-d679a544161c3646.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ##编写测试
```java
import org.junit.Test;
import static org.junit.Assert.*;
public class HelloTest {   
      @Test    
      public void hello() throws Exception {              
            String greeting = new Hello().hello("Leonard");
            assertEquals(greeting, "Hello:Leonard");  
       }
}
```

- #运行测试

点击侧边栏的Run Test

![Run Test](http://upload-images.jianshu.io/upload_images/2437769-38513a5ced925973.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>看到绿条表示测试通过！

![Success](http://upload-images.jianshu.io/upload_images/2437769-e5af401f6876c6ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)