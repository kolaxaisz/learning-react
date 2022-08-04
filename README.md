# Learning React

## Table of Contents

## Chapter 1 : Welcome To React

### Resources
- [Why did we build React?](https://reactjs.org/blog/2013/06/05/why-react.html) 
  - by [Pete Hunt](https://twitter.com/floydophone)

React is a small library that doesn’t come with everything you might need out of
the box to build your application.

- We’re here to build cool stuff with tools that we like to
  use. 
- We’re here for the glory of shipping stuff that we’re proud to say we built.

### 1.1. - A Strong Foundation

A nice side effect of working with React is that it
can make you a stronger JavaScript developer by promoting patterns that are
readable, reusable, and testable.

- We cover foundational React knowledge to understand how to build
out a user interface with components. 
- Then we’ll learn to compose these components
and add logic with props and state. 
- We’ll cover React Hooks, which allow us to reuse
stateful logic between components.

### 1.2. - React’s Past and Future

React was first created by [Jordan Walke](https://www.linkedin.com/in/jordan-walke-1250b634/).

React was billed as a library: concerned with implementing a specific set of features, not providing a tool for every use case.

- The official [React blog](https://reactjs.org/blog/).

### 1.3. - Working with the Files

#### 1.3.1. - File Repository

- [GitHub repository associated with this book](https://github.com/moonhighway/learning-react)

#### 1.3.2. - React Developer Tools

- [React DevTools on GitHub repository](https://github.com/facebook/react-devtools)
  - [Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
  - [Firefox Extension](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)

#### 1.3.3. - Installing Node.js

```shell
# Check Node version
node -v
npm -v

#  Initialize the project and create a package.json file
npm init -y

# An alternative to npm is Yarn
npm i -g yarn

yarn add package-name
yarn remove package-name
```

- [React Documentation](https://facebook.github.io/react/index.html)
- [React Source](https://github.com/facebook/react)
- [React Blog](https://facebook.github.io/react/blog/)
- [React NPM](https://www.npmjs.com/package/react)
- [webpack Documentation](https://webpack.js.org/)
- [Jest Documentation](https://facebook.github.io/jest/)
- [React Router Documentation](https://reacttraining.com/react-router/)


## Chapter 2 : Emerging JavaScript

- [The kangax compatibility table](http://kangax.github.io/compat-table/esnext/)

### 2.1. - Declaring Variables
#### 2.1.1. - The `const` Keyword

- A constant is a variable that cannot be overwritten. 
- Once declared, you cannot change its value.

> <a id="code-02-01">**Listing 2.1** - variables could be overwritten ([run it](http://jsbin.com/gapoxa/1/edit?js,console))</a>

```js
// The value of a variable can change

var pizza = true
pizza = false
console.log(pizza)
```

We cannot reset the value of a constant variable, and it will generate a console error

> <a id="code-02-02">**Listing 2.2** - With const ❌ ([run it](https://jsbin.com/gapoxa/2/edit?js,console))</a>

```js
// ES6 introduces constants

const pizza = true
pizza = false
```

#### 2.1.2. - The `let` Keyword

JavaScript now has _lexical variable scope_.

> <a id="code-02-03">**Listing 2.3** - Without let ([run it](https://jsbin.com/gapoxa/3/edit?js,console))</a>

```js
// Variables cannot be scoped to code blocks

var topic = "JavaScript"

if (topic) {
  var topic = "React"
  console.log('block', topic)
}

console.log('global', topic) 
```

The `topic` variable inside the `if` block resets the value of `topic` outside of the block.

Using `let` protects the value of the global variable.

> <a id="code-02-04">**Listing 2.4** - With let ([run it](https://jsbin.com/gapoxa/4/edit?js,console))</a>

```js
// ES6 lexical variable scoping with let

var topic = "JavaScript"

if (topic) {
  let topic = "React"
  console.log('block', topic)
}

console.log('global', topic)
```

The value of `topic` is not reset outside of the block.

> <a id="code-02-05">**Listing 2.5** - Template Strings - Email ([run it](https://output.jsbin.com/gapoxa/9))</a>

```js
var div,
  container = document.getElementById("container");

for (var i = 0; i < 5; i++) {
  div = document.createElement("div");
  div.onclick = function() {
    alert("This is box #" + i);
  };
  container.appendChild(div);
}
```

> <a id="code-02-06">**Listing 2.6** - `for` loop with `let`</a>

```js
const container = document.getElementById("container");
let div;
for (let i = 0; i < 5; i++) {
  div = document.createElement("div");
  div.onclick = function() {
    alert("This is box #: " + i);
  };
  container.appendChild(div);
}
```

#### 2.1.3. - Template strings

- Template strings provide us with an alternative to string concatenation. 
- They also allow us to insert variables into a string. 
- You’ll hear these referred to as 
  - _template strings_, 
  - _template literals_, or 
  - _string templates_ interchangeably.

> <a id="code-02-07">**Listing 2.7** - Template Strings - HTML ([run it](https://jsbin.com/gapoxa/10/edit?js,output))</a>

```html
var article = {
  title: "Template Strings",
  body: `
    <div>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor</p>
      <p> laboris nisi ut aliquip ex ea commodo consequat.</p>
    </div>
  `
}

document.body.innerHTML = `
<section>
  <header>
      <h1>The HTML5 Blog</h1>
  </header>
  <article>
      <h2>${article.title}</h2>
      ${article.body}
  </article>
  <footer>
      <p>copyright ${new Date().getYear()} | The HTML5 Blog</p>
  </footer>
</section>
`
```

### 2.2. - Creating Functions
#### 2.2.1. - Function Declarations

> <a id="code-02-08">**Listing 2.8** - Function definition</a>

```javascript
function logCompliment() {
  console.log("You're doing great!");
}

logCompliment();
```
#### 2.2.2. - Function Expressions

Creating the function as a variable.

Function declarations are hoisted and function expressions are not. In other words, you can invoke a function before you write a function declaration. You cannot invoke a function created by a function expression.

> <a id="code-02-09">**Listing 2.9** - Function expression</a>

```javascript
// This works!
// Invoking the function before it's declared
hey();
// Function Declaration
function hey() {
  alert("hey!");
}
```

> <a id="code-02-10">**Listing 2.10** - function expression will cause an error</a>

```javascript
// Invoking the function before it's declared
hey();
// Function Expression
const hey = function() {
  alert("hey!");
};
// TypeError: hey is not a function
```

##### Passing arguments

> <a id="code-02-11">**Listing 2.11** - Pass named parameters to a function</a>

```javascript
const logCompliment = function(firstName) {
  console.log(`You're doing great, ${firstName}`);
};

logCompliment("Molly");
```

> <a id="code-02-12">**Listing 2.12** - Pass in a dynamic value as a parameter</a>

```javascript
const logCompliment = function(firstName, message) {
  console.log(`${firstName}: ${message}`);
};

logCompliment("Molly", "You're so cool");
```

##### Function returns

> <a id="code-02-13">**Listing 2.13** - Add a `return` statement to this function</a>

```javascript
const createCompliment = function(firstName, message) {
  return `${firstName}: ${message}`;
};

createCompliment("Molly", "You're so cool");

console.log(createCompliment("You're so cool", "Molly"));
```

#### 2.2.3. - Default Parameters

> <a id="code-02-14">**Listing 2.14** - Set up default strings for the parameters `name` and `activity`</a>

```javascript
function logActivity(name = "Shane McConkey", activity = "skiing") {
  console.log(`${name} loves ${activity}`);
}
```

> <a id="code-02-15">**Listing 2.15** - Default arguments can be any type, not just strings</a>

```javascript
const defaultPerson = {
name: {
first: "Shane",
last: "McConkey"
        },
favActivity: "skiing"
};

function logActivity(person = defaultPerson) {
  console.log(`${person.name.first} loves ${person.favActivity}`);
}
```

#### 2.2.4. - Arrow Functions

> <a id="code-02-16">**Listing 2.16** - With arrow functions, you can create functions without using the `function` keyword</a>

```javascript
const lordify = function(firstName) {
  return `${firstName} of Canterbury`;
};

console.log(lordify("Dale")); // Dale of Canterbury
console.log(lordify("Gail")); // Gail of Canterbury

// with arrow function
const lordify2 = firstName => `${firstName} of Canterbury`;

// Arrow Function
const lordify3 = (firstName, land) => `${firstName} of ${land}`;

console.log(lordify3("Don", "Piscataway")); // Don of Piscataway
console.log(lordify3("Todd", "Schenectady")); // Todd of Schenectady
```

> <a id="code-02-17">**Listing 2.17** - use curly braces</a>

```javascript
const lordify = (firstName, land) => {
  if (!firstName) {
    throw new Error("A firstName is required to lordify");
  }

  if (!land) {
    throw new Error("A lord must have a land");
  }

  return `${firstName} of ${land}`;
};

console.log(lordify("Kelly", "Sonoma")); // Kelly of Sonoma
console.log(lordify("Dave")); // ! JAVASCRIPT ERROR
```

##### Returning objects

> <a id="code-02-18">**Listing 2.18** - Wrap the object you’re returning with parentheses</a>

```javascript
  const person = (firstName, lastName) =>
({
  first: firstName,
  last: lastName
        })

  console.log(person("Brad", "Janson"));
```

##### Arrow functions and scope

> <a id="code-02-19">**Listing 2.19** - Always keeping scope in mind</a>

```javascript
const tahoe = {
  mountains: ["Freel", "Rose", "Tallac", "Rubicon", "Silver"],
  print: function(delay = 1000) {
    setTimeout(function() {
      console.log(this.mountains.join(", "));
    }, delay);
  }
};

tahoe.print(); // Uncaught TypeError: Cannot read property 'join' of undefined


// Working solution:

const tahoe = {
  mountains: ["Freel", "Rose", "Tallac", "Rubicon", "Silver"],
  print: function(delay = 1000) {
    setTimeout(() => {
      console.log(this.mountains.join(", "));
    }, delay);
  }
};

tahoe.print(); // Freel, Rose, Tallac, Rubicon, Silver

```

### 2.3. - Compiling JavaScript


### 2.4. - Objects and Arrays
#### 2.4.1. - Destructuring Objects
#### 2.4.2. - Destructuring Arrays
#### 2.4.3. - Object Literal Enhancement
#### 2.4.4. - The Spread Operator


### 2.5. - Asynchronous JavaScript
#### 2.5.1. - Simple Promises with Fetch
#### 2.5.2. - `Async`/`Await`
#### 2.5.3. - Building Promises

### 2.6. - Classes

### 2.7. - ES6 Modules
#### 2.7.1. - CommonJS

## Chapter 3 : Functional Programming with JavaScript
## Chapter 4 : Pure React
## Chapter 5 : React with JSX
## Chapter 6 : React State Management
## Chapter 7 : Enhancing Components with Hooks
## Chapter 8 : Incorporating Data
## Chapter 9 : Suspense
## Chapter 10 : Testing
## Chapter 11 : React Router
## Chapter 12 : React and the Server**