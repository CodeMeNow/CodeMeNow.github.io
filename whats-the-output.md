## 1. Whats the output #closure
```` javascript
function foo() {
  var callCounter = 0;

  function bar() {
    console.log(++callCounter);
  }
  bar();
}

foo();
foo();
foo();
````

## 2. Whats the output #closure
```` javascript
function foo() {
  var callCounter = 0;

  return function () {
    console.log(++callCounter);
  }
}

var bar = foo();
bar();
bar();
bar();
````



### resources
1. [#closure](https://stackoverflow.com/a/111200/8321804)
