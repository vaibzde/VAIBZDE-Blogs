# #Day05 - Understanding and using different Operators in JavaScript

Welcome to day five of our blogging series on back-end development! In yesterday's session, we covered the basics of variables and data types in JavaScript. Today, we will delve deeper into the world of JavaScript by exploring the operators in JavaScript.

So, let's dive in!

# Operators in JavaScript

An operator is a special symbol that performs a specific task on one or more operands and returns a result. An operand is a value that the operator is applied to.

For example, in the following expression:

```js
5 + 3
```

The `+` symbol is the operator, and the values `5` and `3` are the operands. The operator `+` performs the operation of addition on the operands `5` and `3`, and the result is `8`.

In JavaScript, an operator can be used to perform a wide range of tasks, such as arithmetic calculations, comparisons, and assignments. The operands can be variables, constants, or expressions.

## Types of operators in javascript

There are various types of operators in javascript

* Increment/Decrement operators: `a++, --a`,
    
* Unary operators: `typeof, +, !`
    
* Arithmetic operators: `+, -, /, *`
    
* Comparison operators: `>, <, >=, <= , !=, ===, !==`
    
* Assignment operators: `+=, -=, /=, *=`
    

### Increment/Decrement Operators

The increment operator (`++`) increments (adds one to) its operand and returns a value. For example:

```js
let x = 5;
console.log(x++); // Output: 5
console.log(x); // Output: 6
```

In the code above, the first `console.log` statement prints the value of `x` before it is incremented, while the second `console.log` statement prints the value of `x` after it is incremented.

The decrement operator (`--`) decrements (subtracts one from) its operand and returns a value. For example:

```js
let y = 10;
console.log(y--); // Output: 10
console.log(y); // Output: 9
```

Like the increment operator, the decrement operator can be used either before (prefix) or after (postfix) the operand. If used postfix, with the operator after the operand (for example, `x--`), the decrement operator decrements the operand and returns the value before decrementing. If used prefix, with the operator before the operand (for example, `--x`), the decrement operator decrements the operand and returns the value after decrementing.

### Unary Operators

Unary operators are operators that perform an operation on a single operand. There are several unary operators available in JavaScript, including:

1. `typeof`: This operator returns a string indicating the type of the operand. For example: \`\`\`js let x = 5; console.log(typeof x); // Output: "number"
    

let y = "hello"; console.log(typeof y); // Output: "string"

let z; console.log(typeof z); // Output: "undefined"

````javascript

2.  `+`: This operator attempts to convert a value into a number if it isn't already a number. For example:
```js
console.log(+"5"); // Output: 5
console.log(+true); // Output: 1
console.log(+false); // Output: 0
````

1. `!`: This operator converts truthy values to falsy and vice versa. For example: \`\`\`js console.log(!true); // Output: false console.log(!false); // Output: true console.log(!5); // Output: false console.log(!0); // Output: true
    

````javascript

#### Falsy Values

In JavaScript, there are certain values that are considered "falsy," which means that they are evaluated as false when used in a boolean context. These values include:

-   0
-   0n (BigInt)
-   null
-   undefined
-   NaN
-   false
-   "" (empty string)

All other values are considered "truthy," which means they are evaluated as true when used in a boolean context. It's important to keep in mind that only these specific values are considered falsy in JavaScript, and all other values are truthy.

### Arithmetic Operators in JavaScript

JavaScript has a number of arithmetic operators that allow you to perform basic mathematical operations on numbers. These operators include:

| Operator | Description |
|----------|-------------|
| `+`      | Addition    |
| `-`      | Subtraction |
| `*`      | Multiplication |
| `**`     | Exponentiation (ES2016) |
| `/`      | Division |
| `%`      | Modulus (Division Remainder) |

Let's look at some examples of how these operators can be used:

```JS
let x = 10;
let y = 5;

console.log(x + y); // Output: 15
console.log(x - y); // Output: 5
console.log(x * y); // Output: 50
console.log(x ** y); // Output: 100000
console.log(x / y); // Output: 2
console.log(x % y); // Output: 0
````

In this example, we have declared two variables `x` and `y` and used the arithmetic operators to perform various calculations. The `+` operator is used to add `x` and `y`, the `-` operator is used to subtract `y` from `x`, and so on.

It's important to note that the `**` operator is a new addition to JavaScript, and is used to calculate the exponentiation of a number. The `%` operator is the modulus operator, which returns the remainder of a division operation.

### Comparison Operators in JavaScript

JavaScript has a number of comparison operators that allow you to compare values and determine whether they are equal, greater than, or less than each other. These operators include:

| Operator | Description |
| --- | --- |
| `==` | Equal to |
| `===` | Equal value and equal type |
| `!=` | Not equal |
| `!==` | Not equal value or not equal type |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |
| `?` | Ternary operator |

Let's look at some examples of how these operators can be used:

```js
// Comparison Operators in JavaScript

let x = 10;
let y = "10";

console.log(x == y); // Output: true because x and y have the same value, even though they have different types
console.log(x === y); // Output: false because x and y have different types in addition to having different values
console.log(x != y); // Output: false because x and y have the same value
console.log(x !== y); // Output: true because x and y have different types in addition to having different values
console.log(x > y); // Output: false because x is not greater than y
console.log(x < y); // Output: false because x is not less than y
console.log(x >= y); // Output: true because x is equal to y
console.log(x <= y); // Output: true because x is equal to y

let z = x > y ? "x is greater" : "y is greater";
console.log(z); // Output: "x is greater"
```

here is a test table

| Test | Result |
| --- | --- |
| 1 + 1 | 2 |
| 2 - 1 | 1 |
| 2 \* 2 | 4 |
| 2 \*\* 3 | 8 |
| 10 / 5 | 2 |
| 10 % 3 | 1 |

### Assignment Operators in JavaScript

JavaScript has a number of assignment operators that allow you to assign values to variables. These operators include:

| Operator | Description | Example | Same As |
| --- | --- | --- | --- |
| `=` | Assigns a value to a variable | `x = y` | `x = y` |
| `+=` | Adds a value to a variable and assigns the result to the variable | `x += y` | `x = x + y` |
| `-=` | Subtracts a value from a variable and assigns the result to the variable | `x -= y` | `x = x - y` |
| `*=` | Multiplies a variable by a value and assigns the result to the variable | `x *= y` | `x = x * y` |
| `/=` | Divides a variable by a value and assigns the result to the variable | `x /= y` | `x = x / y` |
| `%=` | Calculates the remainder when a variable is divided by a value and assigns the result to the variable | `x %= y` | `x = x % y` |
| `**=` | Calculates the exponentiation of a variable by a value and assigns the result to the variable | `x **= y` | `x = x ** y` |

Let's look at some examples of how these operators can be used:

```js
let x = 10;
let y = 5;

x = y;
console.log(x); // Output: 5

x += y;
console.log(x); // Output: 10

x -= y;
console.log(x); // Output: 5

x *= y;
console.log(x); // Output: 25

x /= y;
console.log(x); // Output: 5

x %= y;
console.log(x); // Output: 0

x **= y;
console.log(x); // Output: 0
```

### Logical Operators in JavaScript

JavaScript has three logical operators that allow you to perform logical operations on boolean values (values of true or false). These operators are:

| Operator | Description |
| --- | --- |
| `&&` | Logical and |
| `!` | Logical not |

\`|| - Logical or

Let's look at some examples of how these operators can be used:

```js
console.log(true && true); // Output: true
console.log(true && false); // Output: false
console.log(false && true); // Output: false
console.log(false && false); // Output: false

console.log(true || true); // Output: true
console.log(true || false); // Output: true
console.log(false || true); // Output: true
console.log(false || false); // Output: false

console.log(!true); // Output: false
console.log(!false); // Output: true
```

The `&&` operator returns true if both operands are true, and false otherwise. The `||` operator returns true if either operand is true, and false otherwise. The `!` operator negates the boolean value of its operand, returning the opposite value.

By using these logical operators, you can perform complex logical operations in your JavaScript code and make decisions based on the results.

## Operator Precedence in JavaScript

Operator precedence determines the order in which operations are performed in an expression. In JavaScript, some operators have higher precedence than others, meaning they will be evaluated first. For example, in the expression `3 + 4 * 5`, the multiplication operator `*` has higher precedence than the addition operator `+`, so the multiplication is performed first, resulting in the value `20`.

It's important to understand operator precedence when writing expressions in JavaScript, as it can affect the result of the expression if not used correctly. You can use parentheses `( )` to override the default precedence and specify the order in which operations should be performed.

Here is a table of the operator precedence in JavaScript, from highest to lowest:

| Operator | Description |
| --- | --- |
| `()` `[]` `.` `new` | Parentheses, array element, property access, and object creation |
| `!` `~` `++` `--` `+` `-` `typeof` `void` | Logical not, bitwise not, increment, decrement, unary plus, unary minus, typeof, void |
| `**` | Exponentiation (ES2016) |
| `*` `/` `%` | Multiplication, division, modulus |
| `+` `-` | Addition, subtraction |
| `<<` `>>` `>>>` | Bitwise left shift, bitwise right shift, bitwise right shift with zero fill |
| `<` `<=` `>` `>=` | Less than, less than or equal to, greater than, greater than or equal to |
| `==` `!=` `===` `!==` | Equal to, not equal to, equal value and equal type, not equal value or not equal type |
| `&` | Bitwise and |
| `^` | Bitwise xor |
| \` | \` |
| `&&` | Logical and |
| \` |  |
| `?` | Ternary operator (conditional) |
| `=` `+=` `-=` `*=` `/=` `%=` `**=` | Assignment |
| `yield` | Yield (generators) |
| `,` | Comma |

Let us understand the operator precedence with some example -

```js
// example1:
let x = 5;
let y = 10;
let result = x + ++y;
console.log(result); // Output: 16
// In this example, the unary plus operator (++) has higher precedence than the addition operator (+)
// The unary plus operator is applied to y first, so y becomes 11
// Then, x + y is evaluated as 5 + 11, which is 16

// example2:
x = 5;
y = 10;
result = x ** 2 * y;
console.log(result); // Output: 250
// In this example, the exponentiation operator (**) has higher precedence than the multiplication operator (*)
// The exponentiation operator is applied to x first, so x becomes 25
// Then, x * y is evaluated as 25 * 10, which is 250

// example3:
x = 5;
y = 10;
result = "Result: " + x + y;
console.log(result); // Output: "Result: 15"
// In this example, the addition operator (+) and the concatenation operator (++) have the same precedence
// Operators with the same precedence are evaluated from left to right
// In this case, the addition operator is applied to x + y first, resulting in 15
// Then, the concatenation operator is applied to "Result: " and 15, resulting in "Result: 15"
```

# Conclusion

In conclusion, operators are an essential part of programming in JavaScript and are used to perform various operations on variables and values. There are various types of operators, including arithmetic, assignment, comparison, and logical operators. Understanding the different types of operators and their precedence is crucial for writing correct and efficient code.

In this blog, we covered each type of operator in detail and provided examples to illustrate their usage and behavior. We also discussed operator precedence, which determines the order in which operators are evaluated in an expression. By understanding operator precedence, you can use parentheses to specify the order of evaluation and ensure that your code behaves as intended.

I hope this series on operators in JavaScript has been helpful for you and has deepened your understanding of this important topic. Thank you for following along with the 50-day blog series on mastering Backend Development.