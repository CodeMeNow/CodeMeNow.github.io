### Function declaration types in Javascript

an `anonymous function` or `Function expression` is an unnamed function that is assigned to a variable.

```javascript
var test = function() {
  console.log('hello! world');
}
```

anonymous functions will not be hoisted \(link??\).

a named function or Function declaration will have its name in its declaration.

```javascript
function test() {
  console.log('hello! world');
}
```

named functions will be hoisted \(link??\).

an `Immediately-Invoked Function Expression (IIFE)` a function that gets called immediately after the declaration.

```javascript
(function (){
  console.log('hello! world');
}());
```

`Arrow function` is introduced in ES6 which binds the current context in side the function and adds syntactical sugar.

```javascript
var a = () => {
  console.log('hello! world');
}

a() // prints 'hello! world'
```
