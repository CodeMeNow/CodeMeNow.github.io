### Strict mode in Javascript

> JavaScript can be made a little stricter by enabling strict mode. This is done by putting the string "use strict" at the top of a file or a function body. Here’s an example:

```javascript
function canYouSpotTheProblem() {
  "use strict";
  for (counter = 0; counter < 10; counter++) {
    console.log("Happy happy");
  }
}

canYouSpotTheProblem(); // → ReferenceError: counter is not defined
```

> Normally, when you forget to put let in front of your binding, as with counter in the example, JavaScript quietly creates a global binding and uses that. In strict mode, an error is reported instead.
>
> Another change in strict mode is that the this binding holds the value undefined in functions that are not called as methods. When making such a call outside of strict mode, this refers to the global scope object, which is an object whose properties are the global bindings.
>
> So if you accidentally call a method or constructor incorrectly in strict mode JavaScript will produce an error as soon as it tries to read something from this, rather than happily writing to the global scope. For example, consider the following code, which calls a constructor function without the new keyword so that its this will not refer to a newly constructed object:

```javascript
function Person(name) { 
  this.name = name;
}
let ferdinand = Person("Ferdinand"); // oops

console.log(name); // → Ferdinand
```

> So the bogus call to Person succeeded but returned an undefined value and created the global binding name. In strict mode, the result is different.

```javascript
"use strict"
function Person(name) { this.name = name; }
let ferdinand = Person("Ferdinand"); // forgot new
// → TypeError: Cannot set property 'name' of undefined
```

> Fortunately, constructors created with the `class` notation will always complain if they are called without `new`, making this less of a problem even in non-strict mode.
>
> Strict mode does a few more things. It disallows giving a function multiple parameters with the same name and removes certain problematic language features entirely \(such as the with statement\). In short, putting `"use strict"` at the top of your program rarely hurts and might help you spot a problem.
