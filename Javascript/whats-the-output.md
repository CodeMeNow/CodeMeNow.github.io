### 1. Whats the output #closure
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

### 2. Whats the output #closure
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

### 3. Whats the output #closure
```` javascript
var a = 10;

function test() {
  console.log(a);
  console.log(b);
}
var b = 6;
test();
````
### 4. Whats the output #hoisting
 ```javascript
  console.log(myName); //output ?
  myName = 'John Doe';
 ```
### 5. Whats the output #hoisting
 ```javascript
  function test() {
      beerPrice = 4;
      var whiskeyPrice = 100;
  }
  test();
  console.log(beerPrice); //output ?
  console.log(whiskeyPrice); //output ?
 ```



### resources
1. [#closure](https://stackoverflow.com/a/111200/8321804)
