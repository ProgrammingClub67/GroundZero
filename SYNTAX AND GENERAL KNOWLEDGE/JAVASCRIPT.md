
# JavaScript Syntax Reference

> A comprehensive guide to JavaScript for ProgrammingClub67

---

## Table of Contents

1. [Variables](#1-variables)
2. [Data Types](#2-data-types)
3. [Operators](#3-operators)
4. [Strings](#4-strings)
5. [Numbers](#5-numbers)
6. [Arrays](#6-arrays)
7. [Objects](#7-objects)
8. [Conditionals](#8-conditionals)
9. [Loops](#9-loops)
10. [Functions](#10-functions)
11. [Scope and Closures](#11-scope-and-closures)
12. [Array Methods](#12-array-methods)
13. [Object Methods](#13-object-methods)
14. [Destructuring](#14-destructuring)
15. [Spread and Rest](#15-spread-and-rest)
16. [Classes](#16-classes)
17. [Error Handling](#17-error-handling)
18. [Promises and Async](#18-promises-and-async)
19. [DOM Manipulation](#19-dom-manipulation)
20. [Events](#20-events)
21. [Fetch API](#21-fetch-api)
22. [LocalStorage](#22-localstorage)
23. [Modules](#23-modules)
24. [Useful Built-ins](#24-useful-built-ins)
25. [Common Patterns](#25-common-patterns)

---

## 1. Variables

```js
// var — old way, avoid it
var name = "Alice";

// let — can be reassigned
let age = 20;
age = 21;

// const — cannot be reassigned
const PI = 3.14;
const club = "ProgrammingClub67";

// const with objects/arrays — the variable can't be reassigned
// but the contents CAN be changed
const user = { name: "Alice" };
user.name = "Bob"; // this is fine

const nums = [1, 2, 3];
nums.push(4); // this is fine
```

Rules of thumb:
- Use `const` by default
- Use `let` when you know the value will change
- Never use `var`

---

## 2. Data Types

```js
// String
let name = "Alice";
let greeting = 'Hello';
let template = `Hello, ${name}`;

// Number
let age = 25;
let price = 9.99;
let negative = -10;

// Boolean
let isLoggedIn = true;
let hasError = false;

// Null — intentional absence of value
let data = null;

// Undefined — variable declared but not assigned
let result;
console.log(result); // undefined

// BigInt — very large integers
let bigNum = 9007199254740991n;

// Symbol — unique identifier
let id = Symbol("id");

// Object
let user = { name: "Alice", age: 25 };

// Array
let colors = ["red", "green", "blue"];

// Function
function greet() {
  return "Hello!";
}

// Checking types
typeof "hello"        // "string"
typeof 42             // "number"
typeof true           // "boolean"
typeof undefined      // "undefined"
typeof null           // "object" (a known JS quirk)
typeof {}             // "object"
typeof []             // "object"
typeof function(){}   // "function"

// Better array check
Array.isArray([1, 2, 3]); // true
```

---

## 3. Operators

```js
// Arithmetic
5 + 3   // 8
5 - 3   // 2
5 * 3   // 15
5 / 2   // 2.5
5 % 2   // 1  (remainder)
5 ** 2  // 25 (exponent)

// Assignment
let x = 10;
x += 5;   // x = 15
x -= 3;   // x = 12
x *= 2;   // x = 24
x /= 4;   // x = 6
x **= 2;  // x = 36
x %= 5;   // x = 1

// Increment / Decrement
x++;  // x = x + 1 (after)
++x;  // x = x + 1 (before)
x--;  // x = x - 1
--x;

// Comparison
5 == "5"   // true  (loose, converts types)
5 === "5"  // false (strict, checks type too)
5 != "5"   // false
5 !== "5"  // true
5 > 3      // true
5 < 3      // false
5 >= 5     // true
5 <= 4     // false

// Always use === and !== in your code

// Logical
true && true   // true  (AND)
true && false  // false
true || false  // true  (OR)
false || false // false
!true          // false (NOT)

// Nullish coalescing — use right side if left is null/undefined
let username = null ?? "Guest";  // "Guest"
let score = 0 ?? 100;            // 0 (0 is not null/undefined)

// Optional chaining — safely access nested properties
let city = user?.address?.city;  // undefined instead of error
let first = arr?.[0];            // undefined if arr is null
let result = obj?.method?.();    // undefined if method doesn't exist

// Ternary operator
let status = age >= 18 ? "adult" : "minor";

// Short-circuit evaluation
let name = user && user.name;       // name if user exists
let display = name || "Anonymous";  // "Anonymous" if name is falsy
```

---

## 4. Strings

```js
let str = "Hello, World!";

// Length
str.length; // 13

// Access characters
str[0];         // "H"
str.at(-1);     // "!" (last character)

// Case
str.toUpperCase();  // "HELLO, WORLD!"
str.toLowerCase();  // "hello, world!"

// Trim whitespace
"  hello  ".trim();        // "hello"
"  hello  ".trimStart();   // "hello  "
"  hello  ".trimEnd();     // "  hello"

// Check content
str.includes("World");       // true
str.startsWith("Hello");     // true
str.endsWith("!");           // true
str.indexOf("World");        // 7
str.lastIndexOf("l");        // 10

// Slice
str.slice(0, 5);    // "Hello"
str.slice(-6);      // "orld!"
str.slice(7, 12);   // "World"

// Replace
str.replace("World", "Club");        // "Hello, Club!"
str.replaceAll("l", "L");            // "HeLLo, WorLd!"

// Split into array
"a,b,c".split(",");     // ["a", "b", "c"]
"hello".split("");      // ["h", "e", "l", "l", "o"]

// Join
["hello", "world"].join(" ");  // "hello world"

// Repeat
"ha".repeat(3);  // "hahaha"

// Pad
"5".padStart(3, "0");  // "005"
"5".padEnd(3, "0");    // "500"

// Template literals
let name = "Alice";
let age = 25;
let msg = `Hello, ${name}! You are ${age} years old.`;
let math = `2 + 2 = ${2 + 2}`;
let multiline = `
  Line one
  Line two
  Line three
`;

// String to number
Number("42");       // 42
parseInt("42px");   // 42
parseFloat("3.14"); // 3.14
+"42";              // 42 (unary + operator)

// Number to string
String(42);         // "42"
(42).toString();    // "42"
(3.14159).toFixed(2); // "3.14"
```

---

## 5. Numbers

```js
let n = 42;
let f = 3.14;

// Math methods
Math.round(4.6);    // 5
Math.floor(4.9);    // 4
Math.ceil(4.1);     // 5
Math.abs(-10);      // 10
Math.max(1, 5, 3);  // 5
Math.min(1, 5, 3);  // 1
Math.pow(2, 10);    // 1024
Math.sqrt(16);      // 4
Math.cbrt(27);      // 3
Math.log(Math.E);   // 1
Math.log2(8);       // 3
Math.log10(1000);   // 3
Math.trunc(4.9);    // 4 (removes decimal)
Math.sign(-5);      // -1
Math.sign(5);       // 1
Math.sign(0);       // 0

// Random
Math.random();               // 0 to 0.999...
Math.floor(Math.random() * 10);       // 0 to 9
Math.floor(Math.random() * 10) + 1;  // 1 to 10

// Constants
Math.PI;    // 3.141592653589793
Math.E;     // 2.718281828459045

// Number methods
(1234567).toLocaleString();   // "1,234,567"
(3.14159).toFixed(2);         // "3.14"
(0.000123).toExponential(2);  // "1.23e-4"

// Number checks
Number.isInteger(42);         // true
Number.isInteger(42.5);       // false
Number.isFinite(Infinity);    // false
Number.isNaN(NaN);            // true
Number.isNaN("hello");        // false (better than global isNaN)

// Special values
Infinity;
-Infinity;
NaN;  // Not a Number — result of invalid math
```

---

## 6. Arrays

```js
// Create
let fruits = ["apple", "banana", "cherry"];
let nums = [1, 2, 3, 4, 5];
let mixed = [1, "hello", true, null];
let empty = [];
let filled = new Array(3).fill(0); // [0, 0, 0]

// Access
fruits[0];       // "apple"
fruits[2];       // "cherry"
fruits.at(-1);   // "cherry" (last)
fruits.at(-2);   // "banana" (second to last)

// Length
fruits.length;   // 3

// Add items
fruits.push("date");          // add to end
fruits.unshift("avocado");    // add to start
fruits.splice(2, 0, "mango"); // insert at index 2

// Remove items
fruits.pop();                 // remove from end
fruits.shift();               // remove from start
fruits.splice(1, 1);          // remove 1 item at index 1
fruits.splice(1, 2);          // remove 2 items at index 1

// Find
fruits.indexOf("banana");     // 1 (index or -1)
fruits.includes("apple");     // true
fruits.find(x => x > 3);      // first match
fruits.findIndex(x => x > 3); // index of first match

// Slice — returns new array, does not modify original
fruits.slice(1, 3);   // items at index 1 and 2
fruits.slice(-2);     // last 2 items
fruits.slice(1);      // from index 1 to end

// Join
fruits.join(", ");    // "apple, banana, cherry"
fruits.join("");      // "applebananacherry"

// Reverse and sort
fruits.reverse();     // reverses in place
fruits.sort();        // sorts alphabetically in place
nums.sort((a, b) => a - b);  // sort numbers ascending
nums.sort((a, b) => b - a);  // sort numbers descending

// Spread to copy
let copy = [...fruits];
let combined = [...fruits, ...nums];

// Check
Array.isArray(fruits);  // true
```

---

## 7. Objects

```js
// Create
let user = {
  name: "Alice",
  age: 25,
  isAdmin: false,
  address: {
    city: "Accra",
    country: "Ghana"
  }
};

// Access
user.name;            // "Alice"
user["name"];         // "Alice"
user.address.city;    // "Accra"
user?.address?.city;  // "Accra" (safe)

// Add / update
user.email = "alice@example.com";
user["age"] = 26;

// Delete
delete user.isAdmin;

// Check if property exists
"name" in user;              // true
user.hasOwnProperty("name"); // true

// Keys, values, entries
Object.keys(user);    // ["name", "age", "address"]
Object.values(user);  // ["Alice", 26, {...}]
Object.entries(user); // [["name","Alice"], ["age",26], ...]

// Spread to copy/merge
let copy = { ...user };
let merged = { ...user, role: "member", age: 30 };

// Shorthand property (when variable name matches key)
let name = "Alice";
let age = 25;
let person = { name, age }; // same as { name: name, age: age }

// Computed property names
let key = "score";
let obj = { [key]: 100 }; // { score: 100 }

// Methods inside objects
let calculator = {
  value: 0,
  add(n) {
    this.value += n;
    return this;
  },
  subtract(n) {
    this.value -= n;
    return this;
  }
};
```

---

## 8. Conditionals

```js
// if / else if / else
let score = 75;

if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else if (score >= 70) {
  console.log("C");
} else {
  console.log("F");
}

// Ternary
let grade = score >= 50 ? "Pass" : "Fail";

// Nested ternary (keep simple)
let level = score >= 90 ? "A" : score >= 70 ? "B" : "C";

// Switch
let day = "Monday";

switch (day) {
  case "Monday":
  case "Tuesday":
  case "Wednesday":
  case "Thursday":
  case "Friday":
    console.log("Weekday");
    break;
  case "Saturday":
  case "Sunday":
    console.log("Weekend");
    break;
  default:
    console.log("Unknown");
}

// Falsy values — these are all false in conditions
false
0
""
null
undefined
NaN

// Truthy — everything else, including
1
"hello"
[]
{}
```

---

## 9. Loops

```js
// for loop
for (let i = 0; i < 5; i++) {
  console.log(i); // 0 1 2 3 4
}

// for...of — iterate over arrays, strings
let fruits = ["apple", "banana", "cherry"];

for (let fruit of fruits) {
  console.log(fruit);
}

for (let char of "hello") {
  console.log(char);
}

// for...in — iterate over object keys
let user = { name: "Alice", age: 25 };

for (let key in user) {
  console.log(key, user[key]);
}

// while loop
let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}

// do...while — runs at least once
let input;
do {
  input = prompt("Enter a number:");
} while (isNaN(input));

// forEach — runs a function for each array item
fruits.forEach((fruit, index) => {
  console.log(index, fruit);
});

// break — exit loop early
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // 0 1 2 3 4
}

// continue — skip current iteration
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // 0 1 3 4
}
```

---

## 10. Functions

```js
// Function declaration — hoisted (can call before definition)
function greet(name) {
  return `Hello, ${name}!`;
}

greet("Alice"); // "Hello, Alice!"

// Function expression — not hoisted
const greet = function(name) {
  return `Hello, ${name}!`;
};

// Arrow function — shorter syntax
const greet = (name) => `Hello, ${name}!`;
const double = n => n * 2;
const add = (a, b) => a + b;
const getUser = () => ({ name: "Alice" }); // wrap object in ()

// Multi-line arrow function
const greet = (name) => {
  let msg = `Hello, ${name}!`;
  return msg;
};

// Default parameters
function greet(name = "Guest") {
  return `Hello, ${name}!`;
}

greet();         // "Hello, Guest!"
greet("Alice");  // "Hello, Alice!"

// Rest parameters — collects extra arguments into array
function sum(...nums) {
  return nums.reduce((total, n) => total + n, 0);
}

sum(1, 2, 3, 4); // 10

// Returning multiple values (via array or object)
function getMinMax(arr) {
  return {
    min: Math.min(...arr),
    max: Math.max(...arr)
  };
}

const { min, max } = getMinMax([3, 1, 4, 1, 5]);

// Immediately Invoked Function Expression (IIFE)
(function() {
  console.log("Runs immediately!");
})();

// Higher-order functions — functions that take/return functions
function applyTwice(fn, value) {
  return fn(fn(value));
}

applyTwice(x => x * 2, 3); // 12

// Callback functions
function doSomething(callback) {
  console.log("Doing something...");
  callback();
}

doSomething(() => console.log("Done!"));
```

---

## 11. Scope and Closures

```js
// Global scope
let globalVar = "I am global";

function example() {
  // Local/function scope
  let localVar = "I am local";
  console.log(globalVar); // accessible
  console.log(localVar);  // accessible
}

console.log(globalVar); // accessible
// console.log(localVar); // ERROR — not accessible

// Block scope — let and const
{
  let blockVar = "block";
  const blockConst = "block";
  var notBlock = "not block"; // var ignores block scope!
}
// blockVar and blockConst not accessible here
// notBlock IS accessible here (another reason to avoid var)

// Closure — a function that remembers its outer scope
function makeCounter() {
  let count = 0;

  return function() {
    count++;
    return count;
  };
}

const counter = makeCounter();
counter(); // 1
counter(); // 2
counter(); // 3

// Practical closure — private data
function createUser(name) {
  let loginCount = 0;

  return {
    getName: () => name,
    login: () => {
      loginCount++;
      return `${name} logged in. Total logins: ${loginCount}`;
    }
  };
}

const user = createUser("Alice");
user.login(); // "Alice logged in. Total logins: 1"
user.login(); // "Alice logged in. Total logins: 2"
```

---

## 12. Array Methods

```js
let nums = [1, 2, 3, 4, 5];
let users = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 17 },
  { name: "Charlie", age: 30 }
];

// map — transform each item, returns new array
nums.map(n => n * 2);               // [2, 4, 6, 8, 10]
users.map(u => u.name);             // ["Alice", "Bob", "Charlie"]
users.map(u => ({ ...u, id: Math.random() }));

// filter — keep items that pass test, returns new array
nums.filter(n => n > 3);            // [4, 5]
users.filter(u => u.age >= 18);     // [Alice, Charlie]

// find — first item that passes test
users.find(u => u.name === "Bob");  // { name: "Bob", age: 17 }

// findIndex — index of first match
users.findIndex(u => u.age > 20);   // 0

// some — true if at least one passes
nums.some(n => n > 4);              // true
users.some(u => u.age < 18);        // true

// every — true if all pass
nums.every(n => n > 0);             // true
users.every(u => u.age >= 18);      // false

// reduce — accumulate to single value
nums.reduce((total, n) => total + n, 0);      // 15 (sum)
nums.reduce((max, n) => n > max ? n : max, 0); // 5 (max)

// flat — flatten nested arrays
[1, [2, 3], [4, [5, 6]]].flat();    // [1, 2, 3, 4, [5, 6]]
[1, [2, [3, [4]]]].flat(Infinity);  // [1, 2, 3, 4]

// flatMap — map then flat(1)
[[1,2],[3,4]].flatMap(x => x);      // [1, 2, 3, 4]

// forEach — runs a function, returns nothing
nums.forEach(n => console.log(n));

// includes
nums.includes(3);  // true

// indexOf
nums.indexOf(3);   // 2

// Chaining methods
users
  .filter(u => u.age >= 18)
  .map(u => u.name)
  .sort();
// ["Alice", "Charlie"]
```

---

## 13. Object Methods

```js
let user = { name: "Alice", age: 25, role: "admin" };

// Keys, values, entries
Object.keys(user);    // ["name", "age", "role"]
Object.values(user);  // ["Alice", 25, "admin"]
Object.entries(user); // [["name","Alice"], ["age",25], ["role","admin"]]

// Merge objects
let defaults = { theme: "light", lang: "en" };
let settings = { lang: "fr", fontSize: 16 };
let merged = Object.assign({}, defaults, settings);
// { theme: "light", lang: "fr", fontSize: 16 }

// Spread merge (preferred)
let merged2 = { ...defaults, ...settings };

// Freeze — prevents modification
Object.freeze(user);
user.name = "Bob"; // silently fails

// fromEntries — array of pairs to object
let entries = [["name", "Alice"], ["age", 25]];
Object.fromEntries(entries); // { name: "Alice", age: 25 }

// Practical: transform object values
let prices = { apple: 1.5, banana: 0.5, cherry: 2.0 };
let doubled = Object.fromEntries(
  Object.entries(prices).map(([key, val]) => [key, val * 2])
);
// { apple: 3, banana: 1, cherry: 4 }
```

---

## 14. Destructuring

```js
// Array destructuring
let [a, b, c] = [1, 2, 3];
// a=1, b=2, c=3

let [first, , third] = [1, 2, 3]; // skip second
let [x = 10, y = 20] = [5];       // defaults: x=5, y=20
let [head, ...tail] = [1, 2, 3, 4]; // head=1, tail=[2,3,4]

// Swap variables
let p = 1, q = 2;
[p, q] = [q, p]; // p=2, q=1

// Object destructuring
let { name, age } = { name: "Alice", age: 25, role: "admin" };
// name="Alice", age=25

// Rename while destructuring
let { name: userName, age: userAge } = user;

// Default values
let { name, score = 0 } = { name: "Alice" }; // score=0

// Nested destructuring
let { address: { city, country } } = {
  address: { city: "Accra", country: "Ghana" }
};

// Rest in destructuring
let { name, ...rest } = { name: "Alice", age: 25, role: "admin" };
// name="Alice", rest={ age: 25, role: "admin" }

// In function parameters
function greet({ name, age = 0 }) {
  return `${name} is ${age}`;
}

greet({ name: "Alice", age: 25 });

// Destructuring in loops
let users = [{ name: "Alice" }, { name: "Bob" }];

for (let { name } of users) {
  console.log(name);
}
```

---

## 15. Spread and Rest

```js
// Spread — expand iterable into individual elements

// Copy array
let arr = [1, 2, 3];
let copy = [...arr];

// Merge arrays
let merged = [...arr, 4, 5, ...[6, 7]];

// Pass array as function arguments
Math.max(...arr); // same as Math.max(1, 2, 3)

// Copy object
let obj = { a: 1, b: 2 };
let objCopy = { ...obj };

// Merge objects
let merged2 = { ...obj, c: 3, b: 99 }; // b is overridden

// Spread string into array
[..."hello"]; // ["h", "e", "l", "l", "o"]

// Rest — collect multiple values into one

// In functions
function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
sum(1, 2, 3, 4); // 10

// In destructuring
let [first, second, ...others] = [1, 2, 3, 4, 5];
// first=1, second=2, others=[3,4,5]

let { a, ...remaining } = { a: 1, b: 2, c: 3 };
// a=1, remaining={ b: 2, c: 3 }
```

---

## 16. Classes

```js
// Define a class
class Animal {
  // constructor runs when new Animal() is called
  constructor(name, sound) {
    this.name = name;
    this.sound = sound;
  }

  // Method
  speak() {
    return `${this.name} says ${this.sound}`;
  }

  // Static method — called on class, not instance
  static create(name, sound) {
    return new Animal(name, sound);
  }
}

// Create instances
let dog = new Animal("Dog", "Woof");
let cat = new Animal("Cat", "Meow");

dog.speak(); // "Dog says Woof"
Animal.create("Bird", "Tweet");

// Inheritance
class Dog extends Animal {
  constructor(name) {
    super(name, "Woof"); // call parent constructor
    this.tricks = [];
  }

  learn(trick) {
    this.tricks.push(trick);
    return this;
  }

  showTricks() {
    return `${this.name} knows: ${this.tricks.join(", ")}`;
  }
}

let rex = new Dog("Rex");
rex.learn("sit").learn("shake").learn("roll over");
rex.showTricks(); // "Rex knows: sit, shake, roll over"
rex.speak();      // "Rex says Woof" (inherited)

// Getters and setters
class User {
  constructor(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }

  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  }

  set fullName(value) {
    [this.firstName, this.lastName] = value.split(" ");
  }
}

let user = new User("Alice", "Smith");
user.fullName;          // "Alice Smith"
user.fullName = "Bob Jones";
user.firstName;         // "Bob"

// Private fields (modern JS)
class BankAccount {
  #balance = 0; // private

  deposit(amount) {
    this.#balance += amount;
  }

  get balance() {
    return this.#balance;
  }
}
```

---

## 17. Error Handling

```js
// try / catch / finally
try {
  let result = riskyFunction();
  console.log(result);
} catch (error) {
  console.error("Something went wrong:", error.message);
} finally {
  console.log("This always runs");
}

// Throw a custom error
function divide(a, b) {
  if (b === 0) throw new Error("Cannot divide by zero");
  return a / b;
}

try {
  divide(10, 0);
} catch (e) {
  console.log(e.message); // "Cannot divide by zero"
}

// Error types
new Error("generic error");
new TypeError("wrong type");
new RangeError("value out of range");
new ReferenceError("variable not defined");
new SyntaxError("bad syntax");

// Check error type
try {
  null.property;
} catch (e) {
  if (e instanceof TypeError) {
    console.log("Type error!");
  }
}

// Custom error class
class ValidationError extends Error {
  constructor(message, field) {
    super(message);
    this.name = "ValidationError";
    this.field = field;
  }
}

throw new ValidationError("Required", "email");
```

---

## 18. Promises and Async

```js
// Promise — represents a future value
let promise = new Promise((resolve, reject) => {
  let success = true;

  if (success) {
    resolve("It worked!");
  } else {
    reject("It failed!");
  }
});

// .then / .catch / .finally
promise
  .then(result => console.log(result))
  .catch(error => console.error(error))
  .finally(() => console.log("Done"));

// Promise.all — wait for all promises
Promise.all([fetch("/api/users"), fetch("/api/posts")])
  .then(([users, posts]) => {
    console.log(users, posts);
  });

// Promise.allSettled — all promises, even if some fail
Promise.allSettled([p1, p2, p3])
  .then(results => results.forEach(r => console.log(r.status)));

// Promise.race — first to finish wins
Promise.race([p1, p2]).then(first => console.log(first));

// async / await — cleaner way to work with promises
async function getUser(id) {
  try {
    let response = await fetch(`/api/users/${id}`);
    let user = await response.json();
    return user;
  } catch (error) {
    console.error("Failed to get user:", error);
  }
}

// Calling an async function
getUser(1).then(user => console.log(user));

// Or inside another async function
async function main() {
  let user = await getUser(1);
  console.log(user);
}

// Parallel async calls
async function loadData() {
  let [users, posts] = await Promise.all([
    fetch("/api/users").then(r => r.json()),
    fetch("/api/posts").then(r => r.json())
  ]);

  return { users, posts };
}
```

---

## 19. DOM Manipulation

```js
// Select elements
document.getElementById("myId");
document.querySelector(".myClass");       // first match
document.querySelectorAll(".myClass");    // all matches (NodeList)
document.querySelector("h1");
document.querySelector("#nav > li");

// Traverse
element.parentElement;
element.children;
element.firstElementChild;
element.lastElementChild;
element.nextElementSibling;
element.previousElementSibling;

// Read / write content
element.textContent = "New text";
element.innerHTML = "<strong>Bold</strong>";
element.innerText;       // visible text only

// Attributes
element.getAttribute("href");
element.setAttribute("href", "https://example.com");
element.removeAttribute("disabled");
element.hasAttribute("required");

// Classes
element.classList.add("active");
element.classList.remove("hidden");
element.classList.toggle("dark");
element.classList.contains("active"); // true/false
element.classList.replace("old", "new");
element.className = "card featured";

// Styles
element.style.color = "red";
element.style.backgroundColor = "navy";
element.style.display = "none";
element.style.cssText = "color: red; font-size: 18px;";

// Create elements
let div = document.createElement("div");
div.textContent = "Hello!";
div.classList.add("card");

// Add to DOM
parent.appendChild(div);
parent.prepend(div);
parent.insertBefore(div, referenceNode);
parent.append(div, "text", otherElement);
referenceNode.after(div);
referenceNode.before(div);

// Remove from DOM
element.remove();
parent.removeChild(element);

// Replace
parent.replaceChild(newElement, oldElement);
element.replaceWith(newElement);

// Clone
let clone = element.cloneNode(true); // true = deep clone

// Dimensions
element.offsetWidth;
element.offsetHeight;
element.getBoundingClientRect(); // position + size

// Scroll
window.scrollTo(0, 0);
window.scrollTo({ top: 0, behavior: "smooth" });
element.scrollIntoView({ behavior: "smooth" });
```

---

## 20. Events

```js
// Add event listener
element.addEventListener("click", function(event) {
  console.log("Clicked!", event);
});

// Arrow function listener
element.addEventListener("click", (e) => {
  console.log(e.target);
});

// Remove event listener
function handleClick(e) {
  console.log("clicked");
}
element.addEventListener("click", handleClick);
element.removeEventListener("click", handleClick);

// Common events
"click"
"dblclick"
"mouseenter"
"mouseleave"
"mousemove"
"mousedown"
"mouseup"
"keydown"
"keyup"
"keypress"
"input"
"change"
"submit"
"focus"
"blur"
"scroll"
"resize"
"load"
"DOMContentLoaded"

// Event object
element.addEventListener("click", (e) => {
  e.target;           // element that was clicked
  e.currentTarget;    // element with the listener
  e.type;             // "click"
  e.preventDefault(); // stop default behavior (e.g. form submit)
  e.stopPropagation(); // stop event bubbling up
  e.clientX;          // mouse X position
  e.clientY;          // mouse Y position
  e.key;              // keyboard key pressed
  e.code;             // keyboard code
  e.shiftKey;         // was shift held?
  e.ctrlKey;          // was ctrl held?
});

// Event delegation — listen on parent, handle children
document.querySelector("ul").addEventListener("click", (e) => {
  if (e.target.tagName === "LI") {
    e.target.classList.toggle("active");
  }
});

// One-time event
element.addEventListener("click", handler, { once: true });

// Form events
form.addEventListener("submit", (e) => {
  e.preventDefault(); // stop page reload
  let data = new FormData(form);
  console.log(data.get("username"));
});

input.addEventListener("input", (e) => {
  console.log(e.target.value); // live value as user types
});

// keyboard events
document.addEventListener("keydown", (e) => {
  if (e.key === "Escape") closeModal();
  if (e.key === "Enter") submitForm();
  if (e.ctrlKey && e.key === "s") saveDocument();
});

// Window events
window.addEventListener("resize", () => {
  console.log(window.innerWidth, window.innerHeight);
});

window.addEventListener("scroll", () => {
  console.log(window.scrollY);
});

document.addEventListener("DOMContentLoaded", () => {
  // DOM is ready, safe to query elements
});
```

---

## 21. Fetch API

```js
// Basic GET request
fetch("https://api.example.com/users")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));

// With async/await
async function getUsers() {
  try {
    let response = await fetch("https://api.example.com/users");

    if (!response.ok) {
      throw new Error(`HTTP error: ${response.status}`);
    }

    let data = await response.json();
    return data;
  } catch (error) {
    console.error("Fetch failed:", error);
  }
}

// POST request
async function createUser(userData) {
  let response = await fetch("https://api.example.com/users", {
    method: "POST",
    headers: {
      "Content-Type": "application/json"
    },
    body: JSON.stringify(userData)
  });

  return await response.json();
}

createUser({ name: "Alice", email: "alice@example.com" });

// PUT request
async function updateUser(id, userData) {
  let response = await fetch(`https://api.example.com/users/${id}`, {
    method: "PUT",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(userData)
  });

  return await response.json();
}

// DELETE request
async function deleteUser(id) {
  await fetch(`https://api.example.com/users/${id}`, {
    method: "DELETE"
  });
}

// Response methods
response.json();     // parse as JSON
response.text();     // parse as text
response.blob();     // parse as binary/file
response.ok;         // true if status 200-299
response.status;     // 200, 404, 500, etc.
response.headers.get("Content-Type");
```

---

## 22. LocalStorage

```js
// Save data
localStorage.setItem("username", "Alice");
localStorage.setItem("theme", "dark");

// Read data
let username = localStorage.getItem("username"); // "Alice"
let missing = localStorage.getItem("nope");      // null

// Delete one item
localStorage.removeItem("theme");

// Clear everything
localStorage.clear();

// Save objects (must stringify)
let user = { name: "Alice", age: 25 };
localStorage.setItem("user", JSON.stringify(user));

// Read objects (must parse)
let saved = JSON.parse(localStorage.getItem("user"));
saved.name; // "Alice"

// Safe read with default
function getFromStorage(key, defaultValue = null) {
  try {
    let item = localStorage.getItem(key);
    return item ? JSON.parse(item) : defaultValue;
  } catch {
    return defaultValue;
  }
}

// sessionStorage — same API, but cleared when tab closes
sessionStorage.setItem("tempData", "value");
sessionStorage.getItem("tempData");
sessionStorage.removeItem("tempData");
```

---

## 23. Modules

```js
// Named exports
export const PI = 3.14;
export function add(a, b) { return a + b; }
export class User { constructor(name) { this.name = name; } }

// Default export — one per file
export default function greet(name) {
  return `Hello, ${name}!`;
}

// Import named exports
import { PI, add } from './math.js';
import { User } from './user.js';

// Import default
import greet from './greet.js';

// Import both
import greet, { PI, add } from './utils.js';

// Import all as namespace
import * as Math from './math.js';
Math.PI;
Math.add(1, 2);

// Rename imports
import { add as sum } from './math.js';

// Dynamic import — load on demand
async function loadModule() {
  let { add } = await import('./math.js');
  console.log(add(1, 2));
}

// Re-export
export { add } from './math.js';
export { default as greet } from './greet.js';
```

---

## 24. Useful Built-ins

```js
// JSON
JSON.stringify({ name: "Alice", age: 25 });
// '{"name":"Alice","age":25}'

JSON.stringify(obj, null, 2); // pretty print with 2 spaces

JSON.parse('{"name":"Alice"}');
// { name: "Alice" }

// Date
let now = new Date();
let specific = new Date("2026-03-26");
let fromMs = new Date(1711497600000);

now.getFullYear();  // 2026
now.getMonth();     // 0-11
now.getDate();      // 1-31
now.getDay();       // 0-6 (0=Sunday)
now.getHours();
now.getMinutes();
now.getSeconds();
now.getTime();      // milliseconds since epoch

now.toLocaleDateString();  // "3/26/2026"
now.toLocaleTimeString();  // "10:30:00 AM"
now.toISOString();         // "2026-03-26T10:30:00.000Z"

Date.now(); // current timestamp in ms

// Timers
let timeout = setTimeout(() => {
  console.log("Runs once after 2 seconds");
}, 2000);

clearTimeout(timeout); // cancel

let interval = setInterval(() => {
  console.log("Runs every second");
}, 1000);

clearInterval(interval); // cancel

// Console
console.log("info");
console.error("error");
console.warn("warning");
console.table([{ name: "Alice" }, { name: "Bob" }]);
console.group("Group");
console.groupEnd();
console.time("timer");
console.timeEnd("timer");
console.clear();

// Type conversion
Number("42");       // 42
Number(true);       // 1
Number(false);      // 0
Number(null);       // 0
Number(undefined);  // NaN
String(42);         // "42"
Boolean(0);         // false
Boolean("");        // false
Boolean(null);      // false
Boolean([]);        // true (gotcha!)
Boolean({});        // true (gotcha!)

// Regex
let regex = /hello/i;           // case insensitive
let regex2 = /^\d{3}-\d{4}$/;  // phone pattern

regex.test("Hello World");      // true
"Hello World".match(/\w+/g);   // ["Hello", "World"]
"Hello World".replace(/World/, "Club"); // "Hello Club"
"a,b,,c".split(/,+/);          // ["a", "b", "c"]
```

---

## 25. Common Patterns

```js
// Debounce — delay execution until user stops typing
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}

const search = debounce((query) => {
  console.log("Searching:", query);
}, 300);

input.addEventListener("input", (e) => search(e.target.value));

// Throttle — run at most once every X ms
function throttle(fn, limit) {
  let lastRun = 0;
  return function(...args) {
    let now = Date.now();
    if (now - lastRun >= limit) {
      lastRun = now;
      fn(...args);
    }
  };
}

// Deep clone an object
let deep = JSON.parse(JSON.stringify(original));
let deep2 = structuredClone(original); // modern approach

// Generate unique ID
let id = crypto.randomUUID(); // "a1b2c3d4-..."
let shortId = Math.random().toString(36).slice(2, 9);

// Capitalize first letter
let capitalize = str => str.charAt(0).toUpperCase() + str.slice(1);

// Slugify a string
let slugify = str =>
  str.toLowerCase().trim().replace(/\s+/g, "-").replace(/[^\w-]/g, "");

slugify("Hello World!"); // "hello-world"

// Group array by property
let users = [
  { name: "Alice", role: "admin" },
  { name: "Bob", role: "member" },
  { name: "Charlie", role: "admin" }
];

let grouped = users.reduce((acc, user) => {
  (acc[user.role] ??= []).push(user);
  return acc;
}, {});
// { admin: [Alice, Charlie], member: [Bob] }

// Remove duplicates
let unique = [...new Set([1, 2, 2, 3, 3, 4])]; // [1, 2, 3, 4]
let uniqueUsers = [...new Map(users.map(u => [u.name, u])).values()];

// Flatten nested object
function flattenObj(obj, prefix = "") {
  return Object.entries(obj).reduce((acc, [key, val]) => {
    let newKey = prefix ? `${prefix}.${key}` : key;
    if (typeof val === "object" && val !== null && !Array.isArray(val)) {
      Object.assign(acc, flattenObj(val, newKey));
    } else {
      acc[newKey] = val;
    }
    return acc;
  }, {});
}

// Pipeline — chain functions left to right
const pipe = (...fns) => x => fns.reduce((v, f) => f(v), x);

const process = pipe(
  str => str.trim(),
  str => str.toLowerCase(),
  str => str.replace(/\s+/g, "-")
);

process("  Hello World  "); // "hello-world"

// Wait/sleep in async functions
const sleep = ms => new Promise(resolve => setTimeout(resolve, ms));

async function main() {
  console.log("Start");
  await sleep(2000);
  console.log("2 seconds later");
}
```

---

## Quick Reference Card

```js
// Variables
const x = 1;   let y = 2;

// Types
string  number  boolean  null  undefined  object  array  function

// Functions
function fn(a, b = 0) { return a + b; }
const fn = (a, b) => a + b;

// Array methods
map  filter  find  findIndex  some  every  reduce  forEach  flat  includes

// Object methods
Object.keys()  Object.values()  Object.entries()  Object.assign()

// Destructuring
const { name, age } = user;
const [first, ...rest] = arr;

// Spread
const copy = [...arr];
const merged = { ...obj1, ...obj2 };

// Async
async function fn() { const data = await fetch(url).then(r => r.json()); }

// DOM
querySelector  addEventListener  classList  textContent  innerHTML  createElement  appendChild

// Operators to know
===  !==  &&  ||  ??  ?.  ...
```

---

*ProgrammingClub67 — Web Development Semester 2026*
