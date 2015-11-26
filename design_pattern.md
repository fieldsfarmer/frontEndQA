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