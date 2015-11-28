###### Singleton pattern
- Restrict the instantiation of a class to one object
- JS: use self-invoking function (immediately-invoked function) & closure
```javascript
var Singleton = (function(){
	var instance;
	function createInstance(){
		return new Object("I am the instance!");
	}
	return{
		getInstance: function(){
			if(!instance){
				instance = createInstance;
			}
			return instance;
		}
	}
})();
var instance1 = Singleton.getInstance();
var instance2 = Singleton.getInstance();
instance1 === instance2; //true
```
- Java: set constructor as private
```java

```

###### Module pattern
- JS: using closure; revealing module
```javascript
function CoolModule(){
	var h = "Hello!";
	var b = "Bye!";
	function sayHi(){
		console.log(h);
	}
	function sayBye(){
		console.log(b);
	}
	return {
		sayHi: sayHi,
		sayBye: sayBye
	};	
}
var f = CoolModule();
f.sayHi();
f.sayBye();
```

###### Strategy pattern
- Create objects which represent various strategies and a context object whose behavior varies as per its strategy object. The strategy object changes the executing algorithm of the context object.
- Java example
```java
//Strategy.java
public interface Strategy {
   public int doOperation(int num1, int num2);
}
//OperationAdd.java
public class OperationAdd implements Strategy{
   @Override
   public int doOperation(int num1, int num2) {
      return num1 + num2;
   }
}
//OperationSubstract.java
public class OperationSubstract implements Strategy{
   @Override
   public int doOperation(int num1, int num2) {
      return num1 - num2;
   }
}
//Context.java
public class Context {
   private Strategy strategy;

   public Context(Strategy strategy){
      this.strategy = strategy;
   }

   public int executeStrategy(int num1, int num2){
      return strategy.doOperation(num1, num2);
   }
}
//StrategyPatternDemo.java
public class StrategyPatternDemo {
   public static void main(String[] args) {
      Context context = new Context(new OperationAdd());	
      System.out.println("10 + 5 = " + context.executeStrategy(10, 5));
      context = new Context(new OperationSubstract());		
      System.out.println("10 - 5 = " + context.executeStrategy(10, 5));
   }
}
```