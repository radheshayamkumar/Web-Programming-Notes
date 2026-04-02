# JavaScript Fundamentals: A Beginner's Guide

Welcome to the world of JavaScript! Whether you're building interactive websites or complex server-side applications, these core concepts are the building blocks of everything you'll create.

---

## 1. Introduction to JavaScript
JavaScript (JS) is a lightweight, interpreted programming language with first-class functions. While it’s most famous as the scripting language for Web pages, many non-browser environments also use it, such as Node.js.

* **What it does:** It makes websites interactive (think buttons, sliders, and live updates).
* **Where it runs:** Every modern web browser has a built-in JavaScript engine (like Chrome's V8).

---

## 2. Values and Variables
In JavaScript, **Values** are the data itself (like the number 5 or the word "Hello"), and **Variables** are containers used to store those values.

### Declaring Variables
There are three main ways to declare a variable:
1.  **`let`**: Used for values that might change (block-scoped).
2.  **`const`**: Used for values that stay the same (constants).
3.  **`var`**: The older way (generally avoided in modern JS).

```javascript
const name = "Alex"; // This value won't change
let age = 25;        // This value can be updated
age = 26;            // Updating the value
```

### Data Types
* **String:** Text wrapped in quotes (e.g., `"Hello"`).
* **Number:** Integers or decimals (e.g., `10`, `3.14`).
* **Boolean:** True or false (e.g., `true`, `false`).
* **Undefined:** A variable that has been declared but not assigned a value.
* **Null:** An intentional "empty" value.

---

## 3. Operators
Operators allow us to perform actions on variables and values.

### Arithmetic Operators
Used for math:
* `+` (Addition), `-` (Subtraction), `*` (Multiplication), `/` (Division).
* `%` (Remainder/Modulus): Returns what's left over after division.

### Assignment Operators
Used to assign values:
* `=` : Simple assignment.
* `+=` : Add and assign (e.g., `x += 5` is the same as `x = x + 5`).

### Comparison Operators
Used to compare two values (returns `true` or `false`):
* `===` : Strict equality (checks value AND type).
* `!==` : Not equal.
* `>` / `<` : Greater than / Less than.

---

## 4. Statements (Conditional)
Statements are the "logic" of your code. They allow the program to make decisions.

### If-Else Statement
```javascript
let weather = "sunny";

if (weather === "sunny") {
    console.log("Wear sunglasses!");
} else {
    console.log("Take an umbrella.");
}
```

### Switch Statement
Useful when you have many "cases" to check against a single value.
```javascript
let day = "Monday";

switch (day) {
    case "Monday":
        console.log("Start of the work week!");
        break;
    case "Friday":
        console.log("Weekend is near!");
        break;
    default:
        console.log("Just another day.");
}
```

---

## 5. Loops
Loops are used to run the same block of code multiple times.

### For Loop
Best when you know exactly how many times you want to repeat something.
```javascript
// for (initialization; condition; increment)
for (let i = 1; i <= 3; i++) {
    console.log("Iteration number: " + i);
}
// Output: 1, 2, 3
```

### While Loop
Runs as long as a specific condition is `true`.
```javascript
let energy = 3;

while (energy > 0) {
    console.log("Keep running...");
    energy--; // Decreasing energy each time
}
console.log("Tired now!");
```



---

## Summary Table

| Concept | Purpose | Example |
| :--- | :--- | :--- |
| **Variable** | Store data | `let score = 0;` |
| **Operator** | Perform actions | `score + 10` |
| **If Statement** | Decision making | `if (score > 50) { ... }` |
| **Loop** | Repeat actions | `for (i=0; i<5; i++)` |



---

Continuing with our JavaScript journey, let’s dive into the "Objects" that allow JS to interact with data, the browser, and the user.

---

## 1. Built-in Objects (Date, Math, String)

JavaScript provides built-in "tools" (objects) to handle common tasks like calculations, time, and text manipulation.

### Date Object
Used to work with dates and times.
* **Example:**
  ```javascript
  const now = new Date(); 
  console.log(now.toDateString()); // "Thu Apr 02 2026"
  console.log(now.getFullYear()); // 2026
  ```

### Math Object
Allows you to perform mathematical tasks on numbers. Unlike other objects, you don't need to "create" it; you just use it.
* **Common Methods:** `Math.round()`, `Math.floor()`, `Math.random()`.
* **Example:**
  ```javascript
  let pi = Math.PI;             // 3.14159...
  let randomNum = Math.random(); // Random number between 0 and 1
  let power = Math.pow(2, 3);    // 2 to the power of 3 (8)
  ```

### String Object
Used to manipulate sequences of characters.
* **Example:**
  ```javascript
  let text = "JavaScript is Fun";
  console.log(text.length);      // 17
  console.log(text.toUpperCase()); // "JAVASCRIPT IS FUN"
  console.log(text.includes("Fun")); // true
  ```

---

## 2. The Browser Object Model (BOM)
These objects represent the browser itself, rather than the specific webpage content.



### Window Events
The `window` object represents the browser window. Events are things that happen to the window.
* **Example:**
  ```javascript
  // Runs when the whole page finishes loading
  window.onload = () => {
      console.log("Page is fully loaded!");
  };

  // Runs when the window is resized
  window.onresize = () => {
      console.log("Window size changed!");
  };
  ```

### Screen Object
Contains information about the visitor's screen (resolution, depth, etc.).
* **Example:** `console.log(screen.width);` // Returns screen width in pixels.

### Navigator Object
Contains information about the browser (name, version, platform).
* **Example:** `console.log(navigator.onLine);` // Returns true if the browser is online.

---

## 3. The Document Object Model (DOM)
The `document` object is the root of your webpage. Use it to change HTML and CSS.

### Document Object
* **Example:**
  ```javascript
  // Change the text of an element with id="title"
  document.getElementById("title").innerHTML = "Hello World!";
  
  // Change the background color
  document.body.style.backgroundColor = "lightblue";
  ```

---

## 4. Working with Forms
JavaScript can capture and validate what a user types into a form.
* **Example:**
  ```javascript
  function validateForm() {
      let x = document.forms["myForm"]["fname"].value;
      if (x === "") {
          alert("Name must be filled out");
          return false;
      }
  }
  ```

---

## 5. Images and Animation
JavaScript can change images dynamically or move elements to create animations.

### Handling Images
You can change the `src` attribute of an image to swap it.
```javascript
function changeImage() {
    document.getElementById("myImg").src = "landscape.jpg";
}
```

### Simple Animation
Using `setInterval()` or `requestAnimationFrame()` to move an element.
```javascript
let pos = 0;
const box = document.getElementById("animateBox");

function move() {
  if (pos < 150) {
    pos++;
    box.style.left = pos + "px"; // Moves the box 1px to the right
  }
}

setInterval(move, 10); // Runs move() every 10 milliseconds
```

---

## Summary Cheat Sheet

| Object | What it handles |
| :--- | :--- |
| **Date** | Calendars, clocks, and timestamps. |
| **Math** | Complex calculations and random numbers. |
| **String** | Searching and modifying text. |
| **Window** | Browser alerts, resizing, and loading. |
| **Document** | HTML elements, CSS styles, and text on page. |
| **Navigator** | Browser info and internet connection status. |



----

In JavaScript, **Objects** are the most important data type. They allow you to group related data and functions together into a single "package."

---

## 1. Objects: Declaration, Definition, and Referencing

### A. Declaration and Definition
There are two main ways to create (declare and define) an object:

1.  **Object Literal (Most Common):** You define the properties inside curly braces `{}`.
2.  **Object Constructor:** Using the `new Object()` syntax.

```javascript
// 1. Object Literal (Declaration + Definition)
const car = {
    brand: "Tesla",     // Property
    model: "Model 3",   // Property
    start: function() { // Method (a function inside an object)
        console.log("Engine started!");
    }
};

// 2. Object Constructor
const user = new Object();
user.name = "John";
user.age = 30;
```

### B. Referencing Properties
Once an object is defined, you can access or "reference" its data using two methods:

* **Dot Notation:** `object.property`
* **Bracket Notation:** `object["property"]` (Useful when the property name is stored in a variable).

```javascript
console.log(car.brand);      // Tesla
console.log(car["model"]);   // Model 3
```

---

## 2. Identifiers
An **Identifier** is simply a name you give to variables, functions, or objects. In JavaScript, there are specific rules for naming them:

* **Case Sensitive:** `myVar` and `myvar` are different.
* **Allowed Characters:** Must start with a letter, underscore (`_`), or dollar sign (`$`). They cannot start with a number.
* **No Reserved Words:** You cannot name a variable `let`, `function`, or `if`.

---

## 3. Scope Rules
**Scope** determines where a variable or identifier is accessible within your code.



### A. Global Scope
Variables declared outside any function or curly braces are in the **Global Scope**. They can be accessed from anywhere in your script.
```javascript
const globalName = "Alex";

function sayName() {
    console.log(globalName); // Accessible here
}
```

### B. Function Scope
Variables declared inside a `function` using `var`, `let`, or `const` are only accessible inside that function.
```javascript
function greet() {
    let message = "Hello!"; 
    console.log(message); // Works
}
// console.log(message); // Error: message is not defined
```

### C. Block Scope (`let` and `const`)
Introduced in modern JS (ES6), **Block Scope** means a variable is only available inside the specific curly braces `{}` where it was created (like an `if` statement or a `loop`).
* **Note:** `var` does **not** support block scope, which is why we prefer `let` and `const`.

```javascript
if (true) {
    let blockVar = "I am trapped in this if block";
    var functionVar = "I can escape the if block!";
}

// console.log(blockVar);    // Error
console.log(functionVar); // Works (because var ignores blocks)
```

---

## Summary Table

| Concept | Rule |
| :--- | :--- |
| **Object Literal** | Uses `{ key: value }` |
| **Dot Notation** | `obj.key` (Cleaner syntax) |
| **Bracket Notation** | `obj["key"]` (Flexible for variables) |
| **Global Scope** | Available everywhere. |
| **Block Scope** | Limited to `{ ... }` (Used by `let`/`const`). |


---

In JavaScript, **Recursion** and **Arrays** are fundamental concepts for handling data and solving complex logic. Here is a breakdown of how they work.

---

## 1. Recursion
**Recursion** is a technique where a function calls itself to solve a smaller version of the same problem. 

To prevent a function from calling itself forever (causing a "stack overflow"), every recursive function needs two things:
1.  **Base Case:** The condition where the function stops calling itself.
2.  **Recursive Step:** The part where the function calls itself with a modified argument.

### Example: Factorial
Calculating $5!$ (which is $5 \times 4 \times 3 \times 2 \times 1$):

```javascript
function factorial(n) {
    // Base Case
    if (n === 1) return 1;
    
    // Recursive Step
    return n * factorial(n - 1);
}

console.log(factorial(5)); // 120
```



---

## 2. Arrays: Declaration & Allocation
An **Array** is a special variable that can hold more than one value at a time. In JavaScript, memory **allocation** for arrays is dynamic, meaning you don't have to specify the size upfront.

### Declaration
You can declare an array using the literal syntax (preferred) or the constructor.
```javascript
// Literal Syntax
const fruits = ["Apple", "Banana", "Cherry"];

// Array Constructor
const numbers = new Array(10, 20, 30);
```

---

## 3. Accessing Arrays
Array elements are stored at numeric positions called **indexes**. 
> **Important:** JavaScript arrays are **zero-indexed** (the first element is at index 0).

```javascript
const colors = ["Red", "Green", "Blue"];

console.log(colors[0]); // "Red"
console.log(colors[1]); // "Green"

// Changing an element (Modification)
colors[2] = "Yellow"; 
console.log(colors); // ["Red", "Green", "Yellow"]
```

---

## 4. Sorting Arrays
JavaScript provides a built-in `.sort()` method. However, by default, it sorts values as **strings**, which can lead to unexpected results with numbers.

### Sorting Strings
```javascript
const names = ["Zack", "Alice", "Ben"];
names.sort(); 
console.log(names); // ["Alice", "Ben", "Zack"]
```

### Sorting Numbers
To sort numbers correctly, you must provide a **compare function**. Without it, `"25"` comes before `"5"` because "2" is smaller than "5" in string comparison.

```javascript
const scores = [40, 100, 1, 5, 25];

// Ascending Order
scores.sort((a, b) => a - b); 
console.log(scores); // [1, 5, 25, 40, 100]

// Descending Order
scores.sort((a, b) => b - a); 
console.log(scores); // [100, 40, 25, 5, 1]
```



---

## Summary Table

| Operation | Syntax/Method | Key Note |
| :--- | :--- | :--- |
| **Declaration** | `const arr = []` | Use square brackets for literal syntax. |
| **Accessing** | `arr[index]` | Indexes start at **0**. |
| **Recursion** | `func() { func() }` | Always include a **Base Case**. |
| **Sorting** | `arr.sort()` | Use a compare function `(a, b) => a - b` for numbers. |

---
Excellent choice! Mastering these methods will make you a much more efficient developer. In JavaScript, we manipulate arrays using specific methods to add, remove, or find data.

---

## 1. Adding and Removing Elements
These methods are the "bread and butter" of array manipulation. They allow you to modify the start or end of an array.



* **`push()`**: Adds an element to the **end** of an array.
* **`pop()`**: Removes the **last** element and returns it.
* **`unshift()`**: Adds an element to the **beginning**.
* **`shift()`**: Removes the **first** element and returns it.

```javascript
let queue = ["Alice", "Bob"];

queue.push("Charlie");    // ["Alice", "Bob", "Charlie"]
queue.shift();           // ["Bob", "Charlie"] (removes Alice)
```

---

## 2. Searching and Finding
When you have a large list, you need ways to locate specific items.

* **`indexOf()`**: Returns the index of the first occurrence of a value. Returns `-1` if not found.
* **`includes()`**: Returns `true` or `false` if the value exists.
* **`find()`**: Returns the **first** element that passes a specific test (condition).

```javascript
const prices = [10, 25, 40, 55];

// find the first price over 30
const expensive = prices.find(p => p > 30); 
console.log(expensive); // 40

console.log(prices.includes(25)); // true
```

---

## 3. The `splice()` Method
`splice()` is the "Swiss Army Knife" of arrays. It can add, remove, and replace elements all at once at **any position**.

**Syntax:** `array.splice(startIndex, deleteCount, item1, item2, ...)`

```javascript
let months = ["Jan", "March", "April"];

// At index 1, delete 0 items, and insert "Feb"
months.splice(1, 0, "Feb"); 
console.log(months); // ["Jan", "Feb", "March", "April"]

// At index 2, delete 1 item
months.splice(2, 1); 
console.log(months); // ["Jan", "Feb", "April"]
```

---

## 4. Array Transformation (Modern JS)
These methods are used to create new arrays based on existing ones without changing the original data.



* **`map()`**: Creates a **new array** by performing a function on every element.
* **`filter()`**: Creates a **new array** with elements that pass a test.

```javascript
const nums = [1, 2, 3, 4];

// Double every number
const doubled = nums.map(n => n * 2); // [2, 4, 6, 8]

// Keep only even numbers
const evens = nums.filter(n => n % 2 === 0); // [2, 4]
```

---

## Summary of Operations

| Method | Description | Modifies Original? |
| :--- | :--- | :--- |
| `push` / `pop` | Add/Remove from end | **Yes** |
| `shift` / `unshift` | Add/Remove from start | **Yes** |
| `splice` | Add/Remove from middle | **Yes** |
| `indexOf` | Find index of item | No |
| `map` | Transform all items | No |
| `filter` | Select specific items | No |



---

We have touched on some of these briefly, but let's dive deeper into the technical properties of these **Standard Built-in Objects** and the **Document** object. In JavaScript, almost everything is an object, and these built-ins provide the "heavy lifting" functionality for your code.

---

## 1. The Math Object
The `Math` object is static, meaning you don't create an instance of it (no `new Math()`). It works like a toolbox for mathematical constants and functions.

* **Constants:** `Math.PI`, `Math.E`.
* **Rounding:** `Math.floor()` (round down), `Math.ceil()` (round up), `Math.round()` (nearest integer).
* **Random:** `Math.random()` returns a decimal between 0 and 1.

```javascript
// Get a random integer between 1 and 10
let randomInt = Math.floor(Math.random() * 10) + 1;
console.log(randomInt); 

console.log(Math.sqrt(16)); // 4 (Square root)
```

---

## 2. The String Object
Whenever you treat a primitive string like an object (by calling a method), JavaScript temporarily "wraps" it in a String object.

* **Extraction:** `slice(start, end)`, `substring()`.
* **Search:** `indexOf()`, `lastIndexOf()`, `search()`.
* **Manipulation:** `replace()`, `trim()` (removes whitespace), `split()` (converts string to array).

```javascript
let phrase = "I love JavaScript";
console.log(phrase.slice(7, 17)); // "JavaScript"
console.log(phrase.split(" "));   // ["I", "love", "JavaScript"]
```

---

## 3. The Date Object
Unlike `Math`, you must create an instance of `Date` using the `new` keyword to work with time.

* **Current Time:** `new Date()`
* **Getters:** `getDate()`, `getDay()`, `getHours()`.
* **Setters:** `setFullYear()`, `setMonth()`.

```javascript
let birthday = new Date("1995-12-17T03:24:00");
console.log(birthday.getDay()); // Returns a number representing the day of the week
```



---

## 4. The Number and Boolean Objects
While we usually use primitive numbers (like `5`) and booleans (`true`), JavaScript provides object wrappers for them to offer specific properties.

* **Number Properties:** `Number.MAX_VALUE`, `Number.MIN_VALUE`, `Number.isInteger()`.
* **Number Methods:** `toFixed()` (rounds to specific decimals), `toPrecision()`.
* **Boolean:** Primarily used to check if a value is "truthy" or "falsy". Everything with a "value" is true; everything without a "value" (0, "", null, undefined) is false.

```javascript
let pi = 3.14159;
console.log(pi.toFixed(2)); // "3.14" (Returns as string)

console.log(Number.isInteger(10)); // true
```

---

## 5. The Document Object (DOM)
The `document` object represents the web page loaded in the browser. It acts as the entry point to the **DOM Tree**. By using this object, you can programmatically change anything on the page.



### Key Document Tasks:
1.  **Finding Elements:**
    * `document.getElementById("id")`
    * `document.querySelector(".class-name")`
2.  **Changing Content/Style:**
    * `.innerHTML`: Changes the HTML inside an element.
    * `.style.property`: Changes CSS (e.g., `.style.color = "red"`).
3.  **Creating Elements:**
    * `document.createElement("div")`

```javascript
// Simple DOM Manipulation
const myButton = document.getElementById("submitBtn");

myButton.addEventListener("click", () => {
    document.body.style.backgroundColor = "yellow";
    document.title = "Button Clicked!";
});
```

---

## Summary Comparison

| Object | Purpose | Static or Instance? |
| :--- | :--- | :--- |
| **Math** | Calculations / Constants | **Static** (use `Math.`) |
| **String** | Text manipulation | Wrapped automatically |
| **Date** | Handling time and calendar | **Instance** (use `new Date()`) |
| **Number** | Numeric precision / limits | Both |
| **Document** | Page structure / HTML | Global Object |


---

In modern JavaScript, there are two main ways to create your own custom objects at scale: **Constructor Functions** (the traditional way) and **Classes** (the modern, cleaner way). Both allow you to create a "blueprint" so you can make many similar objects without rewriting code.

---

## 1. Constructor Functions
Before 2015 (ES6), this was the standard way to create blueprints. You define a function and use the `this` keyword to assign properties.

> **Rule:** Conventionally, constructor functions start with a **Capital Letter**.

```javascript
function User(name, role) {
    this.name = name;
    this.role = role;
    this.sayHello = function() {
        console.log("Hello, I am " + this.name);
    };
}

// Creating "instances" of the User object
const user1 = new User("Alice", "Admin");
const user2 = new User("Bob", "Editor");

user1.sayHello(); // "Hello, I am Alice"
```

---

## 2. ES6 Classes (The Modern Way)
Classes are "syntactic sugar" over constructors—they do the same thing but are much easier to read and write. They group data (properties) and actions (methods) perfectly.

### Structure of a Class:
* **`constructor()`**: A special method that runs automatically when you create a new object.
* **Methods**: Functions that belong to the object (you don't need the `function` keyword).

```javascript
class Car {
    constructor(brand, speed) {
        this.brand = brand;
        this.speed = speed;
    }

    accelerate() {
        this.speed += 10;
        console.log(`${this.brand} is now going ${this.speed} km/h`);
    }
}

const myCar = new Car("Toyota", 60);
myCar.accelerate(); // "Toyota is now going 70 km/h"
```



---

## 3. The "Prototype" and Inheritance
One of the most powerful features of objects is **Inheritance**. This allows one object to "absorb" the properties and methods of another.

If you have a `Vehicle` class, you can create a `Bike` class that **extends** it.

```javascript
class Vehicle {
    constructor(wheels) {
        this.wheels = wheels;
    }
    move() {
        console.log("Moving on " + this.wheels + " wheels.");
    }
}

// Bike inherits from Vehicle
class Bike extends Vehicle {
    constructor() {
        super(2); // Calls the parent constructor with 2 wheels
    }
    ringBell() {
        console.log("Ring ring!");
    }
}

const myBike = new Bike();
myBike.move();     // "Moving on 2 wheels." (Inherited)
myBike.ringBell(); // "Ring ring!" (Own method)
```



---

## Summary Table: Custom Objects

| Feature | Constructor Function | ES6 Class |
| :--- | :--- | :--- |
| **Declaration** | `function MyObj() { ... }` | `class MyObj { ... }` |
| **Initialization** | Inside the function body | Inside `constructor()` method |
| **Inheritance** | Using `Object.create()` | Using `extends` and `super()` |
| **Readability** | Can get messy | Clean and organized |

### Pro-Tip: When to use which?
In modern development, **Classes** are almost always preferred because they align with how other languages (like Java or Python) work and are much easier for teams to maintain.

Now that you've mastered the building blocks, from variables to custom classes, are you interested in seeing how to handle **Asynchronous JavaScript** (like fetching data from a server)?

