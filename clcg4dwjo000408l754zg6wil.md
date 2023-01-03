# #Day14 - Object-Oriented Programming in JavaScript

# Introduction to Object-Oriented Programming in JavaScript

Welcome to the world of object-oriented programming (OOP)! OOP is a way of writing code that's organized, reusable, and easy to understand. It's like building with LEGOs: you have different "blocks" (called "objects") that represent real-world things or abstract concepts, and you can snap these blocks together to create all sorts of cool projects.

In this post, we'll be discussing the principles of OOP in JavaScript. These principles guide how you use OOP to build your projects, and include concepts like encapsulation (hiding details from the outside world), abstraction (focusing on the important things), inheritance (reusing code from other objects), and polymorphism (creating multiple objects that have the same interface). We'll also be exploring how to implement these principles in JavaScript, using techniques like the class syntax, prototypal inheritance, and design patterns.

So if you want to learn more about OOP in JavaScript, and how to use it to build amazing projects, this post is for you! Let's get started!

# Principles of Object-Oriented Programming in JavaScript

Object-oriented programming (OOP) is all about organizing your code into "objects" that represent real-world things or abstract concepts. These objects have their own properties and behaviours, and they communicate with each other through methods. OOP follows some principles to guide how these objects are designed and used in code. Here are the four main principles of OOP:

* Encapsulation: Imagine each object as a little "capsule" that keeps its properties and behaviours safe inside. Encapsulation is the process of hiding the details of an object's properties and behaviours from the outside world so that you can't accidentally change them in ways you didn't mean to. In JavaScript, you can create "private" properties and methods that can only be accessed or modified by the object itself, using a trick called "symbols".
    
* Abstraction: Abstraction is all about focusing on the most important things and ignoring the rest. In OOP, you can create "interfaces" that define the essential characteristics and behaviors of an object, without worrying about how those characteristics and behaviors are actually implemented. This lets you think about the big picture of what your object does, rather than getting bogged down in the details. In JavaScript, you can create an interface by using a simple object literal with no implementation details.
    
* Inheritance: Inheritance is the process of creating a subclass that "inherits" properties and behaviors from a parent class. This is a way to save time and avoid repeating yourself, by creating a new object that is based on an existing object, and then adding or changing things as needed. In JavaScript, you can use the `extends` keyword to create a subclass that inherits from a parent class. The subclass can access and use the properties and methods of the parent class, and you can use the `super` keyword to call the parent class's constructor and access its methods and properties.
    
* Polymorphism: Polymorphism is the process of creating multiple objects that have the same interface, but different implementations. This is a way to create a "family" of related objects that all do similar things but in their own way. In OOP, you can use "method overloading" to create multiple methods with the same name, but different arguments. You can also use "method overriding" to create a method in a subclass that has the same name and arguments as a method in the parent class, but different implementation. In JavaScript, you can use function overloading and method overriding to achieve polymorphism.
    

By understanding and applying these principles of OOP in JavaScript, you can create code that is well-structured, easy to understand, and easy to reuse. OOP allows you to model real-world things and abstract concepts in a way that makes sense to you, which can make your code more intuitive and expressive.

# Class Syntax

In JavaScript, classes are a way to create objects and define their characteristics and behaviors using a syntax that is similar to other object-oriented languages. To define a class, you use the `class` keyword followed by the name of the class, like this:

```js
class Smartphone {
  constructor(manufacturer, model, storage) {
    this.manufacturer = manufacturer;
    this.model = model;
    this.storage = storage;
  }

  getInfo() {
    return `${this.manufacturer} ${this.model} with ${this.storage}GB storage`;
  }
}
```

The `constructor` function is a special method that is called when an object is created from the class. It is used to initialize the object's properties. In the example above, the `Smartphone` class has three properties: `manufacturer`, `model`, and `storage`.

To create an object from a class, you use the `new` operator followed by the name of the class and the arguments for the constructor function, like this:

```js
const iPhone14 = new Smartphone('Apple', 'iPhone 14', 128);
```

This creates a new `Smartphone` object with the specified manufacturer, model, and storage values. You can then access the object's properties and methods using the dot notation, like this:

```js
console.log(iPhone14.manufacturer); // Outputs "Apple"
console.log(iPhone14.getInfo()); // Outputs "Apple iPhone 14 with 128GB storage"
```

Inheritance is a way to create a subclass that inherits properties and methods from a parent class. To create a subclass in JavaScript, you use the `extends` keyword followed by the name of the parent class, like this:

```js
class iPhone14Pro extends Smartphone {
  constructor(storage) {
    super('Apple', 'iPhone 14 Pro', storage);
  }
}
```

The `super` keyword is used to call the parent class's constructor function. In the example above, the `iPhone14Pro` class is a subclass of the `Smartphone` class that has a fixed manufacturer and model but allows the storage to be specified when the object is created.

Here's an example of how to create an object from the `iPhone14Pro` class:

```js
const myPhone = new iPhone14Pro(256);
console.log(myPhone.getInfo()); // Outputs "Apple iPhone 14 Pro with 256GB storage"
```

# Prototypal Inheritance

In JavaScript, objects can inherit from other objects through a mechanism called prototypal inheritance. This is different from classical inheritance, which is found in languages like Java and C++, where inheritance is based on classes and a hierarchy of class inheritance is used to define the relationships between objects.

In JavaScript, all objects have a `prototype` property that refers to another object. When you access a property or method of an object, the JavaScript engine first checks the object itself for that property or method. If it can't find it, it looks at the object's prototype, and then at the prototype's prototype, and so on, until it reaches the end of the prototype chain. This allows objects to inherit properties and methods from their prototypes, rather than from a class.

You can use the `Object.create()` method to create an object that inherits from another object. The `Object.create()` method takes an object as an argument and creates a new object with that object as its prototype. For example:

```js
const smartphonePrototype = {
  getInfo() {
    return `${this.manufacturer} ${this.model} with ${this.storage}GB storage`;
  }
};

const iPhone14 = Object.create(smartphonePrototype, {
  manufacturer: { value: 'Apple' },
  model: { value: 'iPhone 14' },
  storage: { value: 128 }
});

console.log(iPhone14.getInfo()); // Outputs "Apple iPhone 14 with 128GB storage"
```

In the example above, the `smartphonePrototype` object is the prototype for the `iPhone14` object. The `iPhone14` object has its own properties (`manufacturer`, `model`, and `storage`) that are defined using the `Object.defineProperty()` method. The `getInfo()` method, however, is inherited from the `smartphonePrototype` object.

Prototypal inheritance is a powerful and flexible feature of JavaScript that allows you to create objects that inherit from other objects, rather than from classes. It is especially useful when you want to create objects that share common properties and methods, but also have some differences.

# Design Patterns

Design patterns are proven solutions to common programming problems that can be applied to different contexts and languages. In object-oriented programming, design patterns are used to define the relationships between objects, as well as the ways in which those objects communicate and collaborate with each other.

There are many different design patterns that can be used in object-oriented programming, but some of the most common ones are:

* Singleton pattern: This pattern ensures that a class has only one instance and provides a global point of access to that instance.
    
* Factory pattern: This pattern defines an interface for creating an object, but lets subclasses decide which class to instantiate.
    
* Observer pattern: This pattern defines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.
    

# Conclusion

In this post, we covered some of the key concepts and techniques for implementing object-oriented programming in JavaScript. We looked at the class syntax, which is a modern way of creating objects and defining their characteristics and behaviors. We also discussed prototypal inheritance, which is a unique feature of JavaScript that allows objects to inherit from other objects. Finally, we introduced design patterns, which are proven solutions to common programming problems that can be applied to OOP in JavaScript.

Object-oriented programming is an important concept in JavaScript, as it allows you to organize and reuse code in a logical and modular way. By understanding these concepts and techniques, you can improve the structure and maintainability of your JavaScript code.

> Thankyou! for reading :)