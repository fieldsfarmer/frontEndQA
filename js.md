###### Closure
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

###### Javascript build objects & inheritance
```javascript
function Person(name){
	this.name = name;
}
Person.prototype.sayHi = function(){
	console.log('Hello, '+this.name+'!');
}
var p1 = new Person('Lily');
p1.sayHi();

function Student(props){
	Person.call(this,props.name||'Unamed');
	this.grade = props.grade || 1;
}

// build inheritance method
function F(){}; 
F.prototype = Person.prototype;
Student.prototype = new F();
Student.prototype.constructor = Student;

Student.prototype.getGrade = function(){
	return this.grade;
}

var s1 = new Student({name: 'Eva', grade: 0});
s1.sayHi();
s1.getGrade();

s1.__proto__ === Student.prototype; // true
s1.__proto__.__proto__ === Person.prototype; //true

//The inheritance method can be encapsulated in a function
function inherit(child, parent){
	function F(){};
	F.prototype = parent.prototype;
	child.prototype = new F();
	child.prototype.constructor = child;
}

```
