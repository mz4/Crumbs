# FRONTEND
---
## JAVASCRIPT

<br><br>
<h4>Execution Context</h4>
The environment in which any code is run.  
Javscript engine wraps the code into an execution context.
<br>
<h4>Javscript engine creates in the Execution Context</h4>
- Global Object Window (browser)  
- Special Object 'this'  
- Ref to outer environment  
---
<br><br>
<h4>Javscript Engine</h4>
it performs following two steps while executing any code:  

<h5>Creation Phase</h5>
- Run through your code & identifies variables & functions  
- Setup memory space for Variables & Functions - "Hoisting"  
- Hoisting, before code is executed, the JS Engine set asides memory space for Var & Func used inside the code.  
  ("undefined" is a special value assigned to variables that exists in the code but have not been set)

<h5>Execution Phase</h5>
- When the code is executed line-by-line (by JS interpreeter) it can access the variables defined inside Execution Context  
- Variable assignment are done in this phase 
---
<br><br>
<h4>Variable hoisting</h4>
Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function). 
---
<br><br>
<h4>Single Threaded (One command at the time) & Synchonous</h4>
Javascript for programmers behaves in a single threaded manner.  
And it is Synchronous, one line of code being executed at the time.
---
<br><br>
<h4>Scopes in javascript</h4>
- Global Scope  
- Local Scope  
- Block Scope (let)  

<h4>Old school JavaScript</h4>
Traditionally, JavaScript really only has two types of scope :  
<h4>Global Scope</h4>
Variables are known throughout the application, from the start of the application  
<h4>Functional Scope</h4>
Variables are known within the function they are declared in, from the start of the function  

<h4>Modern JavaScript</h4>
The most recent JavaScript specs now also allow a third scope :  

<h4>Block Scope</h4>
Variables are known within the block they are declared in, from the moment they are declared onwards  
let myVariable = "Some text";  
const myVar = "val";  

<h4>Difference Between Function and Block Scope</h4>
Function scope is within the function. (var is function scope.)  
Block scope is within curly brackets. (let and const are block scope.)  

<h4>Scope chain</h4>
JavaScript engine will try to find the value of the variable in the executing code's block scope (your room) and when unable to find the value there, it will go to its lexical outer scope (your house) and if not even found there, it will go to it’s outer scope’s outer scope(your colony) until it reaches the global scope, let’s say in your case can be the country, which in context of JavaScript will be window, if your working in browser environment.

---
<br><br>
<h4>Bind</h4>
We use the Bind () method primarily to call a function with the this value set explicitly.  
In other words, bind () allows us to easily set which specific object will be bound to this when a function or method is invoked.

---
<br><br>
<h4>Closures</h4>
A closure is an inner function that has access to the outer (enclosing) function’s variables — scope chain. The closure has three scope chains:  
it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables,  
and it has access to the global variables.  

```javascript
<script>
  var updateClickCount=(function(){
  var counter=0;

  return function(){
    ++counter;
     document.getElementById("spnCount").innerHTML=counter;
    }
})();
</script>

<html>
 <button onclick="updateClickCount()">click me</button>
  <div> you have clicked 
    <span id="spnCount">0</span>
 </div>
</html>
```

---
<br><br>
<h4>Promise</h4>
Promises are one way to deal with asynchronous code.  
A Promise is in one of these states:  
- Pending: initial state, neither fulfilled nor rejected.  
- Fulfilled: meaning that the operation completed successfully.  
- Rejected: meaning that the operation failed.  
  
A Promise object is created using the new keyword and its constructor.  
This constructor takes as its argument a function, called the "executor function".  
This function should take two functions as parameters.  
The first (resolve) is called when the asynchronous task completes successfully and returns the results of the task as a value.  
The second (reject) is called when the task fails, and returns the reason for failure, which is typically an error object.  

<h4>Promise example 1</h4>
```javascript
get('supplyData.json').then(function(response) {
  console.log("Success!", response);
}).catch(function(error) {
  console.log("Failed!", error);
})
```
  
<h4>Promise example 2</h4>
```javascript
var promise1 = new Promise(function(resolve, reject) {
  setTimeout(function() {
    resolve('foo');
  }, 300);
});

promise1.then(function(value) {
  console.log(value);
  // expected output: "foo"
});

console.log(promise1);
// expected output: [object Promise]
```

<h4>Promise example 3</h4>
```javascript
function myAsyncFunction(url) {
  return new Promise((resolve, reject) => {
    const xhr = new XMLHttpRequest();
    xhr.open("GET", url);
    xhr.onload = () => resolve(xhr.responseText);
    xhr.onerror = () => reject(xhr.statusText);
    xhr.send();
  });
}
```

<h4>Callback, Promises and Async</h4>
  
<h4>Callback:</h4>
A callback is a function that is passed to another function.  
When the first function is done, it will run the second function.  

Print a string after a random amount of time:
```js
function printString(string, callback){
  setTimeout(
    () => {
      console.log(string)
      callback()
    }, 
    Math.floor(Math.random() * 100) + 1
  )
}
```

Let’s try to print the letters A, B, C in that order:
```js
function printAll(){
  printString("A", () => {
    printString("B", () => {
      printString("C", () => {})
    })
  })
}
printAll()
```

---

<h4>Promises vs callaback</h4>
Promises try to fix callback nesting problem. 
In our function lets use Promises:
```js
function printString(string){
  return new Promise((resolve, reject) => {
    setTimeout(
      () => {
       console.log(string)
       resolve()
      }, 
     Math.floor(Math.random() * 100) + 1
    )
  })
}
```

```js
function printAll(){
  printString("A")
  .then(() => {
    return printString("B")
  })
  .then(() => {
    return printString("C")
  })
}
printAll()
```

<h4>Await:</h4>
```js
async function printAll(){
  await printString("A")
  await printString("B")
  await printString("C")
}
printAll()
```

<h4>Object is an array?</h4>
```
var d = []
console.log(Object.prototype.toString.call(d));
```
---

<h4>Prototype</h4>
[Prototype link](https://tylermcginnis.com/beginners-guide-to-javascript-prototype/)  
Every function in JavaScript has a prototype property that references an object.  
pattern Prototypal Instantiation.  

```javascript
function Animal (name, energy) {
  this.name = name
  this.energy = energy
}

Animal.prototype.eat = function (amount) {
  console.log(`${this.name} is eating.`)
  this.energy += amount
}

Animal.prototype.sleep = function (length) {
  console.log(`${this.name} is sleeping.`)
  this.energy += length
}

Animal.prototype.play = function (length) {
  console.log(`${this.name} is playing.`)
  this.energy -= length
}

const leo = new Animal('Leo', 7)
const snoop = new Animal('Snoop', 10)
```

Without using new keyword, we have to explicitly create a reference:
Looking back at our Animal constructor, the two most important parts were creating the object and returning it.  
Without creating the object with Object.create, we wouldn’t be able to delegate to the function’s prototype on failed lookups.   Without the return statement, we wouldn’t ever get back the created object.  
```javascript
function Animal (name, energy) {
  let animal = Object.create(Animal.prototype)
  animal.name = name
  animal.energy = energy

  return animal
}

Animal.prototype.eat = function (amount) {
  console.log(`${this.name} is eating.`)
  this.energy += amount
}

Animal.prototype.sleep = function (length) {
  console.log(`${this.name} is sleeping.`)
  this.energy += length
}

Animal.prototype.play = function (length) {
  console.log(`${this.name} is playing.`)
  this.energy -= length
}

const leo = Animal('Leo', 7)
const snoop = Animal('Snoop', 10)

leo.eat(10)
snoop.play(5)
```

ES6 syntax  
In 2015, EcmaScript (the official JavaScript specification) 6 was released with support for Classes and the class keyword.  
Let’s see how our Animal constructor function above would look like with the new class syntax.

```javascript
class Animal {
  constructor(name, energy) {
    this.name = name
    this.energy = energy
  }
  eat(amount) {
    console.log(`${this.name} is eating.`)
    this.energy += amount
  }
  sleep(length) {
    console.log(`${this.name} is sleeping.`)
    this.energy += length
  }
  play(length) {
    console.log(`${this.name} is playing.`)
    this.energy -= length
  }
}

const leo = new Animal('Leo', 7)
const snoop = new Animal('Snoop', 10)
```

<h4>Array methods</h4>
We can see all the array’s methods by simply logging Array.prototype.  
console.log(Array.prototype)

/*
  concat: ƒn concat()
  constructor: ƒn Array()
  copyWithin: ƒn copyWithin()
  entries: ƒn entries()
  every: ƒn every()
  fill: ƒn fill()
  filter: ƒn filter()
  find: ƒn find()
  findIndex: ƒn findIndex()
  forEach: ƒn forEach()
  includes: ƒn includes()
  indexOf: ƒn indexOf()
  join: ƒn join()
  keys: ƒn keys()
  lastIndexOf: ƒn lastIndexOf()
  length: 0n
  map: ƒn map()
  pop: ƒn pop()
  push: ƒn push()
  reduce: ƒn reduce()
  reduceRight: ƒn reduceRight()
  reverse: ƒn reverse()
  shift: ƒn shift()
  slice: ƒn slice()
  some: ƒn some()
  sort: ƒn sort()
  splice: ƒn splice()
  toLocaleString: ƒn toLocaleString()
  toString: ƒn toString()
  unshift: ƒn unshift()
  values: ƒn values()
*/

---

<h4>this keyword</h4>
It's a special identifier keyword that's automatically defined in the scope of every function.    
It is based on how the function is called.
Call-site because it's the only thing that matters for this binding.  

```javascript
function baz() {
    // call-stack is: `baz`
    // so, our call-site is in the global scope

    console.log( "baz" );
    bar(); // <-- call-site for `bar`
}

function bar() {
    // call-stack is: `baz` -> `bar`
    // so, our call-site is in `baz`

    console.log( "bar" );
    foo(); // <-- call-site for `foo`
}

function foo() {
    // call-stack is: `baz` -> `bar` -> `foo`
    // so, our call-site is in `bar`

    console.log( "foo" );
}

baz(); // <-- call-site for `baz`
```

<h4>Default binding</h4>
Standalone function invocation.  
In this case "this" points at the global object.  

```javascript
function foo() {
	console.log( this.a );
}

var a = 2;

foo(); // 2
```

<h4>Implicit Binding</h4>
Because obj is the this for the foo() call, this.a is synonymous with obj.a.  

```javascript
function foo() {
	console.log( this.a );
}

var obj = {
	a: 2,
	foo: foo
};

obj.foo(); // 2
```

<h4>Explicit Binding</h4>
All functions you will create, do have access to call(..) and apply(..).
How do these utilities work? They both take, as their first parameter, an object to use for the this, and then invoke the  function with that this specified. 
Since you are directly stating what you want the this to be, we call it explicit binding.  

```javascript
function foo() {
	console.log( this.a );
}

var obj = {
	a: 2
};

foo.call( obj ); // 2
```

<h4>new Binding</h4>
In JS, constructors are just functions that happen to be called with the new operator in front of them.  
They are not attached to classes, nor are they instantiating a class.  
They are not even special types of functions.  
So new is the final way that a function call's this can be bound. We'll call this new binding.

```javascript
function foo(a) {
	this.a = a;
}

var bar = new foo( 2 );
console.log( bar.a ); // 2
```

<h4>Determine "this"</h4>
Is the function called with new (new binding)? If so, this is the newly constructed object.
```js
var bar = new foo()
```

Is the function called with call or apply (explicit binding), even hidden inside a bind hard binding? If so, this is the explicitly specified object.
```js
var bar = foo.call( obj2 )
```

Is the function called with a context (implicit binding), otherwise known as an owning or containing object? If so, this is that context object.
```js
var bar = obj1.foo()
```

Otherwise, default the this (default binding). If in strict mode, pick undefined, otherwise pick the global object.

```js
var bar = foo()
```

---

<h4>Objects</h4>
Objects come in two forms: the declarative (literal) form, and the constructed form.  
Note: It's extremely uncommon to use the "constructed form" for creating objects as just shown.  
You would pretty much always want to use the literal syntax form.  

Literal:  
```javascript
var myObj = {
	key: value
	// ...
};
```

Constructed:    
```javascript
var myObj = new Object();
myObj.key = value;
```

---

<h4>Object Types</h4>
- string
- number
- boolean
- null
- undefined
- object






---



## ES6
<h4>Spread Operator 1</h4>  
```javascript
const userInfo = { isAuthenticated: false }  
const action = { isAuthenticated: true, type: 'nope' }  
const res = { ...userInfo, isAuthenticated: action.isAuthenticated };   
console.log(res);  // { isAuthenticated: true } 
```

<h4>Spread Operator 2</h4>
```javascript
var mid = [3, 4];  
var arr = [1, 2, ...mid, 5, 6];  
console.log(arr);  // [ 1, 2, 3, 4, 5, 6 ]
```

<h4>Spread Operator 3</h4>
```javascript
let nums = [1, 2, 3];
let abcs = ['a', 'b', 'c'];
let alphanum = [ ...nums, ...abs ]; // [1, 2, 3, 'a', 'b', 'c']
```

<h4>Destructuring 1</h4>
```javascript
var address = {
  city: "London",
  state: "UK",
  zip: 1334
};
let {city, state, zip} = address;

log(city); // 'London'
log(state); // 'UK'
log(zip); // 1334
```

<h4>Destructuring 2</h4>
```javascript
var address = {
  city: "London",
  state: "UK",
  zip: 1334
};
let {city: c, state: s, zip: z} = address;
log(c, s, z); // 'London UK 1334'
```

<h4>Destructuring 3</h4>
```javascript
var person = {name: 'Aaaaaa', age: 35};
displayPerson(person);

function displayPerson({name, age}) {
  // do something with name and age to display them
}
```

<h4>Destructuring 4</h4>
```javascript
var person = {name: 'Aaaaaa', age: 35};
let {name, age, address} = person; // error!
let {name, age, ?address} = person; // OK
let ?{name, age, address} = person; // OK
```

<h4>Destructuring 5</h4>
```javascript
var nums = [1, 2, 3, 4];
doSomething(nums);

function doSomething([first, second, ...others]){
  log(first);   //logs 1
  log(second);  //logs 2
  log(others);  //logs [3, 4]
}
```

<h4>Arrow functions 1</h4>
Specifying parameters:
```javascript
    () => { ... } // no parameter
     x => { ... } // one parameter, an identifier
(x, y) => { ... } // several parameters
```

<h4>Specifying a body:</h4>
```javascript
x => { return x * x }  // block
x => x * x  // expression, equivalent to previous line
```

<h4>Arrow function 2</h4>
```javascript
const phraseSplitterEs6 = phrase => phrase.split(" ");
```

<h4>Arrow function 3</h4>
```javascript
var docLogEs6 = () => { console.log(document); };
```

<h4>Arrow function 4</h4>
```javascript
const smartPhones = [
  { name:'iphone', price:649 },
  { name:'Galaxy S6', price:576 },
  { name:'Galaxy Note 5', price:489 }
];

// ES6
const prices = smartPhones.map(smartPhone => smartPhone.price);
console.log(prices); // [649, 576, 489]
```

<h4>Nested keys</h4>
Check existance of nested keys.
```javascript
var update_progress = (((data || {}).Oem || {}).Name || {}).UpdateProgress;
if (update_progress !== null) {
    console.log(JSON.stringify(data));
}
```

<h4>Difference setInterval and setTimeout</h4>
setTimeout(): It is a function that execute a JavaScript statement AFTER x interval.
```js
setTimeout(function () {
    something();
}, 1000); // Execute something() 1 second later.
```

setInterval(): It is a function that execute a JavaScript statement EVERY x interval.
```js
setInterval(function () {
    somethingElse();
}, 2000); // Execute somethingElse() every 2 seconds.
```

<h4>Performance analysis</h4>
```js
console.time("start");
```
// do something
```js
console.timeEnd("end")
```
// this will cause the browser to print time elapsed between start and end.

---

<h4>Various examples of Loops, Promises, callback</h4>

Promise
```javascript
const promise = new Promise (
  function(resolve, reject) {
    if (...something) {
      resolve('data');
    }
    if (...somethingelse) {
      reject('error');
    }
  }
)

promise.then(
  function(data) {...}
).catch(
  function(error) {...}
)
```

Axios
```javascript
axios.get('http://.....')
  .then(
    function(response) {
      ....
    }
  )
  .catch(
    function(error) {
      ....
    }
  )
  .finally(
    function() {
      ....
    }
  )
```

```js
async function getUser() {
  try {
    const output = await axios.get()
  }
  catch {
    ...
  }
}
```

---

Callback functions  

setInterval
```js
setInterval(function(){
  console.log('hello);
}, 1000);
```

```js
const list = ['uno', 'due', 'tre'];

const newList = list.map(function(v) {
  return v + 'a';
}).filter(function(v) {
  return v.value > 'aa';
}
)
```

```js
button.addEventListener('click', function(e){
  ...
})
```

```js
setTimeout(func, 1000);
```

```js
Object.entries(users).forEach(entry, val) =>
{
  const [key, value] = entry;
}
```

---

## REACT

<h4>State</h4>
React is all about one-way data flow down the component hierarchy.  
State is created in the component and stays in the component.  
It can be passed to a children as its props.  


<h4>Basic Concepts</h4>
- JSX
- Rendering Elements
- Components Functional/Container
- State and Lifecycle
- Handling Events
- Conditional Rendering
- Lists and Keys
- Forms

<h4>JSX</h4>
```javascript
<MyComponent message={'hello world'} />
```

<h4>Rendering elements</h4>
```javascript
class TodoList extends React.Component {
  render() {
    return (
      <ul>
        {this.props.items.map(item => (
          <li key={item.id}>{item.text}</li>
        ))}
      </ul>
    );
  }
}
```

<h4>Stateless function component - sfc</h4>
```javascript
const | = props => {
  return ( | );
};

export default |;
```

<h4>State and lifecycle</h4>
```
Mounting  
These methods are called in the following order:  
* constructor()  
* static getDerivedStateFromProps()  
* render()  
* componentDidMount()  
  
Updating  
An update can be caused by changes to props or state. These methods are called in the following order when a component is being re-rendered:  
* static getDerivedStateFromProps()  
* shouldComponentUpdate()  
* render()  
* getSnapshotBeforeUpdate()  
* componentDidUpdate()    
  
Unmounting  
This method is called when a component is being removed from the DOM:  
* componentWillUnmount()  
```

<h4>Handling events</h4>
```javascript
function ActionLink() {
  function handleClick(e) {
    e.preventDefault();
    console.log('The link was clicked.');
  }

  return (
    <a href="#" onClick={handleClick}>
      Click me
    </a>
  );
}
```

<h4>Conditional rendering</h4>
```javascript
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
    </div>
  );
}
```

<h4>List and Keys</h4>
```javascript
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {numbers.map((number) =>
        <ListItem key={number.toString()}
                  value={number} />

      )}
    </ul>
  );
}
```

<h4>Forms</h4>
```javascript
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

---

<h4>React Fragment</h4>
Fragments let you group a list of children without adding extra nodes to the DOM.
```js
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

<h4>Import CSS</h4>
```
import './styles/style.css'
```

<h4>Declare state</h4>
```
export class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {count: props.initialCount};
  }
```

<h4>defaultProps example</h4>
```javascript
Notification.defaultProps = {
  actionTitle: '',
  selectedElements: {},
  actionLogs: [],
};
```

<h4>propTypes example</h4>
```javascript
Notification.propTypes = {
  actionTitle: PropTypes.string,
  isOpen: PropTypes.bool.isRequired,
  close: PropTypes.func.isRequired,
  elementTitle: PropTypes.objectOf(PropTypes.any),
  selectedElements: PropTypes.arrayOf(PropTypes.any),
};
```

<h4>Import statement - imr</h4>
```javascript
import React from 'react';
```

<h4>Import React and Component - imrc</h4>
```javascript
import React, { Component } from 'react';
```

<h4>Make a Class Component and export - cc</h4>
```javascript
class | extends Component {
  state = { | },
  render() {
    return ( | );
  }
}

export default |;
```

<h4>componentDidMount - cdm</h4>
```javascript
componentDidMount() {
  |
}
```

<h4>componentDidUpdate - cdu</h4>
```javascript
componentDidUpdate(prevProps, prevState) {
  |
}
```

<h4>setState - ss</h4>
```javascript
this.setState({ | : | });
```

<h4>render - ren</h4>
```javascript
render() {
  return (
    |
  );
}
```

<h4>export example with mapStateToProps, mapDispatchToProps</h4>
```javascript
export default connect(mapStateToProps, mapDispatchToProps)(Name);
```

<h4>mapStateToProps example</h4>
```javascript
const mapStateToProps = (state) => {
  return {
    elements: state.refreshRaidElements.raidElements,
    controllers: state.refreshControllers.controllers,
    waitingLogs: state.watingLogs.wating_action_logs,
  };
};
```

<h4>mapDispatchToProps</h4>
Import actions  
```javascript
import { checkboxClicked, selectedIndex } from '../../../store/actions/ElementsAction';
```
  
<h4>Emit action </h4> 
```javascript
this.props.selectedRaidIndex(id);
```
  
<h4>Dispatch actions</h4>  
```javascript
const mapDispatchToProps = (dispatch) => {
  return {
    checkboxClicked: id => dispatch(checkboxClicked(id)),
    selectedIndex: id => dispatch(selectedIndex(id)),
  };
};
```

<h4>React Redux Thunk</h4>  

Actions in Redux are dispatched synchronously.   
Thankfully though, Redux allows for middleware that sits between an action being dispatched and the action reaching the reducers.  

**Redux Thunk is a middleware** that lets you call action creators that return a function instead of an action object.   
That function receives the store’s dispatch method, which is then used to dispatch regular synchronous actions inside  
the body of the function once the asynchronous operations have completed.  
  
Install redux-thunk  
```
npm install redux-thunk
```

<h4>Apply middleware to app store.</h4>  
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { createStore, applyMiddleware } from 'redux';
import { Provider } from 'react-redux';
import thunk from 'redux-thunk';

import rootReducer from './reducers';
import App from './App';

// use applyMiddleware to add the thunk middleware to the store
const store = createStore(rootReducer, applyMiddleware(thunk));

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```

The most common use-case for Redux Thunk is for communicating asynchronously with an external API to retrieve or save data.  
**AddTodo.jsx**  
```javascript
import { connect } from 'react-redux';
import { addTodo } from '../actions';
import NewTodo from '../components/NewTodo';

const mapDispatchToProps = dispatch => {
  return {
    onAddTodo: todo => {
      dispatch(addTodo(toto));
    }
  };
};

export default connect(
  null,
  mapDispatchToProps
)(NewTodo);
```

**actions/index.jsx**  
```javascript
import {
  ADD_TODO_SUCCESS,
  ADD_TODO_FAILURE,
  ADD_TODO_STARTED,
  DELETE_TODO
} from './types';

import axios from 'axios';

export const addTodo = ({ title, userId }) => {
  return dispatch => {
    dispatch(addTodoStarted());

    axios
      .post(`https://jsonplaceholder.typicode.com/todos`, {
        title,
        userId,
        completed: false
      })
      .then(res => {
        dispatch(addTodoSuccess(res.data));
      })
      .catch(err => {
        dispatch(addTodoFailure(err.message));
      });
  };
};

const addTodoSuccess = todo => ({
  type: ADD_TODO_SUCCESS,
  payload: {
    ...todo
  }
});

const addTodoStarted = () => ({
  type: ADD_TODO_STARTED
});

const addTodoFailure = error => ({
  type: ADD_TODO_FAILURE,
  payload: {
    error
  }
});
```

**reducers/todoReducers.jsx**  
```javascript
import {
  ADD_TODO_SUCCESS,
  ADD_TODO_FAILURE,
  ADD_TODO_STARTED,
  DELETE_TODO
} from '../actions/types';

const initialState = {
  loading: false,
  todos: [],
  error: null
};

export default function todosReducer(state = initialState, action) {
  switch (action.type) {
    case ADD_TODO_STARTED:
      return {
        ...state,
        loading: true
      };
    case ADD_TODO_SUCCESS:
      return {
        ...state,
        loading: false,
        error: null,
        todos: [...state.todos, action.payload]
      };
    case ADD_TODO_FAILURE:
      return {
        ...state,
        loading: false,
        error: action.payload.error
      };
    default:
      return state;
  }
}
```

<h4>React Portals</h4>

Portals provide a way to render children into any DOM node.  
The first argument is any renderable child.  
The second argument should be a reference to the DOM node where the renderable child will be rendered.  

```javascript
ReactDOM.createPortal(child, container)
```

React portal example
```javascript
import React from "react";
import ReactDOM, { render } from "react-dom";
import { overlay, overlayContent } from "./overlayStyles";

class Overlay extends React.Component {
  constructor(props) {
    super(props);
    // Create container DOM element and append to DOM.
    this.overlayContainer = document.createElement("div");
    document.body.appendChild(this.overlayContainer);
  }

  componentWillUnmount() {
    document.body.removeChild(this.overlayContainer);
  }

  render() {
    return ReactDOM.createPortal(
      <div style={overlay}>
        <div style={overlayContent}>{this.props.children}</div>
      </div>,
      this.overlayContainer
    );
  }
}

class App extends React.Component {
  state = {
    showOverlay: false
  };

  toggleOverlay = () => {
    this.setState(prevState => {
      return { showOverlay: !prevState.showOverlay };
    });
  };

  render() {
    return (
      <div>
        <h1>Dashboard</h1>
        {this.state.showOverlay && (
          <Overlay>
            <div>
              Overlay Content{" "}
              <button onClick={this.toggleOverlay}>Close</button>
            </div>
          </Overlay>
        )}
        <button onClick={this.toggleOverlay}>Open Overlay</button>
      </div>
    );
  }
}

render(<App />, document.getElementById("root"));
```



<h4>React Hooks</h4>
Hooks are a new addition in React 16.8.  
They let you use state and other React features without writing a class.  
Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes.  
Our goal is for Hooks to cover all use cases for classes as soon as possible.  
It is an early time for Hooks, and some third-party libraries might not be compatible with Hooks at the moment.  

Lifecycle methods
constructor: Function components don’t need a constructor.  
componentDidMount, componentDidUpdate, componentWillUnmount: The useEffect Hook can express all combinations of these (including less common cases)  

We recommend to split state into multiple state variables based on which values tend to change together.  
```javascript
function Box() {
  const [position, setPosition] = useState({ left: 0, top: 0 });
  const [size, setSize] = useState({ width: 100, height: 100 });

  useEffect(() => {
    function handleWindowMouseMove(e) {
      setPosition({ left: e.pageX, top: e.pageY });
    }
    // ...
```

<h4>State Hooks</h4>
```javascript
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

<h4>Declaring multiple state variables</h4>

```javascript
function ExampleWithManyStates() {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
}
```

<h4>Effect Hook</h4>

The Effect Hook, useEffect serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes,  
but unified into a single API.  By default, React runs the effects after every render — including the first render.  

Effects may also optionally specify how to “clean up” after them by returning a function.  

```javascript
import React, { useState, useEffect } from 'react';

function FriendStatus(props) {
  const [isOnline, setIsOnline] = useState(null);

  function handleStatusChange(status) {
    setIsOnline(status.isOnline);
  }

  useEffect(() => {
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);

    return () => {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });

  if (isOnline === null) {
    return 'Loading...';
  }
  return isOnline ? 'Online' : 'Offline';
}
```

<h4>Reuse logic in another component.</h4>
It takes friendID as an argument, and returns whether our friend is online.  

```javascript
import React, { useState, useEffect } from 'react';

function useFriendStatus(friendID) {
  const [isOnline, setIsOnline] = useState(null);

  function handleStatusChange(status) {
    setIsOnline(status.isOnline);
  }

  useEffect(() => {
    ChatAPI.subscribeToFriendStatus(friendID, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(friendID, handleStatusChange);
    };
  });

  return isOnline;
}
```

Reuse friend online/offline in multiple components

```javascript
function FriendStatus(props) {
  const isOnline = useFriendStatus(props.friend.id);

  if (isOnline === null) {
    return 'Loading...';
  }
  return isOnline ? 'Online' : 'Offline';
}
```

```javascript
function FriendListItem(props) {
  const isOnline = useFriendStatus(props.friend.id);

  return (
    <li style={{ color: isOnline ? 'green' : 'black' }}>
      {props.friend.name}
    </li>
  );
}
```

---

## REST API  

<h4>Definition</h4>
REST stands for Representational State Transfer. 
It is web standards based architecture and uses HTTP Protocol. 
 
A Web API conforming to the REST architectural style is a REST API.  
A web service is a collection of standards used for exchanging data between applications or systems.  
Web services based on REST Architecture are known as RESTful web services.  
These webservices uses HTTP methods to implement the concept of REST architecture.  
A RESTful web service usually defines a URI, Uniform Resource Identifier a service,  
which provides resource representation such as JSON and set of HTTP Methods.

A REST API is composed of four distinct resource archetypes: document, collection, store, and controller  

<h4>URI Format</h4>
generic URI syntax as shown below:  
```
URI = scheme "://" authority "/" path [ "?" query ] [ "#" fragment ]
```

<h4>Good Practices</h4>
Forward slash separator (/) indicates a hierarchical relationship  
underscores (_) should not be used in uris  
Trailing forward slash (/) should not be included in uris  
hyphens (-) should be used to improve readability of uris  
lowercase letters should be preferred in uri paths  
crud function names should not be used in uris  
query component of a URI may be used to filter collections or stores

<h4>Request Methods</h4>
CRUD requests: DELETE, GET, POST, PUT  
HEAD retrieve metadata.  
OPTIONS retrieve metadata of resource’s available interactions.  

<h4>Some Responses status</h4>
200 success
201 new resource has been created
202 Accepted, start of an asynchronous action
204 No Content body left blank
301 Moved Permanently
400 Bad Request Indicates a nonspecific client error
401 Unauthorized
402 Forbidden
404 Not Found
405 Method Not Allowed

<h4>HTTP Headers</h4>
Various forms of metadata may be conveyed through the entity headers.    
  
<h4>Request headers</h4>
Cookie: HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to the user’s request.  
The client may store it and send it back with the next request to the same server.  
User-Agent: identify the application type, operating system, software vendor
Host: The Host request header specifies the domain name of the server  
X-Requested-With: Mainly used to identify AJAX requests.  
Accept-Language which languages the client is able to understand  
  
<h4>Response headers</h4>
Content-Type  
Content-Length  size of the response body  
Set-Cookie used to send cookies from the server to the client.

<h4>Body Format</h4>
A REST API commonly uses a response message’s entity body to help convey the state of a request message’s identified resource.   
Today, the most commonly used text formats is JSON.

<h4>API Documentation</h4>
- Resource Description  
  example from MailChimp Campaign resource
  ```
  Campaigns are how you send emails to your Mailchimp list. 
  Use the Campaigns API calls to manage campaigns in your Mailchimp account.
  ```
  Resource Description consists of 1-3 sentences.
  Resources usually have various endpoints to access the resource and multiple methods for each endpoint.  
  Sometimes the general resource isn’t described; instead, it just groups the endpoints.
  Although the resource isn’t described, descriptions may be added for each of the endpoints.  

- Endpoint and Methods  
  The endpoints indicate how you access the resource, 
  The method indicates the allowed interactions (such as GET, POST, or DELETE) with the resource.  
  Endpoints usually have brief descriptions similar to the overall resource description but shorter.  
  ```
  POST /campaigns	Create a new campaign
  GET /campaigns	Get all campaigns
  GET /campaigns/{campaign_id}	Get information about a specific campaign
  PATCH /campaigns/{campaign_id}	Update the settings for a campaign
  DELETE /campaigns/{campaign_id}	Delete a campaign
  ```
- Parameters  
  Parameters are options you can pass with the endpoint to influence the response. 
  There are four types of parameters: header parameters, path parameters, query string parameters, and request body parameters.  
    
  <strong>Header parameters</strong> are included in the request header. Usually, the header just includes authorization parameters.  

  <strong>Path parameters</strong> are part of the endpoint itself and are not optional. For example, in the following endpoint,  
  {user} and {bicycleId} are required path parameters:  
  ```
  /service/myresource/user/{user}/bicycles/{bicycleId}
  ```
    
  <strong>Query string parameters</strong> appear after a question mark (?) in the endpoint. The question mark followed by the parameters and  
  their values is referred to as the “query string.”  
  ```
  /surfreport/{beachId}?days=3&units=metric&time=1400
  ```

  <strong>Body parameters</strong>: with POST requests (where you’re creating something), you submit a JSON object in the request body.

- Request example
  The request example includes a sample request using the endpoint, showing some parameters configured.  
  ```
  curl -u "username:password" 
  -H "Content-Type:application/json" 
  -X GET "https://api.callfire.com/v2/texts?limit=50&offset=200"
  ```
- Response example  
  The response example shows a sample response from the request example; the response schema defines all possible elements in the response.
  The response lets developers know if the resource contains the information they want, the format, and how that information is structured and labeled. 
  The description of the response is known as the response schema. The response schema documents the response in a more comprehensive, general way,  
  listing each property that could possibly be returned, what each property contains, the data format of the values, the structure, and other details.  
  The definition of the response is called the schema or model.

  ```
  {
    "Context": "ualize",
    "Destination": "http://aaaa.com/aaa",
    "EventTypes": [
        "StatusChange",
        "ResourceAdded",
        "ResourceRemoved"
    ],
    "Id": "3a5f20212134",
    "Name": "EventSubscription",
    "Oem": {},
    "Protocol": "Redfish"
  }
  ```

[API Documentation example](https://idratherbewriting.com/learnapidoc/docapis_finished_doc_result.html)  
[API Docs list](https://idratherbewriting.com/learnapidoc/pubapis_apilist.html#list_api_doc_sites)  

<h4>OpenApi</h4>
OpenAPI is a specification for describing REST APIs.  

Display frameworks such as Swagger UI can parse the OpenAPI specification and generate interactive documentation that lets users try out endpoints  
while learning about the API.  
With OpenAPI, you have a set of JSON objects, with a specific schema that defines their naming, order, and contents.  

In the OpenAPI specification, your endpoints are paths.  
Instead of writing following example in a text editor, use [Swagger Editor](http://editor.swagger.io/).  
Instead of coding the OpenAPI specification document by hand, you can also auto-generate it from annotations in your programming code.  
```json
paths:
  /pets:
    get:
      summary: List all pets
      operationId: listPets
      tags:
        - pets
      parameters:
        - name: limit
          in: query
          description: How many items to return at one time (max 100)
          required: false
          schema:
            type: integer
            format: int32
      responses:
        '200':
          description: An paged array of pets
          headers:
            x-next:
              description: A link to the next page of responses
              schema:
                type: string
          content:
            application/json:    
              schema:
                $ref: "#/components/schemas/Pets"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
```
After you have a valid OpenAPI specification document that describes your API, you can then feed this specification to different tools  
to parse it and generate the interactive documentation.  
Probably the most common tool used to parse the OpenAPI specification is Swagger UI.  

<h4>OpenAPI root level</h4>
- openapi  
indicate the version of the OpenAPI spec to validate against.  
- info  
The info object contains basic information about your API, including the title, a description, version, link to the license,  
link to the terms of service, and contact information.  
- servers  
In the servers object, you specify the basepath used in your API requests.  
- paths  
listing the paths (endpoints) and their allowed operations (methods).  

```
paths:
  /weather:
    get:
      tags:
      summary:
      description:
      operationId:
      externalDocs:
      parameters:
      responses:
```

```
paths:
  /pet/findByStatus:
    get:
      tags:
      - "pet"
      summary: "Finds Pets by status"
      description: "Multiple status values can be provided with comma separated strings"
      operationId: "findPetsByStatus"
      produces:
      - "application/xml"
      - "application/json"
      parameters:
      - name: "status"
        in: "query"
        description: "Status values that need to be considered for filter"
        required: true
        type: "array"
        items:
          type: "string"
          enum:
          - "available"
          - "pending"
          - "sold"
          default: "available"
        collectionFormat: "multi"
      responses:
        200:
          description: "successful operation"
          schema:
            type: "array"
            items:
              $ref: "#/definitions/Pet"
        400:
          description: "Invalid status value"
      security:
      - petstore_auth:
        - "write:pets"
        - "read:pets"
```
- components  
```
The components object can contain these objects:

schemas
responses
parameters
examples
requestBody
headers
securitySchemes
links
callbacks
```
- security  
Swagger UI supports four authorization schemes:  
  
- API key  
- HTTP  
- OAuth 2.0  
- Open ID Connect  

```
The security object specifies the security or 
authorization protocol used when submitting requests.
``` 
- tags  
```
At the root level, the tags object lists all the tags that are used in the operation objects
```
- externalDocs  
Here’s an example of an externalDocs object:  
```
externalDocs:
  description: API Documentation
  url: https://openweathermap.org/api
```



<!-- https://idratherbewriting.com/learnapidoc/pubapis_swagger_intro.html -->

<h4>Axios - HTTP client</h4>
Axios install  
```
npm install axios --save
```

Basic get request
```
  componentDidMount() {
    axios.get(`https://jsonplaceholder.typicode.com/users`)
      .then(res => {
        const persons = res.data;
        this.setState({ persons });
      })
  }
```

Multiple get requests
```
let URL1 = "https://www.something.com"
let URL2 = "https://www.something1.com
let URL3 = "https://www.something2.com"

const promise1 = axios.get(URL1);
const promise2 = axios.get(URL2);
const promise3 = axios.get(URL3);

Promise.all([promise1, promise2, promise3]).then(function(values) {
  console.log(values);
});
```

---

## GRAPHQL
<h4>About</h4>
GraphQL is a query language for your API, and a server-side runtime for executing queries by using a type system you define for your data.  

- Open source and created by Facebook  
- Gives clients the power to describe exactly what data they want  
- Can sit in front of any existing API because its just a query language  

REST APIs have shown to be too inflexible to keep up with the rapidly changing requirements of the clients that access them.  
GraphQL was developed to cope with the need for more flexibility and efficiency! It solves many of the shortcomings and inefficiencies that developers experience when interacting with REST APIs.  
When working with REST APIs, data is loaded from specific endpoints.  
Instead of having multiple endpoints that return fixed data structures, GraphQL APIs typically only expose a single endpoint. This works because the structure of the data that’s returned is not fixed. Instead, it’s completely flexible and lets the client decide what data is actually needed.

<h4>GraphQL vs REST</h4>
- GraphQL only has one URL.  
  Request details are in a POST body (or GET)  
- In REST, shape and size of data resource is determined by the server,  
  In Graphql its determined by the query (request)  
- In REST, you have to male multiple API calls to retrieve relational data,  
  in GraphQL you can start with entry resource and traverse all the connections in one request  
- In REST, the shape of the response is determined by whom ever created the server,   
  in GraphQL the shape is determined by the query  

 
<h4>Terminology</h4>  
- Query - Queries specify which endpoints we want to call, how we want the response to look  
- Fields - Properties that comprise the shape of a response  
- Type - A collection of fields that make up a specific queryable object.  
- Mutation - A special kind of GraphQL query that causes changes to the data available on the backend  
- Schema - A special kind of document that describes how a GraphQL endpoint can receive and send information  
- Query Language - The syntax we use to write GraphQL queries that retrieve data from an endpoint  
- Self-documenting API - An API that can be easily understood just by reading its schema -- no extra documentation needed  
  
<h4>Basic Query</h4>
```
{
  allPersons {
    name
  }
}
```
allPersons is called the root field of the query.  
Everything that follows the root field, is called the payload of the query.  

This will return:
```
{
  "allPersons": [
    { "name": "Johnny" },
    { "name": "Sarah" },
    { "name": "Alice" }
  ]
}
```

it allows for naturally querying nested information.
```
{
  allPersons {
    name
    age
    posts {
      title
    }
  }
}
```

Each field can have zero or more arguments if that’s specified in the schema.  
For example, the allPersons field could have a last parameter to only return up to a specific number of persons. 
```
{
  allPersons(last: 2) {
    name
  }
}
```

<h4>Mutations</h4>
It allows to reate, update and delete.
Create a new Person:
```
mutation {
  createPerson(name: "Bob", age: 36) {
    name
    age
  }
}
```

GraphQL types have unique IDs that are generated by the server when new objects are created:
```
type Person {
  id: ID!
  name: String!
  age: Int!
}
```

Directly ask for the id in the payload of the mutation
```
mutation {
  createPerson(name: "Alice", age: 36) {
    id
  }
}
```

<h4>Subscriptions</h4>
Realtime connection to the server in order to get immediately informed about important events.  
Subscriptions represent a stream of data sent over to the client.  

Subscribe on events happening on the Person type:  
```
subscription {
  newPerson {
    name
    age
  }
}
```

After a client sent this subscription to a server, a connection is opened between them.  
Then, whenever a new mutation is performed that creates a new Person, the server sends the information about this person over to the client:  
```
{
  "newPerson": {
    "name": "Jane",
    "age": 23
  }
}
```

<h4>Schema</h4>
It specifies the capabilities of the API and defines how clients can request the data.  
There are some special root types:  
```
type Query { ... }
type Mutation { ... }
type Subscription { ... }
```

To enable the allPersons-query that we saw before, the Query type would have to be written as follows:  
```
type Query {
  allPersons: [Person!]!
}
```

<h4>Schema example</h4>
```
type Query {
  allPersons(last: Int): [Person!]!
}

type Mutation {
  createPerson(name: String!, age: Int!): Person!
}

type Subscription {
  newPerson: Person!
}

type Person {
  name: String!
  age: Int!
  posts: [Post!]!
}

type Post {
  title: String!
  author: Person!
}
```

With the ideal declarative data fetching approach, a client shouldn’t be doing more than the following two steps:

- Describe data requirements  
- Display data in UI  

GraphQL client libraries like Relay or Apollo will enable you to do.  
They provide the abstraction that you need to be able to focus on the important parts of your application rather than having to deal with the repetitive implementation of infrastructure.  

---

<h4>Example 1</h4>
 <h5>Frontend graphql query in react with Apollo</h5>
```
npm install -g npx // (npx comes with npm 5.2+ and higher)
npx create-react-app react-graphql-test
npm start
```

Dependencies install  
```
npm install apollo-boost react-apollo graphql-tag graphql
```

apollo-boost: Package containing reccomended Apollo Client setup  
react-apollo: View layer integration for React  
graphql-tag: Necessary for parsing your GraphQL queries  
graphql: Also parses your GraphQL queries  


in App.js  
```
import ApolloClient from "apollo-boost";
const client = new ApolloClient({
  uri: "[Insert URI of GraphQL endpoint]"
});
```

Connect the instance of ApolloClient to the React app
```
import { ApolloProvider } from "react-apollo";
...
const App = () => (
  <ApolloProvider client={client}>
    <div>
      <h2>My first Apollo app</h2>
    </div>
  </ApolloProvider>
);
```

Retrieve a list of Courses.  
Query component makes it extremely easy to embed the GraphQL query directly in the JSX code of the component.  
```
import React from 'react';
import { Query } from "react-apollo";
import gql from "graphql-tag";
const Courses = () => (
  <Query
    query={gql`
      {
        allCourses {
          id
          title
          author
          description
          topic
          url
        }
      }
    `}
  >
    {({ loading, error, data }) => {
      if (loading) return <p>Loading...</p>;
      if (error) return <p>Error :(</p>;
      return data.allCourses.map(({ id, title, author, description, topic, url }) => (
        <div key={id}>
          <p>{`${title} by ${author}`}</p>
        </div>
      ));
    }}
  </Query>
);
export default Courses;
```

---

<h4>Example 2</h4>
```

<!-- 
  https://www.howtographql.com/react-apollo/1-getting-started/
-->

```

## SOCKET

socket client

socket install 
```
npm i socket.io-client
```

```
const io = require('socket.io-client')('https://'.concat(document.domain).concat(':').concat(location.port));
export default io;
```

io Emit from client
```
import io from './components/common/io';
io.emit('populate_table', { table_name: 'users_table' });
```

io Receive
```
io.on('isloggedin', (payload) => {
  ...
}
```

Remove listeners
```
io.removeAllListeners('action_response');
```

socketio server flask
```
from app.server import socketio
@socketio.on(socket_names.UPLOAD_LICENSE)
def upload_license_action(args):
    """
    Upload a new license file.
    """
    data = args['data']
    uuid = args['uuid']
    sid = request.sid
    user_store.update_previous_connection(sid)
    socketio.emit(socket_names.ACTION_TIME, {
        'action_time': now(sid)}, room=sid)
    with thread_lock:
        socketio.start_background_task(
            target=upload_license,
            kwargs={'data': data, 'sid': sid, 'uuid': uuid})
```

---

## CSS3/SASS

<h4>CSS Architecture</h4>
<h4>SMACSS</h4>
SMACSS method consists on organizing CSS rules in five different categories:  

- Basic: Default elements styles. It doesn’t include any class or ID selectors.
- Layout: It divides the content into sections (header, footer, primary content).
- Module: Those components that can be reused. Modules sit inside Layout components.
- State: The rules that establish the state of our modules. A state is something that augments and overrides all other styles.
- Theme: It would allow the more visual aspects of the project.

---

<h4>Display property</h4>
- block: element starts on a new line and stretches out to the left and right as far as it can. 
- inline: element not on a new line and doesnt stretch.
- inline-block: element can have width and height. 
- flex: Displays an element as a block-level flex container.
- grid: Displays an element as a block-level grid container.
- ...

<h4>Position</h4>
- static: is not positioned in any special way.
- relative: the element is positioned relative to its normal position.
- fixed - the element is positioned related to the browser window.
- absolute - the element is positioned absolutely to its first positioned parent.

<h4>Box Model</h4>
- Content: The content of the box, where text and images appear
- Padding: Clears an area around the content. The padding is transparent
- Border: A border that goes around the padding and content
- Margin: Clears an area outside the border. The margin is transparent

<h4>Box sizing</h4>
The box-sizing property can make building CSS layouts easier and a lot more intuitive.  
padding and border add the width of an object.  
With box sizing the padding and border of that element no longer increase its width.

```css
html {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*, *:before, *:after {
  -webkit-box-sizing: inherit;
  -moz-box-sizing: inherit;
  box-sizing: inherit;
}
```

<h4>Centering Things</h4>

- Centering line of texts:  
```css
p { text-align: center }
```

- Centering a block or image:  
```css
p.blocktext {
    margin-left: auto;
    margin-right: auto;
    width: 8em
}
<p class="blocktext">
```

- Centering vertically:  
The trick is to specify that the outer block is to be formatted as a table cell, because the contents of a table cell can be centered vertically.  
```css
DIV.container {
  min-height: 10em;
  display: table-cell;
  vertical-align: middle;
}

<DIV class="container">
  <P>This small paragraph
</DIV>
```

- Centering vertically CSS3:
```css
<div class=container3>
  <p>This paragraph…
</div>

div.container3 {
  height: 10em;
  position: relative 
}
div.container3 p {
  margin: 0;
  position: absolute;
  top: 50%;
  transform: translate(0, -50%) 
}
```

- Centering with flex:
```css
div.container5 {
  height: 10em;
  display: flex;
  align-items: center 
}
div.container5 p {
  margin: 0 
}
```

- Centering horizontally and vertically with css level 3
```css
<div class=container4>
  <p>Centered!
</div>

div.container4 {
  height: 10em;
  position: relative 
}

div.container4 p {
  margin: 0;
  background: yellow;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%)
}
```

- Centering horizontally and vertically in flex
```css
div.container6 {
  height: 10em;
  display: flex;
  align-items: center;
  justify-content: center 
}
div.container6 p {
  margin: 0 
}
```

- Centering in the viewport in css 3
```css
<html>
  <style>
    body {
      background: white 
    }
    section {
      background: black;
      color: white;
      border-radius: 1em;
      padding: 1em;
      position: absolute;
      top: 50%;
      left: 50%;
      margin-right: -50%;
      transform: translate(-50%, -50%) 
    }
  </style>
  <section>
    <h1>Nicely centered</h1>
    <p>This text block is vertically centered.
    <p>Horizontally, too, if the window is wide enough.
  </section>
```

<h4>Formatting CSS - based on Airbnb style guide</h4>
- Use soft tabs (2 spaces) for indentation.
- Prefer dashes over camelCasing in class names.
- Underscores and PascalCasing are okay if you are using BEM (see OOCSS and BEM below).
- Do not use ID selectors.
- When using multiple selectors in a rule declaration, give each selector its own line.
- Put a space before the opening brace { in rule declarations.
- In properties, put a space after, but not before, the : character.
- Put closing braces } of rule declarations on a new line.
- Put blank lines between rule declarations.
- Prefer line comments (// in Sass-land) to block comments.

Bad
```css
.avatar{
    border-radius:50%;
    border:2px solid white; }
.no, .nope, .not_good {
    // ...
}
#lol-no {
  // ...
}
```

Good
```css
.avatar {
  border-radius: 50%;
  border: 2px solid white;
}

.one,
.selector,
.per-line {
  // ...
}
```

<h4>Use a combination of OOCSS and BEM</h4>
- OOCSS, or “Object Oriented CSS”, is an approach for writing CSS that encourages you to think about your stylesheets as a collection of “objects”:  
reusable, repeatable snippets that can be used independently throughout a website.  
  It is based on two main principles:  
  a. Separate structure from skin  
  b. Separate containers from content (you should avoid using child selectors whenever it’s possible.)
  
- BEM, or “Block-Element-Modifier”, is a naming convention for classes in HTML and CSS.  

<h4>Responsive Design</h4>
<h4>Defined by three characteristics</h4>
- Flexible grid-based layout  
- Media queries (CSS3)  
- Images that resize  


<h4>FLEXBOX</h4>
<h4>Parent Flex Container</h4>
```
display: flex | inline-flex;
flex-direction: row | row-reverse | column | columnreverse;
flex-wrap: wrap | nowrap | wrap-reverse; flex-flow (shorthand for flex-direction and flexwrap)
justify-content: flex-start | flex-end | center | spacebetween | space-around | space-evenly;
align-items: flex-start | flex-end | center | baseline | stretch;
align-content (cross axis - adjust to largest item): flex-start | flex-end | center | stretch | spacebetween | space-around;
```

<h4>Children Flex Items</h4>
```
order: <integer>;
flex-grow: <number>;
flex-shrink: <number>;
flex-basis: <length> | auto;
flex: shorthand for grow, shrink, and basis (default: 0 1 auto)
align-self: overrides alignment set on parent
```

<h4>GRID</h4>
<h4>Grid Container</h4>
```
display: grid | inline-grid;
grid-template-columns: <track-size> ... | <line-name> <track-size> ...;
grid-template-rows: <track-size> ... | <line-name> <track-size> ...;
grid-template-areas: <grid-area-name>;
grid-template: A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.
grid-column-gap: <line-size>;
grid-row-gap: <line-size>;
grid-gap: A shorthand for grid-row-gap and grid-column-gap
justify-items: start | end | center | stretch;
align-items: start | end | center | stretch;
place-items: place-items sets both the align-items and justify-items properties in a single declaration.
justify-content: start | end | center | stretch | space-around | space-between | space-evenly;	
align-content: start | end | center | stretch | space-around | space-between | space-evenly;
place-content: place-content sets both the align-content and justify-content properties in a single declaration.
grid-auto-columns: <track-size> ...;
grid-auto-rows: <track-size> ...;
grid-auto-flow: row | column | row dense | column dense
grid: A shorthand for setting all of the following properties in a single declaration: grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow
```

<h4>Grid Items</h4>
```
grid-column-start: <number> | <name> | span <number> | span <name> | auto
grid-column-end: <number> | <name> | span <number> | span <name> | auto
grid-row-start: <number> | <name> | span <number> | span <name> | auto
grid-row-end: <number> | <name> | span <number> | span <name> | auto
grid-column: <start-line> / <end-line> | <start-line> / span <value>;
grid-row: <start-line> / <end-line> | <start-line> / span <value>;
grid-area: <name> | <row-start> / <column-start> / <row-end> / <column-end>;
justify-self: start | end | center | stretch;
align-self: start | end | center | stretch;
place-self: center;
```

<h4>Media Queries</h4>
```
/* 
  ##Device = Desktops
  ##Screen = 1281px to higher resolution desktops
*/
@media (min-width: 1281px) {}
/* 
  ##Device = Laptops, Desktops
  ##Screen = B/w 1025px to 1280px
*/
@media (min-width: 1025px) and (max-width: 1280px) {}
/* 
  ##Device = Tablets, Ipads (portrait)
  ##Screen = B/w 768px to 1024px
*/
@media (min-width: 768px) and (max-width: 1024px) {}
/* 
  ##Device = Tablets, Ipads (landscape)
  ##Screen = B/w 768px to 1024px
*/
@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {}
/* 
  ##Device = Low Resolution Tablets, Mobiles (Landscape)
  ##Screen = B/w 481px to 767px
*/
@media (min-width: 481px) and (max-width: 767px) {}
/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/
@media (min-width: 320px) and (max-width: 480px) {}
```

<h4>BEM (Block Element Modifier)</h4>
```
<div class="block__element block__element--modifier">
  Hallo
</div>
```

```
.block {
  &__element {
    background: blue;
    &--modifier {
      color: white;
    }
  }
}
```

<h4>BEM with Sass</h4>
```
.person {
  &__hand {/* Styles */}

  &__leg {/* Styles */}

  &--male {
    /* Styles */

    &__hand {
      /* Styles */

      &--left {/* Styles */}

      &--right {/* Styles */}
    }

    &__leg {
      /* Styles */

      &--left {/* Styles */}

      &--right {/* Styles */}
    }
  }

  &--female {
    /* Styles */

    &__hand {
      /* Styles */

      &--left {/* Styles */}

      &--right {/* Styles */}
    }

    &__leg {
      /* Styles */

      &--left {/* Styles */}

      &--right {/* Styles */}
    }
  }
}
```
<h4>Install SASS</h4>
```
$ npm install sass-loader node-sass --save-dev
```

<h4>Update the webpack.config.js to chain sass-loader , then css-loader and then chain their output to style-loader (Loader-chaining)</h4>
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

<h4>SCSS Import</h4>
```scss
@import 'reset';
```

<h4>SCSS Variables</h4>
```scss
$zHeader: 2000;
$zOverlay: 5000;
$zMessage: 5050;

.header {
  z-index: $zHeader;
}
.overlay {
  z-index: $zOverlay;
}
.message {
  z-index: $zMessage;
}
```

<h4>SCSS Mixins</h4>
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

<h4>SCSS CrossBrowser Mixins</h4>
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

<h4>SCSS Extend</h4>
<h4>Extending should be used when we need similarly styled elements, which still differ in some detail. </h4>
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

<h4>SCSS Nesting</h4>
<h4>Organize your stylesheet in a way that resembles the HTML more closely.</h4>
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

<h4>Nested Pseudo Classes and Pseudo Elements </h4>
```scss
.weather {
  @extend %module;
  @include transition(all 0.3s ease-out);
  background: LightCyan;
  &:hover {
    background: DarkCyan;
  }
  &::before {
    content: "";
    display: block;
  }
  ...
}
```

<h4>SCSS Operations  </h4>
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

<h4>Selectors</h4>

<h4>Descendant Selector</h4>
all p elements inside div elements  
```
div p {
  background-color: yellow;
}
```
  
<h4>Child Selector</h4>
all p elements that are immediate children of a div element  
```
div > p {
  background-color: yellow;
}
```

<h4>Adjacent Sibling Selector</h4>
all p elements that are placed immediately after div elements  
```
div + p {
  background-color: yellow;
}
```

<h4>General Sibling Selector</h4>
all p elements that are siblings of div elements  
```
div ~ p {
  background-color: yellow;
}
```

---

## TESTING
Enzyme is a JavaScript Testing utility created for react, maintained by Airbnb that makes it easier to assert, manipulate, and traverse your React Components' output.  
Jest is a test framework managed by Facebook.  
install enzyme along with an Adapter corresponding to the version of react.  
```
npm i --save-dev enzyme enzyme-adapter-react-16
```
Jest Setup with React:  
```
npm install --save-dev jest babel-jest babel-preset-env babel-preset-react react-test-renderer
```
Add into babel configuration  
```
"env": {
  "test": {
    "presets": ["es2015", "react", "stage-0"]
  }
}
```

useful for debug
```
console.log(wrapper.debug());
```

```javascript
import configureStore from 'redux-mock-store';
import { shallow } from 'enzyme';
import { shallowWithIntl, loadTranslationObject } from 'enzyme-react-intl';
import toJson from 'enzyme-to-json';
import renderer from 'react-test-renderer';
import translations from '../src/translations/en.json';
import io from '../src/components/common/io';

loadTranslationObject(translations);

const initialState = {
  open: false,
  errors: [],
  elements: [
    {
      id: '0x00000000001',
      size: '300000',
      cache_size: '256',
      state: 'online',
    },
    {
      id: '0x00000000002',
      size: '2000',
      cache_size: '128',
      state: 'offline',
    }
  ]
}
const mockStore= configureStore();
let store;
let wrapper;
let instance;
beforeEach(() => {
  store = mockStore(initialState);
  wrapper = shallowWithIntl(<Raids store={store} {...defaultProps} />).shallow().dive();
  instance = wrapper.instance();
});

describe('Check Initial State', () => {
  it('Open set to false', () => {
    expect(wrapper.state('open')).toBe(false);
  });
  it('Errors set to empty array', () => {
    expect(wrapper.state('errors')).toEqual([]);
  });
});

describe('Simulate Events', () => {
  it('Calls checkErrors on button click', () => {
    wrapper.instance().checkErrors = jest.fn();
    wrapper.find('.buttonSubmit').simulate('click');
    expect(wrapper.instance().checkErrors).toHaveBeenCalled();
  });
});

describe('Component Methods', () => {
  it('Tests state value after calling method', () => {
    const expectedValue = 'AAAAAAAAAA';
    instance.selectName(expectedValue);
    expect(wrapper.state(['elementName'])).toBe(expectedValue);
  });
});

describe('Snapshots tests', () => {
  it('Tests component rendering snapshot', () => {
    expect(toJson(wrapper)).toMatchSnapshot();
  });
  it('DisplayErrors match snapshot', () => {
    const instance = wrapper.instance();
    const displayErrors = instance.displayErrors();
    const errorRender = renderer.create(displayErrors).toJSON();
    expect(errorRender).toMatchSnapshot();
  });
});

describe('Component Rendering', () => {
  it('Renders header', () => {
    const header = wrapper.find('ModalHeader').exists();
    expect(header).toBe(true);
  });
  it('Renders content', () => {
    const content = wrapper.find('ModalContent').exists();
    expect(content).toBe(true);
  });
  it('Renders actions', () => {
    const actions = wrapper.find('ModalActions').exists();
    expect(actions).toBe(true);
  });
});

describe('Emit data check', () => {
  const emit = jest.spyOn(io, 'emit');
  it('Submit form with correct data', () => {
    instance.createElement();
    const uuid = expect.any(String);
    expect(emit).toHaveBeenCalledWith('action', { elements: [elementInfo], action_type: 'create_element', uuid });
  });
});

```