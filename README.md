# React-Cleared-
Interview purposes - Advanced react for SEO as well


# Javascropt concepts
## Variables, Data Types, and Operators:

Variables: Variables are used to store data. In JavaScript, you can declare variables using var, let, or const.
Example:
```bash
let name = "John";
const age = 30;
```

Data Types: JavaScript has several data types, including:

Primitive Data Types: Numbers, Strings, Booleans, Undefined, Null, and Symbols (ES6).
Reference Data Types: Objects (including arrays and functions).
Example:
```bash
let num = 42; // Number
let greeting = "Hello"; // String
let isTrue = true; // Boolean
let person = { name: "Alice", age: 25 }; // Object (Reference Type)
```

Operators: Operators are used to perform operations on variables and values. Common operators include:

Arithmetic Operators (+, -, *, /, %)
Comparison Operators (==, ===, !=, !==, <, >, <=, >=)
Logical Operators (&&, ||, !)
Assignment Operators (=, +=, -=, *=, /=)

## Functions and Closures:

Functions: Functions are blocks of reusable code. They can take parameters and return values.
```bash
function greet(name) {
  return "Hello, " + name + "!";
}
let greeting = greet("Alice"); // Call the function
```

Closures: Closures are functions that have access to variables from their outer (enclosing) scope, even after that scope has finished executing.

```bash
function outer() {
  let message = "Hello from outer!";
  function inner() {
    console.log(message);
  }
  return inner;
}
let closureFn = outer(); // Creates a closure
closureFn(); // Prints "Hello from outer!"

```


## Arrays and Objects:
Arrays: Arrays are ordered collections of values, indexed by integers.
```bash
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // Accessing an element
fruits.push("orange"); // Adding an element
```
Objects: Objects are collections of key-value pairs.
```bash
let person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
  },
};
console.log(person.name); // Accessing a property
```
## DOM Manipulation:
The Document Object Model (DOM) represents the structure of an HTML document as a tree of objects that can be manipulated with JavaScript.
You can access and modify HTML elements in the DOM using JavaScript, such as changing content, adding or removing elements, and handling events.

```bash
// Accessing an element by its ID
let element = document.getElementById("myElement");
// Changing its content
element.innerHTML = "New content";
// Adding an event listener
element.addEventListener("click", function () {
  alert("Element clicked!");
});
```

## React Components:
React components are the building blocks of a React application. They are reusable and self-contained pieces of UI that can be composed together to create complex user interfaces. Components are written using JavaScript and JSX (JavaScript XML), which is an extension of JavaScript allowing you to write HTML-like code within your JavaScript files.

```bash
import React from "react";

function MyComponent() {
  return <div>Hello, World!</div>;
}
export default MyComponent;
```

## props
Props (short for "properties") are a way to pass data from a parent component to a child component in React. They are read-only and help make your components reusable. Props are passed as attributes to a component when it is used in JSX.

```bash
// ParentComponent.js
import React from "react";
import ChildComponent from "./ChildComponent";

function ParentComponent() {
  const name = "Alice";

  return <ChildComponent name={name} />;
}

export default ParentComponent;

// ChildComponent.js
import React from "react";

function ChildComponent(props) {
  return <div>Hello, {props.name}!</div>;
}

export default ChildComponent;
```

## state
State is a way to manage and store data within a component. Unlike props, which are passed from parent to child and are immutable, state is used for data that can change over time and is mutable within the component. 

```bash
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <div>
      Count: {count}
      <button onClick={incrementCount}>Increment</button>
    </div>
  );
}

export default Counter;
```

## Component Lifecycle:
The component lifecycle refers to the various stages a component goes through from its creation to its destruction. Understanding these lifecycle methods is crucial for efficiently managing the behavior and state of a component throughout its lifecycle.













