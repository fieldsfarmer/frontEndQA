```javascript

'use strict';

Function.prototype.method = function(name, func) {
	if(!this.prototype[name]){
		this.prototype[name] = func;
	}
	return this;
};

// Number.method('integer', function(){
// 	return Math[this < 0? 'ceil' : 'floor'](this);
// });

// console.log((-13 / 3).integer()); // -4
// console.log((10/3).integer()); // 3


// var hanoi = function(disc, src, tmp, dst){
// 	if(disc > 0){
// 		hanoi(disc-1, src, dst, tmp);
// 		console.log('Move disc ' + disc + ' from ' + src + ' to ' + dst);
// 		hanoi(disc-1, tmp, src, dst);
// 	}
// }

// hanoi(3, 'Src', 'Tmp', 'Dst');

// tail recursion
// var fact = function(i, a){
// 	a = a || 1;
// 	if(i < 2)
// 		return a;
// 	return fact(i-1, a*i);
// }
// console.log(fact(4));

//// closure
//// bad example
// var printNum = function(){
// 	var i,
// 		arr = [];
// 	for(i=0; i<3; i+=1){
// 		arr.push(function(){
// 			console.log(i*i);
// 		});
// 	}
// 	return arr;
// }
// var result = printNum();
// result[0](); // 9
// result[1](); // 9
// result[2](); // 9

// var printNum1 = function(){
// 	var	arr = [];
// 	for(let i=0; i<3; i+=1){
// 		arr.push(function(){
// 			console.log(i*i);
// 		});
// 	}
// 	return arr;
// }
// var result1 = printNum1();
// result1[0](); // 0
// result1[1](); // 1
// result1[2](); // 4

// var printNum2 = function(){
// 	var	arr = [];
// 	for(let i=0; i<3; i+=1){
// 		arr.push((function(e){
// 			console.log(e*e);
// 		})(i));
// 	}
// 	return arr;
// }
// var result2 = printNum2();
// result2[0]; // 0
// result2[1]; // 1
// result2[2]; // 4


// Module pattern
String.method('deentityfy', function(){
	var entity = {
		quot : '"',
		lt: '<', 
		gt: '>'
	};
	return function(){
		//// [^&;] complemented character set; match anything that is not enclosed in the brackets
		return this.replace(/&([^&;]+);/g, function(a, b){
			var r = entity[b];
			return typeof r === 'string'? r : a;
		});
	};
}());
//// console.log('&lt;&quot;&gt;'.match(/&([^&;]+);/g));
console.log('&lt;&quot;&gt;'.deentityfy());

function replaceTag(a){
	var entity = {
		quot: '"',
		lt: '<',
		gt: '>'
	};
	var b = a.replace(/&([^&;]+);/g, function(x,y){
		var r = entity[y];
		return typeof r === 'string'? r : x;
	});
	return b;
}
var testString = '&lt;&quot;&gt;';
console.log(replaceTag(testString));
// var serialMaker = function(){
// 	var prefix = '',
// 		seq = 0;
// 	return {
// 		setPrefix: function(p){
// 			prefix = p;
// 		},
// 		setSeq: function(s){
// 			seq = s;
// 		},
// 		gensym: function(){
// 			var res = prefix + '_' + seq;
// 			seq += 1;
// 			return res;
// 		}
// 	};
// };

// var serial = serialMaker();
// serial.setPrefix('Nima');
// serial.setSeq(1000);
// console.log(serial.gensym());
// console.log(serial.gensym());


//// Memoization
//// var cnt = 0;
// var fibonacci = (function(){
// 	var memo = [0,1];
// 	var fib = function(n){
// 		var res = memo[n];
// 		if(typeof res !== 'number'){
// 			//cnt ++;
// 			res = fib(n-1) + fib(n-2);
// 			memo[n] = res;
// 		}
// 		return res;
// 	};
// 	return fib;
// })();
// // console.log(fibonacci(2));
// // console.log('Call ' + cnt + ' times.');

// var memorizer = function(memo, fundmental){
// 	var shell = function(n){
// 		var res = memo[n];
// 		if(typeof res !== 'number'){
// 			res = fundmental(shell, n);
// 			memo[n] = res;
// 		}
// 		return res;
// 	}
// 	return shell;
// }

// var fibonacci1 = memorizer([0,1], function(shell, n){
// 	return shell(n-1) + shell(n-2);
// })

// console.log(fibonacci1(10));

// var factorial1 = memorizer([1,1], function(shell, n){
// 	return n*shell(n-1);
// })

// console.log(factorial1(3));

// var isPrime = function(n){
// 	var i;
// 	if(n<2) return false;
// 	if(n === 2) return true;
// 	for(i=2; i*i <= n; i+=1){
// 		if(n%i==0) return false;
// 	}
// 	return true;
// }
// var cnt1 = 0;
// var isPrimeMem = (function(){
// 	var memo = [true];
// 	var helper = function(n){
// 		if(n<2) return false;
// 		var res = memo[n];
// 		if(typeof res !== 'boolean'){
// 			cnt1 += 1;
// 			res = isPrime(n);
// 			memo[n] = res;
// 		}
// 		return res;
// 	}
// 	return helper;
// })();
// console.log(isPrimeMem(13));
// console.log('The function calls '+cnt1+' times');
// console.log(isPrimeMem(13));
// console.log('The function calls '+cnt1+' times');


// private
var PrivatePerson = function(n){
	var name = n || 'unknow';
	var secrets  = 3,
		that = this;
	function dec(){
		if(secrets > 0){
			secrets -= 1;
			return true;
		}else{
			return false;
		}
	}
	this.service = function(){
		return dec()? that.name : null;
	}
}
var xiaoming = new PrivatePerson('xiaoming');
// xiaoming.name = 'nima';
console.log(xiaoming.name);
console.log(xiaoming.service());


function Container(param) {
    var member = param;
    var secret = 3;
    var that = this;
}
var myContainer = new Container('abc');
console.log(myContainer.member); // 依然会打印 abc
myContainer.member = 'efg';
console.log(myContainer.member); // 会打印 efg

```