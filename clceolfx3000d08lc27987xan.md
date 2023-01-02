# #Day13 - Advanced Concepts and Methods for Objects in JavaScript

# Introduction

In our previous blog, we covered the basics of objects in JavaScript, including object literals, properties, methods, looping through objects, and more. In this blog, we will discuss about some of the more advanced concepts and methods related to objects in JavaScript. These include the `Object.create()` method for creating objects, the use of the `this` keyword in objects, various object functions such as `Object.freeze()` and `Object.seal()`, object destructuring, getters and setters, and more. By the end of this blog, I hope you should have a solid understanding of these advanced concepts and be well on your way to becoming a proficient JavaScript developer.

# Using the `this` Keyword in Objects

The `this` keyword in JavaScript refers to the object that is currently executing the code. In the context of objects, `this` can be used to refer to the object's properties and methods.

To use `this` in an object's properties, you can simply refer to the property by name as you would any other variable. For example:

```js
const obj = {
  name: "Vaibhav",
  greet: function() {
    console.log(`Hello, my name is ${this.name}.`);
  }
};
```

Here, the `greet()` method uses `this` to refer to the `name` property of the `obj` object.

To use `this` in an object's methods, the `this` keyword simply refers to the object that the current function is called on. In the following example, `this` is used in the `greet()` and `changeName()` methods of the `obj` object:

```js
const obj = {
  name: "Vaibhav", // this is the name property of the obj object
  greet: function() { // this is a method of the obj object
    console.log(`Hello, my name is ${this.name}.`); // this refers to the name property of the obj object
  },
  changeName: function(newName) { // this is a method of the obj object
    this.name = newName; // this refers to the name property of the obj object and sets it to the value of newName
  }
};
```

In the `greet()` method, [`this.name`](http://this.name) refers to the `name` property of the `obj` object and outputs it to the console. In the `changeName()` method, [`this.name`](http://this.name) refers to the `name` property of the `obj` object and sets it to the value of the `newName` argument.

Using `this` in this way allows you to access and modify the properties and methods of the object that the current function is called on. It is a useful feature of JavaScript that allows you to write more flexible and reusable code.

# Creating Objects with the `Object.create()` Method

In JavaScript, there are several ways to create objects. One of these is the `Object.create()` method. This method allows you to create an object that has a specified *prototype* and includes properties and methods that you define.

In simple terms, a prototype is a model or template that is used as the basis for creating new objects. In object-oriented programming, prototypes are used to create inheritance relationships between objects, allowing one object to inherit properties and methods from another object.. We will be discussing it in our OOPS blog..

So, to use the `Object.create()` method, you can pass in an object that serves as the prototype for the new object, and define the properties and methods of the new object as properties of the object passed to the `Object.create()` method.

Here is an example of using the `Object.create()` method to create a new object based on a prototype:

```js
const person = {
  name: "",
  age: 0,
  occupation: "",
  introduce: function() {
    console.log(`Hi, my name is ${this.name}, I am ${this.age} years old, and I am a ${this.occupation}.`);
  }
};

function createPerson(name, age, occupation) {
  const newPerson = Object.create(person);
  newPerson.name = name;
  newPerson.age = age;
  newPerson.occupation = occupation;
  return newPerson;
}

const vaibhav = createPerson("Vaibhav", 23, "software engineering student");
vaibhav.introduce(); // Outputs: "Hi, my name is Vaibhav, I am 23 years old, and I am a software engineering student."
```

In this example, we have defined a function called `createPerson()` that takes three arguments: `name`, `age`, and `occupation`. The function uses the `Object.create()` method to create a new object based on the `person` prototype, and sets the `name`, `age`, and `occupation` properties of the new object to the values of the arguments passed to the function. The function then returns the new object.

We can then use the `createPerson()` function to create a new object called `vaibhav` with the desired property values, and call the inherited `introduce()` method on the object to output a string introducing `vaibhav`.

Using the `Object.create()` method is a useful way to create new objects and establish inheritance relationships between them in JavaScript. It allows for a clear separation of the prototype and the object itself, and provides a convenient way to set the initial values for the properties of the new object..

# Object Functions: `Object.freeze()`, `Object.seal()`, `Object.isSealed()`, `Object.isFrozen()`

JavaScript provides several object functions that allow you to control the behavior of objects in various ways. These functions include `Object.freeze()`, `Object.seal()`, `Object.isSealed()`, and `Object.isFrozen()`.

The `Object.freeze()` function freezes an object, which means that it prevents new properties from being added to the object and marks all existing properties as non-configurable. This means that you cannot delete or modify the properties of a frozen object. In addition, if the object has any data properties (as opposed to accessor properties), these are marked as read-only.

The `Object.seal()` function seals an object, which means that it prevents new properties from being added to the object and marks all existing properties as non-configurable. However, unlike with `Object.freeze()`, you can still modify the values of the properties of a sealed object.

The `Object.isSealed()` function returns a boolean value indicating whether an object is sealed. Similarly, the `Object.isFrozen()` function returns a boolean value indicating whether an object is frozen.

Here is an example of using these object functions:

```js
const obj = {
  name: "Aryan"
};

Object.seal(obj);
console.log(Object.isSealed(obj)); // outputs true

obj.age = 30;
console.log(obj.age); // undefined

obj.name = "Rahul";
console.log(obj.name); // "Jane"

Object.freeze(obj);
console.log(Object.isFrozen(obj)); // outputs true

obj.name = "John";
console.log(obj.name); // "Rahul"
```

In this example, we first create an object called `obj` with a single property called `name`. We then seal the object using the `Object.seal()` function. We verify that the object is sealed using the `Object.isSealed()` function, which returns `true`. We then try to add a new property called `age` to the object, but this fails because the object is sealed. However, we are able to modify the value of the `name` property because the object is only sealed, not frozen.

We then freeze the object using the `Object.freeze()` function and verify that it is frozen using the `Object.isFrozen()` function. Finally, we try to modify the value of the `name` property again, but this fails because the object is now frozen.

# Object Destructuring

Object destructuring is a feature of JavaScript that allows you to extract values from objects and assign them to variables. This can be useful when you want to extract specific values from an object and use them in your code.

To destructure an object, you use an object pattern on the left side of an assignment. The object pattern consists of a set of variables enclosed in curly braces, each followed by a colon and the name of a property in the object. For example:

```js
const obj = {
  name: "Vaibhav",
  age: 23
};

const { name, age } = obj;

console.log(name); // "Vaibhav"
console.log(age); // 23
```

In this example, we have destructured the `obj` object by extracting the `name` and `age` properties and assigning them to the variables `name` and `age`, respectively.

### Using Default Values

One advantage of object destructuring is that you can set default values for properties that are not present in the object. To do this, you can use the equal sign (=) followed by a default value. For example:

```js
const obj = {
  name: "Vaibhav"
};

const { name, age = 30 } = obj;

console.log(name); // "Vaibhav"
console.log(age); // 30
```

In this example, we have set a default value of `30` for the `age` property. If the `age` property is not present in the `obj` object, it will be set to the default value of `30`

### Combining Array and Object Destructuring

You can also combine array and object destructuring to extract values from both arrays and objects at the same time. For example:

```js
const arr = ["Vaibhav", 23]
const obj = {
  name: "Vaibhav",
  age: 23
};
//To combine array and object destructuring, you can use an object pattern on the left side of the destructuring expression and an array pattern on the right side

const { name: n, age } = obj;
const [a, b] = arr;
console.log(n); // "Vaibhav"
console.log(age); // 23
console.log(a); // "Vaibhav"
console.log(b); // 23
```

In this example, we have used an object pattern to destructure the `obj` object and an array pattern to destructure the `arr` array. This allows us to extract values from both the object and the array into variables.

### Object Destructuring in Nested Objects

Object destructuring can also be used to extract values from nested objects. To do this, you can use object patterns with multiple levels of nesting. For example:

```js
const obj = {
  name: {
    first: "Vaibhav",
    last: "Dewangan"
  },
  age: 23
};

const { name: { first, last }, age } = obj;

console.log(first); // "Vaibhav"
console.log(last); // "Dewangan"
console.log(age); // 23
```

In this example, we have destructured the `obj` object to extract the `first` and `last` properties from the `name` object, as well as the `age` property.

### Rest in Object Destructuring

The rest operator can be used in object destructuring to extract all remaining properties of an object into a new object. To use the rest operator in object destructuring, you include three dots followed by an object pattern.

For example:

```js
const obj = {
  name: "Vaibhav",
  age: 23,
  occupation: "student"
};

const { name, ...rest } = obj;

console.log(name); // "Vaibhav"
console.log(rest); // { age: 23, occupation: "student" }
```

In this example, we have destructured the `obj` object and extracted the `name` property into a separate variable. The rest operator is used to extract all remaining properties (`age` and `occupation`) into a new object called `rest`.

The rest operator can be useful when you want to extract a few properties from an object but also keep the remaining properties together in a separate object.

# Getters and Setters

Getters and setters are special methods that allow you to define a function to be called when a property of an object is accessed or modified. These methods are useful for implementing computed properties, as well as for performing additional logic when a property is accessed or modified.

To define a getter method, you use the `get` keyword followed by a function. The function does not take any arguments, but it can use the `this` keyword to refer to the object that the getter is defined on. For example:

```js
const obj = {
  _name: "Aryan",
  get name() {
    return this._name;
  }
};

console.log(obj.name); // "Aryan"
```

In this example, we have defined a getter method called `name` that returns the value of the `_name` property of the `obj` object.

To define a setter method, you use the `set` keyword followed by a function. The function takes a single argument, which represents the value being set. Like with getters, you can use the `this` keyword to refer to the object that the setter is defined on. For example: \`\`\`js const obj = { *name: "Aryan",* age: 21, get name() { return this.\_name; }, set name(newName) { this.\_name = newName; } };

[obj.name](http://obj.name) = "Rahul"; console.log([obj.name](http://obj.name)); // "Rahul" \`\`\`

In this example, we have defined a setter method called `name` that sets the value of the `_name` property of the `obj` object to the value passed to the setter.

The advantages of using getters and setters in JavaScript:

* Implement computed properties
    
* Perform additional logic when a property is accessed or modified
    
* Enhance the readability of code
    
* Improve encapsulation of object implementation details
    

Keep in mind that it is important to use getters and setters judiciously, as overusing them can make your code more difficult to understand and maintain.

# Conclusion

In this blog, we covered several advanced concepts and methods related to objects in JavaScript. These include the `Object.create()` method for creating objects, the use of the `this` keyword in objects, various object functions such as `Object.freeze()` and `Object.seal()`, object destructuring, getters and setters, and more. By understanding these concepts and methods, you are well on your way to becoming a proficient JavaScript developer.

As always, it is important to practice these concepts in order to fully master them. I recommend trying out the examples in this blog and experimenting with these concepts on your own to get a better understanding of how they work.

> Happy coding!