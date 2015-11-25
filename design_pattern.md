###### Singleton pattern
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