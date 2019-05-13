## 说明

我们有时候在调试代码，或者是有些代码暂时不用，我们可以给代码加注释，

这时候代码就不会被执行；



以及要给代码做一些说明 我们可以加注释；



我们可以在类上，方法上以及语句上加注释；



注释的话 分为 单行注释，多行注释，文档注释



## 单行注释 // 

主要用于代码注释，以及语句备注;

```java
`public` `class` `Note {` `    ``public` `static` `void` `main(String[] args) {``        ``System.out.println(``"java大爷，你好！"``); ``// 这个是hellWorld备注``        ``// System.out.println("java大爷，你好！");``    ``}``}`
```



我们在代码后面加备注 也可以把代码注释掉；



## 多行注释： /* ... */

我们有时候要注释多行，比如有10行 我们都用// 注释 比较累，我们这时候可以用多行注释；

```java
`public` `class` `Note {` `    ``public` `static` `void` `main(String[] args) {``        ``System.out.println(``"java大爷，你好！"``); ``// 这个是hellWorld备注``        ``// System.out.println("java大爷，你好！");``        ` `        ` `        ``/*System.out.println("第一行");``        ``System.out.println("第二行");``        ``System.out.println("第三行");*/``    ``}``}`
```



这里我们对多行代码进行了注释；



## 文档注释： /** ..*/

我们对类和方法上加注释 ，要用文档注释；

```java
`/**`` ``* Java注释`` ``* @author user`` ``*`` ``*/``public` `class` `Note {` `    ``/**``     ``* 主方法``     ``* @param args``     ``*/``    ``public` `static` `void` `main(String[] args) {``        ``System.out.println(``"java大爷，你好！"``); ``// 这个是hellWorld备注``        ``// System.out.println("java大爷，你好！");``        ` `        ` `        ``/*System.out.println("第一行");``        ``System.out.println("第二行");``        ``System.out.println("第三行");*/``    ``}``}`
```