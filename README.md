# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  SOFTWARE ENGINEERING IMMERSIVE

# JavaScript Data Types
This is the JavaScript lesson.

# Objectives
*After this lesson, students will be able to:*
- Understand what JavaScript is
- Execute JavaScript code
- Understand JavaScript Data Types

# What is JavaScript?

Wikipedia: JavaScript often abbreviated as JS, is a high-level, interpreted programming language that conforms to the ECMAScript specification. It is a language that is also characterized as dynamic, weakly typed, prototype-based and multi-paradigm.

Mozilla: JavaScript (JS) is a lightweight interpreted or JIT-compiled programming language with first-class functions. While it is most well-known as the scripting language for Web pages, many non-browser environments also use it. JavaScript is a prototype-based, multi-paradigm, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles.

# JavaScript Data Types

The latest ECMAScript standard defines seven data types:
- Number
- String
- Boolean
- Null
- Undefined
- Symbol
- Object

# Number Data Type

In other languages, numbers are divided into two classes or objects:

* Integers

  ```javascript
   ..., -1,0, 2, 3, 4, 5, ...
  ```

* Floats (or Decimal numbers)

  ```javascript
   2.718, 3.14, .5, .25, etc
  ```

All numbers in JavaScript are **"double-precision 64-bit format IEEE 754 values"** - read this as "There's really no such thing as an integer in JavaScript."

## Arithmetic Operators

Operators are used to work with data in JavaScript. The standard [arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Arithmetic_operators) - that you've been learning since grade school - are supported, including addition, subtraction, modulus (or remainder) arithmetic and so forth.  Check it out:

```javascript
1 + 2
=> 3

2 - 5
=> -3

5 / 2
=> 2.5

6 * 2
=> 12
```

#### Special Number Operators

JavaScript can be a little cheap with the number of operations it allows you to do. For example, how is someone supposed to square a number or cube a number easily? Luckily there is a special `Math` object with some very useful methods.

 - Taking a number to some `power`? Then just use `Math.pow`

```javascript
// 3^2 becomes
Math.pow(3,2)
=> 9
// 2^4 becomes
Math.pow(2,4)
=> 16
```
  -  Taking a square root

```javascript
// √4 becomes
Math.sqrt(4)
=> 2
```
* Need a `random` number? Then use `Math.random`.

```javascript
// The following only returns a random decimal
Math.random()
=> .229375290430
/**
  The following will return a
  random number between 0 and 10
*/
Math.random()*10
```

* Since Numbers can be **Floats** or **Integers** we often want to get rid of remaining decimal places, which can be done using `Math.floor`, `Math.ceil`, or `Math.round`.

```javascript
// round down to the nearest integer
Math.floor(3.14)
=> 3
Math.floor(3.9999)
=> 3

// round up to the nearest integer
Math.ceil(3.14)
=> 4
Math.ceil(3.9999)
=> 4

// Mathematically round to the nearest integer
Math.round(3.14)
=> 3
Math.round(3.9999)
=> 4
```

# String Data Type

Strings are collections of letters and symbols known as *characters*, and we use them to deal with words and text in JavaScript. Strings are just another type of **value** in Javascript.

There are **three** ways to write a string in JavaScript.
1. Surround a word or phrase with double quotes, 
```
"like this"
```
2. Surround a word or phrase with single quotes, 
```
'like this'
```
3. Surround a word or phrase with backticks (below the tilde key), 
```
`like this`
```

This last version, with backticks, allows you to inject javascript into a string using something called **"string interpolation."**

#### String Interpolation
When you wrap a string with backticks, you can "inject" JavaScript into that string, using the following syntax:

```
const firstName = "Brian"
const age = 33

`My name is ${firstName} and on my next birthday, I will be ${age + 1} years old.`
```

As you can see, string interpolation provides an easy way to inject variables or do basic math or logic functions dynamically.


#### String helper methods

To find the length of a string, access its [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length) property:

```js
'hello'.length;
=> 5
```

There's our first brush with JavaScript objects! Did I mention that you can use strings like objects, too?

Strings have other [methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Methods) as well that allow you to manipulate the string and access information about the string:

```js
'hello'.charAt(0);
=> "h"

'hello, world'.replace('hello', 'goodbye');
=> "goodbye, world"

'hello'.toUpperCase();
=> "HELLO"
```

Types of values like `Number` or `String` are not very useful without being able to form **Expressions** or **Combinations**.

Try your favorite number operators as expressions:

```javascript
  1 + 1
  => 2
  2 - 1
  => 1
```

You can also create expressions with strings using the addition operator:

```javascript
  'Hello, ' + 'world!'
  => "Hello, world!"
```

This is called **String Concatentation.**

> Note: the 'plus' binary operator is said to be "**overloaded**"— meaning that it behaves differently depending on what's on either side of it.
> Consider the following expressions. What do they output, and why?
> `1 + 2 + '3'` vs `'1' + 2 + 3`



#### Converting Strings to Integers with parseInt() and parseFloat()

You can convert a string to an integer using the built-in [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) function. This takes the base for the conversion as an optional second argument, which you should always provide:

```javascript
parseInt('123', 10);
=> 123

parseInt('010', 10);
=> 10
```

This will be important later when we're taking user input from the web and using it on our server or in our browser to do some type of numeric calculation.


Similarly, you can parse floating point numbers using the built-in [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) function which uses base 10 always unlike its `parseInt()` cousin.

```javascript
parseFloat('11.2');
=> 11.2
```

You can also use the unary `+` operator to convert values to numbers:

```javascript
+"42";
=> 42
```

#### NaN

The `parseInt()` and `parseFloat()` functions parse a string until they reach a character that isn't valid for the specified number format, then return the number parsed up to that point. However the "+" operator simply converts the string to `NaN` if there is any invalid character in it.


A special value called [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) (short for "Not a Number") is returned if the string is non-numeric:

```javascript
parseInt('hello', 10);
=> NaN
```

**`NaN` is toxic**: if you provide it as an input to any mathematical operation the result will also be `NaN`:

```javascript
NaN + 5;
=> NaN
```

You can test for `NaN` using the built-in [`isNaN()`](ttps://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN) function:

```js
isNaN(NaN);
=> true
```
JavaScript's numeric operators are `+`, `-`, `*`, `/` and `%` and all work as you expect and should have practiced during your pre-work.

# Boolean Data Type

Boolean represents a logical entity and can have two values: `true`, and `false`.

<img src = "Truth_table_for_AND,_OR,_and_NOT.png">


#### Truthy & Falsey

#### All of the following become false when converted to a Boolean

- `false`
- `0`
- `''` (empty string)
- `NaN`
- `null`
- `undefined`

#### All other values become true when converted to a Boolean

There is a simple way of verifying the truthiness or falsiness of a value. When you add `!` in front of a value, the returned value will be the inverse of the value in a boolean. So if you add two `!` then you'll get the boolean value of the original one:

```javascript
!!1
//=> true

!!0
//=> false

!!-1
//=> true

!![]
//=> true

!!{}
//=> true

!!null
//=> false

!!""
//=> false
```

#### Boolean/Logical Operators

[Logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

Logical operators will always return a boolean value `true` or `false`.

There are two "binary" operators that require two values:

- **AND**, denoted `&&`
- **OR**, denoted `||`

A third "unary" operator requires only one value:

* **NOT**, denoted `!`

#### && (AND)

The `&&` operator requires both left and right values to be `true` in order to return `true`:

```javascript
true && true
//=> true
```

Any other combination is false.

```javascript
true && false
//=> false

false && false
//=> false
```

#### || (OR)

The `||` operator requires just one of the left or right values to be `true` in order to return true.

```javascript
true || false
//=> true

false || true
//=> true

false || false
//=> false
```

Only `false || false` will return `false`

The `!` takes a value and returns the opposite boolean value, i.e.

```javascript
!true
//=> false
```

# Null Data Type

The value null represents the intentional absence of a value.

```javascript
let trigger = null;
```

# Undefined Data Type

A variable that has not been assigned a value has the value undefined.

```javascript
let count;
```

# Symbols Data Type

A Symbol is a unique and immutable primitive value and may be used as the key of an Object property.

# Objects Data Type

Objects are a collection of properties. (We will cover objects in-depth in a later lesson)
