---
layout: post
category : test
tagline: "test"
tags : test
---


## 如何创建一个线程

按 Java 语言规范中的说法，创建线程只有一种方式，就是创建一个 Thread 对象。而从 HotSpot 虚拟机的角度看，创建一个虚拟机线程
有两种方式，一种是创建 Thread 对象，另一种是创建 一个本地线程，加入到虚拟机线程中。

如果从 Java 语法的角度。有两种方法。

第一是继承 Thread 类，实现 run 方法，并创建子类对象。

```java
	public void startThreadUseSubClass() {
		class MyThread extends Thread {
			public void run() {
				System.out.println("start thread using Subclass of Thread");
			}
		}

		MyThread thread = new MyThread();
		thread.start();
	}
```

另一种是传递给 Thread 构造函数一个 Runnable 对象。

```java
	public void startThreadUseRunnalbe() {
		Thread thread = new Thread(new Runnable() {
			public void run() {
				System.out.println("start thread using runnable");
			}
		});
		thread.start();
	}
```
