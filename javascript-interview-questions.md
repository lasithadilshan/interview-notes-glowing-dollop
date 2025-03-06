# JavaScript Interview Questions and Answers

## Question 1: What is JavaScript?
**Answer:** JavaScript is a versatile, high-level programming language primarily used for enhancing web pages to provide interactive and dynamic user experiences. It is an interpreted language, which means it can be executed directly by the browser without needing prior compilation.

## Question 2: What are the data types supported by JavaScript?
**Answer:** JavaScript supports the following data types:
- Primitive types: `String`, `Number`, `Boolean`, `Null`, `Undefined`, `Symbol`, and `BigInt`
- Non-primitive types: `Object`

## Question 3: What is the difference between `let`, `const`, and `var`?
**Answer:**
- `var`: Function-scoped variable that can be re-declared and updated.
- `let`: Block-scoped variable that can be updated but not re-declared within the same block.
- `const`: Block-scoped variable that cannot be updated or re-declared. It must be initialized during declaration.

## Question 4: What are closures in JavaScript?
**Answer:** A closure is a function that retains access to its lexical scope even when the function is executed outside that scope. Closures allow functions to access variables from an enclosing scope or outer function even after the outer function has finished executing.

## Question 5: What is the difference between `==` and `===`?
**Answer:**
- `==`: Loose equality operator that compares two values for equality, converting them to a common type if necessary (type coercion).
- `===`: Strict equality operator that compares both value and type without performing type coercion.

## Question 6: What is an IIFE (Immediately Invoked Function Expression)?
**Answer:** An IIFE is a function that is executed immediately after it is defined. It is commonly used to create a private scope and avoid polluting the global namespace.

```javascript
(function() {
    console.log("This is an IIFE!");
})();
```

## Question 7: Explain the concept of promises in JavaScript.
**Answer:** Promises are objects representing the eventual completion or failure of an asynchronous operation. A promise can be in one of three states: pending, fulfilled, or rejected. Promises provide a way to handle asynchronous operations in a more readable and maintainable manner than callbacks.

## Question 8: What is the `this` keyword in JavaScript?
**Answer:** The `this` keyword refers to the object that is executing the current function. Its value depends on the context in which the function is called:
- In a method, `this` refers to the owner object.
- In a function, `this` refers to the global object (or `undefined` in strict mode).
- In an event handler, `this` refers to the element that received the event.

## Question 9: What is event delegation?
**Answer:** Event delegation is a technique in which a single event handler is used to manage multiple elements by taking advantage of event bubbling. Instead of attaching individual event handlers to each element, a common ancestor element is used to handle events, improving performance and reducing memory usage.

## Question 10: What is the difference between `call()`, `apply()`, and `bind()`?
**Answer:**
- `call()`: Invokes a function with a specified `this` context and arguments provided individually.
- `apply()`: Invokes a function with a specified `this` context and arguments provided as an array.
- `bind()`: Creates a new function with a specified `this` context and optional arguments to be prepended to the function's arguments list.

## Question 11: What is the purpose of the `async` and `await` keywords?
**Answer:** The `async` keyword is used to define asynchronous functions, which return a promise. The `await` keyword is used to pause the execution of an `async` function until the promise is resolved or rejected, allowing for more readable and synchronous-like code for handling asynchronous operations.

## Question 12: What are arrow functions, and how do they differ from regular functions?
**Answer:** Arrow functions are a concise syntax for writing functions in JavaScript. They differ from regular functions in several ways:
- They do not have their own `this` value and inherit it from the surrounding lexical context.
- They cannot be used as constructors and do not have a `prototype` property.
- They do not have their own `arguments` object.

```javascript
const add = (a, b) => a + b;
```

## Question 13: What is the Document Object Model (DOM)?
**Answer:** The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a document as a tree of nodes, allowing JavaScript to interact with and manipulate the content, structure, and style of web pages dynamically.

## Question 14: Explain the concept of hoisting in JavaScript.
**Answer:** Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that variables and functions can be used before they are declared. However, variable initializations are not hoisted.

## Question 15: What is the purpose of the `new` keyword in JavaScript?
**Answer:** The `new` keyword is used to create an instance of a user-defined object type or one of the built-in object types that have a constructor function. When used, it:
- Creates a new empty object.
- Sets the `prototype` of the new object to the constructor's `prototype`.
- Executes the constructor function with `this` set to the new object.
- Returns the new object.

```javascript
function Person(name) {
    this.name = name;
}

const person = new Person("John");
```