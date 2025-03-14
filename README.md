# Front-End-Developer-Role-

1.Null vs Undefined in JavaScript:

Undefined: Represents a variable that has been declared but has not been assigned a value. It also represents the value returned by a function that does not explicitly return a value.
javascript

let a;
console.log(a); // undefined
function doSomething() {}
console.log(doSomething()); // undefined
Null: Represents an intentional absence of any object value. It must be assigned to a variable explicitly.
javascript

let b = null;
console.log(b); // null
Event Delegation in JavaScript:

Event delegation is a technique where a single event listener is attached to a parent element to manage events for multiple child elements. This is useful when you have dynamically added elements or a large number of elements.
Example:
html

<ul id="parentList">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<script>
  document.getElementById('parentList').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
      console.log('Clicked on:', event.target.textContent);
    }
  });
</script>
CSS Display Properties:

Inline: Elements are displayed inline with the surrounding content.
Block: Elements are displayed as blocks, taking the full width available.
Inline-block: Elements are displayed as blocks, but flow like inline elements.
Flex: Elements are laid out using the flexbox model.
Example:
css

.inline-example {
  display: inline;
}

.block-example {
  display: block;
}

.inline-block-example {
  display: inline-block;
}

.flex-example {
  display: flex;
}
CSS Specificity:

Specificity determines which CSS rule is applied by the browser when multiple rules could apply to the same element.
Example:
css

/* Specificity examples */
.class-selector {
  color: red; /* specificity: 0,0,1,0 */
}

div p {
  color: blue; /* specificity: 0,0,0,2 */
}

#id-selector {
  color: green; /* specificity: 0,1,0,0 */
}
CORS (Cross-Origin Resource Sharing):

CORS is a security feature implemented by browsers that restricts web pages from making requests to domains other than the one serving the current web page.
To resolve CORS issues, you typically configure the server to include specific CORS headers (like Access-Control-Allow-Origin) that allow requests from specified origins.
CSS Preprocessors:

CSS preprocessors like Sass, Less, and Stylus extend CSS with variables, mixins, functions, and other features to make stylesheets more maintainable and scalable.
Example (using Sass):
scss

// Variables
$primary-color: #3498db;

// Mixin
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  border-radius: $radius;
}

// Usage
.button {
  background-color: $primary-color;
  @include border-radius(5px);
}
Closure in JavaScript:

A closure is a function bundled together with references to its surrounding state (lexical environment). It allows a function to access variables from an enclosing scope even after the parent function has finished executing.
Example:
javascript

function outerFunction() {
  let outerVariable = 'I am outer';

  function innerFunction() {
    console.log(outerVariable); // Accessing outerVariable from outer scope
  }

  return innerFunction;
}

let closureExample = outerFunction();
closureExample(); // Outputs: I am outer


8. LocalStorage vs SessionStorage in HTML5
Both localStorage and sessionStorage store data in the browser, but they have key differences:

Feature	localStorage	sessionStorage
Lifespan	Persists indefinitely until manually cleared	Only available for the session (deleted when the tab is closed)
Scope	Shared across all tabs/windows of the same origin	Only available in the tab it was set in
Size Limit	~5MB per origin	~5MB per origin
Example:

javascript

// localStorage example
localStorage.setItem("username", "JohnDoe");
console.log(localStorage.getItem("username")); // "JohnDoe"
localStorage.removeItem("username");

// sessionStorage example
sessionStorage.setItem("sessionKey", "123456");
console.log(sessionStorage.getItem("sessionKey")); // "123456"
sessionStorage.clear();
9. Web Components
Web Components are reusable custom HTML elements that encapsulate structure, style, and behavior.

Components of Web Components:

Custom Elements: Define new HTML elements.
Shadow DOM: Encapsulated styles and scripts.
HTML Templates: Reusable templates.
Example:

html

<template id="myTemplate">
  <style>
    p { color: blue; }
  </style>
  <p>Custom Web Component</p>
</template>

<script>
  class MyComponent extends HTMLElement {
    constructor() {
      super();
      let template = document.getElementById('myTemplate').content;
      let shadowRoot = this.attachShadow({ mode: 'open' });
      shadowRoot.appendChild(template.cloneNode(true));
    }
  }

  customElements.define('my-component', MyComponent);
</script>

<my-component></my-component>
10. Responsive Design
Responsive design ensures a website adapts to different screen sizes.

Techniques:

CSS Media Queries
Flexible Grid Layouts
Flexible Images
Example:

css

@media screen and (max-width: 768px) {
  body {
    background-color: lightblue;
  }
}
11. GET vs POST HTTP Methods
Feature	GET	POST
Data in URL?	Yes	No
Used for	Fetching data	Sending data
Idempotent?	Yes	No
Example:

javascript

fetch("https://api.example.com/data", { method: "GET" });

fetch("https://api.example.com/data", {
  method: "POST",
  body: JSON.stringify({ name: "John" }),
  headers: { "Content-Type": "application/json" }
});
12. data- Attributes in HTML5
Custom attributes to store extra information.

Example:

html

<button data-user-id="123">Click Me</button>

<script>
  document.querySelector("button").addEventListener("click", function() {
    alert(this.dataset.userId); // "123"
  });
</script>
13. Asynchronous JavaScript (Callbacks, Promises, Async/Await)
javascript

// Callback
function fetchData(callback) {
  setTimeout(() => callback("Data fetched"), 1000);
}

fetchData(console.log);

// Promise
let promise = new Promise((resolve) => setTimeout(() => resolve("Promise Resolved"), 1000));
promise.then(console.log);

// Async/Await
async function asyncExample() {
  let result = await promise;
  console.log(result);
}
asyncExample();
14. box-sizing Property in CSS
Controls how width and height are calculated.

Value	Includes padding/border?
content-box	No (default)
border-box	Yes
Example:

css

.box {
  width: 100px;
  padding: 10px;
  border: 5px solid black;
  box-sizing: border-box;
}
15. Document Object Model (DOM)
The DOM represents an HTML document as a tree structure.

Example (Manipulating DOM with JavaScript):

javascript

document.getElementById("demo").textContent = "Updated text";
16. Progressive Enhancement
A strategy that ensures core functionality works in all browsers while adding advanced features where supported.

Steps:

Start with basic HTML.
Enhance with CSS for better design.
Add JavaScript for interactive features.

17. Website Performance Optimization Techniques
Minify CSS, JavaScript
Use lazy loading for images
Optimize database queries
Use a Content Delivery Network (CDN)
Reduce HTTP requests

18. Handling Browser Compatibility Issues
Use feature detection (if ('fetch' in window) {})
Utilize CSS fallbacks
Use polyfills (e.g., Babel for ES6 features)
Test on multiple browsers
