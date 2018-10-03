## Index
### Javascript
1. [Function declaration types in Javscript](https://iamsbr.github.io/#function-declaration-types-in-javscript)
2. [Async Await](https://iamsbr.github.io/#async-await)

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
