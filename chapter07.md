# day05面向对象

```
/*
java是面向对象的计算机语言。 

对象：真实存在唯一的一个事物(具体)。  比如： 我家的狗， 

类： 同一种事物的公共属性以及公共功能的抽取（抽象的概念）.    

我们从小的时候就不断的接触到很多对象， 通过不断 的接触对象
我们大脑就会把具备相同属性和相同功能的事物进行归类。 

计算机是服务于人类的， 那么为了让我们计算机更加贴近我们的生活，所以面向对象的计算机语言就诞生了。


在现实生活中： 对象--------> 类

在java中： 类----------->创建对象。


面向对象的核心思想：找适合的对象，做适合的事情。 


找对象的方法：
	
	1. 我们自定义类，然后通过自定义类去创建对象。   （自定义类的过程中会涉及到很多的语法，那么这时候我们就可以把这些涉及到的语法学习，然后再看别人写的类，才能看懂）

	2. sun公司已经定义 好了很多的类，我们只需要认识这些类即可创建对象使用。



自定义类创建对象的步骤：
	1. 先使用class自定义个类。
	格式：
		class 类名{
			
			事物的公共属性使用成员变量描述；
			
			事物的公共行为功能使用函数描述；
		}

	2. 通过自定义的类创建对象。
			创建对象的格式: 
				类名  变量名 = 	new 类名(); 
	3. 访问对象的属性或者调用对象的功能。
		
			访问对象的属性格式：
					对象.属性名;
			
			调用对象的功能行为：
					对象.函数名(); 



需求： 使用java描述一个车类， 车具备颜色， 轮子数、 名字这些公共的属性， 车还具备跑的功能行为。

 
*/

//车类
class Car{
	
	//事物的公共属性使用成员变量描述
	String name;  //名字的属性

	String	color; //颜色属性
	
	int wheel ;  //轮子数

	//事物的公共行为功能使用函数描述 .  一个方法内部可以直接访问成员变量的。
	public void  run(){
		System.out.println(name+"跑得非常快!!");
	}
}


class Demo1 
{
	public static void main(String[] args) 
	{
		Car	c = new Car(); // 声明了一个Car类型的变量c指向了一个Car对象。
		
		//给对象的属性进行赋值
		c.name = "法拉利";
		c.color = "红色";
		c.wheel = 4 ;
		System.out.println("名字："+ c.name+" 颜色："+ c.color+"  轮子："+ c.wheel);
		
		c.run();  //调用对象的run功能
	}
}

```

```
/*
自定义类创建对象的步骤：
	1. 先使用class自定义个类。
	格式：
		class 类名{
			
			事物的公共属性使用成员变量描述；
			
			事物的公共行为功能使用函数描述；
		}

	2. 通过自定义的类创建对象。
			创建对象的格式: 
				类名  变量名 = 	new 类名(); 

	3. 访问对象的属性或者调用对象的功能。
		
			访问对象的属性格式：
					对象.属性名;
			
			调用对象的功能行为：
					对象.函数名(); 





*/

class Demo3 
{
	public static void main(String[] args) 
	{
		System.out.println("Hello World!");
	}
}




class Car{
	
	//事物的公共属性使用成员变量描述
	String name;  //名字的属性

	String	color; //颜色属性
	
	int wheel ;  //轮子数

	//事物的公共行为功能使用函数描述 .  一个方法内部可以直接访问成员变量的。
	public void  run(){
		System.out.println(name+"跑得非常快!!");
	}
}


class Demo2 
{
	public static void main(String[] args) 
	{
		Car c1 = new Car();
		Car c2 = new Car();
		//c1= null;
		c2 = c1;
		c1.name = "法拉利";  //一个引用类型的变量没有指向任何的对象，而访问了对象 的属性或者是调用了对象的方法。
		c2.name = "保时捷";
		System.out.println("名字:"+ c1.name);  //  
	}
}

```

```
/*

练习：使用java描述一个车类与一个修车厂类， 车具备的公共属性： 名字、 颜色、 轮子数。 车具备的公共
行为是跑的功能，但是跑之前必须要先检查轮子　是否够４个，如果不够４个轮子送去修车厂修理。修理完毕之后
车　的轮子就具备了４个。

修车厂具备公共的属性：名字、 地址、 电话。 还具备一个公共行为就是修车。 

*/

//车类
class Car{

	//事物的公共属性使用成员变量描述
	String name;  //描述名字属性

	String color; //描述颜色属性

	int wheel ; //描述车的轮子数属性

	
	//事物的公共行为使用函数描述
	public void run(){
		if(wheel>=4){
			System.out.println(name+wheel+"轮子飞快的跑起来了..");
		}else{
			System.out.println("当前轮子只有"+ wheel+"个，赶快去修理吧！！");
		
		}
	}
}


//修车厂类
class CarFactory{
	
	//公共的属性
	String name;//名字属性

	String address;  //地址属性

	String tel; // 电话属性


	//公共的行为  --- 修车的行为..
	public void repair(Car car){ //定义一个形式参数用于接收破车.
		if(car.wheel<4){
			car.wheel = 4;
			System.out.println("修改了，给钱！！");
		}else{
			System.out.println("非常努力修好了，给多点钱！！");
		}
	}
}


class  Demo4{
	
	public static void main(String[] args) 
	{
		/*
		//创建一个车对象
		Car c = new Car();
		//给车对象分配属性值
		c.name= "宝马";
		c.color = "银色";
		c.wheel = 4;
		//调用车的跑功能
		for(int i = 0 ; i< 100 ; i++){
			c.run();
		}
		c.wheel = 3;
		c.run();


		//创建一个修车厂对象
		CarFactory f = new CarFactory();
		//给修车厂赋值属性值
		f.name = "啊强修车厂";
		f.address = "广州天河棠东东路32号";
		f.tel = "020-110";


		//调用修车厂的修理方法
		f.repair(c);
		c.run();

		需求： 调用一次repair方法。
		*/
	
		new CarFactory().repair(new Car());

	}
}

```

```
/*
成员变量与局部变量的区别：
	1.位置的区别：
		成员变量是定义在方法之外，类之内的变量。
		局部变量是定义在方法之内的变量。
	
	2.作用上的区别：
		成员变量的作用是用于描述一个事物的属性.
		局部变量的作用就是用于提供一个变量给方法内部去使用而已。
	
	3. 生命周期的区别：
		  成员变量的生命周期是随着对象的创建而创建，随着对象的消失而消失。
		  
		  局部变量调用到对应的方法时执行到了创建该局部变量语句的时候存在，局部变量
		   一旦出了自己的作用域会马上消失。

	4. 初始值的区别： 
			
			成员变量有默认的初始值。 具体的初始值要看变量的数据类型
				int			 0
				double		0.0
				float		0.0f
				char		' '
				boolean		false
				String		null
			
			局部变量是没有默认的初始值的，要先初始化才能使用。




*/

//人类
class Person{
		
	 String name; //成员变量


	//人吃饭的行为   
	public void eat(){
		int num;
		
		num = 10;
		System.out.println(num);	
	}
}

class Demo5 
{
	public static void main(String[] args) 
	{
		
		
	}
}

```

```
/*
匿名对象：没有引用类型变量指向的对象称作为匿名对象。

匿名对象的好处： 简化书写。 

匿名对象要注意的细节：
	1. 两个匿名对象不可能是同一个对象。
	2. 一般不会给匿名对象赋予属性值，因为无法获取到。

匿名对象的应用场景： 
	1. 如果需要调用一个对象的方法一次的时候，然后改对象就不再使用了，可以使用匿名对象。
	2. 作为实参传递数据。

需求：调用student的study方法.。 

*/

//学生类
class Student{

	//事物公共的属性使用成员变量描述
	
	String name;   // 姓名属性

	int age; //年龄


	//事物的公共行为使用函数描述
	public void  study(){
		System.out.println("good good study , day day up");
	}
}


class Demo6 
{
	public static void main(String[] args) 
	{
		/*创建一个学生对象  普通的方式创建对象。
		Student s = new Student();   
		
		new Student(); //匿名对象
		
		
		System.out.println(new Student() == new Student());  // == 用于比较引用类型数据的时候，比较的是内存地址。
		
		
		Student s = new Student();  
		s.name = "狗娃";
		s.age = 3; 
		System.out.println("名字： "+ s.name+" 年龄："+ s.age);
	
		

		new Student().name = "狗剩";
		System.out.println("名字： "+ new Student().name); // null ~~
		
		*/


		
		
		new Student().study();


	}
}

```

```
/*
面向对象的语言三大特征：
	1. 封装
	2. 继承
	3. 多态



封装的步骤：
	1. 使用private修饰需要被封装的属性。
	2. 根据需求提供公共的方法set或者get方法获取以及设置该私有属性的值。
		方法的命名规范：
			set属性名 或者  get属性名


封装的好处：
	1. 提高了数据的安全性。
	2. 操作简单。
	3. 隐藏了实现。
	

疑问1 ：封装的应用场景？ 
	如果一个属性不想被其他人直接的访问，那么这时候就可以使用封装。

	现实开发中的实体类的成员属性(成员变量)一般我们都会封装起来。


实体类:用于描述一类事物的类则称作为实体类。   比如： class Car{ }  class Student



疑问2：封装一定需要提供get方法和set方法吗？
	
	不一定，看使用这个类的人需要需要使用到(看需求).  






权限修饰符： 权限修饰符就是用于控制变量或者方法的可见范围。

public : 公共， public 修饰的变量或者方法可以在任何范围内可见。

private : 私有的， private 修饰的变量或者是方法只能在本类中可见。


问题：出现了性别错乱的问题。


需求： 使用java类描述一个世纪佳缘网站的会员。
*/

//
class Menber{
	
	public String userName; 	//用户名
	
	private	String sex; // 性别

	private int age; //年龄  

	public	int salary;  //收入


	//提供一个公共的方法设置性别
	public void setSex(String s){
		if(s.equals("男")||s.equals("女")){
			sex = s;
		}else{
			//默认是男
			sex = "男";
		}
	}


	//提供一个公共方法获取性别
	public String getSex(){
		return  sex;
	}


	public void meet(){
		System.out.println("姓名："+ userName+ " 性别："+ sex+" 收入："+ salary);
	}
}


class Demo7 
{
	public static void main(String[] args) 
	{
		Menber m = new Menber();
		
		//给会员赋予属性值
		m.userName = "狗娃";
		m.setSex("女");
		m.salary = 10000;
		System.out.println("姓名："+ m.userName+ " 性别："+ m.getSex()+" 收入："+ m.salary);
		
	}
}

```

