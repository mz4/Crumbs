# FRONTEND

---
  
## JAVASCRIPT

<h3>Execution Context</h3>
The environment in which code is running. It is created when your code is executed.  
<br>
<h3>Global Execution Context creates</h3>
- Global Object Window (browser)  
- Special Object 'this'  
- Ref to outer environment  
<br>
<h3>JS Engine</h3>
it performs following two steps while executing any code:  
<h5>Creation Phase</h5>
- Run through your code & identifies variables & functions  
- Setup memory space for Variables & Functions - "Hoisting"  
- Hoisting, before code is executed, the JS Engine set asides memory space for Var & Func used inside the code.  
<br>
<h5>Execution Phase</h5>
- When the code is executed line-by-line (by JS interpreeter) it can access the variables defined inside Execution Context  
- Variable assignment are done in this phase 
<br>
<h3>Bind</h3>
We use the Bind () method primarily to call a function with the this value set explicitly.  
In other words, bind () allows us to easily set which specific object will be bound to this when a function or method is invoked.


```javascript
// <button>Get Random Person</button>
// <input type="text">
var user = {
    data        :[
        {name:"T. Woods", age:37},
        {name:"P. Mickelson", age:43}
    ],
    clickHandler:function (event) {
        var randomNum = ((Math.random () * 2 | 0) + 1) - 1; // random number between 0 and 1
        $ ("input").val (this.data[randomNum].name + " " + this.data[randomNum].age);
    }
}
// Assign an eventHandler to the button's click event
$ ("button").click (user.clickHandler);
```

<h3>Scopes in javascript</h3>
- Global Scope  
- Local Scope  
- Block Scope (let)  

<h3>Old school JavaScript</h3>
Traditionally, JavaScript really only has two types of scope :  
<h3>Global Scope</h3>
Variables are known throughout the application, from the start of the application  
<h3>Functional Scope</h3>
Variables are known within the function they are declared in, from the start of the function  

<h3>Modern JavaScript</h3>
The most recent JavaScript specs now also allow a third scope :  
<h3>Block Scope</h3>
Variables are known within the block they are declared in, from the moment they are declared onwards  
let myVariable = "Some text";  
const myVar = "val";  

<h3>Difference Between Function and Block Scope</h3>
Function scope is within the function. (var is function scope.)  
Block scope is within curly brackets. (let and const are block scope.)  

<h3>Variable hoisting</h3>
Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).  

<h3>Scope chain</h3>
JavaScript engine will try to find the value of the variable in the executing code's block scope (your room) and when unable to find the value there, it will go to its lexical outer scope (your house) and if not even found there, it will go to it’s outer scope’s outer scope(your colony) until it reaches the global scope, let’s say in your case can be the country, which in context of JavaScript will be window, if your working in browser environment.  

<h3>Closures</h3>
A closure is an inner function that has access to the outer (enclosing) function’s variables — scope chain. The closure has three scope chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables, and it has access to the global variables.  

<h3>Promise</h3>
A promise is commonly defined as a proxy for a value that will eventually become available.  
Promises are one way to deal with asynchronous code, without writing too many callbacks in your code.  
Although they’ve been around for years, they were standardized and introduced in ES2015, and now they have been superseded in ES2017 by async functions.  
Async functions use the promises API as their building block, so understanding them is fundamental even if in newer code you’ll likely use async functions instead of promises.  

A Promise is in one of these states:  
  
pending: initial state, neither fulfilled nor rejected.  
fulfilled: meaning that the operation completed successfully.  
rejected: meaning that the operation failed.  
  
A Promise object is created using the new keyword and its constructor.  
This constructor takes as its argument a function, called the "executor function".  
This function should take two functions as parameters.  
The first (resolve) is called when the asynchronous task completes successfully and returns the results of the task as a value.  
The second (reject) is called when the task fails, and returns the reason for failure, which is typically an error object.  

<h3>Promise example 1</h3>
```javascript
get('supplyData.json').then(function(response) {
  console.log("Success!", response);
}).catch(function(error) {
  console.log("Failed!", error);
})
```
  
<h3>Promise example 2</h3>
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

<h3>Promise example 3</h3>
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

<h3>Callback</h3>
You can’t know when a user is going to click a button, so what you do is, you define an event handler for the click event. This event handler accepts a function, which will be called when the event is triggered.  
This is the so-called callback.  
A callback is a simple function that’s passed as a value to another function, and will only be executed when the event happens.  

<h3>Callback example 1</h3>
```javascript
document.getElementById('button').addEventListener('click', () => {
  //item clicked
})
```

<h3>Callback example 2</h3>
```javascript
setTimeout(() => {
  // runs after 2 seconds
}, 2000)
```

<h3>Random number</h3>
```javascript
Math.floor(Math.random() * (100 - 1 + 1)) + 1;
    graphData = graphData.map((graph) => {
      graph.read_bytes = Math.floor(Math.random() * (10000 - 1024 + 1)) + 1024;
      return graph;
    });
```

---

## ES6
<h3>Spread Operator 1</h3>  
```javascript
const userInfo = { isAuthenticated: false }  
const action = { isAuthenticated: true, type: 'nope' }  
const res = { ...userInfo, isAuthenticated: action.isAuthenticated };   
console.log(res);  // { isAuthenticated: true } 
```

<h3>Spread Operator 2</h3>
```javascript
var mid = [3, 4];  
var arr = [1, 2, ...mid, 5, 6];  
console.log(arr);  // [ 1, 2, 3, 4, 5, 6 ]
```

<h3>Spread Operator 3</h3>
```javascript
let nums = [1, 2, 3];
let abcs = ['a', 'b', 'c'];
let alphanum = [ ...nums, ...abs ]; // [1, 2, 3, 'a', 'b', 'c']
```

<h3>Destructuring 1</h3>
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

<h3>Destructuring 2</h3>
```javascript
var address = {
  city: "London",
  state: "UK",
  zip: 1334
};
let {city: c, state: s, zip: z} = address;
log(c, s, z); // 'London UK 1334'
```

<h3>Destructuring 3</h3>
```javascript
var person = {name: 'Aaaaaa', age: 35};
displayPerson(person);

function displayPerson({name, age}) {
  // do something with name and age to display them
}
```

<h3>Destructuring 4</h3>
```javascript
var person = {name: 'Aaaaaa', age: 35};
let {name, age, address} = person; // error!
let {name, age, ?address} = person; // OK
let ?{name, age, address} = person; // OK
```

<h3>Destructuring 5</h3>
```javascript
var nums = [1, 2, 3, 4];
doSomething(nums);

function doSomething([first, second, ...others]){
  log(first);   //logs 1
  log(second);  //logs 2
  log(others);  //logs [3, 4]
}
```

<h3>Arrow functions 1</h3>
Specifying parameters:
```javascript
    () => { ... } // no parameter
     x => { ... } // one parameter, an identifier
(x, y) => { ... } // several parameters
```

<h3>Specifying a body:</h3>
```javascript
x => { return x * x }  // block
x => x * x  // expression, equivalent to previous line
```

<h3>Arrow function 2</h3>
```javascript
const phraseSplitterEs6 = phrase => phrase.split(" ");
```

<h3>Arrow function 3</h3>
```javascript
var docLogEs6 = () => { console.log(document); };
```

<h3>Arrow function 4</h3>
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

<h3>Nested keys</h3>
Check existance of nested keys.
```javascript
var update_progress = (((data || {}).Oem || {}).Name || {}).UpdateProgress;
if (update_progress !== null) {
    console.log(JSON.stringify(data));
}
```

<h3>Difference setInterval and setTimeout</h3>
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

<h3>Performance analysis</h3>
```js
console.time("start");
```
// do something
```js
console.timeEnd("end")
```
// this will cause the browser to print time elapsed between start and end.






















---

## REACT

<h3>State</h3>
React is all about one-way data flow down the component hierarchy.  
State is created in the component and stays in the component.  
It can be passed to a children as its props.  


<h3>Basic Concepts</h3>
- JSX
- Rendering Elements
- Components Functional/Container
- State and Lifecycle
- Handling Events
- Conditional Rendering
- Lists and Keys
- Forms

<h3>JSX</h3>
```javascript
<MyComponent message={'hello world'} />
```

<h3>Rendering elements</h3>
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

<h3>Stateless function component - sfc</h3>
```javascript
const | = props => {
  return ( | );
};

export default |;
```

<h3>State and lifecycle</h3>
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

<h3>Handling events</h3>
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

<h3>Conditional rendering</h3>
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

<h3>List and Keys</h3>
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

<h3>Forms</h3>
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

<h3>React Fragment</h3>
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

<h3>Import CSS</h3>
```
import './styles/style.css'
```

<h3>Declare state</h3>
```
export class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {count: props.initialCount};
  }
```

<h3>defaultProps example</h3>
```javascript
Notification.defaultProps = {
  actionTitle: '',
  selectedElements: {},
  actionLogs: [],
};
```

<h3>propTypes example</h3>
```javascript
Notification.propTypes = {
  actionTitle: PropTypes.string,
  isOpen: PropTypes.bool.isRequired,
  close: PropTypes.func.isRequired,
  elementTitle: PropTypes.objectOf(PropTypes.any),
  selectedElements: PropTypes.arrayOf(PropTypes.any),
};
```

<h3>Import statement - imr</h3>
```javascript
import React from 'react';
```

<h3>Import React and Component - imrc</h3>
```javascript
import React, { Component } from 'react';
```

<h3>Make a Class Component and export - cc</h3>
```javascript
class | extends Component {
  state = { | },
  render() {
    return ( | );
  }
}

export default |;
```

<h3>componentDidMount - cdm</h3>
```javascript
componentDidMount() {
  |
}
```

<h3>componentDidUpdate - cdu</h3>
```javascript
componentDidUpdate(prevProps, prevState) {
  |
}
```

<h3>setState - ss</h3>
```javascript
this.setState({ | : | });
```

<h3>render - ren</h3>
```javascript
render() {
  return (
    |
  );
}
```

<h3>export example with mapStateToProps, mapDispatchToProps</h3>
```javascript
export default connect(mapStateToProps, mapDispatchToProps)(Name);
```

<h3>mapStateToProps example</h3>
```javascript
const mapStateToProps = (state) => {
  return {
    elements: state.refreshRaidElements.raidElements,
    controllers: state.refreshControllers.controllers,
    waitingLogs: state.watingLogs.wating_action_logs,
  };
};
```

<h3>mapDispatchToProps</h3>
Import actions  
```javascript
import { checkboxClicked, selectedIndex } from '../../../store/actions/ElementsAction';
```
  
<h3>Emit action </h3> 
```javascript
this.props.selectedRaidIndex(id);
```
  
<h3>Dispatch actions</h3>  
```javascript
const mapDispatchToProps = (dispatch) => {
  return {
    checkboxClicked: id => dispatch(checkboxClicked(id)),
    selectedIndex: id => dispatch(selectedIndex(id)),
  };
};
```

<h3>React Redux Thunk</h3>  

Actions in Redux are dispatched synchronously.   
Thankfully though, Redux allows for middleware that sits between an action being dispatched and the action reaching the reducers.  

**Redux Thunk is a middleware** that lets you call action creators that return a function instead of an action object.  
That function receives the store’s dispatch method, which is then used to dispatch regular synchronous actions inside the body of the function once the asynchronous operations have completed.  
  
Install redux-thunk  
```
npm install redux-thunk
```

<h3>Apply middleware to app store.</h3>  
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

<h3>React Portals</h3>

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



<h3>React Hooks</h3>
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

<h3>State Hooks</h3>
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

<h3>Declaring multiple state variables</h3>

```javascript
function ExampleWithManyStates() {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
}
```

<h3>Effect Hook</h3>

The Effect Hook, useEffect serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes, but unified into a single API.  
By default, React runs the effects after every render — including the first render.  

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

<h3>Reuse logic in another component.</h3>
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

<h3>Definition</h3>
REST stands for Representational State Transfer. 
It is web standards based architecture and uses HTTP Protocol. 
 
A Web API conforming to the REST architectural style is a REST API.  
A web service is a collection of standards used for exchanging data between applications or systems.  
Web services based on REST Architecture are known as RESTful web services.  
These webservices uses HTTP methods to implement the concept of REST architecture.  
A RESTful web service usually defines a URI, Uniform Resource Identifier a service, which provides resource representation such as JSON and set of HTTP Methods.

A REST API is composed of four distinct resource archetypes: document, collection, store, and controller  

<h3>URI Format</h3>
generic URI syntax as shown below:  
```
URI = scheme "://" authority "/" path [ "?" query ] [ "#" fragment ]
```

<h3>Good Practices</h3>
Forward slash separator (/) indicates a hierarchical relationship  
underscores (_) should not be used in uris  
Trailing forward slash (/) should not be included in uris  
hyphens (-) should be used to improve readability of uris  
lowercase letters should be preferred in uri paths  
crud function names should not be used in uris  
query component of a URI may be used to filter collections or stores

<h3>Request Methods</h3>
CRUD requests: DELETE, GET, POST, PUT  
HEAD retrieve metadata.  
OPTIONS retrieve metadata of resource’s available interactions.  

<h3>Some Responses status</h3>
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

<h3>HTTP Headers</h3>
Various forms of metadata may be conveyed through the entity headers.    
  
<h3>Request headers</h3>
Cookie: HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to the user’s request. The client may store it and send it back with the next request to the same server.  
User-Agent: identify the application type, operating system, software vendor
Host: The Host request header specifies the domain name of the server  
X-Requested-With: Mainly used to identify AJAX requests.  
Accept-Language which languages the client is able to understand  
  
<h3>Response headers</h3>
Content-Type  
Content-Length  size of the response body  
Set-Cookie used to send cookies from the server to the client.

<h3>Body Format</h3>
A REST API commonly uses a response message’s entity body to help convey the state of a request message’s identified resource.   
Today, the most commonly used text formats is JSON.

<h3>API Documentation</h3>
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

  <strong>Path parameters</strong> are part of the endpoint itself and are not optional. For example, in the following endpoint, {user} and {bicycleId} are required path parameters:  
  ```
  /service/myresource/user/{user}/bicycles/{bicycleId}
  ```
    
  <strong>Query string parameters</strong> appear after a question mark (?) in the endpoint. The question mark followed by the parameters and their values is referred to as the “query string.”  
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
  The description of the response is known as the response schema. The response schema documents the response in a more comprehensive, general way, listing each property that could possibly be returned, what each property contains, the data format of the values, the structure, and other details.  
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

<h3>OpenApi</h3>
OpenAPI is a specification for describing REST APIs.  

Display frameworks such as Swagger UI can parse the OpenAPI specification and generate interactive documentation that lets users try out endpoints while learning about the API.  
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
After you have a valid OpenAPI specification document that describes your API, you can then feed this specification to different tools to parse it and generate the interactive documentation.  
Probably the most common tool used to parse the OpenAPI specification is Swagger UI.  

<h3>OpenAPI root level</h3>
- openapi  
indicate the version of the OpenAPI spec to validate against.  
- info  
The info object contains basic information about your API, including the title, a description, version, link to the license, link to the terms of service, and contact information.  
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

<h3>Axios - HTTP client</h3>
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
<h3>About</h3>
GraphQL is a query language for your API, and a server-side runtime for executing queries by using a type system you define for your data.  

- Open source and created by Facebook  
- Gives clients the power to describe exactly what data they want  
- Can sit in front of any existing API because its just a query language  

REST APIs have shown to be too inflexible to keep up with the rapidly changing requirements of the clients that access them.  
GraphQL was developed to cope with the need for more flexibility and efficiency! It solves many of the shortcomings and inefficiencies that developers experience when interacting with REST APIs.  
When working with REST APIs, data is loaded from specific endpoints.  
Instead of having multiple endpoints that return fixed data structures, GraphQL APIs typically only expose a single endpoint. This works because the structure of the data that’s returned is not fixed. Instead, it’s completely flexible and lets the client decide what data is actually needed.

<h3>GraphQL vs REST</h3>
- GraphQL only has one URL.  
  Request details are in a POST body (or GET)  
- In REST, shape and size of data resource is determined by the server,  
  In Graphql its determined by the query (request)  
- In REST, you have to male multiple API calls to retrieve relational data,  
  in GraphQL you can start with entry resource and traverse all the connections in one request  
- In REST, the shape of the response is determined by whom ever created the server,   
  in GraphQL the shape is determined by the query  

 
<h3>Terminology</h3>  
- Query - Queries specify which endpoints we want to call, how we want the response to look  
- Fields - Properties that comprise the shape of a response  
- Type - A collection of fields that make up a specific queryable object.  
- Mutation - A special kind of GraphQL query that causes changes to the data available on the backend  
- Schema - A special kind of document that describes how a GraphQL endpoint can receive and send information  
- Query Language - The syntax we use to write GraphQL queries that retrieve data from an endpoint  
- Self-documenting API - An API that can be easily understood just by reading its schema -- no extra documentation needed  
  
<h3>Basic Query</h3>
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

<h3>Mutations</h3>
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

<h3>Subscriptions</h3>
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

<h3>Schema</h3>
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

<h3>Responsive Design</h3>
<h3>Defined by three characteristics</h3>
- Flexible grid-based layout  
- Media queries (CSS3)  
- Images that resize  

<h3>FLEXBOX</h3>
<h3>Parent Flex Container</h3>
```
display: flex | inline-flex;
flex-direction: row | row-reverse | column | columnreverse;
flex-wrap: wrap | nowrap | wrap-reverse; flex-flow (shorthand for flex-direction and flexwrap)
justify-content: flex-start | flex-end | center | spacebetween | space-around | space-evenly;
align-items: flex-start | flex-end | center | baseline | stretch;
align-content (cross axis - adjust to largest item): flex-start | flex-end | center | stretch | spacebetween | space-around;
```

<h3>Children Flex Items</h3>
```
order: <integer>;
flex-grow: <number>;
flex-shrink: <number>;
flex-basis: <length> | auto;
flex: shorthand for grow, shrink, and basis (default: 0 1 auto)
align-self: overrides alignment set on parent
```

<h3>GRID</h3>
<h3>Grid Container</h3>
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

<h3>Grid Items</h3>
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

<h3>Media Queries</h3>
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

<h3>BEM (Block Element Modifier)</h3>
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

<h3>BEM with Sass</h3>
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
<h3>Install SASS</h3>
```
$ npm install sass-loader node-sass --save-dev
```

<h3>Update the webpack.config.js to chain sass-loader , then css-loader and then chain their output to style-loader (Loader-chaining)</h3>
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

<h3>SCSS Import</h3>
```scss
@import 'reset';
```

<h3>SCSS Variables</h3>
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

<h3>SCSS Mixins</h3>
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

<h3>SCSS CrossBrowser Mixins</h3>
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

<h3>SCSS Extend</h3>
<h3>Extending should be used when we need similarly styled elements, which still differ in some detail. </h3>
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

<h3>SCSS Nesting</h3>
<h3>Organize your stylesheet in a way that resembles the HTML more closely.</h3>
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

<h3>Nested Pseudo Classes and Pseudo Elements </h3>
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

<h3>SCSS Operations  </h3>
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

<h3>Selectors</h3>

<h3>Descendant Selector</h3>
all p elements inside div elements  
```
div p {
  background-color: yellow;
}
```
  
<h3>Child Selector</h3>
all p elements that are immediate children of a div element  
```
div > p {
  background-color: yellow;
}
```

<h3>Adjacent Sibling Selector</h3>
all p elements that are placed immediately after div elements  
```
div + p {
  background-color: yellow;
}
```

<h3>General Sibling Selector</h3>
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