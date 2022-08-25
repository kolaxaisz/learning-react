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

> <a id="code-02-01">**Listing 2.1** - variables could be overwritten, without `const`</a> ([run it](http://jsbin.com/gapoxa/1/edit?js,console))
>  - [01-const.html](chapter-2/01-declaring-variables/01-const.html)

```javascript
// The value of a variable can change

var pizza = true
pizza = false
console.log(pizza)
```

We cannot reset the value of a constant variable, and it will generate a console error

> <a id="code-02-02">**Listing 2.2** - With const ❌ ([run it](https://jsbin.com/gapoxa/2/edit?js,console))</a>
> - [02-const.html](chapter-2/01-declaring-variables/02-const.html)

```js
// ES6 introduces constants

const pizza = true
pizza = false
```

#### 2.1.2. - The `let` Keyword

With let ([run it](https://jsbin.com/gapoxa/4/edit?js,console))
5. Loops with var ([run it](http://jsbin.com/gapoxa/5/edit?js,output))
6. Loops with let ([run it](http://jsbin.com/gapoxa/6/edit?js,output))

JavaScript now has _lexical variable scope_.

> <a id="code-02-03">**Listing 2.3** - Without let ([run it](https://jsbin.com/gapoxa/3/edit?js,console))</a>
> - [03-let.html](chapter-2/01-declaring-variables/03-let.html)

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
> - [04-let.html](chapter-2/01-declaring-variables/04-let.html)

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

> <a id="code-02-05">**Listing 2.5** - `for` loop with `var`</a>
> - [05-let.html](chapter-2/01-declaring-variables/05-let.html)

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
> - [06-let.html](chapter-2/01-declaring-variables/06-let.html)

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

> <a id="code-02-07">**Listing 2.7** - Without Template Strings - Simple Concatenation ([run it](https://jsbin.com/gapoxa/7/edit?js,console))</a>
> - [07-template-strings.html](chapter-2/01-declaring-variables/07-template-strings.html)

```javascript
const lastName = "Ferrell"
const middleName = "William"
const firstName = "John"

// string concatenation

console.log(lastName + ", " + firstName + " " + middleName)
```

> <a id="code-02-08">**Listing 2.8** - With Template Strings - Simple concatenation ([run it](https://jsbin.com/gapoxa/8/edit?js,console))</a>
> - [08-template-strings.html](chapter-2/01-declaring-variables/08-template-strings.html)

```javascript
const lastName = "Ferrell"
const middleName = "William"
const firstName = "John"

// ES6 template strings

console.log(`${lastName}, ${firstName} ${middleName}`)
```

- Template strings provide us with an alternative to string concatenation. 
- They also allow us to insert variables into a string. 
- You’ll hear these referred to as 
  - _template strings_, 
  - _template literals_, or 
  - _string templates_ interchangeably.

> <a id="code-02-09">**Listing 2.9** - Template Strings - Email ([run it](https://jsbin.com/gapoxa/10/edit?js,output))</a>
> - [09-template-strings.html](chapter-2/01-declaring-variables/09-template-strings.html)

```javascript
var lastName = "Ferrell"
var middleName = "William"
var firstName = "John"

var ticketAgent = "The iO Theater"
var event = "TJ & Dave"
var qty = 2
var price = 10

// ES6 template strings do not ignore whitespace

console.log(`

Hello ${firstName},

Thanks for ordering ${qty} tickets to ${event}.

Order Details
 ${firstName} ${middleName} ${lastName}
 ${qty} x $${price} = $${qty*price} to ${event}

You can pick your tickets up at will call 30 minutes before
the show.

Thanks,

${ticketAgent}

`)
```

> <a id="code-02-10">**Listing 2.10** - Template Strings - HTML ([run it](https://jsbin.com/gapoxa/10/edit?js,output))</a>
> - [10-template-strings.html](chapter-2/01-declaring-variables/10-template-strings.html)


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

1. Default Parameters ([run it](http://jsbin.com/yeqexu/1/edit?js,console))
2. Default Parameters with Objects ([run it](http://jsbin.com/yeqexu/2/edit?js,console))

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

1. Regular Function
   ([run it](http://jsbin.com/tegefa/1/edit?js,console))
2. Arrow Function ([run it](http://jsbin.com/tegefa/2/edit?js,console))
3. Arrow Function - Multiple Args ([run it](http://jsbin.com/tegefa/3/edit?js,console))
4. Multiple Args - One Line ([run it](http://jsbin.com/tegefa/4/edit?js,console))
5. Arrow Functions with if statements ❌ ([run it](http://jsbin.com/tegefa/5/edit?js,console))
6. Arrow Functions with errors ❌ ([run it](http://jsbin.com/tegefa/6/edit?js,console))
7. setTimeout ❌ ([run it](http://jsbin.com/tegefa/7/edit?js,console))
8. setTimeout with .bind ([run it](http://jsbin.com/tegefa/8/edit?js,console))
9. setTimeout with Arrow Function ([run it](http://jsbin.com/tegefa/9/edit?js,console))
10. setTimeout with 'this' problem ❌ ([run it](http://jsbin.com/tegefa/10/edit?js,console))
11. Showing 'this' problem ([run it](http://jsbin.com/tegefa/11/edit?js,console))


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
const person = (firstName, lastName) => ({
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

The only way to be sure that your code will work is to convert it 
to more widely compatible code before running it in the browser. 
This process is called compiling. One of the most popular tools for JavaScript compilation is [Babel](www.babeljs.io).

Babel has made it possible to use the latest features of JavaScript right away.
it’s transformed into syntax that can be interpreted by a wider range of browsers.

- [Babel REPL](https://babeljs.io/repl#?browsers=defaults%2C%20not%20ie%2011%2C%20not%20ie_mob%2011&build=&builtIns=false&corejs=3.21&spec=false&loose=false&code_lz=Q&debug=false&forceAllTransforms=false&shippedProposals=false&circleciRepo=&evaluate=false&fileSize=false&timeTravel=false&sourceType=module&lineWrap=true&presets=env%2Creact%2Cstage-2&prettier=false&targets=&version=7.18.12&externalPlugins=&assumptions=%7B%7D)

### 2.4. - Objects and Arrays

#### 2.4.1. - Destructuring Objects

Locally scope fields within an object and to declare which values will be used.

> <a id="code-02-20">**Listing 2.20** - Destructuring Assignment ([run it](http://jsbin.com/jukokaf/1/edit?js,console))</a>

```javascript
const sandwich =  {
bread: "dutch crunch",
meat: "tuna",
cheese: "swiss",
toppings: ["lettuce", "tomato", "mustard"]
}

let {bread, meat} = sandwich

console.log(bread, meat)

bread = "garlic"
meat = "turkey"

console.log(bread,meat)
console.log(sandwich.bread, sandwich.meat) 
```

> <a id="code-02-21">**Listing 2.21** - Destructuring with Arguments ([run it](http://jsbin.com/jukokaf/2/edit?js,console))</a>

```javascript
// Function with object arguments

var lordify = regularPerson => {
  console.log(`${regularPerson.firstname} of Canterbury`)
}

var regularPerson = {
firstname: "Bill",
lastname: "Wilson"
}

lordify(regularPerson)
```
> <a id="code-02-22">**Listing 2.22** - 4. Destructured Object Arguments ([run it](http://jsbin.com/jukokaf/3/edit?js,console))</a>

```javascript
// Destructuring object arguments

var lordify = ({firstname}) =>
console.log(`${firstname} of canterbury`)

var regularPerson = {
firstname: "Dale",
lastname: "Smith"
}

lordify(regularPerson)
```

> <a id="code-02-23">**Listing 2.23** - Nested object destructuring ([run it]())</a>

```javascript
const regularPerson = {
  firstname: "Bill",
  lastname: "Wilson",
  spouse: {
    firstname: "Phil",
    lastname: "Wilson"
  }
};

const lordify = ({ spouse: { firstname } }) => {
  console.log(`${firstname} of Canterbury`);
};

lordify(regularPerson); // Phil of Canterbury
```

> <a id="code-02-24">**Listing 2.24** - Destructuring Arrays ([run it](http://jsbin.com/jukokaf/4/edit?js,console))</a>

```javascript
// Destructuring Arrays

var [firstResort] = ["Kirkwood", "Squaw", "Alpine"]

console.log(firstResort)
```

> <a id="code-02-24">**Listing 2.24** - Destructuring with Comma Placeholders ([run it](http://jsbin.com/jukokaf/5/edit?js,console))</a>

```javascript
// More Array Destructuring

var [,,thirdResort] = ["Kirkwood", "Squaw", "Alpine"]

console.log(thirdResort)
```


#### 2.4.2. - Destructuring Arrays
#### 2.4.3. - Object Literal Enhancement

6. Object Literal Enhancement ([demo](https://rawgit.com/MoonHighway/learning-react/master/chapter-02/04-objects-and-arrays/06-object-literal-enhancement.html), [code](http://github.com/MoonHighway/learning-react/blob/master/chapter-02/04-objects-and-arrays/06-object-literal-enhancement.html), [bin](http://jsbin.com/jukokaf/6/edit?js,console))
7. Object Literal Enhancements with Functions ([demo](https://rawgit.com/MoonHighway/learning-react/master/chapter-02/04-objects-and-arrays/07-object-literal-enhancement.html), [code](http://github.com/MoonHighway/learning-react/blob/master/chapter-02/04-objects-and-arrays/07-object-literal-enhancement.html), [bin](http://jsbin.com/jukokaf/7/edit?js,console))
8. Literal Enhancements: The Old Way ([demo](https://rawgit.com/MoonHighway/learning-react/master/chapter-02/04-objects-and-arrays/08-object-literal-enhancement.html), [code](http://github.com/MoonHighway/learning-react/blob/master/chapter-02/04-objects-and-arrays/08-object-literal-enhancement.html), [bin](http://jsbin.com/jukokaf/8/edit?js,console))
9. Literal Enhancements Now ([demo](https://rawgit.com/MoonHighway/learning-react/master/chapter-02/04-objects-and-arrays/09-object-literal-enhancement.html), [code](http://github.com/MoonHighway/learning-react/blob/master/chapter-02/04-objects-and-arrays/09-object-literal-enhancement.html), [bin](http://jsbin.com/jukokaf/9/edit?js,console))

#### 2.4.4. - The Spread Operator

10. Spread Operator with Arrays ([run it](http://jsbin.com/jukokaf/10/edit?js,console))
11. Array Destructuring with .reverse() ([run it](http://jsbin.com/jukokaf/11/edit?js,console))
12. Spread Operator with Destructuring and .reverse() ([run it](http://jsbin.com/jukokaf/12/edit?js,console))
13. Destructuring and the Spread Operator ([run it](http://jsbin.com/jukokaf/13/edit?js,console))
14. Directions Functions ([run it](http://jsbin.com/jukokaf/14/edit?js,console))
15. Spread Operator with Objects ([run it](http://jsbin.com/jukokaf/15/edit?js,console))


### 2.5. - Asynchronous JavaScript
#### 2.5.1. - Simple Promises with Fetch

1. getFakeMembers ([run it](http://jsbin.com/pupojik/1/edit?js,console))
2. fetch members ([run it](http://jsbin.com/haguhe/1/edit?js,console))

#### 2.5.2. - `Async`/`Await`
#### 2.5.3. - Building Promises

### 2.6. - Classes

### 2.7. - ES6 Modules

1. The Constructor and the Prototype ([run it](http://jsbin.com/hoqileh/1/edit?js,console))
2. Classes ([run it](http://jsbin.com/hoqileh/2/edit?js,console))
3. Class Inheritance ([run it](http://jsbin.com/hoqileh/3/edit?js,console))

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