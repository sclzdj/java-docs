## 选择语句

在Java中 选中语句可以用if else 和switch来实现；

### if else

首先来说下if else

if else可以直接用 条件满足执行里面的代码；

或者多条件 可以用if else... else if ... else；

我们直接上代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo12 {` `    ``public` `static` `void` `main(String[] args) {``        ``int` `a=-``1``;``        ``// if语句``        ``// 多行注释快捷方式  ctrl+shift+/``        ``if``(a>``0``){``            ``System.out.println(a+``"是正数"``);``        ``}``        ` `        ``// if...else语句``        ``if``(a>``0``){``            ``System.out.println(a+``"是正数"``);``        ``}``else``{``            ``System.out.println(a+``"不是正数"``);``        ``}``        ` `        ``// if...else if...else``        ``if``(a>``0``){``            ``System.out.println(a+``"是正数"``);``        ``}``else` `if``(a<``0``){``            ``System.out.println(a+``"是负数"``);``        ``}``else``{``            ``System.out.println(a+``"是0"``);``        ``}``    ``}``}`
```



输出：

```
`-``1``不是正数``-``1``是负数`
```

### switch

switch语句 用于条件很多的情况；

在switch在jdk1.6或者jdk1.6以下版本，仅支持整型类型；jdk1.7开始支持字符串；

我们先看一个int类型的实例：

```
`package` `com.java1234.chap02;`  `import` `java.util.Scanner;` `public` `class` `Demo13 {` `    ``public` `static` `void` `main(String[] args) {``        ``System.out.println(``"请输入一个数字："``);``        ``// 定义一个系统输入对象``        ``// 自动导包  ctrl+shift+o``        ``Scanner scanner=``new` `Scanner(System.in);``        ``int` `n=scanner.nextInt();``        ``scanner.close();``        ``switch``(n){``            ``case` `1``:{``                ``System.out.println(``"用户输入的是1"``);``                ``break``;``            ``}``            ``case` `2``:{``                ``System.out.println(``"用户输入的是2"``);``                ``break``;``            ``}``            ``default``:{``                ``System.out.println(``"用户输入的是其他数字"``);``            ``}``        ``}``    ``}``}`
```



输入：

```
`请输入一个数字：``2``用户输入的是``2`
```



我们再来看一个字符串类型的实例：

```
`package` `com.java1234.chap02;` `import` `java.util.Scanner;` `public` `class` `Demo14 {` `    ``public` `static` `void` `main(String[] args) {``        ``System.out.println(``"请输入一个字符串："``);``        ``Scanner scanner=``new` `Scanner(System.in);``        ``String str=scanner.next();``        ``scanner.close();``        ``switch``(str){``            ``case` `"张三"``:{``                ``System.out.println(``"输入的是张三"``);``                ``break``;``            ``}``            ``case` `"李四"``:{``                ``System.out.println(``"输入的是李四"``);``                ``break``;``            ``}``            ``default``:{``                ``System.out.println(``"用户输入的是其他字符串"``);``            ``}``        ``}``    ``}``}`
```



输入：

```
`请输入一个字符串：``张三``输入的是张三`
```



## 循环语句

在java中 我们可以用 while或者do...while循环语句来实现，后面我们还会讲到for循环语句；

### while

**首先是while循环语句；**



我们来用while来实现下在控制台输出1到10；

```java
`int` `i=``1``;``while``(i<=``10``){``    ``System.out.print(i+``" "``);``    ``i++;``}`
```



这里我们先定义i变量，while() 括号里加条件判断；

循环体里 我们输出i 以及i++；后面是不断的循环执行，直到while条件不满足为止，退出循环



### do...while

**然后我们再用do...while循环语句来实现**

```java
`int` `j=``1``;``do``{``    ``System.out.print(j+``" "``);``    ``j++;``}``while``(j<=``10``);`
```



这里我们还是定义一个j变量，然后我们执行是执行输出语句，再j++；

最后才是判断；直到while条件不满足为止，退出循环



**while和do...while的区别**



从前面两个实例我们很容易看出，while是先判断后执行 do...while是先执行后判断。

do..while是肯定会至少执行一次，while的话，不一定会执行；



完整代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo15 {` `    ``public` `static` `void` `main(String[] args) {``        ``// 在控制台输出1到10``        ``// while循环语句``        ``int` `i=``1``;``        ``while``(i<=``10``){``            ``System.out.print(i+``" "``);``            ``i++;``        ``}``        ` `        ``System.out.println(``"==================="``);``        ` `        ``// do....while 循环语句``        ``int` `j=``1``;``        ``do``{``            ``System.out.print(j+``" "``);``            ``j++;``        ``}``while``(j<=``10``);``        ` `        ``System.out.println(``"==================="``);``        ` `        ``// while和do...while的区别``        ``// while是先判断后执行 do...while是先执行后判断``        ` `        ` `    ``}``}`
```



输出：

```
1 2 3 4 5 6 7 8 9 10 ===================

1 2 3 4 5 6 7 8 9 10 ===================
```



### for

**前面我们讲了while和do...while循环语句。接下来还有一个for循环语句；**

```java
`for``(``int` `k=``1``;k<=``10``;k++){``    ``System.out.print(k+``" "``);``}`
```



for循环有点类似while循环语句；

int k=1;定义一个变量；

k<=10是条件语句 ，满足条件就执行循环体，不满足就结束循环；

执行完循环体，再执行k++;





**for循环嵌套**



假如在for循环中还有for循环，我们称之为循环的嵌套；

```java
`for``(``int` `m=``0``;m<``10``;m++){``    ``for``(``int` `n=``0``;n<``10``;n++){``        ``System.out.print(``"m="``+m+``"n="``+n+``" "``);``    ``}``    ``System.out.println();``}`
```



我们先运行 看下输出：

```
m=0n=0 m=0n=1 m=0n=2 m=0n=3 m=0n=4 m=0n=5 m=0n=6 m=0n=7 m=0n=8 m=0n=9 

m=1n=0 m=1n=1 m=1n=2 m=1n=3 m=1n=4 m=1n=5 m=1n=6 m=1n=7 m=1n=8 m=1n=9 

m=2n=0 m=2n=1 m=2n=2 m=2n=3 m=2n=4 m=2n=5 m=2n=6 m=2n=7 m=2n=8 m=2n=9 

m=3n=0 m=3n=1 m=3n=2 m=3n=3 m=3n=4 m=3n=5 m=3n=6 m=3n=7 m=3n=8 m=3n=9 

m=4n=0 m=4n=1 m=4n=2 m=4n=3 m=4n=4 m=4n=5 m=4n=6 m=4n=7 m=4n=8 m=4n=9 

m=5n=0 m=5n=1 m=5n=2 m=5n=3 m=5n=4 m=5n=5 m=5n=6 m=5n=7 m=5n=8 m=5n=9 

m=6n=0 m=6n=1 m=6n=2 m=6n=3 m=6n=4 m=6n=5 m=6n=6 m=6n=7 m=6n=8 m=6n=9 

m=7n=0 m=7n=1 m=7n=2 m=7n=3 m=7n=4 m=7n=5 m=7n=6 m=7n=7 m=7n=8 m=7n=9 

m=8n=0 m=8n=1 m=8n=2 m=8n=3 m=8n=4 m=8n=5 m=8n=6 m=8n=7 m=8n=8 m=8n=9 

m=9n=0 m=9n=1 m=9n=2 m=9n=3 m=9n=4 m=9n=5 m=9n=6 m=9n=7 m=9n=8 m=9n=9 


```

通过输出结果我们也应该能够知道执行的具体过程；

先执行外层循环 比如m=0 执行到内层循环，n从0到9 

也就是输出了 m=0n=0 m=0n=1 m=0n=2 m=0n=3 m=0n=4 m=0n=5 m=0n=6 m=0n=7 m=0n=8 m=0n=9 

执行第二次外层循环 m=1  执行到内层循环，n从0到9 

再次输出了 m=1n=0 m=1n=1 m=1n=2 m=1n=3 m=1n=4 m=1n=5 m=1n=6 m=1n=7 m=1n=8 m=1n=9 

一次类推，外层有多少次，也就输出多少行，内层有多少次，就是输出多少列；

### 循环语句的控制

循环结构的控制

 1，break语句

 2，continue语句

 3，return语句



#### break



在Java中，我们可以通过一些语句，比如break,continue,return来控制循环语句的执行；



这里举例下：

我们写一个嵌套循环打印i和j；

```java
`package` `com.java1234.chap02;` `public` `class` `Demo17 {` `    ``public` `static` `void` `main(String[] args) {``        ``for``(``int` `i=``0``;i<``10``;i++){``            ``for``(``int` `j=``0``;j<``10``;j++){``                ``System.out.print(``"i="``+i+``" "``+``"j="``+j+``" "``);``            ``}``            ``System.out.println();``        ``}``    ``}``}`
```



执行输出：

i=0 j=0 i=0 j=1 i=0 j=2 i=0 j=3 i=0 j=4 i=0 j=5 i=0 j=6 i=0 j=7 i=0 j=8 i=0 j=9 

i=1 j=0 i=1 j=1 i=1 j=2 i=1 j=3 i=1 j=4 i=1 j=5 i=1 j=6 i=1 j=7 i=1 j=8 i=1 j=9 

i=2 j=0 i=2 j=1 i=2 j=2 i=2 j=3 i=2 j=4 i=2 j=5 i=2 j=6 i=2 j=7 i=2 j=8 i=2 j=9 

i=3 j=0 i=3 j=1 i=3 j=2 i=3 j=3 i=3 j=4 i=3 j=5 i=3 j=6 i=3 j=7 i=3 j=8 i=3 j=9 

i=4 j=0 i=4 j=1 i=4 j=2 i=4 j=3 i=4 j=4 i=4 j=5 i=4 j=6 i=4 j=7 i=4 j=8 i=4 j=9 

i=5 j=0 i=5 j=1 i=5 j=2 i=5 j=3 i=5 j=4 i=5 j=5 i=5 j=6 i=5 j=7 i=5 j=8 i=5 j=9 

i=6 j=0 i=6 j=1 i=6 j=2 i=6 j=3 i=6 j=4 i=6 j=5 i=6 j=6 i=6 j=7 i=6 j=8 i=6 j=9 

i=7 j=0 i=7 j=1 i=7 j=2 i=7 j=3 i=7 j=4 i=7 j=5 i=7 j=6 i=7 j=7 i=7 j=8 i=7 j=9 

i=8 j=0 i=8 j=1 i=8 j=2 i=8 j=3 i=8 j=4 i=8 j=5 i=8 j=6 i=8 j=7 i=8 j=8 i=8 j=9 

i=9 j=0 i=9 j=1 i=9 j=2 i=9 j=3 i=9 j=4 i=9 j=5 i=9 j=6 i=9 j=7 i=9 j=8 i=9 j=9 



假如我们有一个需求，把第二行 i=1的情况 不输出，这时候，我们可以用到break，结束当前循环；



上代码：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo17 {` `    ``public` `static` `void` `main(String[] args) {``        ``for``(``int` `i=``0``;i<``10``;i++){``            ``for``(``int` `j=``0``;j<``10``;j++){``                ``if``(i==``1``){``                    ``break``;``                ``}``                ``System.out.print(``"i="``+i+``" "``+``"j="``+j+``" "``);``            ``}``            ``System.out.println();``        ``}``    ``}``}`
```



这里，当i==1的时候，break 结束内层的整个循环；



我们执行输出：

i=0 j=0 i=0 j=1 i=0 j=2 i=0 j=3 i=0 j=4 i=0 j=5 i=0 j=6 i=0 j=7 i=0 j=8 i=0 j=9 



i=2 j=0 i=2 j=1 i=2 j=2 i=2 j=3 i=2 j=4 i=2 j=5 i=2 j=6 i=2 j=7 i=2 j=8 i=2 j=9 

i=3 j=0 i=3 j=1 i=3 j=2 i=3 j=3 i=3 j=4 i=3 j=5 i=3 j=6 i=3 j=7 i=3 j=8 i=3 j=9 

i=4 j=0 i=4 j=1 i=4 j=2 i=4 j=3 i=4 j=4 i=4 j=5 i=4 j=6 i=4 j=7 i=4 j=8 i=4 j=9 

i=5 j=0 i=5 j=1 i=5 j=2 i=5 j=3 i=5 j=4 i=5 j=5 i=5 j=6 i=5 j=7 i=5 j=8 i=5 j=9 

i=6 j=0 i=6 j=1 i=6 j=2 i=6 j=3 i=6 j=4 i=6 j=5 i=6 j=6 i=6 j=7 i=6 j=8 i=6 j=9 

i=7 j=0 i=7 j=1 i=7 j=2 i=7 j=3 i=7 j=4 i=7 j=5 i=7 j=6 i=7 j=7 i=7 j=8 i=7 j=9 

i=8 j=0 i=8 j=1 i=8 j=2 i=8 j=3 i=8 j=4 i=8 j=5 i=8 j=6 i=8 j=7 i=8 j=8 i=8 j=9 

i=9 j=0 i=9 j=1 i=9 j=2 i=9 j=3 i=9 j=4 i=9 j=5 i=9 j=6 i=9 j=7 i=9 j=8 i=9 j=9 





我们发现 i=1的这行 没有输出；





关键break 还有一个break标签 我们可以从内层跳到外层，结束外层循环；

比如我们只需要输出第一行  我们时候可以用标签实现：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo17 {` `    ``public` `static` `void` `main(String[] args) {``        ``outer:``        ``for``(``int` `i=``0``;i<``10``;i++){``            ``for``(``int` `j=``0``;j<``10``;j++){``                ``if``(i==``1``){``                    ``break` `outer;``                ``}``                ``System.out.print(``"i="``+i+``" "``+``"j="``+j+``" "``);``            ``}``            ``System.out.println();``        ``}``    ``}``}`
```



输出：

i=0 j=0 i=0 j=1 i=0 j=2 i=0 j=3 i=0 j=4 i=0 j=5 i=0 j=6 i=0 j=7 i=0 j=8 i=0 j=9 



#### continue



continue是结束当前循环，比如我们输出1到10 但是我们需要把3和6剔除，这时候我们可以用continue来实现：

```java
`package` `com.java1234.chap02;` `public` `class` `Demo17 {` `    ``public` `static` `void` `main(String[] args) {``        ``for``(``int` `i=``1``;i<=``10``;i++){``            ``if``(i==``3` `|| i==``6``){``                ``continue``;``            ``}``            ``System.out.print(``"i="``+i+``" "``);``        ``}``    ``}``}`
```



运行输出：

i=1 i=2 i=4 i=5 i=7 i=8 i=9 i=10 



#### return

return语句的话，比较狠，直接结束方法里的内容执行了。

```java
`package` `com.java1234.chap02;` `public` `class` `Demo17 {` `    ``public` `static` `void` `main(String[] args) {``        ``for``(``int` `i=``0``;i<``10``;i++){``            ``for``(``int` `j=``0``;j<``10``;j++){``                ``if``(i==``1``){``                    ``return``;``                ``}``                ``System.out.print(``"i="``+i+``" "``+``"j="``+j+``" "``);``            ``}``            ``System.out.println();``        ``}``        ``System.out.println(``"执行到这里"``);``    ``}``}`
```



输出：

i=0 j=0 i=0 j=1 i=0 j=2 i=0 j=3 i=0 j=4 i=0 j=5 i=0 j=6 i=0 j=7 i=0 j=8 i=0 j=9 