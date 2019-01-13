### 

###  CSS3/SASS

SCSS Mixins
```scss
@mixin square($size, $color) {
  width: $size;
  height: $size;
  background-color: $color;
}

.small-blue-square {
  @include square(20px, rgb(0,0,255));
}

.big-red-square {
  @include square(300px, rgb(255,0,0));
}
```

SCSS CrossBrowser Mixins
```scss
@mixin transform-tilt() {
  $tilt: rotate(15deg);
  -webkit-transform: $tilt; /* Ch <36, Saf 5.1+, iOS, An =<4.4.4 */
      -ms-transform: $tilt; /* IE 9 */
          transform: $tilt; /* IE 10, Fx 16+, Op 12.1+ */
}

.frame:hover { 
  @include transform-tilt; 
}
```

SCSS Extend
Extending should be used when we need similarly styled elements, which still differ in some detail. 

```scss
.dialog-button {
  box-sizing: border-box;
  color: #ffffff;
  box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.12);
  padding: 12px 40px;
  cursor: pointer;
}

.confirm {
  @extend .dialog-button;
  background-color: #87bae1;
  float: left;
}

.cancel {
  @extend .dialog-button;
  background-color: #e4749e;
  float: right;
}
```

SCSS Nesting
Organize your stylesheet in a way that resembles the HTML more closely.

```scss
ul {
  list-style: none;

  li {
    padding: 15px;
    display: inline-block;

    a {
      text-decoration: none;
      font-size: 16px;
      color: #444;
    }
  }
}
```

SCSS Operations
```scss
$width: 800px;

.container { 
  width: $width;
}

.column-half {
  width: $width / 2;
}

.column-fifth {
  width: $width / 5;
}
```

Install SASS
```
$ npm install sass-loader node-sass --save-dev
```
Update the webpack.config.js to chain sass-loader , then css-loader and then chain their output to style-loader (Loader-chaining)
```scss
Module:{
     Rules:[
             {
                 test:/\.(s*)css$/,
                 use:['style-loader','css-loader', 'sass-loader']
              }
      ]
   },
```


## JAVASCRIPT Questions
- **[What are the different scopes in javascript?](#jsq1)**
- **What is the Difference Between Function and Block Scope in JavaScript?**
- **What is variable hoisting?**
- What is the scope chain?
- What is an IIFE and why might you use it?
- What are function closures?
- What does the this keyword mean?
- What do the functions call, bind and apply do?
- What is the prototype chain?
- What is the difference between prototypal and classical inheritance?
- What is the Constructor OO pattern?
- What is the Prototype OO pattern?
- What is CORS? 
- What is JSONP?
- What is the difference between event capturing and bubbling?
- What is the difference between stopPropagation and preventDefault?

--------------------------------------------------------------------------
#### What are the different scopes in javascript? {#jsq1}

Global Scope, Local Scope, Block Scope (let)  
**Old school JavaScript**
Traditionally, JavaScript really only has two types of scope :  
**Global Scope** : Variables are known throughout the application, from the start of the application  
**Functional Scope** : Variables are known within the function they are declared in, from the start of the function  

**Modern JavaScript**
The most recent JavaScript specs now also allow a third scope :  
**Block Scope** : Variables are known within the block they are declared in, from the moment they are declared onwards  
let myVariable = "Some text";  
const myVar = "val";

--------------------------------------------------------------------------
#### What is the Difference Between Function and Block Scope in JavaScript?**

Function scope is within the function. (var is function scope.)
Block scope is within curly brackets. (let and const are block scope.)

--------------------------------------------------------------------------
#### What is variable hoisting?

Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).

--------------------------------------------------------------------------
#### What is scope chain?
JavaScript engine will try to find the value of the variable in the executing code's block scope (your room) and when unable to find the value there, 
it will go to its lexical outer scope (your house) and if not even found there, it will go to it’s outer scope’s outer scope(your colony) until it reaches the global scope, 
let’s say in your case can be the country, which in context of JavaScript will be window, if your working in browser environment.

--------------------------------------------------------------------------




### GENERAL CONCEPTS
- BOM Browser Object Model
* What Is Browser Object Model (BOM)? 
* Window Object 
* Window Object Timing 
* Screen Object 
* History Object 
* Navigator Object 
* Location Object 
* Cookies 

- DOM (Document Object Model)
* What Is Document Object Model (DOM)? 
* Document Object 
* Accessing Elements & Attributes - Part 01 
* Navigating Between Elements 
* Creating Elements & Attributes 
* Changing Element Content & Attributes Values 
* Modifyig Elements Style 
* Removing Elements & Attributes 
* Document Element Animation 

- Events
* JavaScript Events 
* Adding & Removing Event Handlers 
* Event Object 
* Internet Explorer 8 Event Model 
* Cross Browser Event Handling 
* JavaScript Errors 
* Strict Mode 

### Object-oriented Programming in JavaScript
- Object
* Object Literals
* Factories
* Constructors
* Constructor Property
* Functions are Objects
* Value vs Reference Types
* Adding or Removing Properties
* Enumerating Properties
* Abstraction
* Private Properties and Methods
* Getters and Setters

- Prototypes
* Inheritance
* Prototypes and Prototypical Inheritance
* Multi-level Inheritance
* Property Descriptors
* Constructor Prototypes
* Prototype vs. Instance Members
* Iterating Instance and Prototype Members
* Avoid Extending the Built-in Objects

- Prototypical Inheritance
* Creating Your Own Prototypical Inheritance
* Resetting the Constructor
* Calling the Super Constructor
* Intermediate Function Inheritance
* Method Overriding
* Polymorphism
* When to Use Inheritance

- ES6 Classes
* ES6 Classes
* Hoisting
* Static Methods
* The This Keyword
* Private Members Using Symbols
* Private Members Using WeakMaps
* Getters and Setters
* Inheritance
* Method Riding

- ES6 Modules
* Modules
* CommonJS Modules
* ES6 Modules
* ES6 Tooling
* Babel
* Webpack

### ES6 
- Syntax
* Let & Block Scope 
* Constants with "const" 
* Hoisting in ES6 
* Arrow Functions 
* Arrow Functions and the "this" Keyword 
* Functions and Default Parameters 
* Object Literal Extensions 
* The Rest Operator 
* The Spread Operator 
* The for-of Loop 
* Template Literals 
* Destructuring - Arrays 
* Destructuring - Objects 
* Destructuring - Summary 

- Classes
Alternative Plunker Setup
Modules Setup 
Modules Basics 
Import & Export Syntax 
Modules - Strict Mode and Global Scope 
Class Basics 
Classes & Prototypes 
Inheritance 
Inheritance & Prototypes 
Static Methods 
Classes & Modules 
Getters & Setters 
Extending Built-in Objects 

- Iterators and Generators
Iterator Basics 
Iterators in Action 
Creating a Custom, Iterateable Object 
Generators Basics 
Generators in Action 
Controlling Iterators with throw and return 

- Promises
Creating & Resolving Promises 
Rejecting Promises 
Chaining Promises 
Catching Errors 
Built-in Methods - All and Race 

-Maps and Sets
Maps - Creation & Adding Items 
Maps - Managing Items 
Maps - Looping through Maps 
Maps - Wrap Up 
The WeakMap 
Sets - Creation and Adding Items 
Sets - Managing Items 
Sets - Looping through Sets 


## Links
#### Javascript  
from [freeCodeCamp:](https://medium.freecodecamp.org/these-are-the-concepts-you-should-know-in-react-js-after-you-learn-the-basics-ee1d2f4b8030)  
Component Lifecycle, HOC higher-order components, State and setState, Context

from [creativebloq:](https://www.creativebloq.com/news/5-expert-reactjs-tips-that-you-need-to-know-today)  
Container and presentational components, Error boundaries, Portals, CSS with styled-components, Using React-specific linting, Snapshot testing with Jest, Code splitting, Server rendering, Internationalization

[React Various articles](https://react.christmas/)

#### CSS Links  
[cssreference.io](https://cssreference.io)

#### Various links
[github pages markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
