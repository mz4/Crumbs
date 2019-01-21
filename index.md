### ---

###  GIT

#### get tag
```
git log --decorate v0.4bugfix|head -n1|sed 's/.*tag: //;s/[^a-zA-Z.0-9].*//'
```
#### get commits by date and author
```
git log --pretty=format:"%ad - %an: %s" --after="2010-02-15" --until="2018-08-20" --author="John"
```

#### number of commits by author
```
git shortlog -s -n --all
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

###  CSS3/SASS

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

## JAVASCRIPT  

#### Global Environment and the Global Object.
Whenever code is run in JavaScript, it's run inside an execution context.  
The global execution context creates a Global Object and it creates a special variable, called 'this'.  
The JavaScript engine is creating these two things for you whenever your code is run, because your code is wrapped inside an execution context.  
So, your variables and your functions when lexically is not sitting inside a function, they're just sitting right there on the global object.  
All right, so, when code is executed, your JavaScript code is executed, an execution context is created.  
At the base level, when you're not inside a function, you have a global object that the JavaScript engine creates for you as part of that execution context.  
If you're running code inside a browser, that Global Object is the window object. You'd get a special variable called "this:. And in the case of the browser this at that global level is just the same as the window object, it's equal to the window object.  

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

### ES6
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

## React

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

## Linux Commands
#### File Commands
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

###  WEBPACK

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

## Links
#### Javascript  
from [freeCodeCamp:](https://medium.freecodecamp.org/these-are-the-concepts-you-should-know-in-react-js-after-you-learn-the-basics-ee1d2f4b8030)  
Component Lifecycle, HOC higher-order components, State and setState, Context

from [creativebloq:](https://www.creativebloq.com/news/5-expert-reactjs-tips-that-you-need-to-know-today)  
Container and presentational components, Error boundaries, Portals, CSS with styled-components, Using React-specific linting, Snapshot testing with Jest, Code splitting, Server rendering, Internationalization

[React Various articles](https://react.christmas/)

#### CSS Links  
[cssreference.io](https://cssreference.io)

#### GIT
[git commands](https://git-scm.com/docs)

#### Various links
[github pages markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
