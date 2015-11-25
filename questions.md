###### 1. What is MVC?

Model: managing data; Controller: application logic; View: presenting data

###### 2. GET vs POST?

GET: retrieve representations of resources; no side effects; no data in request body. 

POST: upload data from the browser to server; returns information from the server; side effects are likely; data contained in the request body.

###### 3. AngularJS
* client-side templating. templates, which are HTML documents defining the UI, are loaded from server; once in the browser, Angular merges template with data, defining a vew.

* template data binding. Use $scope to expose model data to view. Views dynamically load template fragment via routes

###### 4. Closure
A closure is that a function having access to the parent scope, even after the parent function has closed.
```javascript
// add is assigned with the value of a self-invoking function
var add = (function(){
	var count = 0;
	return function(){return count+=1;};
})();
add();
add();
add(); // count is now 3
function createCounter(initial){
	var x = initial || 0;
	return function(){
		return x+=1;
	}
}
var c1 = createCounter();
c1();
c1(); //2

function createCounter1(initial){
	var x = initial || 0;
	return {
		inc: function(){
			return x+=1;
		}
	}
	
}
var c2 = createCounter1(10);
c2.inc();
c2.inc();
c2.inc(); // 13
```
