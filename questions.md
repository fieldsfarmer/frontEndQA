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
var add = (function(){
	var count = 0;
	return function(){++count;};
})();
add();
add();
add();
```
