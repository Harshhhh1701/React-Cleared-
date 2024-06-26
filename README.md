# React-Cleared-
Interview purposes - Advanced react for SEO as well


# Javascript concepts
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

constructor()

This is the first method called when a component is instantiated. It's typically used for initializing state and binding event handlers.
render()

The render() method is called whenever a component needs to be rendered or re-rendered due to changes in state or props. It returns the JSX (UI representation) for the component.
componentDidMount()

This method is invoked immediately after a component is inserted into the DOM. It's often used to perform initial setup, fetch data from an API, or add event listeners.
componentDidUpdate(prevProps, prevState)

componentDidUpdate is called after a component's state or props have been updated, triggering a re-render. It allows you to perform actions based on changes in state or props.
shouldComponentUpdate(nextProps, nextState)

This method is called before a re-render, allowing you to optimize performance by determining if the component needs to re-render based on changes in props or state. It should return a boolean indicating whether or not to proceed with the update.
componentWillUnmount()

componentWillUnmount is invoked just before a component is removed from the DOM. It's used for cleanup tasks like removing event listeners or cancelling network requests to prevent memory leaks.
static getDerivedStateFromProps(nextProps, prevState)

Introduced in React 16.3, this method is invoked whenever the component receives new props and is used to update the component's state based on those props.
getSnapshotBeforeUpdate(prevProps, prevState)

Introduced in React 16.3, this method is called right before the most recent render is committed to the DOM. It allows you to capture information (e.g., scroll position) before a potential update.


## Event Handling :
These methods are responsible for responding to specific events, such as clicks or form submissions. 

## Synthetjc events
These synthetic events provide a consistent interface for handling events across different browsers. They have the same properties and methods as native events but are automatically cleaned up by React to avoid memory leaks.

When you define event handlers in React, you'll often receive a synthetic event as an argument. You can access event properties like event.target and event.preventDefault() just like you would with native events.

## Rendering items

```bash
import React from 'react';

function ItemList({ items }) {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}

export default ItemList;
```



## Fetching data from APIs using fetch or Axios

```bash
import React, { useEffect, useState } from 'react';

function DataFetching() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then((response) => response.json())
      .then((data) => {
        setData(data);
        setLoading(false);
      })
      .catch((error) => {
        console.error('Error fetching data:', error);
        setLoading(false);
      });
  }, []);

  return (
    <div>
      {loading ? (
        <p>Loading...</p>
      ) : (
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      )}
    </div>
  );
}

export default DataFetching;
```

Axios
```bash
import React, { useEffect, useState } from 'react';
import axios from 'axios';

function DataFetching() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    axios
      .get('https://api.example.com/data')
      .then((response) => {
        setData(response.data);
        setLoading(false);
      })
      .catch((error) => {
        console.error('Error fetching data:', error);
        setLoading(false);
      });
  }, []);

  return (
    <div>
      {loading ? (
        <p>Loading...</p>
      ) : (
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      )}
    </div>
  );
}

export default DataFetching;
```

## Asynchronous JavaScript and Promises:
Promises are a way to handle asynchronous operations in JavaScript. They represent a value that may not be available yet but will be resolved in the future, either with a value (fulfilled) or with an error (rejected).
Promises have three states:

Pending: Initial state, neither fulfilled nor rejected.
Fulfilled: The operation completed successfully, and a value is available.
Rejected: The operation failed, and an error is available.

```bash
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = { message: 'Data fetched successfully' };
      resolve(data); // Fulfilled
      // To simulate an error:
      // reject(new Error('Failed to fetch data'));
    }, 2000);
  });
}

// Usage:
fetchData()
  .then((data) => {
    console.log(data.message);
  })
  .catch((error) => {
    console.error(error.message);
  });
```

## Memoization and useCallback
Memoization is a technique used to optimize expensive calculations or function calls by caching their results. In React, you can use the useMemo hook to memoize the result of a function or a calculation and ensure that it's only recomputed when the dependencies change.

```bash
import React, { useMemo } from 'react';

function ExpensiveComponent({ data }) {
  const result = useMemo(() => {
    // Expensive calculation based on data
    return performExpensiveCalculation(data);
  }, [data]);

  return <div>{result}</div>;
}
```
useCallback for Memoizing Event Handlers:

When you pass functions as props to child components, you can use the useCallback hook to memoize these functions. This ensures that the function reference remains the same unless its dependencies change, preventing unnecessary re-renders of child components.
```bash
import React, { useCallback } from 'react';

function ParentComponent() {
  const handleButtonClick = useCallback(() => {
    // Handle button click
  }, []);

  return <ChildComponent onClick={handleButtonClick} />;
}
```

## Code Splitting
Code splitting is the process of breaking up your JavaScript bundle into smaller, more manageable chunks. Instead of sending all of your JavaScript code to the client in a single large file, you can split it into smaller files, which are loaded on-demand as needed. This can significantly reduce the initial loading time of your application, especially for large-scale projects.

In React, code splitting can be achieved using dynamic imports, the import() function, or using Webpack's import() syntax. Here's an example of how you can do it:
```bash
// Before code splitting
import ComponentA from './ComponentA';
import ComponentB from './ComponentB';

// After code splitting
const ComponentA = React.lazy(() => import('./ComponentA'));
const ComponentB = React.lazy(() => import('./ComponentB'));
```

## Lazy Loading
Lazy Loading:
Lazy loading is closely related to code splitting. It refers to the practice of loading only the necessary assets (such as JavaScript, CSS, or images) when they are needed, rather than loading everything upfront when the user initially visits the web page.

Lazy loading can be applied not only to React components but also to other assets like images or stylesheets. This helps reduce the initial load time and improve the overall performance of your application.
```bash
import React, { lazy, Suspense } from 'react';

const LazyComponent = lazy(() => import('./LazyComponent'));

function App() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <LazyComponent />
      </Suspense>
    </div>
  );
}
```
## Virtualization in react
Virtualization involves rendering only the elements that are currently visible on the screen, rather than rendering the entire list. 
React-virtualized:
React-virtualized is a library for React that offers a set of high-quality components and utilities for implementing virtualization in your applications. It provides various components for efficiently rendering large lists, grids, and tables. Some of the key components and concepts in React-virtualized include:

List and Grid: The List and Grid components are used to render lists and grids with virtualization. They only render the items that are currently in the viewport and recycle them as you scroll.

Cell Measurer: This component helps with variable-sized items in a grid. It measures each item's size before rendering, which is useful when dealing with items of different heights or widths.

AutoSizer: AutoSizer is a higher-order component that automatically resizes its child components to fit within its container. This is especially useful when the container size changes dynamically.

WindowScroller: This component helps with virtualization in the case of a window-scoped list. It ensures that the list is sized correctly and scrolls with the window.

InfiniteLoader: InfiniteLoader simplifies the implementation of infinite scrolling by loading more data as the user scrolls down a list.



```bash
import React from 'react';
import { List } from 'react-virtualized';

const MyList = ({ data }) => (
  <List
    width={300}
    height={400}
    rowCount={data.length}
    rowHeight={50}
    rowRenderer={({ index, key, style }) => (
      <div key={key} style={style}>
        {data[index]}
      </div>
    )}
  />
);
```

## Immutability 
In React, immutability is a fundamental concept to ensure predictable and efficient rendering of components. When you need to update the state of a component or create a new state based on the previous state, you should always follow the principle of immutability. 



## Routes
Nested Routes in React:

Nested routes allow you to create complex, nested UI structures by rendering child components within a parent route's component. This is often used to build layouts with multiple sections or subpages.
```bash
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <Switch>
        <Route path="/dashboard" component={Dashboard} />
        <Route path="/profile" component={Profile} />
      </Switch>
    </Router>
  );
}

function Dashboard() {
  return (
    <div>
      <h1>Dashboard</h1>
      <Route path="/dashboard/overview" component={Overview} />
      <Route path="/dashboard/analytics" component={Analytics} />
    </div>
  );
}

function Overview() {
  return <h2>Overview</h2>;
}

function Analytics() {
  return <h2>Analytics</h2>;
}

function Profile() {
  return <h1>Profile</h1>;
}

// Example URLs:
// - /dashboard
// - /dashboard/overview
// - /dashboard/analytics
// - /profile
```


Dynamic Routes in React:

Dynamic routes allow you to handle URLs with variable parameters. These parameters are extracted from the URL and used to render specific content based on the parameter values. React Router supports dynamic routing with the use of route parameters.


```bash
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <Switch>
        <Route path="/product/:id" component={ProductDetail} />
      </Switch>
    </Router>
  );
}

function ProductDetail({ match }) {
  const { id } = match.params;
  return <h1>Product ID: {id}</h1>;
}

// Example URLs:
// - /product/123
// - /product/456
```


Route Guards in React:

Route guards are used to protect routes and control access based on certain conditions. In React Router, you can implement route guards using a combination of components and functions like Route and Redirect.

```bash
import { BrowserRouter as Router, Route, Redirect } from 'react-router-dom';

function App() {
  return (
    <Router>
      <Route path="/admin" render={() => {
        // Check if the user is authenticated; if not, redirect to the login page.
        if (!isAuthenticated) {
          return <Redirect to="/login" />;
        }
        // Render the admin component if authenticated.
        return <AdminDashboard />;
      }} />
      {/* Other routes */}
    </Router>
  );
}
```

### Optimize Images and Assets:

```bash
<img src="image.jpg" alt="Description" loading="lazy" />
```

```bash
import LazyLoad from 'react-lazyload';

// ...

<LazyLoad height={200} offset={100}>
  <img src="image.jpg" alt="Description" />
</LazyLoad>
```

