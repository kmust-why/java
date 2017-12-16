# day03流程控制语句

```
/*
控制流程语句：

语句：以分号结束的代码就称作为一个语句。

顺序语句； 按照代码顺序执行的语句称作为顺序语句。


*/
class Demo1 {

	public static void main(String[] args) 
	{	
		System.out.println("A");
		System.out.println("B");
		System.out.println("C");
		System.out.println("D");
	}
}
```

```
/*
(if语句)条件判断语句:
	
需求：招聘工作经验两年或者两年以上的人员，符合条件，电话通知面试。

if语句的格式：
	
	格式一： 只能适用于一种情况下去使用。
		
		if(判断条件){
			符合条件执行的代码;
		}
	
	格式二： 适用于两种情况下去使用。
		if(判断条件){
			符合条件执行的代码;
		}else{
			不符合条件执行的代码；
		}
	
	格式2的作用于三元运算符非常的相象.如何选择使用呢？

	布尔表达式？"值1"："值2"；

	三元运算符的优点： 结构清晰简单。 

	三元运算符运算完毕之后的结果必须要使用一个变量存储，或者是直接使用其结果。而且必须要返回一个值。
	

	格式3： 适用于多种情况下下去使用。

		 if(判断条件1){
			符合条件1执行的代码;
		 }else  if(判断条件2){
			符合条件2执行的代码;
		 }else  if(判断条件3){
			符合条件3执行的代码;

		 }... else{
			都不符合上述条件执行的代码；
		 }
	




if语句要注意的细节：
	1. 如果符合条件只有一个语句需要执行，那么可以省略大括号。不建议省略，因为结构不清晰.
	2. if判断条件后面不要加上分号，否则会影响执行的效果。


要接受用户录入的数据的步骤：
	1. 创建一个扫描器对象
		Scanner scanner  = new Scanner(System.in);
	2. 调用扫描器扫描是否输入了数据
		 int num = scanner.nextInt(); 
	3. 导包
		import java.util.*;


练习：
	1. 键盘录入一个分数，然后根据分数输出对应的等级。100-90 A等级  89-80 B等级.... E等级
	2. 键盘录入用户名与密码，如果用户名与密码分别是 root ， admin ,那么提示登录成功，否则提示用户名或者密码错误。



*/

import java.util.*;
class Demo2 
{
	public static void main(String[] args) 
	{
		/*
		int workAge = 2;
		if(workAge>=2){
			System.out.println("电话通知明天过来面试...");
		}else{
			System.out.println("电话通知你不要再投我们公司，不要你！！");		
		}


		需求： 根据键盘录入一个数字， 然后输出对应的星期。
			0 -  星期天
			1 -  星期1
		*/
		
		
		System.out.println("请输入一个数字：");
		//第一步: 创建一个扫描器对象
		Scanner scanner  = new Scanner(System.in);
		//第二步：调用扫描器扫描是否输入了数据
		 int num = scanner.nextInt();  //扫描的是整数
		 //scanner.next();// 扫描一个字符串

		 if(num==0){
			System.out.println("星期天");
		 }else if(num==1){
			System.out.println("星期一");
		 }else if(num==2){
			System.out.println("星期二");
		 }else if(num==3){
			System.out.println("星期三");
		 }else if(num==4){
			System.out.println("星期四");
		 }else if(num==5){
			System.out.println("星期五");
		 }else if(num==6){
			System.out.println("星期六");
		 }else{
			System.out.println("瞎搞...");
		}
	}
}

```

