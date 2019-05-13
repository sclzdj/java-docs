![QQ鎴浘20160612083126.jpg](http://blog.java1234.com/static/userImages/20160612/1465692856084020492.jpg)



首先 何为“运算符”，何为表达式？

如上图，100+200 ，这里的 “+”，即为“运算符”；

“100”，“200”为“操作数”；



然后这个100+200连起来 就算一个表达式



## 赋值运算符



符号 "=" （赋值）



我们开发的时候，可以先定义变量，然后再赋值，分两个步骤；

也可以定义变量的同时再赋值，一个操作；

```
`package` `com.java1234.chap02;` `public` `class` `Demo06 {` `    ``public` `static` `void` `main(String[] args) {``        ``// 定义变量a``        ``int` `a;``        ``// 给变量a赋值``        ``a=``1``;``        ``System.out.println(``"a="``+a);``        ` `        ``// 定义变量a，并且给a赋值``        ``int` `a2=``2``;``        ``System.out.println(``"a2="``+a2);``    ``}``}`
```

## 算数运算符

在java中 算数运算符有：

\+ (加)；

\- (减)；

\* (乘)；

/ (除)；

%（取模）；取模其实就是求余数



实例代码；

```java
`package` `com.java1234.chap02;` `public` `class` `Demo7 {` `    ``public` `static` `void` `main(String[] args) {``        ``int` `a=``10``;``        ``int` `b=``3``;``        ``// +运算符``        ``System.out.println(a+``"+"``+b+``"="``+(a+b));``        ``// -运算符``        ``System.out.println(a+``"-"``+b+``"="``+(a-b));``        ``// *运算符``        ``System.out.println(a+``"*"``+b+``"="``+(a*b));``        ``// /运算符``        ``System.out.println(a+``"/"``+b+``"="``+(a/b));``        ``// %运算符``        ``System.out.println(a+``"%"``+b+``"="``+(a%b));``        ` `    ``}``}`
```



运行结果：

```
`10``+``3``=``13``10``-``3``=``7``10``*``3``=``30``10``/``3``=``3``10``%``3``=``1`
```

这里的除，要说明下，因为是int类型除以int类型 所以结果还是int类型 小数自动去掉了；



## 自增与自减运算符

符号：++（自增）； --(自减)

重点掌握 a++ 和++a的区别 

a++是先操作后加1；

++a是先加1后操作；



实例代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo08 {` `    ``public` `static` `void` `main(String[] args) {``        ``int` `a1=``1``;``        ``// a1++; 表示先做赋值操作，后自增``        ``int` `b1=a1++;``        ``System.out.println(``"b1="``+b1);``        ``System.out.println(``"a1="``+a1);``        ` `        ``System.out.println(``"==================="``);``        ``// ++a2；表示先自增，后做赋值操作``        ``int` `a2=``1``;``        ``int` `b2=++a2;``        ``System.out.println(``"b2="``+b2);``        ``System.out.println(``"a2="``+a2);``        ` `    ``}``}`
```



运行输出：

```
`b1=``1``a1=``2``===================``b2=``2``a2=``2`
```

## 逻辑运算符

符号：

&& 与 ；&& 与  前后两个操作数必须都是true才返回true,否则返回false

& 不短路与 ； & 不短路与 表达式都会执行到

|| 或； || 或 只要两个操作数中有一个是true，就返回true，否则返回false

|不短路或 ；| 不短路 或 表达式都会执行到

!非；! 非 ，如果操作数为true，返回false，否则，返回true

^异或；^ 异或 ，当两个操作数不相同时返回true，返回false



示例代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo09 {` `    ``public` `static` `void` `main(String[] args) {``        ``// && 与  前后两个操作数必须都是true才返回true,否则返回false``                ``boolean` `b1=(``5``<``3``)&&(``4``>``5``);``                ``System.out.println(``"b1="``+b1);``                ` `                ``// & 不短路与``                ``boolean` `b2=(``5``<``3``)&(``4``>``5``);``                ``System.out.println(``"b2="``+b2);``                ` `                ``// 一般都用&& 短路  ``                ``// 原因：效率高``                ` `                ``// || 或 只要两个操作数中有一个是true，就返回true，否则返回false``                ``boolean` `b3=(``2``<``3``)||(``4``>``5``);``                ``System.out.println(``"b3="``+b3);``                ` `                ``// | 不短路 或``                ``boolean` `b4=(``2``<``3``)|(``4``>``5``);``                ``System.out.println(``"b4="``+b4);``                ` `                ``// ! 非 ，如果操作数为true，返回false，否则，返回true``                ``boolean` `b5=!(``3``<``4``);``                ``System.out.println(``"b5="``+b5);``                ` `                ``// ^ 异或 ，当两个操作数不相同时返回true，返回false``                ``boolean` `b6=(``5``>``4``)^(``4``>``5``);``                ``System.out.println(``"b6="``+b6);``    ``}``}`
```

## 关系运算符

符号：

\> 大于；

< 小于；

\>=大于等于；

<=小于等于；

==等于；

!=不等于；



实例代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo10 {` `    ``public` `static` `void` `main(String[] args) {``        ``int` `a=``2``;``        ``int` `b=``3``;``        ` `        ``// >大于``        ``System.out.println(a+``">"``+b+``":"``+(a>b));``        ` `        ``// <小于``        ``System.out.println(a+``"<"``+b+``":"``+(a<b));``        ` `        ``// >=大于等于``        ``System.out.println(a+``">="``+b+``":"``+(a>=b));``        ` `        ``// <=小于等于``        ``System.out.println(a+``"<="``+b+``":"``+(a<=b));``        ` `        ``// ==等于``        ``System.out.println(a+``"=="``+b+``":"``+(a==b));``        ` `        ``// !=不等于``        ``System.out.println(a+``"!="``+b+``":"``+(a!=b));``    ``}``}`
```

## 三目运算符

格式：  (表达式)?表达式为true返回值:表达式为false返回值



实例代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo11 {` `    ``public` `static` `void` `main(String[] args) {``        ``// 三目运算符``        ``String s=``2``>``3``?``"表达式为真"``:``"表达式为假"``;``        ``System.out.println(s);``        ` `        ``boolean` `b=``2``>``3``?``true``:``false``;``        ``System.out.println(b);``    ``}``}`
```