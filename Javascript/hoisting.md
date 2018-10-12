### Hoisting

> Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.
>
> Inevitably, this means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local.
>
> Of note however, is the fact that the hoisting mechanism only moves the declaration. The assignments are left in place.
>
> we can use variables before we declare them. However, we have to be careful because the hoisted variable is initialized with a value of undefined. The best option would be to declare and initialize our variable before use.

```javascript
printMessage("Github"); // outputs "Hello Github"

function printMessage(msg) {
  console.log("Hello " + msg);
}
```

```javascript
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
```
