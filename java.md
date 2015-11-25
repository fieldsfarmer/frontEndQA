###### Abstract Class vs Interface
- An abstract class is one with at least one abstract method, which just has no implementation code .
- An abstract class can have some implementation code. Thus can have non-abstract methods, can also have constructors and instance variables.
```java
//Figure.java
public abstract class Figure{
	public abstract double getArea();
}

//Any classes that derive from the Figure class basically has 2 options: 
//1. The derived class must provide a definition for the getArea method
//2. The derived class must be declared abstract itself

// Circle.java
public class Circle extends Figure{
	private double radius;
	Circle(double r){
		radius = r;
	}
	public double getArea(){
		return 3.14*radius*radius;
	}
	public static void main(String[] args){
		Circle a = new Circle(1);
		System.out.println(a.getArea());
	}
}
```
- An interface can only provide method headings.
- Interface allows multiple inheritance. But abstract class doesn't.

###### constructor inheritance
```java
class Base{
	private int x;
	Base(int a){
		x = a;
	}
}
class Derived extends Base{
	private int y;
	Derived(int a, int b){
		super(a);
		y = b;
	}
}
```


###### Strategy pattern


