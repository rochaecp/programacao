# Javascript

## Syntax

#### Ex.: javascript in the body tag

~~~html
<body>
  <script>
    alert("Hi!");  
  </script>
</body> 
~~~

#### Ex.: javascript in external files 

~~~html
<head>
  <script src="js/main.js"></script>
</head>
~~~

## Comments

~~~javascript
// comment
/* comment */
~~~

## Data Types

### Basic Data Types

- number
- string
- boolean - typeof true -> boolean
- null - typeof null -> object
- undefined
- symbol

### Derived Data Types

- Object
  - Function
  - Array

## Variables

- var
- let
- const

#### Ex.: Destructuring Assignment - ecmascript6

~~~javascript
var [apple, banana, orange] = ["Apple", "Banana", "Orange"];
console.log(apple);
~~~

## Constants

#### Ex.: Symbols - generate a unique identifier 

~~~javascript
const uniqueId = Symbol('valueToDebug');
console.log(uniqueId);
~~~

## Operators

- Arithmetic operators: + - * / % ++ -- 
- Assignment operators: = += -= *= /= %= &= |= ^= >>= <<=
- Comparison operators: == === != > < >= <=
- Logical operators: && || ! !!
- Bitwise operators: & | ^ << >> ~
- spread, delete, typeof, in, instanceof


## Strings

~~~javascript
var txt = 'aaa';
var size = txt.length;                  
var pos = txt.indexOf('a');            
var pos = txt.indexOf('a', 2);         
var pos = txt.lastIndexOf('a');        
var pos = txt.lastIndexOf('a', 12);    
var pos = str.search('a');               
var myStr = str.slice(0, 5);               
var myStr = str.slice(-1);                 
var myStr = str.substring(0, 5);           
var myStr = str.substr(0, 8);              
var myStr = str.substr(-4);                
var myStr = str.replace('aaa', 'bbb');     
var myStr = str.replace(/aaa/i, 'bbb');    
var myStr = str.replace(/aaa/g, 'bbb');    
var myStr = str.replace(/aaa/ig, 'bbb');   
var n = nome.toLowerCase();    
var n = nome.toUpperCase();
var myStr = text1.concat('#',text2);  
var myStr = str.trim();               
var myStr = str.charAt(0);            
var myStr = str.charCodeAt(0);        
var arr = str.split(',');
~~~

## Number

~~~javascript
const num = 12.4032;
const str = num.toString(); 
const num2 = num.toString(10);  
const num2 = num.toString(16);  
const num2 = num.toString(8);   
const num2 = num.toString(2);   
const num2 = num.toFixed(2)     
const num = parseFloat('10.23');
const num = parseInt('10.23');
const num = parseInt('100', 10);  
const num = parseInt('a', 16);    
const num = parseInt('20', 8);    
const num = parseInt('1111', 2);  
const num = eval('2 + 3');        
const bool = isNaN('aaa'); 
~~~

## Math 

~~~javascript
var x = Math.PI;            
var x = Math.E;             
var x = Math.LN2;           
var x = Math.LN10;          
var x = Math.LOG2E;         
var x = Math.LOG10E;        
var x = Math.SQRT1_2;       
var x = Math.SQRT2;         
var x = Math.abs( valor );  
var x = Math.sin( 0 );      
var x = Math.cos( 0.12 );   
var x = Math.tan( 0 );      
var x = Math.asin( 1 );     
var x = Math.acos( 1 );     
var x = Math.exp( 1 );      
var x = Math.log(1);        
var x = Math.max( 2, 9 );   
var x = Math.min( 2, 9 );   
var x = Math.pow( 2, 3 );   
var x = Math.sqrt( 100 );   
var x = Math.floor( 2.6 );  
var x = Math.ceil( 2.4 );   
var x = Math.round(125.6);  
var x = Math.random();
~~~

## Date 

- JavaScript counts months from 0 to 11.

~~~javascript
var date = new Date();              
var date = new Date(2019, 10, 18);  
var y = date.getFullYear();         
var m = date.getMonth();            
var d = date.getDate();             
var h = date.getHours();            
var m = date.getMinutes();          
var s = date.getSeconds();          
var msg = date.getMilliseconds();   
var d = date.getTime();             
var d = date.getDay();              
date.toLocaleString();              
date.setFullYear(2020);             
date.setMonth(11);                  
date.setDate(19);                   
date.setHours(17);                  
date.setMinutes(30);                
date.setSeconds(1);                 
date.setMilliseconds();             
date.setTime();                     
date.setDate(date.getDate() + 50);  
~~~

#### Ex.: date - date3 = date2 - date1

~~~javascript
var date1 = new Date(2019, 10, 18); 
var date2 = new Date(2019, 10, 19);
var date3 = date2;
date3.setDate( date2.getDate() - date1.getDate() ); 
alert( date3.getDate() );
~~~

#### Ex.: date - converting a date to a number 

~~~javascript
Number(new Date("2017-09-30")); // returns 1506729600000
~~~

## If...Else

~~~javascript
var grade = 10;
if (grade >= 6)
  console.log("student was approved");
else 
  console.log("student was not approved");
~~~

## Conditional Operator 

~~~javascript
x >= 6 ? 'foo' : 'bar';
a = typeof a === 'undefined' ? 0 : a;
~~~

## Switch

~~~javascript
const fruit = "pera";
switch (fruit) {
  case "banana":
    console.log("bananaaa");
    break;
  case "pera":
    console.log("peraaa");
    break;
  default:
    console.log("erro");
}
~~~

## While Loop

~~~javascript
var count = 0;
while (count <= 10) {
  console.log(count);
  count++;
}
~~~

## Do...While Loop

~~~javascript javascript
var count = 0;
do {
  console.log(count);
  count++;
} while (count <= 10);
~~~

## For Loop

~~~javascript
const array = ['one', 'two', 'three'];
for (let index = 0; index < array.length; index++) {
  const element = array[index];
  console.log(`Element #${index}: ${element}.`);
}
~~~

## For...in Loop

~~~javascript
array = [3, 5, 7];
array.foo = "hello"; 

for (let i in array)
  console.log(i);
~~~

## For...of Loop

~~~javascript
array = [3, 5, 7];
array.foo = "hello"; 

for (let i of array)
  console.log(i);

const arr = [1, 2, 3, 4];

for (let value of arr) {
  console.log(value);
}
~~~

## Arrays

~~~javascript
var myArray = [];                    
var myArray = ['aaa', 'bbb'];        
var myArray[0] = 'abacate';          
var size = myArray.length;var x = myArray.push('ccc');         
var x = myArray.pop();               
var x = myArray.shift();             
var x = myArray.unshift('ddd')       
var type = typeof(myArray)           
var isArr = Array.isArray(myArray);  
var str = myArray.toString();        
var str = myArray.join('*');         
myArray.reverse();                   
myArray.sort();                      
delete myArray[0];                         
var myArray.splice(0, 2);                  
var myChildren = myGirls.concat(myBoys);   
var myChildren = arr1.concat(arr2, arr3);  
var myChildren = arr1.concat('Peter');     
var arr2 = arr1.slice(2);                  
var arr2 = arr1.slice(0, 3);               
var highest = Math.max.apply(null, num); 
lowest = Math.min.apply(null, num);   
var indice = lista.indexOf('Apple');       
var indice = lista.lastIndexOf('Apple');   
const bool = arr.includes(1);               
const bool = arr.some(value => value > 2);  
const bool = arr.every(value => value > 2); 
~~~

## Functions

- Functions are objects in javascript.
- Arrow functions are anonymous functions.

#### Ex.: function - classic

~~~javascript
function fn(num1, num2) {
  return num1 + num2;
}
console.log(fn(6, 4));
~~~

#### Ex.: function - anonymous function 

~~~javascript
var log = function (value) {
  console.log(value);
}
log('test');
~~~

#### Ex.: function - anonymous function 

~~~javascript
var sum = function (a, b) {
  return a + b;
}
console.log(sum(2, 3));
~~~

#### Ex.: function - arrow function - 1 arg

~~~javascript
var sum = a => a + 10; // we can omit the word function, a+b == return
console.log(sum(5));
~~~

#### Ex.: function - arrow function - 2 args

~~~javascript
var sum = (a, b) => a + b; // we can omit the word function, a+b == return
console.log(sum(2, 3));
~~~

#### Ex.: function - arrow function - create object

~~~javascript
var createObj = () => ({
  myAtrib: 20
});
console.log(createObj());
~~~

### Function Arguments

#### Ex.: arguments - default function arguments

~~~javascript
function multiply(a = 1, b = 1) {
  return a * b;
}
console.log(multiply());
~~~

#### Ex.: arguments - default function arguments - ex 2

~~~javascript
function multiply(a = 1, b = a) {
  return a * b;
}
console.log(multiply(5));
~~~

#### Ex.: arguments - default function arguments - lazy evaluation

~~~javascript
function randomNumbers() {
  return Math.floor(Math.random() * 10) + 1;
}

function multiply(a = 1, b = randomNumbers()) {
  return a * b;
}
console.log(multiply(2));
console.log(multiply(2));
~~~

#### Ex.: arguments - unlimited arguments 

~~~javascript
function myFunc() {
  console.log(arguments);
}
myFunc(1, 2, 3, 4);
~~~

#### Ex.: arguments - unlimited arguments 

~~~javascript
function sum() {
  var value = 0;
  for (var i = 0; i < arguments.length; i++)
    value += arguments[i];
  console.log(value);
}
sum(1, 2, 3, 4);
~~~

#### Ex.: arguments - ecmascript6 - rest operator: ...

~~~javascript
function sum(...myArg) {
  return myArg.reduce((acc, value) => acc + value, 0); // 0 == initial value
}
console.log(sum(1, 2, 3, 4));
~~~

#### Ex.: arguments - ecmascript6 - rest operator: ...

~~~javascript
const myFunc = (a, b, ...rest) => {
  console.log(a, b, rest);
}
myFunc(1, 2, 3, 4);
~~~

#### Ex.: arguments - ecmascript6 - spread operator: ...

- Usable in strings, arrays, literal objects

~~~javascript
const multiply = (...myArgs) => myArgs.reduce((acc, value) => acc * value, 1); // spread operator: ...

const sum = (a, b, ...rest) => { // rest operator: ...
  return a + b + multiply(...rest);
}

console.log(multiply(10, 10, 10)); // 1000
console.log(sum(1, 1, 10, 10, 10)); // 1002
~~~

## Dictionaries

~~~javascript
var fruit = {
  name: "apple",
  color: "red"
};

// lista de dicionarios
var fruits = [{
    name: "apple",
    color: "red"
  },
  {
    name: "uva",
    color: "roxa"
  }
];
console.log(fruits[0].name);
~~~

## OOP

### Classes/Objects

~~~javascript
let user = {
  name: 'aaa',
  age: 100
};

user.name = 'bbb';  
user.age = 100;
user.email = 'ccc'; 
delete user.email;  
let keys = Object.keys(user);     
let values = Object.values(user); 
let arr = Object.entries(user);   
user2 = Object.assign({}, user, {email: 'ccc'}); 
Object.freeze(user);  
Object.seal(user);  
~~~

#### Ex.: 

~~~javascript
class Person {
  constructor(name) {
    this.name = name;
  }
}
p = new Person('Mauricio');
console.log(p.name);
~~~

### Class Attributes

#### Ex.: attribute - classic way

~~~javascript
var myObj = {
  prop1: "my property 1"
};
~~~

#### Ex.: attribute - attribute name obtained by variable 

~~~javascript
var propertyName = 'test';
var myObj = {};
myObj[propertyName] = "property value";
console.log(myObj);
~~~

### Class Methods

#### Ex.: method - classic way

~~~javascript
var myObj = {
  sum: function sum(a, b) {
    return a + b;
  }
};
console.log(myObj.sum(2, 3));
~~~

#### Ex.: method - ecmascript 6

~~~javascript
var myObj = {
  sum(a, b) {
    return a + b;
  }
};
console.log(myObj.sum(2, 3));
~~~

### Inheritance

~~~javascript
class Person {
  constructor(name) {
    this.name = name;
  }
}

class Employee extends Person {
  constructor(name, cpf) {
    super(name); 
    this.cpf = cpf;
  }
}
e = new Employee('Mauricio', '123');
console.log(e);
~~~

### Iterator

#### Ex.: iterator - array

~~~javascript
const myArray = [{
    name: 'Mauricio',
    age: 29,
    gender: 'man'
  },
  {
    name: 'Maria',
    age: 100,
    gender: 'woman'
  },
];

myArray.forEach((myArray) => {
  console.log(`Name: ${myArray.name}`);
});


myArray.forEach((myArray, index, arr) => {
  console.log(`Name: ${myArray.name} index: ${index}`, arr);
});

const men = myArray.filter(myArray => myArray.gender === 'man');
console.log('Men: ', men);

const myArray2 = myArray.map(myArray => {
  myArray.course = 'ECP';
  return myArray;
});
console.log(myArray2);
~~~

#### Ex.: iterator - array

~~~javascript
const array = [0, 1, 2, 3, 4, 5];

array.forEach(item => {
  if (item % 2 === 0)
    console.log(`O número ${item} é par.`);
  else
    console.log(`O número ${item} é impar.`);
})
~~~

#### Ex.: iterator - map

~~~javascript
arr = [1, 2, 3, 4, 5];
arr2 = arr.map(value => value * 2); 
console.log(arr2);
~~~

#### Ex.: iterator - flat

~~~javascript
arr = [1, 2, [3, 4]];
arr2 = arr.flat(); 
console.log(arr2);

arr3 = [1, 2, [3, 4, [5, 6]]];
arr4 = arr3.flat(2); 
console.log(arr4);
~~~

#### Ex.: iterator - array iterator

~~~javascript
const arr = [10, 20];
const arrIterator = arr.keys(); 
const arrIterator2 = arr.values(); 
console.log(arrIterator.next());
console.log(arrIterator.next());
console.log(arrIterator.next());
console.log(arrIterator2.next());
console.log(arrIterator2.next());
console.log(arrIterator2.next());
~~~

#### Ex.: array iterator - Symbol.iterator

~~~javascript
const arr = [1, 2, 3, 4];

const arr_iterator = arr[Symbol.iterator]();

console.log(arr_iterator.next());
console.log(arr_iterator.next());
console.log(arr_iterator.next());
~~~

#### Ex.: iterator - find and findIndex

~~~javascript
const arr = [1, 2, 3, 4, 5];
const firstPair = arr.find(value => value % 2 === 0);
console.log(firstPair);
~~~

#### Ex.: iterator - array filter

~~~javascript
const arr = [1, 2, 3, 4, 5];
const arr2 = arr.filter(value => value % 2 === 0);
console.log(arr2);
~~~

## Events

~~~javascript
onblur = alert("Hi");        
onselect = alert("Hi");      
onfocus = alert("Hi");       
onchange = alert("Hi");      
onclick = alert("Hi");       
onmouseover = alert("Hi");   
onmouseout = alert("Hi");    
onmousemove = alert("Hi");   
onmousedown = alert("Hi");   
onmouseup = alert("Hi");     
onkeydown = alert("Hi");     
onkeypmyStrs = alert("Hi");    
onkeyup = alert("Hi");       
onload = alert("Hi");        
onsubmit = alert("Hi"); 
~~~

#### Ex.: events - onlclick

~~~html
<button onclick="this.innerHTML=Date()">The time is?</button>
~~~

#### Ex.: events - onmouseover and onmouseout

~~~javascript
function mouseMove(elemment) {
  elemment.innerHTML = "Obrigado.";
}

function mouseOut(elemment) {
  elemment.innerHTML = "Passe o mouse aqui.";
}
</script>
<p onmouseover="mouseMove(this)" onmouseout="mouseOut(this)">Passe o mouse aqui.</p>
~~~

#### Ex.: events - onchange

~~~html
<script>
  function functionChange(elemment) {
    console.log(elemment.value);
  }
</script>

<select onchange="functionChange(this)">
  <option value="1">Value 1</option>
  <option value="2">Value 2</option>
  <option value="3">Value 3</option>
</select>
~~~

## Output

~~~javascript
const textSize = 'txt'.length;
console.log(`Size: ${textSize}`);

console.warn("my warn");
console.error("my error");
~~~

## How To

### How To: Random numbers

~~~javascript
function randomNumbers() {
  return Math.floor(Math.random() * 100) + 1; // 1 - 10
}
~~~

### How To redirect to another page 

~~~javascript
window.location.href = "https://www.google.com/"; // mesma aba
window.open("https://www.google.com/");           // outra aba
~~~

## Tests

- TDD - Test Driven Development
  - The Red Phase: create test
  - The Green Phase: create code
  - The Refactor Phase: refactor
- BDD - Behavior Driven Development
  - Is an Agile process designed to keep focus on stakeholder's value throughout the whole project. 

### Mocha

Mocha is a JavaScript test framework for Node.js programs, featuring browser support, asynchronous testing, test coverage reports, and use of any assertion library.

### Chai

Chai is a BDD / TDD assertion library for [node](http://nodejs.org) and the browser that can be delightfully paired with any javascript testing framework.

### Sinon

Standalone test spies, stubs and mocks for JavaScript. 

## Links

- [MDN](https://developer.mozilla.org/en/docs/Web/JavaScript)
- [typescript](https://www.typescriptlang.org/)
- [flow](https://flow.org/)
- [ECMAScript](https://pt.wikipedia.org/wiki/ECMAScript)
- [TC39](https://tc39.es/)
- [Babel compiler](https://babeljs.io/)

## To be continued

- W3schools 
- MDN 
- JavaScript APIs
- browser -> F12 -> console -> create an object -> ctrl + space == options
- WebGL ?
- Math.js
- [brain.js](https://www.w3schools.com/ai/ai_brainjs.asp)
- [plotly.js](https://www.w3schools.com/ai/ai_plotly.asp)
- [threejs](https://threejs.org/)

