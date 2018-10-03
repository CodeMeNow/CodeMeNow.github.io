## Index
### Javascript
1. [Hoisting in Javascript](https://iamsbr.github.io/#hoisting)
2. [Function declaration types in Javscript](https://iamsbr.github.io/#function-declaration-types-in-javscript)
3. [Async Await](https://iamsbr.github.io/#async-await)


#### Hoisting
In Javascript variables and function declarations are moved to the top of their scope before code execution.
This allows us to call the function even before they are declared in the code.

```` javascript
printMessage("Github"); // outputs "Hello Github"

function printMessage(msg) {
  console.log("Hello " + msg);
}
````
#### Function declaration types in Javscript
an `anonymous function` or `Function expression`is an unnamed function that is assigned to a variable.
```` javascript
var test = function() {
  console.log('hello! world');
}
````
_anonymous functions will not be `hoisted` (link??)_.

a `named function` or `Function declaration` will have its name in its declaration.

```` javascript
function test() {
  console.log('hello! world');
}
````
_named functions will be `hoisted` (link??)_.


an `Immediately-Invoked Function Expression (IIFE)` a function that gets called immedialty after the declaration.
```` javascript
(function (){
  console.log('hello! world');
}());

````
Arrow function` is introduced in ES6 which binds the current context in side the function and adds syntaxical sugar.

```` javascript
var a = () => {
  console.log('hello! world');
}

a() // prints 'hello! world'
````

#### Async Await
* Async Await is syntaxical sugar to the existing Javascript Promises.
* Async function returns a promise regardless of return value. You dont need to wrap the return value in Promise. its by default.
