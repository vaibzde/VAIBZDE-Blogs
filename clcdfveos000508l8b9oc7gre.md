# #Day12 - Fundamentals of Objects in JavaScript

# Introduction

Objects are a fundamental concept in JavaScript and are used to store data as key-value pairs. They can represent real-world objects and have properties that describe their characteristics and methods that define their behaviour. Just like a smartphone has properties like make, model, and operating system, and methods like making calls and sending text messages, objects in JavaScript can have properties and methods as well.

In this blog post, we'll be covering the basics of objects in JavaScript, including how to create them using object literals, add properties and values, access and modify their properties, delete properties and add methods. We'll also cover how to loop through objects and how to work with JSON. By the end of this post, you'll have a good understanding of how to work with objects in your JavaScript code.

# What is an object in JavaScript?

An object in JavaScript is a data type that can represent a real-world object. It consists of a **collection of key-value pairs**, where the **keys are called properties** and **the values can be any data type, including other objects.**

For example, let's say we want to create an object to represent a smartphone. We could do it like this:

```js
let smartphone = {
  make: "Apple",
  model: "iPhone 12",
  operatingSystem: "iOS 14"
};
```

Here, we've created an object called `smartphone` with three properties: `make`, `model`, and `operatingSystem`. The values of these properties are "Apple", "iPhone 12", and "iOS 14" respectively. The smartphone object also has several methods, such as `makeCalls()` and `sendText()`, that allow it to perform certain actions.

# Declaring an object literal

There are a few different ways to create an object in JavaScript, but the most common is using an object literal. This is simply a set of curly braces `{}` that contain a list of key-value pairs separated by commas.

Here's an example of an object literal that represents a laptop:

```js
let laptop = {
  make: "Apple",
  model: "Macbook Air",
  year: 2020
};
```

# Adding properties and values to an object

You can add properties and values to an object by using the assignment operator `=`. For example, to add a property called `color` to the `laptop` object, you can do the following:

```js
laptop.color = "silver";
```

Or you can use the square bracket notation to add a property:

```js
laptop["screenSize"] = 13.3;
```

# Accessing object properties

There are two ways to access the properties of an object in JavaScript: using the dot notation and the square bracket notation.

To access a property using the dot notation, you can do the following:

```js
console.log(laptop.make); // Outputs "Apple"
```

To access a property using the square bracket notation, you can do the following:

```js
console.log(laptop["model"]); // Outputs "Macbook Air"
```

# Modifying object properties

You can modify the value of an object's property by using the assignment operator `=`. For example, to change the value of the `year` property of the `laptop` object, you can do the following:

```js
laptop.year = 2021;
```

# Adding methods to an object

In addition to properties, objects can also have methods, which are functions that belong to an object. To add a method to an object, you can use the same syntax as adding a property, but the value will be a function.

Here's an example of adding a method to the `laptop` object:

```js
laptop.turnOn = function() {
  console.log("The laptop is turning on");
};
```

You can then call the method like this:

```js
laptop.turnOn(); // Outputs "The laptop is turning on"
```

# Looping through objects

There are a few different ways to loop through the properties of an object in JavaScript. Here are a few common methods:

## for...in

The `for...in` loop iterates over the properties of an object and is often used for this purpose. Here's an example of using a `for...in` loop to loop through the properties of the `laptop` object:

```js
for (let key in laptop) {
  console.log(`${key}: ${laptop[key]}`);
}
```

This will output each property and its value, like this:

```javascript
make: Apple
model: Macbook Air
year: 2021
color: Silver
screenSize: 13.3
turnOn:
```

## Object.keys()

The `Object.keys()` method returns an array of the object's own enumerable property names. Here's an example of using `Object.keys()` to loop through the properties of the `laptop` object:

```js
let keys = Object.keys(laptop);

for (let i = 0; i < keys.length; i++) {
  console.log(`${keys[i]}: ${laptop[keys[i]]}`);
}
```

This will output the same result as the `for...in` loop above.

## Object.entries()

The `Object.entries()` method returns an array of the object's own enumerable property entries, in the form of \[key, value\] pairs. Here's an example of using `Object.entries()` to loop through the properties of the `laptop` object:

```js
let entries = Object.entries(laptop);

for (let i = 0; i < entries.length; i++) {
  console.log(`${entries[i][0]}: ${entries[i][1]}`);
}
```

This will also output the same result as the `for...in` loop above.

## Object.values()

The `Object.values()` method returns an array of the object's own enumerable property values. Here's an example of using `Object.values()` to loop through the values of the `laptop` object:

```js
let values = Object.values(laptop);

for (let i = 0; i < values.length; i++) {
  console.log(values[i]);
}
```

This will output the values of the `laptop` object's properties:

```javascript
Apple
Macbook Air
2021
silver
13.3
```

## Object.assign()

The `Object.assign()` method is used to copy the values of all enumerable own properties from one or more source objects to a target object. It returns the target object. Here's an example of using `Object.assign()` to copy the properties of the `laptop` object to a new object called `newLaptop`:

```js
let newLaptop = Object.assign({}, laptop);
```

# Deleting properties in Object

You can remove a non-inherited property using the `delete` operator. The following code shows how to remove a property.

To delete a property from the `laptop` object, we can use the `delete` operator followed by the property we want to delete. For example, to delete the `color` property, we can do the following:

```js
console.log(laptop)
//output
/*
{ make: "Apple", 
model: "Macbook Air", 
year: 2021, 
color: "silver", 
screenSize: 13.3 }
*/
delete laptop.color;
console.log(laptop)
```

After deleting the `color` property, the `laptop` object will look like this:

```javascript
{
  make: "Apple",
  model: "Macbook Air",
  year: 2021,
  screenSize: 13.3
}
```

It's important to note that the `delete` operator only works on object properties and not on variables.

Deleting object properties can be useful in certain situations, such as when you want to remove unnecessary or outdated data from an object. However, be careful when using the `delete` operator, as it can have unintended consequences, such as deleting properties from the prototype chain of an object.

# JSON - (JavaScript Object Notation)

JSON (JavaScript Object Notation) is a text-based data interchange format that is used to represent simple data structures and objects in JavaScript. It is commonly used for exchanging data between a server and a web application. JSON is based on the JavaScript object literal syntax, but it is strictly a data format and does not contain any of the JavaScript code that objects contain.

Here's an example of a JSON object:

```js
{
  "make": "Apple",
  "model": "Macbook Air",
  "year": 2021,
  "color": "silver",
  "screenSize": 13.3
}
```

To convert a JavaScript object to JSON, you can use the `JSON.stringify()` method. For example:

```js
let laptopJSON = JSON.stringify(laptop);
```

To convert a JSON string to a JavaScript object, you can use the `JSON.parse()` method. For example:

```js
let laptop = JSON.parse(laptopJSON);
```

#### Conclusion

In this blog post, we've covered the basics of objects in JavaScript, including how to create them using object literals, add properties and values, access and modify their properties, deleting properties and add methods. We've also discussed how to loop through objects using various methods and how to work with JSON. With this knowledge, you should now be able to work with objects in your JavaScript code with confidence.

> Thankyou for reading the blog.. :)