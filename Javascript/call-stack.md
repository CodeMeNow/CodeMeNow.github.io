**Javascript** is a single threaded single concurrent language, meaning it can handle one task at a time or a piece of code at a time.
It has a single call stack which along with other parts like heap, queue constitutes the Javascript Concurrency Model (implemented inside of V8). 
Let us first go through each of these terminologies :

1. **Call Stack** : It’s a data structure which records the function calls, basically where in the program we are.
If we call a function to execute , we push something on to the stack, and when we return from a function, we pop off the top of the stack.

2. **Heap** : Objects are allocated in a heap i.e mostly unstructured region of memory. All the memory allocation to variables and objects happens here.

3. **Queue** : A JavaScript runtime contains a message queue, which is a list of messages to be processed and the associated callback functions to execute. 
When the stack has enough capacity, a message is taken out of the queue and processed which consists of calling the associated function (and thus creating an initial stack frame).
The message processing ends when the stack becomes empty again.
In basic words , these messages are queued in response to external async events(such as a mouse being clicked or receiving the response to an HTTP request), given a callback function has been provided. 
If, for example a user were to click a button and no callback function was provided — no message would have been enqueued.


**Event Loop**

Basically, when we evaluate the performance of our JS code, so a function in a stack makes it slow or fast, `console.log()` will be fast but performing iteration with for or while over thousands or millions of line items will be slower, and will keep the stack occupied or blocked.
This is termed as blocking script, which you have read or heard about in Webpage Speed Insights.

Network requests can be slow, the image requests can be slow, but thankfully the server requests can be done through AJAX, an asynchronous function.
If suppose, these network requests are made through synchronous functions, then what would happen?

The network requests are send to some server, which is basically another computer/machine somewhere.
Now, computers can be slow sending back the response. In the meantime , if I click some CTA button, or some other rendering needs to be done, nothing will happen as the stack is blocked. 
In multi threaded language like Ruby, it can be handled, but in single threaded language like Javascript, this is not possible unless function inside the stack returns a value.
The webpage will hell breaks loose as the browser can’t do anything.
This is not ideal if we want fluid UI for the end user. How do we handle this?

The easiest solution is by using asynchronous callbacks, which means that we run some part of code and give it a callback (function) which will execute later.
We all must have encounter asynchronous callbacks like any AJAX request using `$.get()`,`setTimeout()`,`setInterval()`, `Promises`, etc. Node is all about asynchronous function execution.
All these async callbacks doesn’t run immediately and are going to run some time later, so can’t be pushed immediately inside the stack unlike synchronous functions like `console.log()`, mathematical operations.
Where the hell then they go and how they are handled?

The decoupling of the caller from the response allows for the JavaScript runtime to do other things while waiting for your asynchronous operation to complete and their callbacks to fire.
This is where browser APIs kicks in and call its APIs, which are basically threads created by browser implemented in C++ to handle async events like DOM events, http request, setTimeout, etc.

> Browser Web APIs- threads created by browser implemented in C++ to handle async events like DOM events, http request, setTimeout, etc.


The Event Loop now is responsible for the execution of these callbacks in the queue and pushing it in the stack, when it is empty 
Event loop basic job is to look both at the stack and the task queue, pushing the first thing on the queue to the stack when it see stack as empty.
Each message or callback is processed completely before any other message is processed.

![Event Loop](https://github.com/codemenow/codemenow.github.io/blob/master/media/js-event-loop.png)
