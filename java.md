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

###### static class
- Only nested classes can be static.
- Nested static class doesn't need reference/instance of Outer class, but Non-static nested class or Inner class requires Outer class reference.
- Inner class(or non-static nested class) can access both static and non-static members of Outer class. A static class cannot access non-static members of the Outer class. It can access only static members of Outer class.
- An instance of Inner class cannot be created without an instance of outer class and an Inner class can reference data and methods defined in Outer class in which it nests, so we don't need to pass reference of an object to the constructor of the Inner class. For this reason Inner classes can make program simple and concise.
```java
class OuterClass{
   private static String msg = "GeeksForGeeks";
    
   // Static nested class
   public static class NestedStaticClass{
      
       // Only static members of Outer class is directly accessible in nested 
       // static class 
       public void printMessage() {
 
         // Try making 'message' a non-static variable, there will be 
         // compiler error  
         System.out.println("Message from nested static class: " + msg); 
       }
    }
    
    // non-static nested class - also called Inner class
    public class InnerClass{
        
       // Both static and non-static members of Outer class are accessible in 
       // this Inner class
       public void display(){
          System.out.println("Message from non-static nested class: "+ msg);
       }
    }
} 
class Main
{
    // How to create instance of static and non static nested class?
    public static void main(String args[]){
        
       // create instance of nested Static class
       OuterClass.NestedStaticClass printer = new OuterClass.NestedStaticClass();
        
       // call non static method of nested static class
       printer.printMessage();   
  
       // In order to create instance of Inner class we need an Outer class 
       // instance. Let us create Outer class instance for creating 
       // non-static nested class
       OuterClass outer = new OuterClass();        
       OuterClass.InnerClass inner  = outer.new InnerClass();
        
       // calling non-static method of Inner class
       inner.display();
        
       // we can also combine above steps in one step to create instance of 
       // Inner class
       OuterClass.InnerClass innerObject = new OuterClass().new InnerClass();
        
       // similarly we can now call Inner class method
       innerObject.display();
    }
}
```

###### checked exceptions vs unchecked exceptions
- A checked exception is an exception that occurs at the compile time.
- An Unchecked exception (Runtim Exception) is an exception that occurs at the time of execution. These exceptions include programming bugs, such as logic errors or improper use of an API. runtime exceptions are ignored at the time of compilation.

- A checked exception must be caught somewhere in your code. If not code will not compile. That's why they're called checked exceptions. In other hand RuntimeExceptions (unchecked exceptions), the calling 
method is under no obligation to handle or declare it. 

- Therefore all the exceptions which compiler force you to handle are directly derived from the class java.lang.Exception and all the other exceptions which compiler not force you to handle are derived from java.lang.RuntimeException.

- Examples of checked exceptions are: FileNotFoundException, IOException, etc

- Examplse of RuntimeException: NullPointerException, IndexOutOfBoundsException, etc

