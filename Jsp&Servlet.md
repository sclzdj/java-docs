## Tomcat目录

/bin：存放windows或Linux平台上启动和关闭Tomcat的脚本文件

/conf：存放Tomcat服务器的各种全局配置文件，其中最重要的是server.xml和web.xml

/doc：存放Tomcat文档

/server：包含三个子目录：classes、lib和webapps

/server/lib：存放Tomcat服务器所需的各种JAR文件

/server/webapps：存放Tomcat自带的两个WEB应用admin应用和 manager应用

/common/lib：存放Tomcat服务器以及所有web应用都可以访问的jar文件

/shared/lib：存放所有web应用都可以访问的jar文件（但是不能被Tomcat服务器访问）

/logs：存放Tomcat执行时的日志文件

/src：存放Tomcat的源代码

/webapps：Tomcat的主要Web发布目录，默认情况下把Web应用文件放于此目录

/work：存放JSP编译后产生的class文件



## 运行一个基础项目

我们示例运行Hello项目。

在/webapps里面建一个Hello文件夹，在Hello文件夹里面建一个WEB-INF文件夹，WEB-INF文件夹属于服务器web配置文件夹，里面放一个web.xml配置文件，文件内容如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/javaee" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" id="WebApp_ID" version="2.5">
  <display-name>T1</display-name>
  <welcome-file-list>
    <welcome-file>index.html</welcome-file>
    <welcome-file>index.htm</welcome-file>
    <welcome-file>index.jsp</welcome-file>
    <welcome-file>default.html</welcome-file>
    <welcome-file>default.htm</welcome-file>
    <welcome-file>default.jsp</welcome-file>
  </welcome-file-list>
</web-app>
```

这只是最基本的配置。

我们再在Hello文件夹建立一个index.html文件，里面的内容随便定义。然后就可以启动tomcat，然后用浏览器输入http://localhost:8080/Hello/或者http://localhost:8080/Hello/index.html访问即可。
  

## IntelliJ IDEA配置Tomcat

查找该问题的童鞋我相信IntelliJ IDEA，Tomcat的下载，JDK等其他的配置都应该完成了，那我直接进入正题了。

1.新建一个项目

![img](assets/989956-20170227213944657-702871077.png)

2.由于这里我们仅仅为了展示如何成功部署Tomcat，以及配置完成后成功运行一个jsp文件，我仅勾选JavaEnterprise-->Web Application-->Next。可能由于我之前配置过了所以在Application Server这一栏会显示已有Tomcat，你们忽略就好。

![img](assets/989956-20170227214915141-378455628.png)

3.项目名称这些默认就好了，为了快速部署Tomcat嘛，这些不是重点。点击Finish,等待IntelliJ IDEA加载完

![img](assets/989956-20170227215106157-1593092065.png)

4.点击如图所示小三角，接着点击（Edit Configurations或者ADD Configurations）-->绿色加号-->如果列表里没有则-->点击33 items more irrelevant这一项后继续寻找。

![img](assets/989956-20170227215824454-197127890.png)

Tomcat Server-->Local

5.

![img](assets/989956-20170227220209610-1948280101.png)

点击"Configure..."，配置Apache你从官网上下载的Tomcat，zip压缩包解压后的文件目录 ，我的是apache-tomcat-9.0.0.M13。而且我没有进行配置，是IDE自己定位好的，很智能，我当时有小惊奇哈哈。

![img](assets/989956-20170227220625641-2009058084.png)

6.选择浏览器

![img](assets/989956-20170227220757157-2113495013.png)

我用的是火狐，并配置firefox.exe路径。我建议使用火狐或者Chrome，开发者必备。

 7.配置artifacts，我第一次因为忘了配置也不懂这个东西是干嘛的，运行Tomcat后会报错，错误信息是：

[RMI TCP Connection(2)-127.0.0.1] org.apache.catalina.core.StandardContext.startInternal One or more Filters failed to start.

官方的说法:https://www.jetbrains.com/help/idea/2016.3/configuring-web-application-deployment.html(我英语不好不忍心翻译）点击Fix

![img](assets/989956-20170227221436313-2129797296.png)

标签由Server跳到Deploment，点击小铅笔一样的图标对artifacts进行配置

![img](assets/989956-20170227221708001-53068555.png)

新建文件夹-->绿色小加号-->Directory Content选择Web存放的位置，当然是Tomcat的webapps了,生成的war文件部署在该项目中才可以在Tomcat服务器上运行。直接运行在web文件夹下的index。jsp文件，做最后验证。

点击下图按钮验证

![1560307020119](assets/1560307020119.png)



## intellij idea 打包成war

点击【File】->【Project Structure】菜单（或使用Shift+Ctrl+Alt+S快捷键），打开【Project Structure】窗口。

![1560309011782](assets/1560309011782.png)

编译及执行打war包，点击【Build】->【BuildArtifacts】->【Build】。

然后进入对应目录，把war包改成项目名称后直接扔到wabapps目录里面，启动tomcat，然后访问即可。



## Jsp基础语法

### page指令介绍

> Language : 用来定义要使用的脚本语言； 

> contentType：定义 JSP 字符的编码和页面响应的 MIME 类型；

> pageEncoding：Jsp 页面的字符编码

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<html>
<head>
    <title>Title</title>
</head>
<body>

</body>
</html>

```

### scriptlet 标签

通过 scriptlet 标签我们可以在 Jsp 里嵌入 Java 代码

> <%! %> 我们可以在里面定义全局变量、方法、类

> <%%> 我们可以在里面定义局部变量、编写语句

> <%= %> 我们可以在里面输出一个变量或一个具体内容

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<%!
    String str="全局变量";
    public void fun(){
        System.out.println("全局函数");
    }
    class Cla{
        public void claFun(){
            System.out.println("全局类");
        }
    }
%>
<%
    String str1="局部变量";
    out.println(str1);//编写语句
%>
<%=str %>
<html>
<head>
    <title>Title</title>
</head>
<body>

</body>
</html>

```

### Jsp 注释

> Html 注释 客户端可见 

> <%-- --%> Jsp 注释 客户端不可见 

> // java 单行注释 

> /* */ java 多行注释 

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<%-- 这是jsp语法的注释 --%>
<html>
<head>
    <title>Title</title>
</head>
<body>

</body>
</html>

```



### Jsp 包含指令

> <%@ includefile=”要包含的文件”%> 静态包含 先包含，后编译处理； 

> \<jsp:includepage=”要包含的文件” /> 动态包含 先编译处理，后包含； 

**以后开发用动态包含**

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
    <%--静态包含--%>
    <%@include file="include/header.html" %>
    <%@include file="include/nav.jsp" %>
    <div>这是内容</div>
    <%@include file="include/footer.html" %>

    <%--动态包含--%>
    <jsp:include page="include/header.html" />
    <jsp:include page="include/nav.jsp" />
    <div>这是内容</div>
    <jsp:include page="include/footer.html" />
</body>
</html>

```



### Jsp 跳转指令

> \<jsp:forward> 
>
> ​	<jsp:param value=”” name=”” />
>
> \< /jsp:forward>
>
> 跳转页面接受参数方式：<%=request.getParameter("参数名称") %>
>
> 服务器内部跳转，可带参数，注意：内部跳转后的链接地址不会发生变化

![1560320043626](assets/1560320043626.png)

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
  <jsp:forward page="target.jsp">
      <jsp:param name="username" value="sclzdj" />
      <jsp:param name="password" value="123456" />
  </jsp:forward>
</body>
</html>
```

taget.jsp接受参数的代码

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<div>
    username:<%=request.getParameter("username") %>
</div>
<div>
    password:<%=request.getParameter("password") %>
</div>
</body>
</html>

```



## JSP引入类

```jsp
<%@ page import="java.util.*" %>
```



## JSP获取请求头信息

```jsp
<%@ page language="java" contentType="text/html; charset=utf-8" pageEncoding="utf-8" %>
<%@ page import="java.util.*" %>
<%
	// 获取头信息
	Enumeration enu=request.getHeaderNames();
	while(enu.hasMoreElements()){
		String headerName=(String)enu.nextElement();
		String headerValue=request.getHeader(headerName);
%>
<div>
	<%=headerName %>&nbsp;<%=headerValue %>
</div>
<%
	}
%>
```



##  JSP 九大内置对象

在 Jsp 开发中，Jsp 提供了 9 个内置对象，这些内置对象将由容器为用户进行实例化，用户直接使用即可。这个 9 个内置对象分别是：pageContext,request,response,session,application,config,out,page,exception；常用的是前面 5 个，需要熟练掌握

> 在 Jsp 开发中，可以保存数据，Jsp 提供了四种数据保存范围；分别是 page,request,session,application;

###  JSP 四个作用域

#### Page 范围

> 只在一个页面中保存数据； javax.servlet.jsp.PageContext(抽象类)

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    pageContext.setAttribute("name", "sclzdj");
    pageContext.setAttribute("age", 25);
%>
<%
    String name = (String) pageContext.getAttribute("name");
    int age = (Integer) pageContext.getAttribute("age");
%>
<div>
    name:<%=name %>
</div>
<div>
    age:<%=age %>
</div>
</body>
</html>

```

#### Request 范围

> 只在一个请求中保存数据； javax.servlet.http.HttpServletRequest(接口) 

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    request.setAttribute("name", "sclzdj");
    request.setAttribute("age", 25);
%>
<jsp:forward page="target.jsp"></jsp:forward>
</body>
</html>

```

taget.jsp代码这样写

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<div>
    name:<%=request.getAttribute("name") %>
</div>
<div>
    age:<%=request.getAttribute("age") %>
</div>
</body>
</html>

```

#### Session 范围

> 在一次会话范围中保存数据，仅供单个用户使用；javax.servlet.http.HttpSession(接口) 

第一个页面代码：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    session.setAttribute("name", "sclzdj");
    session.setAttribute("age", 25);
%>
</body>
</html>

```

第二个页面代码：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<div>
    name:<%=session.getAttribute("name") %>
</div>
<div>
    age:<%=session.getAttribute("age") %>
</div>
</body>
</html>

```

上面的两个页面需要在同一浏览器打开，才能生效

#### Application 范围

> 在整个服务器上保存数据，所有用户共享；javax.servlet.ServletContext(接口)

第一个页面代码：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    application.setAttribute("name", "sclzdj");
    application.setAttribute("age", 25);
%>
</body>
</html>

```

第二个页面代码：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Title</title>
</head>
<body>
<div>
    name:<%=application.getAttribute("name") %>
</div>
<div>
    age:<%=application.getAttribute("age") %>
</div>
</body>
</html>

```

上面的两个页面可以在不同浏览器里面打开，也能生效