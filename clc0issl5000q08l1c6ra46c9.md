# #Day03 - An Introduction to JavaScript: Features, Uses, and Setting Up a Development Environment

🚀 Are you ready to dive into the exciting world of programming? 💻 In this blog, we'll take a deep dive into the versatile programming language JavaScript and learn how to get started with running code on your own system. We'll even write our very first line of code together! 💪 Whether you're a complete beginner or looking to brush up on your skills, this blog is the perfect place to start your journey.

Before we dive into the world of JavaScript and learn about its role in back-end programming, let's take a moment to understand why we choose to use this powerful language.

# Why use Javascript?

There are plenty of good reasons to consider learning Javascript.

* 🌟 JavaScript is used on the front end of every website to create the UI.
    
* 💡 While it is possible to use other languages to create the UI, they ultimately get translated into JavaScript for the browser to execute.
    
* 🤓 By learning JavaScript, you can become a full-stack developer without the need to learn any additional languages.
    
* 💻 JavaScript can be used to create desktop apps with frameworks like Electron and React Native Desktop.
    
* 📱 JavaScript can also be used to create Android and iOS apps using React Native.
    
* 🚀 Learning JavaScript opens up a wide range of possibilities and sets you up for success as a developer.
    

# What is JavaScript?

Simply put, Javascript is a programming language that helps you write  
instructions that a computer, to be more specific, a browser can understand.

  
Javascript was primarily used to be executed on browsers, but then NodeJS  
was created, which can help execute Javascript on your machine outside the  
browser.

And characteristics wise -

> **Javascript is a single-threaded, synchronous, high-level, interpreted programming language.**

Hey, But what does that mean, exactly?  
Let's see..

* 🧵 Single-threaded means that JavaScript can only execute one task at a time. In other words, it cannot break up a program into smaller sub-programs and execute them in parallel. Think of it like a rope with a single thread running through it.
    
* 📈 Synchronous means that the code is executed in the order in which it appears. This means that the program cannot skip certain lines of code and come back to them later. However, JavaScript does have mechanisms for performing asynchronous tasks, such as web APIs, which allow it to do multiple things at once.
    
* 🤓 A high-level programming language is one that is more human-readable and easier for people to understand, as opposed to being more machine-readable. This means that code written in a high-level language is often more concise and easier to read and write than code written in a low-level language.
    
* 💾 An interpreted programming language is one that is not compiled (translated) into machine code before it is executed. Instead, the code is interpreted by a program called an interpreter at runtime, which reads and executes the code. This means that interpreted languages are generally easier to write and debug, but they can also be slower to run than compiled languages.
    

Ok, now. Ready to start coding? Here's how to run JavaScript on your system

# How to Run JavaScript Code in your System

There are two main ways to run JavaScript code on your own system:

## Method 1: Running JavaScript in a Browser

Using the console of a web browser: Most modern web browsers come with a built-in JavaScript console that allows you to run and test your code directly from the browser.

I recommend using the **Mozilla Firefox Developer Edition**. This browser includes a multiline console that makes it easy to write and test your code

* Go to the following link to install the Mozilla Firefox Developer Edition: [**https://www.mozilla.org/en-US/firefox/developer/**](https://www.mozilla.org/en-US/firefox/developer/)
    
* Once the browser is installed, open it and press F12 or right-click and select "Inspect."
    
* In the developer tools window of the Mozilla Firefox browser, open the dev-tools window in a "separate window", select the "console" tab, write your code in the code panel on the left side, and click the "Run" button to see the output in the console on the right side.
    

## Method2: Running JS in VS Code using NodeJS

If you are developing a web application and want to run JavaScript code on your system, one of the best methods is to use Visual Studio Code (VS Code). VS Code is a popular code editor, and it makes it easy to write and run JavaScript code.

Using Node.js: Node.js is a runtime environment that allows you to run JavaScript on your own computer, outside of a web browser.

To set up VS Code and Node.js on your system and run JavaScript code:

1. Download and install VS Code from the official website ([**https://code.visualstudio.com/download**](https://code.visualstudio.com/download)).
    
2. Download and install Node.js from the official website ([**https://nodejs.org/en/download/**](https://nodejs.org/en/download/)).
    
3. After installing Node.js, you will need to add the path to the "bin" folder to your system's environment variables.
    

After installing Visual Studio Code (VS Code) and Node.js, open VS Code, create a new file with the ".js" extension in a folder, and you're ready to start programming in JavaScript

# Writing Your First Line of JS Code

Now that you know how to run JavaScript code on your own system,

let's write our first line of code together! In this example, we will use the console of a web browser to print the message And click on ‘Run’  
You should see ‘Hello world’ on your console. to the screen.

To do this, open the console in your web browser or in VS Code and type the following code:

```javascript
console.log("Namaste World");
```

And click on ‘Run’

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671798423206/88e906e1-411b-45d8-a40d-65d859b5a8cf.png align="center")

You should see **Namaste World** on your console.

> **🎉🎉🎉 Congratulations on running your first code in JavaScript! 🎉🎉🎉**

Now let’s understand the line of code.

The console.log() function is a built-in function in JavaScript that allows you to print messages to the console. You can pass any type of data to the function, including strings, numbers, and variables. In this case, we passed a string to the function by enclosing it in quotation marks.

Note that you can use single quotes or double quotes or backticks *to define a string* in JavaScript. For example, the following code will produce the same result

```javascript
console.log("Namaste World");    //using single quotes
console.log('Namaste World');    //using single quotes
console.log(`Namaste World`);    //Using template literals (backticks)
```

Don't forget to try out the different ways to print messages to the console using console.log() and practice writing code in your browser or using VS Code. And be sure to tune in for the next class where we will cover even more exciting topics in JavaScript!

# Conclusion

JavaScript is a versatile and widely-used programming language that is essential for creating user interfaces for websites and for building desktop and mobile apps. It is single-threaded, synchronous, high-level, and interpreted, and it can be run in a browser using the console or in a development environment using a text editor and the Node.js runtime. Whether you are a complete beginner or looking to brush up on your skills, learning JavaScript is a great way to open up a wide range of possibilities and set yourself up for success as a developer.!