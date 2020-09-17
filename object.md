```java
public static void main(String[] args) {

 Object []arr= new Object[4];//object可以容纳任何类型的值

 

 arr[0]=new Object();

 arr[1]=new String("字符串");//相当于重写了toString

 arr[2]= 10;

 arr[3]=new Obj();//类的自我调用

for(Object obj:arr) {

System.out.println(obj.toString());//返回字符串形式

}    

}

 public String toString(){

 return "S";//重写了Obj类的toString方法;

 }
```



```java
public class person {
String name;
String id;
public boolean equals(Object obj) {
/*重写equals,使用String类的equals:对比两个值是否相等
	（String类中的equals是继承object类的，但重写过）
	，object判断两个对象是否相等，根据是内存位置是否相同*/
	person p = (person)obj;
	boolean b1=this.name.equals(p.name);
	boolean b2=this.id.equals(p.id);
	return b1&&b2;
}
}

```

### equals：

```java
public class person {
String name;
String id;
public boolean equals(Object obj) {
/*重写equals,使用String类的equals:对比两个值是否相等
	（String类中的equals是继承object类的，但重写过）
	，object判断两个对象是否相等，根据是内存位置是否相同*/
	person p = (person)obj;
	boolean b1=this.name.equals(p.name);
	boolean b2=this.id.equals(p.id);
	return b1&&b2;
}
}

```

##### 指针不一样，内容一样

```java
public class Demo {
	public static void main(String[] args) {
		person p1 = new person();
		person p2 = new person();
		person p3 =new person ();
		p1.name="小明";
		p1.id="123";
		 
		p2.name="小红";
		p2.id="123";
		
		p3.name="小明";
		p3.id="123";
		System.out.println(p1.equals(p2));
		System.out.println(p2.equals(p3));
		System.out.println(p1.equals(p3));
	}
	
}

```

> false
>
> false
>
> false



