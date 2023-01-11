# #Day21 - Promises in JavaScript: Understanding, Implementing and Overcoming Challenges

# Introduction

Welcome to my 21st blog post on Backend Mastery! In my previous blogs, we talked about using callbacks and an introduction to async programming. Today, we are going to dive deeper into a powerful tool for handling async operations in JavaScript: Promises.

Promises in JavaScript are a special kind of object that represents the completion or failure of an asynchronous operation. They provide a more structured and elegant way to handle async operations, compared to the traditional callback approach.

Promises allow you to write cleaner and more organized code, by avoiding callback hell, a situation where the code becomes unreadable due to the abundance of nested callbacks. Promises also provide a more robust way of handling errors and make it easy to chain async operations together.

In this blog post, we'll take a closer look at Promises. We'll understand the basics of how they work, how to create and use Promises, chaining them together and handling errors in a clean and efficient way. We will also look into the `Promise.all` method which allows you to run multiple promises parallelly.

By the end of this post, you'll have a solid understanding of how to use Promises in your JavaScript applications and how to handle the common pitfalls and challenges that arise when using them.

# The Promise Object

* Creating Promises: Promises are created using the `Promise` constructor. The constructor takes a single argument, a function called the executor. The executor function has two arguments, a resolve function and a reject function. The resolve function is used to indicate that the promise has been fulfilled, while the reject function is used to indicate that the promise has been rejected.
    

```js
const promise = new Promise((resolve, reject) => {
    // some async operation
    if(operationWasSuccessful) {
        resolve(result);
    } else {
        reject(error);
    }
});
```

* Using the Promise object methods (then, catch, finally) Once a promise is created, you can attach callbacks to it using the `then` and `catch` methods. The `then` method is used to attach a callback that will be called when the promise is fulfilled. The `catch` method is used to attach a callback that will be called when the promise is rejected. The `finally` method is called regardless of whether the promise is fulfilled or rejected.
    

```js
promise.then(result => {
    // do something with the result
}).catch(error => {
    // handle the error
}).finally(() => {
    // do something regardless of whether the promise was fulfilled or rejected
});
```

* Examples of the Promise object in action Here's an example that demonstrates how to use the `then` and `catch` methods to handle the fulfillment and rejection of a promise:
    

```js
const myPromise = new Promise((resolve, reject) => {
    setTimeout(() => resolve('Hello World'), 1000);
});

myPromise.then(result => console.log(result))
        .catch(error => console.log(error))
```

In this example, `console.log('Hello World')` is going to be called after one second, because it's wrapped into the resolve function.

Promise object is the fundamental object in javascript which is used to handle async operations.

# Handling Errors

* How Promises handle errors differently than callbacks: Promises provide a more robust way of handling errors than callbacks. With callbacks, errors can easily be missed and can lead to difficult to diagnose bugs. Promises, on the other hand, have a built-in mechanism for handling errors, which makes it easier to detect and fix errors in your code.
    
* Using the catch method: The `catch` method is used to handle errors that occur during the execution of a promise. The `catch` method is called when a promise is rejected. It takes a single argument, a function called the rejection handler. The rejection handler is called with the reason for the rejection.
    

```js
myPromise.then(result => {
    // do something with the result
}).catch(error => {
    // handle the error
});
```

In this example, if the promise is rejected, the function passed to `catch` will be called with the reason for the rejection.

* Best practices for error handling with Promises:
    
    * Always use the `catch` method to handle promise rejections
        
    * Always handle errors as close to the source of the error as possible
        
    * Never swallow errors (i.e. don't silence error messages without logging them or responding to them in some way)
        
    * Use the `finally` method to perform cleanup operations regardless of whether the promise was fulfilled or rejected
        

Handling errors is a critical part of any application, and promises provide a more robust way of handling errors.

# Chaining Promises

* Understanding promise chaining: Promise chaining is the ability to chain multiple promises together. This allows you to execute multiple async operations in a specific order and handle errors more efficiently. Chaining promises is done by returning a promise from the fulfillment handler of a previous promise. The returned promise is then resolved with the result of the returned promise.

```js
promise1.then(result1 => {
    // do something with result1
    return promise2;
}).then(result2 => {
    // do something with result2
});

```

In this example, promise1 is fulfilled first and it returns promise2, which is then fulfilled and passed to the second then method.

* Examples of chaining Promises: Here's an example that demonstrates how to chain multiple promises together:
    
```js

    const promise1 = new Promise((resolve, reject) => {
      setTimeout(() => resolve('Hello '), 1000);
});

const promise2 = new Promise((resolve, reject) =&gt; { setTimeout(() =&gt; resolve('World!'), 2000); });

promise1.then(result1 =&gt; { console.log(result1); return promise2; }).then(result2 =&gt; { console.log(result2); });

```

In this example, `console.log('Hello ')` is going to be called after one second, and `console.log('World!')` is going to be called after two seconds.

- The benefits of chaining Promises: 
  Chaining promises allows you to chain async operations together in a synchronous way, making it easy to read and understand the order of async operations. It also makes it easy to handle errors as close to the source of the error as possible, and it allows for easy reuse of async operations by chaining together smaller async operations into more complex async operations.


# Promise.all

- An introduction to Promise.all: 
  `Promise.all` is a method that allows you to run multiple promises parallelly. It takes an array of promises as an argument and returns a single promise that is fulfilled with an array of the fulfilled values of the original promises. If any of the original promises is rejected, the returned promise is rejected with the reason of the first rejected promise.

```js
Promise.all([promise1, promise2, promise3]).then(result => {
    // do something with the results
}).catch(error => {
    // handle the error
});
```

In this example, `promise1`, `promise2`, and `promise3` will be run parallelly and if all of them gets fulfilled then the `then` method is called with an array of the results.

* Examples of using Promise.all: Here's an example that demonstrates how to use `Promise.all` to run multiple promises parallelly:
    
```js
const promise1 = new Promise((resolve, reject) => {
    setTimeout(() => resolve(1), 1000);
});

const promise2 = new Promise((resolve, reject) => {
    setTimeout(() => resolve(2), 2000);
});

const promise3 = new Promise((resolve, reject) => {
    setTimeout(() => resolve(3), 3000);
});

Promise.all([promise1, promise2, promise3]).then(result => {
    console.log(result);
});
```

In this example, `promise1`, `promise2`, and `promise3` are resolved parallelly and the `then` method is called with an array of the results \[1, 2, 3\].

* Pros and cons of using Promise.all: `Promise.all` can be useful when you need to run multiple promises parallelly and need to wait for all of them to complete before doing something with the results. Some other benefits include the ability to handle multiple promises with a single error handler and not having to nest multiple promises. However, one of the main cons of using `Promise.all` is that it only returns the first rejection and ignores the rest, so if you need to handle multiple rejections, it's not suitable. Also, if you don't need all the promises to complete before proceeding, it's not the best choice since it waits for all the promises to complete.
    

# Conclusion

In this blog post, we've explored the world of Promises in JavaScript, and how they can help you write cleaner and more organized code. We've looked at the basics of how Promises work, how to create and use them, and how to handle errors in a clean and efficient way. We've also seen how to chain promises together and how to use the `Promise.all` method to run multiple promises parallelly.

To summarize, some key points to remember about Promises are:

* Promises are a powerful tool for handling async operations in JavaScript
    
* Promises provide a more structured and elegant way to handle async operations than callbacks
    
* The `then` and `catch` methods can be used to handle the fulfillment and rejection of a promise
    
* Promise chaining allows you to chain async operations together in a synchronous way
    
* The `Promise.all` method allows you to run multiple promises parallelly
    

As a developer, it's important to understand the basics of Promises and the best practices of using them in your code. If you have any questions or if you have examples of using Promises in your own projects, I would love to hear about them in the comments. I hope this blog post has been helpful and informative.

Thank you for reading and being a part of my Backend Mastery blog series. It's been a great journey so far, and I look forward to continuing this journey with you.