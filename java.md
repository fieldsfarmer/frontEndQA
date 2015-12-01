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
- If you think you will need to add methods in the future, then an abstract class is better. Because if you add new method headings to an interface, then all of the classes that already implement that interface will have to implement the new methods. 
- An abstract class is also good if you want to be able to declare non-public members. In an interface, all methods must be public.

###### constructor inheritance
```java
class Base{
	private int x;
	Base(int a){
		x = a;
	}
	public void display(){
		System.out.println("This is a base class!");
	}
}
class Derived extends Base{
	private int y;
	Derived(int a, int b){
		super(a);
		y = b;
	}
	//override the method in the base class
	public void display(){
		System.out.println("This is a derived class!");
	}
}
```

###### inheritance vs composition
- inheritance is an "is-a" relationship; composition is a "has-a". Examples can be seen in Strategy Pattern, i.e. the context class.
```java
//inheritance
class Fruit {
    //...
}
class Apple extends Fruit {
    //this is a inheritance
}
class ThingsAtHome{
	private Fruit fruit = new Fruit();
}
//class ThingsAtHome is related to class Fruit by composition, because it has an instance variable that holds a reference to a Fruit object. 
```

###### Syntax
- Array, ArrayList
```java
ArrayList<Integer> l = new ArrayList<Integer>()
ArrayList<Integer> l1 = new ArrayList<>() 

```

###### static method
- One rule-of-thumb: ask yourself "does it make sense to call this method, even if no Obj has been constructed yet?" If so, it should definitely be static.

###### checked exceptions vs unchecked exceptions
- A checked exception is an exception that occurs at the compile time.
- An Unchecked exception (Runtim Exception) is an exception that occurs at the time of execution. These exceptions include programming bugs, such as logic errors or improper use of an API. runtime exceptions are ignored at the time of compilation.

- A checked exception must be caught somewhere in your code. If not code will not compile. That's why they're called checked exceptions. In other hand RuntimeExceptions (unchecked exceptions), the calling 
method is under no obligation to handle or declare it. 

- Therefore all the exceptions which compiler force you to handle are directly derived from the class java.lang.Exception and all the other exceptions which compiler not force you to handle are derived from java.lang.RuntimeException.

- Examples of checked exceptions are: FileNotFoundException, IOException, etc

- Examplse of RuntimeException: NullPointerException, IndexOutOfBoundsException, etc

