📘 Web Technology – JavaScript (Detailed Notes)
## 1. Introduction to JavaScript

JavaScript is a high-level, interpreted programming language used to create dynamic and interactive web pages. It runs inside the browser (client-side) but can also run on servers (using Node.js).

🔹 Why JavaScript?
Adds interactivity (buttons, forms, animations)
Works with HTML + CSS
Enables dynamic content updates without reloading
🔹 Example:
<script>
  document.write("Hello, JavaScript!");
</script>

👉 Without JavaScript → websites are static
👉 With JavaScript → websites become interactive

## 2. Values and Variables
🔹 Values

Values are the data stored in variables.

Types of values:

Number → 10, 3.14
String → "Hello"
Boolean → true, false
Undefined → variable declared but not assigned
Null → intentionally empty
🔹 Variables

Variables store values in memory.

var name = "Radhe";
let age = 25;
const pi = 3.14;
🔹 Difference:
Keyword	Scope	Reassign	Use Case
var	Function	Yes	Old JS
let	Block	Yes	Preferred
const	Block	No	Constants

👉 Mistake students make: using var everywhere → avoid it.

## 3. Operators in JavaScript

Operators perform operations on variables.

🔹 Types:
1. Arithmetic Operators
let a = 10, b = 5;
console.log(a + b); // 15
console.log(a % b); // 0
2. Assignment Operators
let x = 10;
x += 5; // x = x + 5
3. Comparison Operators
console.log(10 == "10");  // true
console.log(10 === "10"); // false

👉 === is strict → always prefer it

4. Logical Operators
console.log(true && false); // false
console.log(true || false); // true
## 4. Loops and Control Statements
🔹 Loops

Used to repeat code.

for loop
for(let i = 1; i <= 5; i++){
  console.log(i);
}
while loop
let i = 1;
while(i <= 5){
  console.log(i);
  i++;
}
🔹 Conditional Statements
let age = 20;

if(age >= 18){
  console.log("Adult");
}else{
  console.log("Minor");
}
🔹 Switch Case
let day = 1;

switch(day){
  case 1: console.log("Monday"); break;
  case 2: console.log("Tuesday"); break;
}
## 5. Date Object

Used to work with date and time.

let date = new Date();

console.log(date); // full date
console.log(date.getFullYear());
console.log(date.getMonth()); // 0-11
console.log(date.getDate());

👉 Important: Month starts from 0 (January)

## 6. Math Object

Provides built-in math functions.

console.log(Math.PI);
console.log(Math.sqrt(25)); // 5
console.log(Math.random()); // 0 to 1
console.log(Math.floor(4.7)); // 4
## 7. String Object

Used to manipulate text.

let str = "Hello World";

console.log(str.length);
console.log(str.toUpperCase());
console.log(str.toLowerCase());
console.log(str.substring(0,5));
## 8. Window Object

Represents browser window.

alert("Hello");
confirm("Are you sure?");
prompt("Enter your name:");

👉 It is the global object in browser.

## 9. Window Events

Triggered by user or browser actions.

window.onload = function(){
  alert("Page Loaded");
};
Common events:
onclick
onload
onresize
## 10. Working with Forms

Used to collect user input.

<form onsubmit="return validate()">
  <input type="text" id="name">
  <input type="submit">
</form>

<script>
function validate(){
  let name = document.getElementById("name").value;
  if(name == ""){
    alert("Enter name");
    return false;
  }
}
</script>

👉 Key concept: Form validation

## 11. Document Object (DOM)

Represents HTML page structure.

document.getElementById("demo").innerHTML = "Hello";
Common methods:
getElementById()
getElementsByClassName()
querySelector()

👉 DOM = bridge between JS and HTML

## 12. Screen Object

Gives screen information.

console.log(screen.width);
console.log(screen.height);
## 13. Navigator Object

Provides browser details.

console.log(navigator.userAgent);
console.log(navigator.language);

👉 Used for browser detection.

## 14. Images and Animation
🔹 Changing Image
document.getElementById("img").src = "new.jpg";
🔹 Animation Example
let pos = 0;

function move(){
  pos++;
  document.getElementById("box").style.left = pos + "px";
}

setInterval(move, 10);

👉 Core concept: DOM + timing functions

## 15. JavaScript Objects
🔹 Declaration
let obj = {};
🔹 Definition
let person = {
  name: "Radhe",
  age: 25
};
🔹 Accessing
console.log(person.name);
console.log(person["age"]);
## 16. Identifiers and Scope Rules
🔹 Identifiers Rules:
Cannot start with number
No spaces
Case-sensitive
🔹 Scope Types
Type	Description
Global	Accessible everywhere
Local	Inside function
Block	Inside {}
let x = 10;

function test(){
  let y = 5;
}
## 17. Recursion

Function calling itself.

function factorial(n){
  if(n == 1) return 1;
  return n * factorial(n - 1);
}

👉 Risk: infinite recursion → stack overflow

## 18. Arrays
🔹 Declaration
let arr = [10, 20, 30];
🔹 Access
console.log(arr[0]);
🔹 Methods
arr.push(40);
arr.pop();
arr.sort();
## 19. Built-in Objects
🔹 Math
Math.max(10,20);
🔹 String
"hello".toUpperCase();
🔹 Date
new Date();
🔹 Number
let num = 10;
num.toString();
🔹 Boolean
let flag = true;
## 20. Document (Detailed)

Document is part of DOM used to manipulate HTML.

document.write("Hello");
document.getElementById("id");
document.querySelector(".class");

👉 Real use:

Change content
Handle events
Update UI dynamically
