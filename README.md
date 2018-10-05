## Index
## Javascript

1. [Hoisting in Javascript](#hoisting)
2. [`var` vs `let`](#var-vs-let)
3. [Strict mode in Javascript](#strict-mode-in-Javascript)
3. [Function declaration types in Javscript](#function-declaration-types-in-javascript)
4. [Async await](#async-await)
5. [Events and Delegation](#events-and-delegation)
6. [Take the quiz](#javascript-quiz)
7. [References and resources](#references-and-resources)

### Hoisting

> Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.  

> Inevitably, this means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local.  

> Of note however, is the fact that the hoisting mechanism only moves the declaration. The assignments are left in place.  

> we can use variables before we declare them. However, we have to be careful because the hoisted variable is initialized with a value of undefined. The best option would be to declare and initialize our variable before use.  



````javascript
printMessage("Github"); // outputs "Hello Github"

function printMessage(msg) {
  console.log("Hello " + msg);
}

````
````javascript
function setBeerPrice(){
  beerPrice = 10;
}

setBeerPrice();

console.log(beerPrice);

function setBeerPriceAgain(){
  var beerPrice = 20;
}

setBeerPriceAgain();

console.log(beerPrice); // outputs 10.🤷‍
````

### `var` vs `let`
`var`: The scope of a variable declared with the keyword var is its current execution context. This is either the enclosing function or for variables declared outside any function, global.

`let`: 

### Strict mode in Javascript

> JavaScript can be made a little stricter by enabling strict mode. This is done by
putting the string "use strict" at the top of a file or a function body. Here’s an example:

````javascript
function canYouSpotTheProblem() {
  "use strict";
  for (counter = 0; counter < 10; counter++) {
    console.log("Happy happy");
  }
}

canYouSpotTheProblem(); // → ReferenceError: counter is not defined
````
> Normally, when you forget to put let in front of your binding, as with
counter in the example, JavaScript quietly creates a global binding and uses
that. In strict mode, an error is reported instead.

> Another change in strict mode is that the this binding holds the value undefined in functions that are not called as methods. When making such a call outside of strict mode, this refers to the global scope object, which is an object whose properties are the global bindings. 

> So if you accidentally call
a method or constructor incorrectly in strict mode JavaScript will produce an error as soon as it tries to read something from this, rather than happily
writing to the global scope. For example, consider the following code, which calls a constructor function
without the new keyword so that its this will not refer to a newly constructed
object:


````javascript
function Person(name) { 
  this.name = name;
}
let ferdinand = Person("Ferdinand"); // oops

console.log(name); // → Ferdinand
````

> So the bogus call to Person succeeded but returned an undefined value and
created the global binding name. In strict mode, the result is different.


````javascript
"use strict"
function Person(name) { this.name = name; }
let ferdinand = Person("Ferdinand"); // forgot new
// → TypeError: Cannot set property 'name' of undefined
````

> Fortunately, constructors created with the `class` notation will always complain if they are called without `new`, making this less of a problem even in non-strict mode. 

> Strict mode does a few more things. It disallows giving a function multiple parameters with the same name and removes certain problematic language features entirely (such as the with statement). In short, putting `"use strict"` at the top of your program rarely hurts and
might help you spot a problem.

### Function declaration types in Javascript
an `anonymous function` or `Function expression` is an unnamed function that is assigned to a variable.

````javascript
var test = function() {
  console.log('hello! world');
}
````

anonymous functions will not be hoisted (link??).

a named function or Function declaration will have its name in its declaration.

````javascript
function test() {
  console.log('hello! world');
}
````

named functions will be hoisted (link??).

an `Immediately-Invoked Function Expression (IIFE)` a function that gets called immediately after the declaration.

````javascript
(function (){
  console.log('hello! world');
}());
````

`Arrow function` is introduced in ES6 which binds the current context in side the function and adds syntactical sugar.

````javascript
var a = () => {
  console.log('hello! world');
}

a() // prints 'hello! world'
````

### Async await
Async Await is syntactical sugar to the existing Javascript Promises.

* Async function returns a promise regardless of return value. 
* You don’t need to wrap the return value in Promise. its by default.

### Events and Delegation
//todo

### Javascript quiz
1. What will be the console output of the following code and why is it ?
    ````javascript
    console.log(myName); //output ?
    myName = 'John Doe';
    ````
    ````javascript
    function test() {
        beerPrice = 4;
        var whiskeyPrice = 100;
    }
    test();
    console.log(beerPrice); //output ?
    console.log(whiskeyPrice); //output ?
    ````

### References and resources
The following references are used in the code snippets, examples, definitions.
1. [Eloquent-JavaScript.pdf](https://eloquentjavascript.net/Eloquent_JavaScript.pdf)
2. [Understanding hoisting in javascript](https://scotch.io/tutorials/understanding-hoisting-in-javascript)
3. [A Beginner's Guide to JavaScript's Prototype](https://tylermcginnis.com/beginners-guide-to-javascript-prototype/)
4. [30secondsofinterviews](https://30secondsofinterviews.org/)
