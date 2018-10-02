# Programmer notes

## Index
* Javascript
* CSS
* HTML

## Javascript
### Anonymous Function vs named function vs Immediately-Invoked Function Expression
an `anonymous function` is an unnamed function that is assigned to a variable.
```` javascript
var test = function() {
  console.log('hello! world');
}
````
a `named function` will have its name in its declaration.

```` javascript
function test() {
  console.log('hello! world');
}

````

an `Immediately-Invoked Function Expression (IIFE)` is an anonymous function that calls gets called immedialty after the declaration.
```` javascript
(function (){
  console.log('hello! world');
}());
````
### Async Await
* Async Await is syntaxical sugar to the existing Javascript Promises.
* Async function returns a promise regardless of return value. You dont need to wrap the return value in Promise. its by default.
