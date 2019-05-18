## 多线程

### 多线程的引入



定义：同时对多项任务加以控制；



什么是多线程呢，我可以简单的理解成 一边吃饭，一边听音乐 这个是多线程；假如  吃完饭再听音乐，或者先听音乐再吃饭，这个是单线程。



程序里同时执行多个任务并且加以控制 这个是java多线程的含义。同时干多个事，能充分利用cpu 内存等硬件设备，提高程序运行效率。



下面我们通过一个实例来体验下多线程：

```java
package com.java1234.chap09.sec01;
 
public class Test01 {
 
    /**
     * 听音乐
     */
    private static void music(){
        for(int i=0;i<100;i++){
            System.out.println("听音乐");
        }
    }
     
    /**
     * 吃饭
     */
    private static void eat(){
        for(int i=0;i<100;i++){
            System.out.println("吃饭");
        }
    }
     
    public static void main(String[] args) {
        music();
        eat();
    }
}
```



这个代码应该很简单理解。先听音乐，再吃饭，运行输出类似：

听音乐

听音乐

.

.

.

听音乐

吃饭

吃饭

.

.

.

吃饭

吃饭





我们用上多线程，一般吃饭，一边听音乐，



Eat线程类：

```java
package com.java1234.chap09.sec01;
 
public class Eat extends Thread{
 
    @Override
    public void run() {
        for(int i=0;i<100;i++){
            try {
                Thread.sleep(100);
                System.out.println("吃饭");
            } catch (InterruptedException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }
        }
    }
 
     
}

```



Music类：

```java
package com.java1234.chap09.sec01;
 
public class Music extends Thread{
 
    @Override
    public void run() {
        for(int i=0;i<100;i++){
            try {
                Thread.sleep(100);
                System.out.println("听音乐");
            } catch (InterruptedException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }
        }
    }
 
}
```



测试类：

```java
package com.java1234.chap09.sec01;
 
public class Test02 {
 
    public static void main(String[] args) {
        Music musicThread=new Music();
        Eat eatThread=new Eat();
        musicThread.start();
        eatThread.start();
    }
}

```



运行输出类似：

吃饭

听音乐

.

.

.

吃饭

听音乐

.

.

吃饭

听音乐



### 多线程实现

1,继承Thread类

2,实现Runnable接口

3,多线程实现数据共享



#### 继承Thread类

```java
package com.java1234.chap09.sec02;

public class Thread1 extends Thread{

	private int baoZi=1;
	
	private String threadName;

	public Thread1(String threadName) {
		super();
		this.threadName = threadName;
	}

	@Override
	public void run() {
		while(baoZi<=10){
			System.out.println(threadName+" 吃"+baoZi+"第个包子");
			baoZi++;
		}
	}
	
	public static void main(String[] args) {
		// 张三 李四一起吃包子 每人吃10个
		Thread1 t1=new Thread1("张三线程");
		Thread1 t2=new Thread1("李四线程");
		t1.start();
		t2.start();
	}
	
	
	
}
```

运行输出：

张三线程 吃1第个包子

张三线程 吃2第个包子

张三线程 吃3第个包子

张三线程 吃4第个包子

张三线程 吃5第个包子

张三线程 吃6第个包子

张三线程 吃7第个包子

张三线程 吃8第个包子

张三线程 吃9第个包子

张三线程 吃10第个包子

李四线程 吃1第个包子

李四线程 吃2第个包子

李四线程 吃3第个包子

李四线程 吃4第个包子

李四线程 吃5第个包子

李四线程 吃6第个包子

李四线程 吃7第个包子

李四线程 吃8第个包子

李四线程 吃9第个包子

李四线程 吃10第个包子





#### 实现Runnable接口

```java
package com.java1234.chap09.sec02;

public class Thread2 implements Runnable{

	private int baoZi=1;
	
	private String threadName;

	public Thread2(String threadName) {
		super();
		this.threadName = threadName;
	}

	@Override
	public void run() {
		while(baoZi<=10){
			System.out.println(threadName+" 吃"+baoZi+"第个包子");
			baoZi++;
		}
	}
	
	public static void main(String[] args) {
		// 张三 李四一起吃包子 每人吃10个
		Thread2 t1=new Thread2("张三线程");
		Thread2 t2=new Thread2("李四线程");
		Thread t11=new Thread(t1);
		Thread t12=new Thread(t2);
		t11.start();
		t12.start();
	}

}
```

运行输出：

张三线程 吃1第个包子

张三线程 吃2第个包子

李四线程 吃1第个包子

张三线程 吃3第个包子

李四线程 吃2第个包子

李四线程 吃3第个包子

李四线程 吃4第个包子

李四线程 吃5第个包子

李四线程 吃6第个包子

李四线程 吃7第个包子

李四线程 吃8第个包子

张三线程 吃4第个包子

李四线程 吃9第个包子

李四线程 吃10第个包子

张三线程 吃5第个包子

张三线程 吃6第个包子

张三线程 吃7第个包子

张三线程 吃8第个包子

张三线程 吃9第个包子

张三线程 吃10第个包子



#### 多线程实现数据共享

```java
package com.java1234.chap09.sec02;

public class Thread3 implements Runnable{

	private int baoZi=1;
	
	private String threadName;

	public Thread3(String threadName) {
		super();
		this.threadName = threadName;
	}

	@Override
	public synchronized void run() {
		while(baoZi<=10){
			System.out.println(threadName+" 吃"+baoZi+"第个包子");
			baoZi++;
		}
	}
	
	public static void main(String[] args) {
		Thread3 t1=new Thread3("超级张三线程");
		Thread t11=new Thread(t1);
		Thread t12=new Thread(t1);
		Thread t13=new Thread(t1);
		t11.start();
		t12.start();
		t13.start();
	}

}
```

运行输出：

超级张三线程 吃1第个包子

超级张三线程 吃2第个包子

超级张三线程 吃3第个包子

超级张三线程 吃4第个包子

超级张三线程 吃5第个包子

超级张三线程 吃6第个包子

超级张三线程 吃7第个包子

超级张三线程 吃8第个包子

超级张三线程 吃9第个包子

超级张三线程 吃10第个包子



这里我们定义一个实例 然后用这个实例来是实例化三个Thread对象，run方法我们要加synchronized锁，否则会出现多个线程同时进入方法的情况，导致多个线程吃同一个包子；