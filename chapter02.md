# day02变量、关键字

1. 自定义标识符

```
/*
自定义标识符：在java中有些名字是需要自己定义的，那么我们就把这些称作为自定义标示符。


标识符的要注意的细节：
	1. 标识符的组成元素是 字母（a-z A-Z）,数字（0~9） 、下划线（_）、 美元符号（$）
	2. 标识符不能以数字开头。
	3. java的标示符是严格区分大小写的。
	4. 标识符的长度可以是任意。
	5. 自定义的标识符名称一般要有意义。 
	6. 关键字、保留字(goto)不能用于自定义的标识符。 

标识符的命名规范：
	1. 类名、接口名的命名规范： 单词的首字母大写，其他字母小写。  比如： LastTime
	2. 变量名、方法名的命名规范： 首单词全部小写，其他单词的首字母大写，其他小写。   比如： userName
	3. 包名的命名规范： 全部小写。  比如： itcast
	4. 常量名的命名规范： 全部大写，单词与单词之间使用下划线分隔。 比如： UP_DIRECTION 


判断下面那些是符合的标示符：
	abc_123   合法
	_123abc   合法
	abc%123   不合法
	abc123    合法
	$_abc123   合法
	123abc     不合法 

关键字：在java程序中有些标识符是有着特殊含义的，而我们就把这些有着特殊含义的标识符就称作为关键字。

关键字一般用于表示一个程序的结构或者是数据类型。


*/

class Demo2{

	public static void main(String[] args) 
	{
		System.out.println("Hello World!");
	}
}

```

2. 如何生成开发者文档

```
/*

软件：用户帮助文档 +  开发人员的帮助文档。 

文档注释与多行注释的区别: 文档注释的内容可以用于生成一个开发者文档。
	
如果需要生成一个开发者文档需要使用到java的开发工具---javadoc.exe 

如何使用javadoc工具， 
	
	javadoc的使用格式：
			javadoc -d  存储文档的路径   java的源文件。

生成开发者文档要注意的细节：
	1. 如果一个类需要生成开发者文档，那么需要使用关键字public 修饰该类， 让该类是公共的。
	2. 文档注释一定要位于一个类的上方或者是一个方法的上方。 否则注释的内容也没法抽取。


注释的作用：
	1. 使用文字对程序的说明。
	2. 注释可以用于调试使用。

*/


/**
该类是用于模拟QQ的登陆过程的。写得不好不要喷！！
@version 1.0
@author  0416java基础班
*/

public class Demo4{

	/**
	QQ的登陆过程： 
		1.要用户用户名与密码。
		2.校验用户名与密码
		3.展示好友列表
	*/	
	public static void main(String[] args) 
	{
	   
		System.out.println("请输入用户名与密码");
		System.out.println("校验用户名与密码");
		System.out.println("展示好友列表..");
	}

}
```

3. 注释的细节

```
/*
需求： 使用java程序模拟QQ登陆过程。

注释： 注释就是使用文字对程序的说明，注释是写给程序员看的，java编译器会忽略注释的内容。

注释的类型： 
	单行注释      实现方式： // 注释的内容
	
	多行注释：    实现方式： /*  */
/*

	文档注释：    实现方式： /** 注释的内容  */


/*

	注释要注意的细节：
		1. 单行注释可以嵌套使用，多行注释是不能嵌套使用的。
		2. 一般单行注释都是在写在代码的右边, 多行注释一般写在代码的上方。 
		3. 文档注释也是多行注释。
	


*/
class  Demo3
{
	/**
	这个是一个主方法，
	是程序的主入口
	
	程序是从这里开始执行的，
	如果一个需要独立运行，那么则需要主方法。
	*/
	public static void main(String[] args) 
	{
		System.out.println("请输入用户名与密码");
		System.out.println("aaa...");   // 这句语句是用于测试，没个鸟用。  
		System.out.println("校验用户名与密码");
		System.out.println("展示好友列表..");
	}
}

```

4. 常量

```
/*
软件 =  数据 + 指令    + 说明文档

常量: 在程序运行过程中其值不能发生变化的量就是称作为常量。

常量的类型：
	整数常量 	比如： 12 10
	小数常量	比如：	3.14
	布尔常量    布尔常量只有两个值， true（对） 、 false(错)。 
	字符常量    单个字符使用了单引号引起来的内容称作为字符常量。
	字符串常量  数据内容使用了双引号引起来的内容称作为字符串常量，

进制： 使用有限的字符描述我们现实生活中的所有数据。 

	比如： 星期 (七进制 0~6 )  ,  生活： (十进制 0~9)


计算机出现的目的是为了服务于人类，既然计算机要服务人类，那么计算机
就必须要存储我们现实生活中的数据。计算机是如何存储现实生活中的数据呢？


整数常量的表现形式：
	
	十进制转二进制的方法：使用十进制的数据不断的除以2，直到商为0为止。从下往上取余数即可
			11（十进制）--------> 1011 (二进制)
	
	二进制转十进制: 使用二进制的每一位数不断的乘以2的n次方，n从0开始，每次递增1，然后相加即可。
			1101(二进制)-------->  13  (十进制)
	
	1000（十进制）----------->  001,111,101,000(二进制） ------> 1,7,5,0

	二进制的缺点： 书写比较长，不方便我们记忆。

	解决方案：  每三个二进制位就记忆一个数字。
	
	三个二进制位表示的范围是（0~7）： 八进制。 三个二进制位则是一个八进制位。 

	十进制转成八进制: 使用十进制的数据不断的除以8，直到商为0为止。从下往上取余数即可
		14(十进制) --------- > 16  (八进制) 


	八进制转成十进制: 使用八进制的每一位数不断的乘以8的n次方，n从0开始，每次递增1，然后相加即可。
		17（八进制） --------> 15  (十进制)


	四个二进制位记忆一个数字， 
	
	十六进制的组成元素（0-9 a~f）

	
	十进制与十六进制之间的转换： 使用十进制的数据不断的除以16，直到商为0为止。从下往上取余数即可
		54(十进制)-----------> 36 （十六进制）

	十六进制转成十进制：使用十六进制的每一位数不断的乘以16的n次方，n从0开始，每次递增1，然后相加即可。
		12(十六进制) --------> 18  (十进制)



整数的表现形式： 十进制、 二进制、 八进制、 十六进制.

*/

class Demo5 
{
	public static void main(String[] args) 
	{
		//System.out.println(Integer.toBinaryString(1000));  //Integer.toBinaryString()--》 sun 给我们提供一个功能可以把十进制的数据转成成二进制数据。
		System.out.println(10);
		//如果一个数据要以二进制的形式体现，是以0b开头.  jdk7.0的新特性
		System.out.println(0b10);
		//如果数据是以0开头，那么该数据就是一个八进制 的数据。
		System.out.println(010);
		//如果数据是以0x开头，那么该数据就是一个十六进制 的数据。
		System.out.println(0x10);
	}
}
```

5. 变量

```
/*
在现实生活中很多的数据都要在程序运行的过程中发生变化的：

	比如： 温度， 游戏积分...

变量： 程序在运行过程中其值可以发生变化的量称作为变量。

变量就是用于存储一个数据的容器。

容器具体特点：
	1. 容量
	2. 存储一定格式的数据。（类型）
	3. 名字


变量的定义格式：
	
	数据类型  变量名 = 数据; 


变量名是由我们自定义的标识符， 变量名的命名规范： 首单词全部小写，其他单词的首字母大写，其他字母小写。


在java中表示变量的容量 大小是使用了数据类型表示的。


java中: 八种基本数据类型
	整数
		byte(字节)      8bit     2^8 =256		 -128 ~ 127
		short(短整型)   16bit    2^16=65536		
		int(整型)       32bit    
		long(长整型)    64bit 

	注意： 一个整数没有加上任何的标识的时候，那么该整数默认是int类型 的数据。
	如果一个数据需要表示成一个长整型，那么该数据要以L结尾。  L是不区分大小写的，但是建议使用大写。
	
	选用数据类型的原则： 在能满足需求的前提下，能小就尽量使用小数据类型，可以节省内存空间。
	
	在现实开发中一般我们都是使用了int类型。

	

	小数
		flaot(单精度浮点型)		32bit        
		double(双精度浮点型)    64bit
	
	注意： 一个小数如果没有加上任何的标识的时候，默认都double类型。如果是float
	类型的数据那么该数据必须要以f结尾。 不区分大小写。

	

	布尔 ： 布尔类型只有两个值： true， false。 

		boolean   一个字节或者四个字节。 (java规范2)   : 
		如果boolean 用于声明一个基本类型变量时是占四个字节， 如果用于声明一个数据类型的时候
		，那么数组中每个元素占一个字节。

	字符
		char    2个字节


字符串类型： String

java中的八种基本数据类型：
	
	整数:	byte short int long
	小数:	float double
	布尔：	boolean 
	字符：  char
	



*/
class Demo6 
{
	public static void main(String[] args) 
	{
/*
	//整数
		//需求：定义一个变量用于存储正常人的年龄。
		byte age = 29; // 左边： 声明了一个名称为age的byte类型数据，右边：把29赋值给age变量
		System.out.println(age);
		
		//需求： 定义一个变量存储辅导员钱。 
		short money = 3000;
		System.out.println(money);

		//需求： 定义一个变量用于存储校长的钱。
		int bossMoney = 100000000;
		System.out.println(bossMoney);

		//需求： 存储周永康的钱。
		long allMoney = 10000000000000000L;
		System.out.println(allMoney);
		allMoney = 10;  //对变量进行重新赋值
		System.out.println(allMoney);
	
	小数：
	
	    float pi = 3.14f;
		double height = 175.78;
		System.out.println(pi);
		System.out.println(height);
	
	布尔类型
	
	boolean b = false;
	System.out.println(b);

字符类型
	char c = 'a';

	System.out.println(c);

*/	

	String str = "abc";
	System.out.println(str);

	}
}
```

6. 变量的定义格式

```
/*
变量的声明(定义)格式：

	方式一： 
		数据类型  变量名；

	方式二：可以一次声明多个变量。 
		数据类型 变量1 , 变量2 ，.....

*/
class Demo7 
{
	public static void main(String[] args) 
	{
		/*
		方式一： 
		int age  ; //声明一个变量
		age = 12;  //给变量赋值
		
		方式二：
		*/
		int age = 12,height=78;
		age =14;//重新对age变量赋值
		// int age = 15;  重复声明了变量。 这种语法是不允许的。
		System.out.println(age);
		System.out.println(height);
	}
}
```

```
/*
变量： 

声明变量格式：
	
	格式一： 
		数据类型  变量名 ；

	格式二： 
		数据类型 变量名1 ， 变量名2 ...
	
java中的八种基本数据类型

	整数
		byte(字节)			8bit 
		short(短整型)		16bit
		int(整型)           32bit
		long (长整型)       64bit

	小数
		float(单精度浮点型)  32bit
		double(双精度浮点型)  64bit

	布尔
		boolean  一个字节或者是4个字节。  只有两个值 。 true ， false.

	字符
		char       2个字节

变量的选用原则： 在能够满足需求的前提下，能使用小类型的数据类型就尽量的使用小的数据类型。 节省内存空间。

*/
class Demo1 
{
	public static void main(String[] args) 
	{
		System.out.println("Hello World!");
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

```
/*
变量： 

声明变量格式：
	
	格式一： 
		数据类型  变量名 ；

	格式二： 
		数据类型 变量名1 ， 变量名2 ...
	
java中的八种基本数据类型

	整数
		byte(字节)			8bit 
		short(短整型)		16bit
		int(整型)           32bit
		long (长整型)       64bit

	小数
		float(单精度浮点型)  32bit
		double(双精度浮点型)  64bit

	布尔
		boolean  一个字节或者是4个字节。  只有两个值 。 true ， false.

	字符
		char       2个字节

变量的选用原则： 在能够满足需求的前提下，能使用小类型的数据类型就尽量的使用小的数据类型。 节省内存空间。

*/
class Demo1 
{
	public static void main(String[] args) 
	{
		System.out.println("Hello World!");
	}
}

```

```
/*
数据类型转换:
	
	小数据类型------------>大的数据类型    自动类型转换
	
	大的数据类型---------->小的数据类型    强制类型转换

	强制类型转换的格式：
			
		小数据类型  变量名 =(小数据类型) 大数据类型数据;

数据类型转换要注意的细节：
	1. 凡是byte、 short、 char 数据类型数据在运算的时候，会自动的转换成int类型再运算的。
	2. 两个不同数据类型的数据在运算的时候， 结果取决于大的数据类型。

*/
class Demo2 
{
	public static void main(String[] args) 
	{
		/*
		自动类型转换
		byte b = 12;  //一个字节。   
		short s = b; //把b变量存储的值赋予给s变量。  两个字节。
		int i =  s;
		long l = i;
		System.out.println(l);
		

		int i = 128;  // 4个字节
		byte b = (byte)i; //把i变量存储的值赋予给b。  强制类型转换
		System.out.println(b); // -128
		任何一个负数的最高位肯定是1，
	
		
	
		//凡是byte、 short、 char 数据类型数据在运算的时候，会自动的转换成int类型再运算的。
		byte b1 = 1;
		byte b2= 2;
		byte b3 = (byte)(b1+b2);
		System.out.println(b3);
	


	//2. 两个不同数据类型的数据在运算的时候， 结果取决于大的数据类型的数据。
		int i = 10;
		long l = 20;
		int sum = (int)(i+l);
		System.out.println(sum);


	  //
		System.out.println('a'+1); //98
*/
	

/*
 java编译器在编译的过程中可以检测到一个常量的值，而不能检测到变量的的值， 因为一个变量
 在java虚拟机运行到该变量语句的时候才在内存中开辟对应的空间，编译的时候并不会开辟内存空间。


 byte b = 10; java编译器在编译的时候，10是一个常量，java编译器就可以检测到10没有超过byte的存储范围
 ，所以没有报错。

byte b = i; 

*/
		int i = 10;
		byte b = i;
		System.out.println(b);
	}
}

```

```
/*
转义字符：特殊字符使用”\”把其转化成字符的本身输出，那么使用”\”的字符称作为转移字符。

常用的转义字符：
	\b	Backspace （退格键）
	\t	Tab   （Tab键盘）   制表符  制表符的意义是保证一列对齐。   
	
	\r	Carriage Return（回车）  把光标移动到一行的首位置上。
	\n	Linefeed （换行）

如果在windows操作系统的文件需要换行，那么需要\r\n一起使用。  在其他操作系统上如果需要
换行只需要\n即可。 


	
*/
class Demo3 
{
	public static void main(String[] args) 
	{
		//需求： 在控制台上输出 hello" world。
		//System.out.println("hello\tworld");  // hllo world
		System.out.println("hello\nworld"); 
	}
}


```

```
/*
算术运算符
	+ (正数，加法 、 连接符)

连接符： 如果数据与字符串使用+号，那么这时候“+ ”就是一个连接符。拼接字符串。
任何数据与字符串使用连接符，那么结果的类型都是字符串类型。
	-

	*
	/（除法）
	%（取模，取余数）
	
*/

class Demo4 
{
	public static void main(String[] args) 
	{
	
		/*System.out.println(10 + " world");  // hello world ， 10 world
		System.out.println(1+2+3 + "hello"+1+2+3); // 赵 刘：  6hello6   .   林：6hello123
		System.out.println(12.0/4); //  3.0
		*/
	

		//注意： 取模运算的结果正负是取决于被除数的正负。
		System.out.println(10%3); //   1     
		System.out.println(10%-3); //  1
		System.out.println(-10%3); //  -1
		System.out.println(-10%-3); // -1


	}
}
/*
1+2+3 + "hello"+1+2+3
3+3+ "hello"+1+2+3
6+ "hello"+1+2+3

"6hello"+1+2+3
"6hello123"

*/


```

```
/*
++(自增): 自增就是操作数+1.
	前自增: ++位于操作数的前面。 先自增，后使用。

	后自增: ++位于操作数的后面。 先使用，后自增，


*/
class Demo5 
{
	public static void main(String[] args) 
	{
		/*
		int i = 0;
		int result = ++i; //前自增。i=i+1;  result = i;
		int result = i++; //后自增。 result = i;  i=i+1
		System.out.println("结果："+result+" i="+i);
	

		int num  =10;
		int result = 10*num++; // int result = 10*10 .  num = num+1;
		System.out.println("结果："+result);
		*/

		int i = 0;
		i = i++;
/*

jvm对于后自增的运行原理：

i=i++; ------->  先运算i++ ， 再运算赋值运算符（=）。

后自增要使用到没有+1之前的值。

i++的运行原理： 
	int temp = i;  //创建一个变量保存i没有+1的值。
	i = i+1; //自增
	把temp的值作为运算结果返回。

======================================================

	int i = 0; 
	i = i++;


分析i = i++; 运算过程：
	
	先算：i++;
		int temp = i; // 0
		i = i+1; // i =1
		i = temp; // i = 0

i值变化的过程 ： 0 ----> 1 ------>0

*/

		System.out.println("i="+i);


	}
}

```

```
/*
--（自减）： 自减就是操作数-1.
	前自减： --位于操作数 的前面。 先自减，后使用。

	后自减: --位于操作数 的后面， 先使用，后自减


*/

class Demo6 
{
	public static void main(String[] args) 
	{
		/*
		int i = 1;
		int result = --i; //前自减。i = i-1; result = i;
		int result = i--; //后自减， result = i ; i= i-1;
		System.out.println("result : "+ result);  //
		*/

		int num = 10;
		int result = 10*num--;
		System.out.println("result : "+ result);
	}
}

```

```
/*
赋值运算符
	=	(赋值运算符)
	+= 
	-=
	*=
	/=
	%=
*/
class Demo7 
{
	public static void main(String[] args) 
	{
		/*
		int i = 10; // 把10赋值给i变量。
		System.out.println("i="+i);
		
		int i = 10;
		i+=2; // i = i+2;
		System.out.println("i="+i);
		*/

		byte b1 = 1;
		b1 = b1 +1;
		b1+=1; // b1 =  （byte）(b1+1);  // java编译器对于b1+=1的时候，java编译器会进行强制类型转换。我们不需要再手动转换了。
		System.out.println("b1 = " +b1);

	}
}

```

```
/*
比较运算符
	== 

==作用：
	1. 用于基本数据类型数据比较时，判断的是两个数据是否相等。
	2. ==用于引用数据类型比较的时候，那么比较的是两个变量所指向的对象是否为同一个（比较的是内存地址）.

	! =(不等于)
	<  (小于)
	>	(大于)
	<=  (小于等于)
	>=	(大于等于)
*/
class Demo8 
{
	public static void main(String[] args) 
	{
		System.out.println("相等吗？"+ (1==2));
		System.out.println("不相等吗？"+ (1!=2));
		
		//两个不同数据类型,但是数据类型是兼用的数据在比较的时候，小的数据类型数据会自动转换成大数据类型然后再比较。
		long l  = 10;
		int i = 9;
		System.out.println("不同数据类型的数据比较："+(l>i));

	}
}

```

```
/*
比较运算符
	== 

==作用：
	1. 用于基本数据类型数据比较时，判断的是两个数据是否相等。
	2. ==用于引用数据类型比较的时候，那么比较的是两个变量所指向的对象是否为同一个（比较的是内存地址）.

	! =(不等于)
	<  (小于)
	>	(大于)
	<=  (小于等于)
	>=	(大于等于)
*/
class Demo8 
{
	public static void main(String[] args) 
	{
		System.out.println("相等吗？"+ (1==2));
		System.out.println("不相等吗？"+ (1!=2));
		
		//两个不同数据类型,但是数据类型是兼用的数据在比较的时候，小的数据类型数据会自动转换成大数据类型然后再比较。
		long l  = 10;
		int i = 9;
		System.out.println("不同数据类型的数据比较："+(l>i));

	}
}

```

```
/*
逻辑运算符： 逻辑运算符的主要作用是用于连接布尔表达式的。 
	
	&  (与,并且) 
规律： 只有两边的布尔表达式都是true 的时候，结果才是true，否则就是false。 

	|  (或 )
规律： 只要有一边的布尔表达式为true，那么结果就为true，只有两个同时为false的时候，结果才是false。

	! （非）

	^ （异或）
规律：两边的布尔表达式如果结果不一致，那么结果为true。否则为false。


	&&（短路与）
短路与 和 单与的区别：
	 相同点： 得到的结果是一样的。
	 不同点： 使用短路与的时候，如果左边 的布尔表达式为false 的时候，则不会运算右边的布尔表达式。结果返回结果false.
	 使用单与的时候，发现了左边的布尔表达式为false 的时候，还是会继续运算右边的布尔表达式的。


	||（短路或）

短路或与单或的区别：
	相同点： 得到 的结果是一致的。

	不同点： 使用短路或的时候，如果左边的布尔表达式为true，则不会运算右边的布尔表达式了，直接返回结果true。
			使用单或的时候， 即使发现了左边的布尔表达式为true，还是运算右边的布尔表达式的。



需求: 模拟投递简历，如果简历人年龄大于18岁，工作经验2年或者以上满足条件。 

*/
class Demo9 
{
	public static void main(String[] args) 
	{
		/*
		System.out.println(true&true); //  true 
		System.out.println(true&false); // false
		System.out.println(false&true); // false
		System.out.println(false&false); //false
		

		System.out.println(true|true); //  true
		System.out.println(true|false); // true
		System.out.println(false|true); // true
		System.out.println(false|false); // false

		
		System.out.println(!!true);

		

		System.out.println(true^true); //  false
		System.out.println(true^false); // true
		System.out.println(false^true); // true
		System.out.println(false^false); // false
		
		

			System.out.println(true&&true); //  true 
			System.out.println(true&&false); // false
			System.out.println(false&&true); // false
		System.out.println(false&&false); //false
		*/


		System.out.println(true||true); //  true
		System.out.println(true||false); // true
		System.out.println(false||true); // true
		System.out.println(false||false); // false

		/*
		int age = 17; //年龄
		int workAge = 3;//工作经验
		System.out.println("条件满足吗？"+(age>=18&&workAge++>=2));
		System.out.println("工作经验："+workAge); // 4
		*/
	}
}

```

```
/*

位运算符 : 直接操作数据的二进制位的。

	&
	
	|
	
	^
	规律： 如果操作数A连续异或另外一个操作数两次，那么结果还是操作数A.
	加密文件...

	~ (取反)
*/

class Demo10 
{
	public static void main(String[] args) 
	{
		System.out.println(6&3); // 2
		System.out.println(6|3); // 7
		System.out.println(6^3^3); // 5
		System.out.println(~6);  // -7
	}
}

```

```
/*

面试题目1：定义了两个变量a ,b ，然后交换a和b的值，不准出现第三方变量。  


面试题目2：取出下面二进制数据的低4四位数据。 
			
			00000000-00010000-00110000-11000111
		&   00000000-00000000-00000000-00001111
		----------------------------------------- 
										   0111



*/

class Demo11 
{
	public static void main(String[] args) 
	{
		int a = 3;
		int b = 5; 
		
		/*
		int temp = a;  // temp = 3
		a = b; //a = 5
		b = temp; //b = 3

		方式一： 相加法。 缺陷：两个int值相加有可能会超出int的表示范围。
	
		a = a+b;  // a = 8 
		b = a - b; // b = 8-5 = 3
		a = a - b; // a = 8 - 3 = 5

		
		方式二： 使用异或. 缺点： 逻辑不清晰。
		*/
		a = a^b;  // a = 3^5
		b = a^b;  // b = 3^5^5 = 3
		a = a^b;  // a  = 3^5^3 = 5 
		System.out.println("a = "+ a+" , b="+b);
	}
}

```

```
/*
移位运算符： 直接操作数据的二进制位
	<< 左移
规律：一个操作数进行左移运算 的时候，实际上就是等于该操作数乘以2的n次方，n就是移动的位数。 

面试题目： 使用最高效率的方式算出2乘以8的结果。
	2<<3 = 2*2(3) = 16
	
	2*8 = 16 
	
	>> 右移
规律： 一个操作数进行右移运算 的时候，实际上就是等于该操作数除以2的n次方，n就是移动的位数。

	>>> 无符号右移

无符号右移的特殊之处： 一个操作数进行无符号右移的时候，不管该操作数是正数还是负数，左边空缺位都是使用0来补。


*/
class Demo12 
{
	public static void main(String[] args) 
	{
		/*
		System.out.println(6<<1); // 12   6*2(1) = 12
		System.out.println(6<<2); // 24   6*2(2) = 24
		System.out.println(6<<3); // 48   6*2(3) = 48
		*/

		System.out.println(6>>1) ; // 3   6/2(1) = 3
		System.out.println(6>>2) ; // 1   6/2(2) = 1
		System.out.println(6>>3) ; // 0   6/2(3) = 0
 
	}
}

```

```
/*
三元运算符(三目运算符): 

三元运算符的格式：
	
	布尔表达式？值1：值2;

学生管理系统

	姓名      缴费
	           0  未交费    1 缴费
			   1
			   0
*/
class Demo13 {

	public static void main(String[] args) 
	{
		int age = 16;
		System.out.println(age>=18?"成年人":"未成年人");

		int status= 0;
		System.out.println(status==0?"未缴费":"已缴费");
	}
}

```

```
/*
运算符的优先级

	



*/
class Demo14 
{
	public static void main(String[] args) 
	{
		int a = 1;
		int b = 2;
		int c = 3; 
		int result = 1+a/b*3 +c/(a*b/c+1);

		System.out.println("结果："+ result); // 4
	}
}
/*
1+a/b*3 +c/(a*b/c+1);

(a*b/c+1) = 1*2/3+1 = 1

1+a/b*3 +c/1  = 1+ 0 + 3/1 = 4

*/
```

```
/*
目标： 演示使用java程序写文件，没有\r\n一起使用的时候不能换行。 

*/
import java.io.*;
class TestFile 
{
	public static void main(String[] args)  throws Exception
	{
		//找到要写入的目标文件。 
		File file = new File("F:\\a.txt");
		//建立数据的输出通道
		FileWriter out = new FileWriter(file);
		//编写数据
		out.write("大家好\r\n首长好");
		//关闭资源
		out.close();
	}
}

```

```
import java.io.*;
class ReadImage 
{
	public static void main(String[] args) throws Exception
	{
		//找到目标文件
		File inFile = new File("F:\\加密.jpg");  
		File outFile = new File("F:\\还原.jpg");

		//建立数据的输入通道
		FileInputStream input = new FileInputStream(inFile);
		FileOutputStream out = new FileOutputStream(outFile);

		//边读边写。 读取文件的数据
		int content = 0;  //用于保存每次读取到的数据
		while((content=input.read())!=-1){
			out.write( content^123);
		}
		//关闭资源
		out.close();
		input.close();

	}
}

```

