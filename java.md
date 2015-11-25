###### Abstract Class vs Interface
- An abstract class is one with at least one abstract method, which just has no implementation code .
- An abstract class can have some implementation code. Thus can have non-abstract methods, can also have constructors and instance variables.
- An interface can only provide method headings.


###### Strategy pattern


###### Singleton pattern
- JS use self-invoking function (immediately-invoked function) & closure
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