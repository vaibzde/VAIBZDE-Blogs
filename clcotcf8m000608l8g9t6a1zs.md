# #Day20 - Exploring Callbacks in JavaScript: A Primer for Asynchronous Programming

Welcome to the 20th instalment of our blog series on exploring callbacks in JavaScript, a primer for asynchronous programming. In this blog post, we will be diving deep into the world of callbacks, covering everything you need to know about how they work and how to use them in your own projects.

Callbacks are a fundamental concept in JavaScript and are an essential tool for handling asynchronous actions. They are functions that are passed as arguments to other functions and are called when a certain event or task has been completed.

In this post, we will be exploring the ins and outs of callbacks. By the end of this post, you should have a solid understanding of how callbacks work and how to use them in your own JavaScript projects.

# CallBacks

Callbacks are a fundamental concept in JavaScript and are used to handle asynchronous actions. A callback function is simply a function that is passed as an argument to another function and is executed after some event or task has been completed.

For example:

```js
function greet(name, callback) {
  console.log(`Hello, ${name}!`);
  callback();
}

function sayGoodbye() {
  console.log('Goodbye!');
}

// pass the sayGoodbye function as a callback to greet
greet('John', sayGoodbye);
```

In this example, we have a `greet` function that takes a name and a callback function as arguments. The `greet` function logs a greeting to the console and then invokes the callback function. We also have a separate `sayGoodbye` function that simply logs a goodbye message to the console.

When we call the `greet` function and pass in `'John'` and the `sayGoodbye` function as arguments, the `greet` function is executed first, logging `'Hello, John!'` to the console. The callback function, `sayGoodbye`, is then invoked and logs `'Goodbye!'` to the console.

This example illustrates how a callback function is passed to an outer function and is invoked to perform its operation at a later time. It's important to note that callbacks should be implemented asynchronously to prevent blocking the event loop in the JavaScript engine.

### Connecting the Call Stack and Callbacks

The call stack is an important concept to understand when working with callbacks in JavaScript. It is a data structure that keeps track of the current function being executed and the functions that called it.

When a function is called, it is added to the top of the call stack. The function is then executed, and when it completes, it is removed from the top of the call stack. This process continues until the call stack is empty.

Here's an example of how the call stack works with a simple callback function:

```js
function performAction(callback) {
  console.log('Starting action...');
  callback();
  console.log('Action completed.');
}

function sayHello() {
  console.log('Hello!');
}

performAction(sayHello);
```

In this example, we have a `performAction` function that takes a callback function as an argument. The `performAction` function logs a message to the console, then invokes the callback function. After the callback function is executed, another message is logged to the console.

We also have a separate `sayHello` function that simply logs a hello message to the console. When we call the `performAction` function and pass in the `sayHello` function as an argument, the `performAction` function is executed first.

The `performAction` function logs `'Starting action...'` to the console, then invokes the `sayHello` callback function. The `sayHello` function is then executed, logging `'Hello!'` to the console. Finally, the `performAction` function logs `'Action completed.'` to the console.

This example illustrates how a callback function is passed to an outer function and is invoked to perform its operation at a later time. It also shows how the call stack plays a role in the execution of callback functions, with the `performAction` function being added to the top of the call stack first, followed by the `sayHello` function.

The call stack plays an important role in the execution of callback functions, as it determines the order in which functions are executed and helps keep track of the current function being executed

### The Callback Queue

The callback queue is a data structure that stores callback functions that are waiting to be executed. Unlike the call stack, which executes functions in a Last In, First Out (LIFO) manner, the callback queue follows a First In, First Out (FIFO) pattern.

When a callback function is invoked, it is not immediately added to the call stack for execution. Instead, it is listed in the Web API and the result of the callback is stored in the callback queue.

Once the call stack is empty, the callback queue is checked for any ready callback functions. If there are any, they are removed from the queue and added to the call stack for execution. This process continues until the callback queue is empty.

The purpose of the callback queue is to ensure that callback functions are executed in the correct order, even if they are invoked at different times. It is an important part of the JavaScript event loop, which handles the execution of async actions in the language.

# Callbacks with Async example

```js
console.log('Hi'); // logs "Hi"

function callback() {
  console.log('Welcome to Grandline'); // logs "Welcome to Grandline"
}

setTimeout(callback, 2000); // waits 2 seconds before executing the callback function

console.log('Join our Pirate Crew & be our Nakama'); // logs "Join our Pirate Crew & be our Nakama"
```

In the above example, we are using the `setTimeout` function, which is a Web API function that waits for a specified amount of time (in this case, 2000 milliseconds or 2 seconds) before executing a callback function.

Here's how the example works:

1. The global execution context is created and the first line of code, `console.log('Hi')`, is executed.
    
2. The function definition for `callback` is created and stored in memory, but it is not yet executed.
    
3. The `setTimeout` function is called with a timer of 2000 milliseconds and the `callback` function as a parameter. The `callback` function is registered in the Web API, but it will not be executed until the timer has expired and the call stack is empty.
    
4. The `console.log('Join our Pirate Crew & be our Nakama')` line is executed.
    
5. After 2 seconds have passed, the `callback` function is pushed onto the call stack and executed. It logs `Welcome to Grandline`.
    
6. The `callback` function is popped off the call stack and the execution context is ended.
    

It's important to note that callback functions can be nested, meaning a callback function can be called within another callback function. In this case, the nested callback functions will be placed in a queue and executed in a first-in-first-out (FIFO) order.

### Callback hell

Callback hell is a term used to describe situations where callback functions are nested within other callback functions, resulting in a pyramid-like structure of code that can be difficult to read and understand. This can happen when using callback functions to handle asynchronous operations, especially if there are multiple asynchronous operations that depend on each other.

Here is an example of code that could be considered callback hell:

```js
doTask1(function(result1) {
  doTask2(result1, function(result2) {
    doTask3(result2, function(result3) {
      doTask4(result3, function(result4) {
        doTask5(result4, function(result5) {
          // continue with more tasks and nested callbacks...
        });
      });
    });
  });
});
```

As you can see, the code becomes increasingly indented as the number of nested callback functions increases, making it hard to read and follow the flow of execution. This can make it difficult to debug the code and understand what is happening at each step.

To avoid callback hell, it can be helpful to use other programming constructs such as promises or async/await, which can make asynchronous code easier to read and understand.

# Timers in JS

Timers are a fundamental concept in programming, and learning how to use them is essential for any programmer. In Javascript, there are two Timing Events that allow you to execute a certain block of code after a certain time interval:

* **setTimeout(function, milliseconds, arg1, arg2, ...)**: This function executes a given function after a specified number of milliseconds. The function and arguments are optional, so you can pass them as null if you don't need to execute a function or pass any arguments. The syntax is as follows:
    

```js
setTimeout(function, milliseconds, arg1, arg2, ...);
```

Here is an example that uses setTimeout

```js
function sayHello() {
  console.log('Hello, World!');
}

console.log('Before setTimeout');
setTimeout(sayHello, 2000);
console.log('After setTimeout');
// Output: "Before setTimeout", "After setTimeout", "Hello, World!" (after a 2 second delay)
```

**setlnterval(function, milliseconds, arg1, arg2, ...)**: This function executes a given function repeatedly, with a fixed time interval between each execution. The function and arguments are optional, just like in setTimeout. The syntax is as follows:

```js
setlnterval(function, milliseconds, arg1, arg2, ...);
```

You can stop the execution of setTimeout or setlnterval by using the following functions:

* **clearTimeout(timeoutId)**: This function cancels the execution of setTimeout, using the id of the timeout that you want to cancel. The syntax is as follows:
    

```js
clearTimeout(timeoutId);
```

* **clearlnterval(intervalId)**: This function cancels the execution of setlnterval, using the id of the interval that you want to cancel. The syntax is as follows:
    

```js
clearlnterval(intervalId);`
```

> In both examples, the timeout ID or interval ID is returned by the `setTimeout` or `setInterval` function and can be used to cancel the timer or interval using the `clearTimeout` or `clearInterval` function.

example of using setInterval and clearInterval with setTimeout

```js
let count = 0;

function sayHello() {
  console.log(`Hello, World! ${count}`);
  count++;
}

console.log('Before setInterval');
const intervalID = setInterval(sayHello, 1000);
console.log('After setInterval');
// Output: "Before setInterval", "After setInterval", "Hello, World! 0" (after a 1 second delay), "Hello, World! 1" (after a 1 second delay), "Hello, World! 2" (after a 1 second delay), ...

// stop the interval after 5 iterations
setTimeout(() => {
  clearInterval(intervalID);
}, 5000);
```

# Conclusion

In conclusion, callbacks are an essential tool for handling asynchronous actions in JavaScript. They are functions that are passed as arguments to other functions and are executed after some event or task has been completed. Understanding how callbacks work and how to use them can greatly improve your ability to write efficient and effective code. I hope that this blog series has provided you with a solid foundation in callbacks and that you are now able to confidently use them in your own projects. Thank you for following along with our series, and I hope you will continue to join us for more programming discussions in the future.

If you enjoyed this post, please give it a like and feel free to share your thoughts and comments below. We always appreciate hearing from our readers and value your feedback.