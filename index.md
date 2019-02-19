# Crumbs

---
# **GIT**


#### Single file history
```
git log -p filename
```

#### get tag
```
git log --decorate v0.4bugfix|head -n1|sed 's/.*tag: //;s/[^a-zA-Z.0-9].*//'
```
#### get commits by date and author
```
git log --pretty=format:"%ad - %an: %s" --after="2010-02-15" --until="2018-08-20" --author="John"
```

#### git log commit subject of last 10 commits
```
git log -10 --pretty=format:"%h %s"
```

#### number of commits by author
```
git shortlog -s -n --all
```

#### remove local untracked files 
```
git clean -n
git clean -f
```

#### undo last commit. Warning: Don't do this if you've already pushed
```
 git reset HEAD~
```
  
If you don't want the changes and blow everything away:
```  
 git reset --hard HEAD~
```

#### untrack .pyc files
```
$ find . -name '*.pyc' | xargs -n 1 git rm --cached
```

#### Switch to branch 
```
git checkout BRANCHNAME
```

#### Pull from master branch
```
git pull origin master
```

#### Squash
```
git reset --soft HEAD~$squashCount
git commit -m "$commitMsg"
```

#### Check git status
```
git status
```

#### Add files
```
git add sys_ui/css/FILE.css 
git add sys_ui/FILE.html 
git add sys_ui/js/FILE.js 
```

#### Commit
```
git commit
```

#### Push
```
git push
```

#### Checkout master
```
git chekcout master
```

#### Merge branch into master
```
git merge user_interface
```

#### Check Log
```
git log
```

#### Create branch and switch
```
git checkout -b v0.4bugfix v0.4Master
```

```
git branch NAME
git checkout NAME
```

#### Push a branch to origin
```
git push -u origin <branch>
```

#### Tags
```
git tag v1.0 ec32d32
git push origin --tags
```

#### How to undo a local commit
```
git reset --soft HEAD^     # use --soft if you want to keep your changes
git reset --hard HEAD^     # use --hard if you don't care about keeping the changes you made
```

#### How to undo git add
```
git reset filename.jsx
```

#### Delete a local branch - Delete remote branch
```
git branch -d branch_name
git push origin --delete <branch_name>
```

#### show differences after git pull
```
git diff master@{1} master
```

#### clone specific branch
```
git clone -b <branch> <remote_repo>
git clone -b my-branch git@github.com:user/myproject.git
```

#### clone repo
```
git clone USER@10.0.2.10:/home/git/repos/sys .
```

#### lists branches merged into master
```
git branch --merged master
```

#### lists branches merged into HEAD (i.e. tip of current branch)
```
git branch --merged 
```

#### lists branches that have not been merged
```
git branch --no-merged
```

#### Checkout previous branch
```
git checkout -
```

#### Diff between branches
Diff between current branch and master:  
```
git diff master
```
Diff between two branches, e.g. master and staging:  
```
git diff master..staging
```
Show only files that are different between the two branches (without changes themselves):  
```
git diff --name-status master..staging
```

#### Create New Branch and Checkout – In One Command
```
git checkout -b <branch_name>
```

#### Revert Changes to File
```
git checkout -- <file>
```

#### Edit Last Commit Message
Change the last commit message through the command-line:  
```
git commit --amend -m "New commit message"
```

#### Create a New Git Repository
```
git init
```

---
# **CSS3/SASS**  

#### BEM Block Element Modifier
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
#### BEM with Sass
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

#### SCSS Import
```scss
@import 'reset';
```

#### SCSS Variables
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

#### SCSS Mixins
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

#### SCSS CrossBrowser Mixins
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

#### SCSS Extend  
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

#### SCSS Nesting  
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

#### Nested Pseudo Classes and Pseudo Elements 
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


#### SCSS Operations  
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

#### Install SASS
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

#### Selectors

##### Descendant Selector
all <p> elements inside <div> elements  
```
div p {
  background-color: yellow;
}
```
  
##### Child Selector
all <p> elements that are immediate children of a <div> element  
```
div > p {
  background-color: yellow;
}
```

##### Adjacent Sibling Selector
all <p> elements that are placed immediately after <div> elements  
```
div + p {
  background-color: yellow;
}
```

##### General Sibling Selector
all <p> elements that are siblings of <div> elements  
```
div ~ p {
  background-color: yellow;
}
```
---
# **Javascript**  

#### Execution Context.  
**Execution context**: the environment in which code is running. It is created when your code is executed.  
    
**Global Execution Context** creates 3 things:  
- Global Object Window (browser)  
- Special Object 'this'  
- Ref to outer environment  

**JS Engine** performs following two steps while executing any code:  
**Creation Phase**
- Run through your code & identifies variables & functions  
- Setup memory space for Variables & Functions - "Hoisting"  
- Hoisting, before code is executed, the JS Engine set asides memory space for Var & Func used inside the code.  

**Execution Phase**  
- When the code is executed line-by-line (by JS interpreeter) it can access the variables defined inside Execution Context  
- Variable assignment are done in this phase 

#### Bind
We use the Bind () method primarily to call a function with the this value set explicitly. In other words, bind () allows us to easily set which specific object will be bound to this when a function or method is invoked.

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

#### Scopes in javascript
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

#### Difference Between Function and Block Scope

Function scope is within the function. (var is function scope.)  
Block scope is within curly brackets. (let and const are block scope.)  

#### Variable hoisting

Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).  

#### Scope chain
JavaScript engine will try to find the value of the variable in the executing code's block scope (your room) and when unable to find the value there, it will go to its lexical outer scope (your house) and if not even found there, it will go to it’s outer scope’s outer scope(your colony) until it reaches the global scope, let’s say in your case can be the country, which in context of JavaScript will be window, if your working in browser environment.  

#### Closures
A closure is an inner function that has access to the outer (enclosing) function’s variables — scope chain. The closure has three scope chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables, and it has access to the global variables.  

#### Promise
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

##### Promise example 1
```javascript
get('supplyData.json').then(function(response) {
  console.log("Success!", response);
}).catch(function(error) {
  console.log("Failed!", error);
})
```
  
##### Promise example 2
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

##### Promise example 3
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
#### Callback
You can’t know when a user is going to click a button, so what you do is, you define an event handler for the click event. This event handler accepts a function, which will be called when the event is triggered.  
This is the so-called callback.  
A callback is a simple function that’s passed as a value to another function, and will only be executed when the event happens.  

##### Callback example 1
```javascript
document.getElementById('button').addEventListener('click', () => {
  //item clicked
})
```

##### Callback example 2
```javascript
setTimeout(() => {
  // runs after 2 seconds
}, 2000)
```


#### Promises vs Callbacks

#### Random number
```javascript
Math.floor(Math.random() * (100 - 1 + 1)) + 1;
    graphData = graphData.map((graph) => {
      graph.read_bytes = Math.floor(Math.random() * (10000 - 1024 + 1)) + 1024;
      return graph;
    });
```

---
## **ES6**  
  
#### Spread Operator 1  
```javascript
const userInfo = { isAuthenticated: false }  
const action = { isAuthenticated: true, type: 'nope' }  
const res = { ...userInfo, isAuthenticated: action.isAuthenticated };   
console.log(res);  
```

####  Spread Operator 2
```javascript
var mid = [3, 4];  
var arr = [1, 2, ...mid, 5, 6];  
  
console.log(arr);  
```

#### Arrow functions 1
Specifying parameters:
```javascript
    () => { ... } // no parameter
     x => { ... } // one parameter, an identifier
(x, y) => { ... } // several parameters
```
Specifying a body:
```javascript
x => { return x * x }  // block
x => x * x  // expression, equivalent to previous line
```

#### Arrow function 2
```javascript
const phraseSplitterEs6 = phrase => phrase.split(" ");
```

#### Arrow function 3
```javascript
var docLogEs6 = () => { console.log(document); };
```

#### Arrow function 4
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

---
# **React**  

#### Import statement - imr
```javascript
import React from 'react';
```

#### Import React and Component - imrc
```javascript
import React, { Component } from 'react';
```

#### Make a Class Component and export - cc
```javascript
class | extends Component {
  state = { | },
  render() {
    return ( | );
  }
}

export default |;
```

#### Make a stateless function component - sfc
```javascript
const | = props => {
  return ( | );
};

export default |;
```

#### componentDidMount - cdm
```javascript
componentDidMount() {
  |
}
```

#### componentDidUpdate - cdu
```javascript
componentDidUpdate(prevProps, prevState) {
  |
}
```

#### setState - ss
```javascript
this.setState({ | : | });
```

#### render - ren
```javascript
render() {
  return (
    |
  );
}
```

#### defaultProps example
```javascript
Notification.defaultProps = {
  actionTitle: '',
  selectedElements: {},
  actionLogs: [],
};
```

#### propTypes example
```javascript
Notification.propTypes = {
  actionTitle: PropTypes.string,
  isOpen: PropTypes.bool.isRequired,
  close: PropTypes.func.isRequired,
  elementTitle: PropTypes.objectOf(PropTypes.any),
  selectedElements: PropTypes.arrayOf(PropTypes.any),
};
```

#### export example with mapStateToProps, mapDispatchToProps
```javascript
export default connect(mapStateToProps, mapDispatchToProps)(Name);
```

#### mapStateToProps example
```javascript
const mapStateToProps = (state) => {
  return {
    elements: state.refreshRaidElements.raidElements,
    controllers: state.refreshControllers.controllers,
    waitingLogs: state.watingLogs.wating_action_logs,
  };
};
```

#### mapDispatchToProps
Import actions  
```javascript
import { checkboxClicked, selectedIndex } from '../../../store/actions/ElementsAction';
```
  
Emit action  
```javascript
this.props.selectedRaidIndex(id);
```
  
Dispatch actions  
```javascript
const mapDispatchToProps = (dispatch) => {
  return {
    checkboxClicked: id => dispatch(checkboxClicked(id)),
    selectedIndex: id => dispatch(selectedIndex(id)),
  };
};
```

#### React Redux Thunk  

Actions in Redux are dispatched synchronously.   
Thankfully though, Redux allows for middleware that sits between an action being dispatched and the action reaching the reducers.  

**Redux Thunk is a middleware** that lets you call action creators that return a function instead of an action object.  
That function receives the store’s dispatch method, which is then used to dispatch regular synchronous actions inside the body of the function once the asynchronous operations have completed.  
  
Install redux-thunk  
```
npm install redux-thunk
```

Apply middleware to app store.  
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

# Test Jest Enzyme
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

#### useful for debug
```
console.log(wrapper.debug());
```

---
# REST API - Application Programming Interface (API)  
A REST API consists of an assembly of interlinked resources.  
A Web API conforming to the REST architectural style is a REST API.  
Having a REST API makes a web service “RESTful.”  
A REST API is composed of four distinct resource archetypes: document, collection, store, and controller  

#### URI Format  
generic URI syntax as shown below:  
```
URI = scheme "://" authority "/" path [ "?" query ] [ "#" fragment ]
```
Forward slash separator (/) indicates a hierarchical relationship  
underscores (_) should not be used in uris  
Trailing forward slash (/) should not be included in uris  
hyphens (-) should be used to improve readability of uris  
lowercase letters should be preferred in uri paths  
crud function names should not be used in uris  
query component of a URI may be used to filter collections or stores

#### Request Methods
CRUD requests: DELETE, GET, POST, PUT  
HEAD retrieve metadata.  
OPTIONS retrieve metadata of resource’s available interactions.  

#### Some Responses status
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

#### HTTP Headers
Various forms of metadata may be conveyed through the entity headers.  
##### Request headers
Cookie: HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to the user’s request. The client may store it and send it back with the next request to the same server.  
User-Agent: identify the application type, operating system, software vendor
Host: The Host request header specifies the domain name of the server  
X-Requested-With: Mainly used to identify AJAX requests.  
Accept-Language which languages the client is able to understand  
##### Response headers
Content-Type  
Content-Length  size of the response body  
Set-Cookie used to send cookies from the server to the client.
####  Body Format
A REST API commonly uses a response message’s entity body to help convey the state of a request message’s identified resource.   
Today, the most commonly used text formats is JSON.


---
# **Linux Commands**  

#### truncate file content
```
truncate -s 0 dash.txt
```

#### cat long file
```
cat branch | more -d
```

#### Check if port is listening
```
sudo netstat -ntlp | grep :443
```
#### Find a string
```
grep -r "test" - find string
```
#### Find string include, exclude, ignore case
```
grep -r -i ".ui" --include \*.scss --exclude app.scss
```
#### Find Large files
```
find / -size +10M -ls
```
#### Directory Size
```
du -hs direcotryName
```
#### Show system name and kernel
```
uname -a
```
#### Start a screen session.
```
screen
```
#### Resume a screen session.
```
screen -r
```
#### List screen sessions.
```
screen -list
```
#### List All Available Packages
```
apt-cache pkgnames
```
#### Package Name and Description of Software
```
apt-cache search vsftpd
```
#### Package Information
```
apt-cache show netcat
```
#### Dependencies for Specific Packages
```
apt-cache showpkg vsftpd
```
#### Update System Packages
```
sudo apt-get update
```
#### Clean up disks space
```
sudo apt-get clean
```
#### Download only source code
```
sudo apt-get --download-only source vsftpd
```
#### Check broken dependencies
```
sudo apt-get check
```
#### Remove files containing a string
```
rm ?*foo?*
ls -d '*foo*' | egrep -v '^foo|foo$' | xargs rm
```
#### Most used Commands
```
ls Directory listing
ls -al Formatted listing with hidden files
ls -lt Sorting the Formatted listing by time modification
cd dir Change directory to dir
cd Change to home directory
pwd Show current working directory
mkdir dir Creating a directory dir
cat >file Places the standard input into the file
more file Output the contents of the file
head file Output the first 10 lines of the file
tail file Output the last 10 lines of the file
tail -f file Output the contents of file as it grows,starting with the last 10 lines
touch file Create or update file
rm file Deleting the file
rm -r dir Deleting the directory
rm -f file Force to remove the file
rm -rf dir Force to remove the directory dir
cp file1 file2 Copy the contents of file1 to file2
cp -r dir1 dir2 Copy dir1 to dir2;create dir2 if not present
mv file1 file2 Rename or move file1 to file2,if file2 is an existing directory
ln -s file link Create symbolic link link to file
```

#### Process Management
```
ps To display the currently working processes
top Display all running process
kill pid Kill the process with given pid
killall proc Kill all the process named proc
pkill pattern Will kill all processes matching the pattern
bg List stopped or background jobs,resume a stopped job in the background
fg Brings the most recent job to foreground
fg n Brings job n to the foreground
```

#### File permission
```
chmod octal file Change the permission of file to octal,which can be found separately for user,group,world by adding,
• 4-read(r)
• 2-write(w)
• 1-execute(x)
```

#### Create folder and cd into it
```
mkdir foo && cd "$_"
```

#### Create Swap file
```
sudo mkdir -v /var/cache/swap
cd /var/cache/swap
sudo dd if=/dev/zero of=swapfile bs=1K count=8M
sudo chmod 600 swapfile
sudo mkswap swapfil
sudo mkswap swapfile
sudo swapon swapfile
top -bn1 | grep -i swap
echo "/var/cache/swap/swapfile none swap sw 0 0" | sudo tee -a /etc/fstab
```

---
# **WEBPACK**  

#### webpack installation
```
npm install --save-dev webpack
```
If you're using webpack v4 or later, you'll need to install the CLI.  
```
npm install --save-dev webpack-cli
```
Create a webpack config file e.g. webpack.config.js  
```
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```

in package.json  
```
 "scripts": {
+     "build": "webpack"
    },
```

---
# **Node/npm**  

#### version
```
which node
which npm
node --version
npm --version
```

#### global install packages
```
npm install uglify-js --global
```

#### list global packages
```
npm list --global
npm list -g --depth=0
```

#### initialize project
```
npm init
```

#### local install packages devDependencies
```
npm install should --save-dev
```

#### local install packages dependencies
```
npm install should --save
```

#### uninstall packages
```
npm uninstall underscore
```

#### install specific version
```
npm install underscore@1.8.2
```

#### check outdated packages
```
npm outdated
```

#### update packages
```
npm update underscore
```

#### Quick Project Setup - React, Webpack, Babel, ESLint
  
##### Dependencies
```
npm install --save react react-dom
```

##### Dev Dependencies
```
npm install --save-dev babel-{core,loader} babel-preset-es2015 babel-preset-react babel-eslint css-loader node-sass sass-loader style-loader file-loader webpack webpack-dev-server eslint eslint-plugin-import eslint-plugin-react eslint-watch
```

##### NPM Scripts (package.json)
```
"scripts": {
  "start": "webpack-dev-server --progress --hot --inline",
  "build": "webpack",
  "lint": "esw webpack.config.js src",
  "lint:watch": "npm run lint -- --watch",
  "fix": "./node_modules/.bin/eslint src --fix"
},
```

##### Babel (.babelrc)
```
{
  "presets": [
    "es2015",
    "react"
  ]
}
```
##### Webpack Performance codesplitting react-loadable
```
npm install --save react-loadable
```

```
import Loadable from 'react-loadable';
import Loading from '../../layout/Loading';
const ComponentName = Loadable({ loader: () => import(/* webpackChunkName: "ComponentName" */'./subcomponents/ComponentName'), loading: Loading });
```
in webpack.config.js
```
  output: {
    path: path.join(__dirname, 'app/static/bin'),
    filename: 'bundle.js',
    publicPath: '/static/bin/',
    chunkFilename: '[name].bundle.js',
  },
```

##### general performance improvements
```
React-loadable: this is a code splitting library. It allows to load components only when those are needed.  
There are 2 main ways to split code:  
by route
by subcomponents

Show loading icon when initial page is loading.
The objective in this case is to give immediately a feedback to the user that page is loading.

Webpack Plugin: UglifyWebpackPlugin minify js files
(license MIT) uglifyjs-webpack-plugin

Webpack Plugin: MomentLocalesPlugin remove unused locales from Moment
(license MIT) moment-locales-webpack-plugin

Webpack Plugin: BundleAnalyzerPlugin analyze build files (use http://127.0.0.1:8888 after running npm run-script build)
(license MIT): Webpack Bundle Analyzer

Babel Plugin: transform-imports import only needed modules
(license ISC) babel-plugin-transform-imports

Babel Plugin: transform-react-remove-prop-types Remove React propTypes from the production build, as they are only used in development.
(license MIT) babel-plugin-transform-react-remove-prop-types
```

##### webpack treeshaking
```
npm run-script build -- --display-used-exports
```

##### .babelrc transform imports
npm install --save-dev babel-plugin-transform-imports  
in .babelrc

```
{
    "plugins": [
        ["transform-imports", {
            "react-bootstrap": {
                "transform": "react-bootstrap/lib/${member}",
                "preventFullImport": true
            },
            "lodash": {
                "transform": "lodash/${member}",
                "preventFullImport": true
            }
        }]
    ]
}
```

##### .eslintrc configuration
```
module.exports = {
    "parser": "babel-eslint",
    "extends": "airbnb",
    "env": {
        "browser": true
    },
    "rules": {
      "class-methods-use-this": "off",
      "react/sort-comp": "off"
    }
};
```

##### Webpack (webpack.config.js)
```
const path = require('path');

module.exports = {
	target: 'web',

	// Entry file where webpack starts the bundling process
	entry: path.resolve(__dirname, 'src/index.js'),

	// Location where bundled code will be saved
	output: {

		// Target directory for all output files
		path: path.resolve(__dirname, './dist'),

		// Name of each Output bundle file
		filename: "bundle.js",
	},

	// Webpack development server (config)
	devServer: {
		port: 9000,

		// Directory to serve content from
		contentBase: path.resolve(__dirname, './src'),

		// Automatically open browser when local server boots up
		open: true
	},

	// Source Map setting
	devtool: "inline-source-map",

	// Modules & Loaders
  module: {
    rules: [
      {
        test: /\.js$/,
        loader: 'babel-loader',
        exclude: /node_modules/
      },
      {
        test: /\.(jpe?g|png|gif)$/i,
        loader: 'file-loader',
        exclude: /node_modules/
      },
      {
        test: /(\.css|\.scss|\.sass)$/,
        loaders: [
          'style-loader',
          'css-loader',
          'sass-loader'
        ]
      }
    ]
  }
};
```

##### ESLint (.eslintrc.json)
```
{
  "root": true,
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:import/warnings"
  ],
  "plugins": [
    "react"
  ],
  "parser": "babel-eslint",
  "parserOptions": {
    "ecmaVersion": 7,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true,
    "mocha": true
  },
  "rules": {
    "quotes": 0,
    "no-console": 1,
    "no-debugger": 1,
    "no-var": 1,
    "semi": [1, "always"],
    "no-trailing-spaces": 1,
    "eol-last": 0,
    "no-unused-vars": 1,
    "no-underscore-dangle": 0,
    "no-alert": 0,
    "no-lone-blocks": 0,
    "no-multi-spaces": 1,
    "jsx-quotes": 1,
    "react/display-name": [ 1, {"ignoreTranspilerName": false }],
    "react/forbid-prop-types": [1, {"forbid": ["any"]}],
    "react/jsx-boolean-value": 1,
    "react/jsx-closing-bracket-location": 1,
    "react/jsx-curly-spacing": 1,
  }
}
```
---
#### Webpack setup2
-y takes the default
```
npm init -y
```
From root folder:
```
mkdir dist
cd dist
touch index.html
```
in dist/index.html
```
<!DOCTYPE html>
<html>
  <head>
    <title>The Minimal React Webpack Babel Setup</title>
  </head>
  <body>
    <div id="app"></div>
    <script src="./bundle.js"></script>
  </body>
</html>
```
Install Webpack from root folder
```
npm install --save-dev webpack webpack-dev-server webpack-cli
```
Folder Structure
```
- dist
-- index.html
- node_modules
- package.json
```
package.json
```
"scripts": {
  "start": "webpack-dev-server --config ./webpack.config.js --mode development",
  ...
},
```
Create webpack configuration file
```
touch webpack.config.js
```
webpack config content
```
module.exports = {
  entry: './src/index.js',
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'bundle.js'
  },
  devServer: {
    contentBase: './dist'
  }
};
```
Start Webpack dev server
```
npm start
```

## Babel Setup
Babel transpiles back to vanilla JavaScript so that every browser can interpret it. 
```
npm install --save-dev @babel/core @babel/preset-env
```
hook it to webpack
```
npm install --save-dev babel-loader
```
JSX to javasript
```
npm install --save-dev @babel/preset-react
```
package.json
```
"keywords": [],
"author": "",
"license": "ISC",
"babel": {
  "presets": [
    "@babel/preset-env",
    "@babel/preset-react"
  ]
```
webpack.config.json
```
module.exports = {
  entry: './src/index.js',
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: ['babel-loader']
      }
    ]
  },
  resolve: {
    extensions: ['*', '.js', '.jsx']
  },
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'bundle.js'
  },
  devServer: {
    contentBase: './dist'
  }
};
```

Install packages for react
```
npm install --save react react-dom
```
src/index.js
```
import React from 'react';
import ReactDOM from 'react-dom';

const title = 'My Minimal React Webpack Babel Setup';

ReactDOM.render(
  <div>{title}</div>,
  document.getElementById('app')
);
```

## Hot Module Replacement in React
apply changes to the browser
```
npm install --save-dev react-hot-loader
```
webpack.config.js
```
const webpack = require('webpack');

module.exports = {
  entry: './src/index.js',
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: ['babel-loader']
      }
    ]
  },
  resolve: {
    extensions: ['*', '.js', '.jsx']
  },
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'bundle.js'
  },
  plugins: [
    new webpack.HotModuleReplacementPlugin()
  ],
  devServer: {
    contentBase: './dist',
    hot: true
  }
};
```

in src/index.js add at the end
```
module.hot.accept();
```
```
npm start
```







--- 
# **Docker**  
##### Docker terminology
- Images: The blueprints of our application which form the basis of containers.  
- Containers: Created from Docker images and run the actual application. 
- Docker Daemon: The background service running on the host that manages building, running and distributing Docker containers. 
- Docker Client: The command line tool that allows the user to interact with the daemon. 
- Docker Hub: A registry of Docker images. If required, one can host their own Docker registries and can use them for pulling images.
  
- Base images: are images that have no parent image, usually images with an OS like ubuntu, busybox or debian.  
- Child images: are images that build on base images and add additional functionality.  
  
- Official images: are images that are officially maintained and supported by the folks at Docker. These are typically one word long.  
- User images: images created and shared by users. They build on base images and add additional functionality. Typically, these are formatted as user/image-name.  
  
##### Install latest Docker  
```
sudo apt-get install docker-ce
```

##### Test your Docker installation by running the following  
```
docker run hello-world
```
  
##### The pull command fetches image from the Docker registry and saves it to system.  
```
docker pull busybox
```

##### Docker Hub  
[Docker Images hub](https://hub.docker.com/search/?q=&type=image)  

##### to see a list of all images on your system.  
```
docker images
```

##### run a container
```
docker run busybox
docker run busybox echo "hello from busybox"
```

##### show running containers
```
docker ps
```

##### show containers that ran previously
```
docker ps -a
```

##### live tty session
```
docker run -it busybox sh
```

##### Remove containers from which you left
```
docker rm $(docker ps -a -q -f status=exited)
OR
docker container prune
```

--rm flag can be passed to docker run which automatically deletes the container once it's exited from  

##### Run detached  
-d will detach our terminal  
-P will publish all exposed ports to random ports and finally  
--name corresponds to a name we want to give.  
```
docker run -d -P --name static-site name/static-site
```

##### See the ports by running the docker port [CONTAINER] command
```
docker port static-site
```

##### Specify a custom port
```
docker run -p 8888:80 prakhar1989/static-site
```

##### Stop a container
```
docker stop static-site
```

##### Creating an image  
A Dockerfile is a simple text-file that contains a list of commands that the Docker client calls while creating an image.  
CMD is to tell the container which command it should run when it is started  
port number that needs to be exposed  
specifying our base image. Use the FROM keyword to do that  
```
# Dockerfile
FROM python:3-onbuild

# tell the port number the container should expose
EXPOSE 5000

# run the command
CMD ["python", "./app.py"]
```

##### Build image from Dockerfile
```
docker build -t mz2kh/catnip .
```

##### Run the container
```
run -p 8888:5000 mz2kh/catnip
```
  
##### Publish image to Docker HUB
```
docker push mz2kh/catnip
```
  
##### Now that your image is online, anyone who has docker installed can play with your app by typing just a single command.  
```
docker run -p 8888:5000 prakhar1989/catnip
```

##### Search for images
```
docker search elasticsearch
```

##### When docker is installed, it creates three networks automatically.
```
docker network ls
NETWORK ID          NAME                DRIVER              SCOPE
77192b388b9d        bridge              bridge              local
3a125533ca3f        host                host                local
13e644755906        none                null                local
```

##### The bridge network is the network in which containers are run by default.  
##### Inspect bridge Network:
```
docker network inspect bridge
```

##### Create our own network  
A bridge network allows containers connected to the same bridge network to communicate,  
while providing isolation from containers which are not connected to that bridge network. 
```
docker network create catnip-net
```

##### Launch containers into network (--net foodtrucks-net)
```
$ docker run -d --name es --net foodtrucks-net -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.3.2
13d6415f73c8d88bddb1f236f584b63dbaf2c3051f09863a3f1ba219edba3673
$ docker network inspect foodtrucks-net
```

##### Create and run container on a created Network  
##### ./setup-docker.sh
```
!/bin/bash

build the flask container
docker build -t prakhar1989/foodtrucks-web .

create the network
docker network create foodtrucks-net

start the ES container
docker run -d --name es --net foodtrucks-net -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.3.2

start the flask app container
docker run -d --net foodtrucks-net -p 5000:5000 --name foodtrucks-web prakhar1989/foodtrucks-web
```

##### Docker Registries & Repositories  
Searching an Image  
```
##### docker search nginx
docker search --filter stars=3 --no-trunc nginx
```
##### Pulling an Image
```
docker image pull nginx
docker image pull eon01/nginx localhost:5000/myadmin/nginx
```
##### Pushing an Image
```
docker image push eon01/nginx
docker image push eon01/nginx localhost:5000/myadmin/nginx
```
##### Running Containers  
##### Create and Run a Simple Container  
##### Start an ubuntu:latest image  
##### Bind the port 80 from the CONTAINER to port 3000 on the HOST  
##### Mount the current directory to /data on the CONTAINER  
```
docker container run --name infinite -it -p 3000:80 -v ${PWD}:/data ubuntu:latest
```

##### Creating a Container  
```
docker container create -t -i eon01/infinite --name infinite
```
##### Running a Container  
```
docker container run -it --name infinite -d eon01/infinite
```
##### Renaming a Container  
```
docker container rename infinite infinity
```
##### Removing a Container
```
docker container rm infinite
```
##### Updating a Container
```
docker container update --cpu-shares 512 -m 300M infinite
```

##### Starting & Stopping Containers  
##### Starting  
```
docker container start nginx
```

##### Stopping
```
docker container stop nginx
```
##### Restarting
```
docker container restart nginx
```
##### Pausing
```
docker container pause nginx
```
##### Unpausing
```
docker container unpause nginx
```
##### Blocking a Container
```
docker container wait nginx
```
##### Sending a SIGKILL
```
docker container kill nginx
```
##### Sending another signal
```
docker container kill -s HUP nginx
```
##### Connecting to an Existing Container
```
docker container attach nginx
```
##### Getting Information about Containers
##### Running Containers
```
docker container ls
docker container ls -a
```
##### Container Logs
##### docker logs infinite
##### Follow Container Logs
```
docker container logs infinite -f
```
##### Inspecting Containers
```
docker container inspect infinite
docker container inspect --format '{{ .NetworkSettings.IPAddress }}' $(docker ps -q)
```
##### Containers Events
```
docker system events infinite
```
##### Public Ports
```
docker container port infinite
```
##### Running Processes
```
docker container top infinite
```
##### Container Resource Usage  
```
docker container stats infinite  
```
##### Inspecting changes to files or directories on a container’s filesystem  
```
docker container diff infinite  
```
##### Manipulating Images  
##### Listing Images  
```
docker image ls
```
##### Building Images  
```
docker build .
docker build github.com/creack/docker-firefox
docker build - < Dockerfile
docker build - < context.tar.gz
docker build -t eon/infinite .
docker build -f myOtherDockerfile .
curl example.com/remote/Dockerfile | docker build -f - .
```
##### Removing an Image  
```
docker image rm nginx
```
##### Loading a Tarred Repository from a File or the Standard Input Stream
```
docker image load < ubuntu.tar.gz
docker image load --input ubuntu.tar
```
##### Save an Image to a Tar Archive
```
docker image save busybox > ubuntu.tar
```
##### Showing the History of an Image
```
docker image history
```
##### Creating an Image From a Container
```
docker container commit nginx
```
##### Tagging an Image
```
docker image tag nginx eon01/nginx
```
##### Pushing an Image
```
docker image push eon01/nginx
```
##### Networking  
##### Creating Networks  
```
docker network create -d overlay MyOverlayNetwork
docker network create -d bridge MyBridgeNetwork
docker network create -d overlay \
  --subnet=192.168.0.0/16 \
  --subnet=192.170.0.0/16 \
  --gateway=192.168.0.100 \
  --gateway=192.170.0.100 \
  --ip-range=192.168.1.0/24 \
  --aux-address="my-router=192.168.1.5" --aux-address="my-switch=192.168.1.6" \
  --aux-address="my-printer=192.170.1.5" --aux-address="my-nas=192.170.1.6" \
  MyOverlayNetwork
```
##### Removing a Network
```
docker network rm MyOverlayNetwork
```
##### Listing Networks
```
docker network ls
```
##### Getting Information About a Network
```
docker network inspect MyOverlayNetwork
```
##### Connecting a Running Container to a Network
```
docker network connect MyOverlayNetwork nginx
```
##### Connecting a Container to a Network When it Starts
```
docker container run -it -d --network=MyOverlayNetwork nginx
```
##### Disconnecting a Container from a Network
```
docker network disconnect MyOverlayNetwork nginx
```
##### Exposing Ports  
##### Using Dockerfile, you can expose a port on the container using:
```
EXPOSE <port_number>
You can also map the container port to a host port using:

e.g.

docker run -p $HOST_PORT:$CONTAINER_PORT --name infinite -t infinite
```

##### Cleaning Docker  
##### Removing a Running Container  
```
docker container rm nginx
```
##### Removing a Container and its Volume
```
docker container rm -v nginx
```
##### Removing all Exited Containers
```
docker container rm $(docker container ls -a -f status=exited -q)
```
##### Removing All Stopped Containers
```
docker container rm `docker container ls -a -q`
```
##### Removing a Docker Image
```
docker image rm nginx
```
##### Removing Dangling Images
```
docker image rm $(docker image ls -f dangling=true -q)
```
##### Removing all Images
```
docker image rm $(docker image ls -a -q)
```
##### Removing all untagged images
```
docker image rm -f $(docker image ls | grep "^<none>" | awk "{print $3}")
```
##### Stopping & Removing all Containers
```
docker container stop $(docker container ls -a -q) && docker container rm $(docker container ls -a -q)
```
##### Removing Dangling Volumes
```
docker volume rm $(docker volume ls -f dangling=true -q)
```
##### Removing all unused (containers, images, networks and volumes)
```
docker system prune -f
```
##### Clean all
```
docker system prune -a
```

---
# **Links**  

#### Javascript  
from [freeCodeCamp:](https://medium.freecodecamp.org/these-are-the-concepts-you-should-know-in-react-js-after-you-learn-the-basics-ee1d2f4b8030)  
Component Lifecycle, HOC higher-order components, State and setState, Context

from [creativebloq:](https://www.creativebloq.com/news/5-expert-reactjs-tips-that-you-need-to-know-today)  
Container and presentational components, Error boundaries, Portals, CSS with styled-components, Using React-specific linting, Snapshot testing with Jest, Code splitting, Server rendering, Internationalization

[React Various articles](https://react.christmas/)

[Flavio Copes](https://flaviocopes.com)

#### React
[Awesome-react](https://github.com/enaqx/awesome-react)  
[Articles about frontend](https://alligator.io/)  
[Frontend Articles](https://www.robinwieruch.de/)  
[Frontend Articles](https://www.valentinog.com)  
[Hooks collection](https://nikgraf.github.io/react-hooks/)

#### CSS Links  
[cssreference.io](https://cssreference.io)  
[Jen Simmons CSS Lab](https://labs.jensimmons.com/)  
[BEM Block Element Modifier](https://www.toptal.com/css/introduction-to-bem-methodology)  
[CSS Animation](http://animista.net)
##### CSS Grids  
[css grids](https://learncssgrid.com/)  
[Grids by example](https://gridbyexample.com)  
[Grid CSS Garden](http://cssgridgarden.com)  
[Grid CSS Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)  
##### CSS Flexbox
[Flexbox CSS Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)  

#### GIT
[git commands](https://git-scm.com/docs)  

#### Linux
[Linux commands](http://landoflinux.com/linux_basic_fundamentals.html)  

#### Various links
[github pages markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)  
[Recording Screen](https://github.com/phw/peek)
[Site Point](https://www.sitepoint.com/)
[cheatsheets](https://devhints.io)
[github help](https://help.github.com/)
[REST API Design Rulebook](https://pepa.holla.cz/wp-content/uploads/2016/01/REST-API-Design-Rulebook.pdf)
