# BACKEND
---
  
## PYTHON

<h4>Byte code compilation</h4>
Internally, Python compiles sourcecode into a format called bytecode.  
Compilation is simply a translation step, and byte code is a lower-level, and platform-independent,representation of your source code.  
This byte code translation is performed to speed execution.  

byte code it is executed to something called PythonVirtual Machine.  
PVM iterates through bytecode.  
It is the runtime engine of Python; it’s always present as part of thePython system, and is the component that truly runs your scripts.  
Technically, it’s just the last step of what is called the Python interpreter.  

<h4>Built-in datatypes</h4>
- Numbers
- Strings
- Lists and Dictionaries
- Tuples, Files...

<h4>Strings</h4>
String Methods
```
capitalize() - Returns the string with first letter capitalized and the rest lowercased.
casefold() - Returns a lowercase string, generally used for caseless matching. This is more aggressive than the lower() method.
center() - Center the string within the specified width with optional fill character.
count() - Count the non-overlapping occurrence of supplied substring in the string.
encode() - Return the encoded version of the string as a bytes object.
endswith() - Returns ture if the string ends with the supplied substring.
expandtabs() - Return a string where all the tab characters are replaced by the supplied number of spaces.
find() - Return the index of the first occurrence of supplied substring in the string. Return -1 if not found.
format() - Format the given string.
format_map() - Format the given string.
index() - Return the index of the first occurrence of supplied substring in the string. Raise ValueError if not found.
isalnum() - Return true if the string is non-empty and all characters are alphanumeric.
isalpha() - Return true if the string is non-empty and all characters are alphabetic.
isdecimal() - Return true if the string is non-empty and all characters are decimal characters.
isdigit() - Return true if the string is non-empty and all characters are digits.
isidentifier() - Return true if the string is a valid identifier.
islower() - Return true if the string has all lowercased characters and at least one is cased character.
isnumeric() - Return true if the string is non-empty and all characters are numeric.
isprintable() - Return true if the string is empty or all characters are printable.
isspace() - Return true if the string is non-empty and all characters are whitespaces.
istitle() - Return true if the string is non-empty and titlecased.
isupper() - Return true if the string has all uppercased characters and at least one is cased character.
join() - Concatenate strings in the provided iterable with separator between them being the string providing this method.
ljust() - Left justify the string in the provided width with optional fill characters.
lower() - Return a copy of all lowercased string.
lstrip() - Return a string with provided leading characters removed.
maketrans() - Return a translation table.
partition() - Partition the string at first occurrence of substring (separator) and return a 3-tuple with part before separator, the separator and part after separator.
replace() - Replace all old substrings with new substrings.
rfind() - Return the index of the last occurrence of supplied substring in the string. Return -1 if not found.
rindex() - Return the index of the last occurrence of supplied substring in the string. Raise ValueError if not found.
rjust() - Right justify the string in the provided width with optional fill characters.
rpartition() - Partition the string at last occurrence of substring (separator) and return a 3-tuple with part before separator, the separator and part after separator.
rsplit() - Return a list of words delimited by the provided subtring. If maximum number of split is specified, it is done from the right.
rstrip() - Return a string with provided trailing characters removed.
split() - Return a list of words delimited by the provided subtring. If maximum number of split is specified, it is done from the left.
splitlines() - Return a list of lines in the string.
startswith() - Return true if the string starts with the provided substring.
strip() - Return a string with provided leading and trailing characters removed.
swapcase() - Return a string with lowercase characters converted to uppercase and vice versa.
title() - Return a title (first character of each word capitalized, others lowercased) cased string.
translate() - Return a copy of string that has been mapped according to the provided map.
upper() - Return a copy of all uppercased string.
zfill() - Return a numeric string left filled with zeros in the provided width.
```

<h4>Lists</h4>
List methods
```
append() - Add an element to the end of the list
extend() - Add all elements of a list to the another list
insert() - Insert an item at the defined index
remove() - Removes an item from the list
pop() - Removes and returns an element at the given index
clear() - Removes all items from the list
index() - Returns the index of the first matched item
count() - Returns the count of number of items passed as an argument
sort() - Sort items in a list in ascending order
reverse() - Reverse the order of items in the list
copy() - Returns a shallow copy of the list
```

List comprehension
```
pow2 = [2 ** x for x in range(10)]

# Output: [1, 2, 4, 8, 16, 32, 64, 128, 256, 512]
print(pow2)

# Equivalent to
pow2 = []
for x in range(10):
   pow2.append(2 ** x)
```

built-in functions list
```
all()	Return True if all elements of the list are true (or if the list is empty).
any()	Return True if any element of the list is true. If the list is empty, return False.
enumerate()	Return an enumerate object. It contains the index and value of all the items of list as a tuple.
len()	Return the length (the number of items) in the list.
list()	Convert an iterable (tuple, string, set, dictionary) to a list.
max()	Return the largest item in the list.
min()	Return the smallest item in the list
sorted()	Return a new sorted list (does not sort the list itself).
sum()	Return the sum of all elements in the list.
```

<h4>Tuples</h4>
The difference between the two is that we cannot change the elements of a tuple once it is assigned  
```
# tuple having integers
# Output: (1, 2, 3)
my_tuple = (1, 2, 3)
print(my_tuple)
```

<h4>Dictionaries</h4>
Python dictionary is an unordered collection of items. While other compound data types have only value as an element, a dictionary has a key: value pair.  
```python
# empty dictionary
my_dict = {}

# dictionary with integer keys
my_dict = {1: 'apple', 2: 'ball'}

# dictionary with mixed keys
my_dict = {'name': 'John', 1: [2, 4, 3]}

# using dict()
my_dict = dict({1:'apple', 2:'ball'})

# from sequence having each item as a pair
my_dict = dict([(1,'apple'), (2,'ball')])
```

Access elements from a dictionary
```python
my_dict = {'name':'Jack', 'age': 26}

# Output: Jack
print(my_dict['name'])

# Output: 26
print(my_dict.get('age'))
```

Update/Add
```python
my_dict = {'name':'Jack', 'age': 26}

# update value
my_dict['age'] = 27

#Output: {'age': 27, 'name': 'Jack'}
print(my_dict)

# add item
my_dict['address'] = 'Downtown'  

# Output: {'address': 'Downtown', 'age': 27, 'name': 'Jack'}
print(my_dict)
```

Delete/Removes
```python
# create a dictionary
squares = {1:1, 2:4, 3:9, 4:16, 5:25}  

# remove a particular item
# Output: 16
print(squares.pop(4))  

# Output: {1: 1, 2: 4, 3: 9, 5: 25}
print(squares)

# remove an arbitrary item
# Output: (1, 1)
print(squares.popitem())

# Output: {2: 4, 3: 9, 5: 25}
print(squares)

# delete a particular item
del squares[5]  

# Output: {2: 4, 3: 9}
print(squares)

# remove all items
squares.clear()

# Output: {}
print(squares)

# delete the dictionary itself
del squares

# Throws Error
# print(squares)
```

Dictionaries methods
```python
clear()	Remove all items form the dictionary.
copy()	Return a shallow copy of the dictionary.
fromkeys(seq[, v])	Return a new dictionary with keys from seq and value equal to v (defaults to None).
get(key[,d])	Return the value of key. If key doesnot exit, return d (defaults to None).
items()	Return a new view of the dictionary's items (key, value).
keys()	Return a new view of the dictionary's keys.
pop(key[,d])	Remove the item with key and return its value or d if key is not found. If d is not provided and key is not found, raises KeyError.
popitem()	Remove and return an arbitary item (key, value). Raises KeyError if the dictionary is empty.
setdefault(key[,d])	If key is in the dictionary, return its value. If not, insert key with a value of d and return d (defaults to None).
update([other])	Update the dictionary with the key/value pairs from other, overwriting existing keys.
values()	Return a new view of the dictionary's values
```

<h4>Sets</h4>
A set is an unordered collection of items. Every element is unique (no duplicates) and must be immutable (which cannot be changed).  
However, the set itself is mutable. We can add or remove items from it.  
```python
# initialize my_set
my_set = {1, 3, 4, 5, 6}
print(my_set)
```

sets methods
```python
add()	Adds an element to the set
clear()	Removes all elements from the set
copy()	Returns a copy of the set
difference()	Returns the difference of two or more sets as a new set
difference_update()	Removes all elements of another set from this set
discard()	Removes an element from the set if it is a member. (Do nothing if the element is not in set)
intersection()	Returns the intersection of two sets as a new set
intersection_update()	Updates the set with the intersection of itself and another
isdisjoint()	Returns True if two sets have a null intersection
issubset()	Returns True if another set contains this set
issuperset()	Returns True if this set contains another set
pop()	Removes and returns an arbitary set element. Raise KeyError if the set is empty
remove()	Removes an element from the set. If the element is not a member, raise a KeyError
symmetric_difference()	Returns the symmetric difference of two sets as a new set
symmetric_difference_update()	Updates a set with the symmetric difference of itself and another
union()	Returns the union of sets in a new set
update()	Updates the set with the union of itself and others
```

---

Get minimum/max/sort value from a dictionary
```
prices = {
 'shows': 41,
 'tshirts': 55,
 'gloves': 22,
 'hats': 11
}

min_price = min(zip(prices.values(), prices.keys()))
max_price = max(zip(prices.values(), prices.keys()))
prices_sorted = sorted(zip(prices.values(), prices.keys()))
```

Given two dictionaries
```
# Find keys in common
a.keys() & b.keys()
# Find keys in a that are not in b
a.keys() - b.keys()
# Find (key,value) pairs in common
a.items() & b.items()
# Make a new dictionary with certain keys removed
c = {key:a[key] for key in a.keys() - {'z', 'w'}}
# Make a dictionary of all prices over 200
p1 = { key:value for key, value in prices.items() if value > 200 }
# Make a dictionary of tech stocks
tech_names = { 'AA', 'BB', 'CC', 'DD' }
p2 = { key:value for key,value in prices.items() if key in tech_names }
```
https://d.cxcore.net/Python/Python_Cookbook_3rd_Edition.pdf

## NODE
<h4>About</h4>
Node.js is an open source, cross-platform runtime environment for developing server-side and networking applications.  

<h4>Features of Node.js</h4>
- Asynchronous and Event Driven  
- Fast: based on Google Chrome's V8 JavaScript Engine  
- Single Threaded but scalable: Event mechanism helps the server to respond in a non-blocking way  
- No buffering  

<h4>Node components</h4>
A Node.js application consists of the following three components:  

- Import required modules: Use the require directive to load Node.js modules.  
- Create server: A server which will listen to client's requests similar to Apache HTTP Server.  
- Read request and return response: Read the HTTP request made by the client which can be a browser or a console and return the response.  

<h4>Node application 'Hello World'</h4>
Import required module:
```
var http = require("http");
```

Create Server main.js
```
http.createServer(function (request, response) {

 // Send the HTTP header
 // HTTP Status: 200 : OK
 // Content Type: text/plain
 response.writeHead(200, {'Content-Type': 'text/plain'});

 // Send the response body
 response.end('Hello World\n');
}).listen(8081);

// Console print the message
console.log('Server running at http://127.0.0.1:8081/');
```

Run it
```
node main.js
```

<h4>REPL stands for Read Eval Print Loop</h4>
REPL stands for Read Eval Print Loop.  
it represents a computer environment like a Windows console or Unix/Linux shell where a command is entered and the system responds with an output in an interactive mode.  
REPL can be started by simply running node on shell/console.  

<h4>NPM node package manager</h4>
- Online repositories for node.js  
- Command line utility to install Node.js packages  

<h4>Install Modules using npm</h4>
```
npm install <Module Name>
```

install express
```
npm install express
```
use it as follow:
```
var express = require('express');
```
other commands
```
npm uninstall express
npm update express
npm search express
```

<h4>Callback function</h4>
A callback function is called at the completion of a given task.  
Node makes heavy use of callbacks.  
All the APIs of Node are written in such a way that they support callbacks.  
```
var fs = require("fs");
fs.readFile('input.txt', function (err, data) {
 if (err) return console.error(err);
 console.log(data.toString());
});
console.log("Program Ended");
```

<h4>Streams</h4>
Streams are objects that let you continuosly read data.  
There are 4 types of stream:
- Readable  
- Writable  
- Duplex  
- Trasform  

example
```
var fs = require("fs");
var data = '';

// Readable stream
var readerStream = fs.createReadStream('input.txt');

// Encoding to be utf8. 
readerStream.setEncoding('UTF8');

// Stream events
readerStream.on('data', function(chunk) {
   data += chunk;
});

readerStream.on('end',function() {
   console.log(data);
});

readerStream.on('error', function(err) {
   console.log(err.stack);
});

console.log("End");
```

<h4>Modules</h4>
Utility modules:
- OS Module  
- Path Module  
- Net Module  
- DNS Module  
- Domain Module  

<h4>Express</h4>
Express is a minimal Node.js web application framework.  
Allows to set up middlewares to respond to HTTP Requests.  
Defines a routing table which is used to perform different actions based on HTTP Method and URL.  
Allows to dynamically render HTML Pages based on passing arguments to templates.  

Install Express
```
npm install express --save
```

Other important modules:  
body-parser − middleware for handling JSON, Raw, Text and URL encoded form data.  
cookie-parser − Parse Cookie header  
multer − This is a node.js middleware for handling multipart/form-data.  

```
$ npm install body-parser --save
$ npm install cookie-parser --save
$ npm install multer --save
```

Express example:  
```
var express = require('express');
var app = express();

app.get('/', function (req, res) {
   res.send('Hello World');
})

var server = app.listen(8081, function () {
   var host = server.address().address
   var port = server.address().port
   
   console.log("Example app listening at http://%s:%s", host, port)
})
```
Run it
```
node server.js
```

Return a list of users from a JSON file:  
```
var express = require('express');
var app = express();
var fs = require("fs");

app.get('/listUsers', function (req, res) {
   fs.readFile( __dirname + "/" + "users.json", 'utf8', function (err, data) {
      console.log( data );
      res.end( data );
   });
})

var server = app.listen(8081, function () {
   var host = server.address().address
   var port = server.address().port
   console.log("Example app listening at http://%s:%s", host, port)
})
```
<h4>Events driven</h4>
Whenever an event gets fired, its listener function starts executing.  
EventEmitter class which is used to bind events and event-listeners.  
Any async function accepts a callback as the last parameter and a callback function accepts an error as the first parameter.  
```
// Import events module
var events = require('events');

// Create an eventEmitter object
var eventEmitter = new events.EventEmitter();

// Bind event and event  handler as follows
eventEmitter.on('eventName', eventHandler);
```

// Fire an event 
```
eventEmitter.emit('eventName');
```

<h4>EventEmitter</h4>
```
// Import events module
var events = require('events');

// Create an eventEmitter object
var eventEmitter = new events.EventEmitter();
```

Methods
```
addListener(event, listener)
on(event, listener)
once(event, listener)
removeListener(event, listener)
removeAllListeners([event])
setMaxListeners(n)
listeners(event)
emit(event, [arg1], [arg2], [...])
```

Class Methods
```
listenerCount(emitter, event)
```

Events
```
newListener
removeListener
```

```
var events = require('events');
var eventEmitter = new events.EventEmitter();

// listener #1
var listner1 = function listner1() {
   console.log('listner1 executed.');
}

// listener #2
var listner2 = function listner2() {
   console.log('listner2 executed.');
}

// Bind the connection event with the listner1 function
eventEmitter.addListener('connection', listner1);

// Bind the connection event with the listner2 function
eventEmitter.on('connection', listner2);

var eventListeners = require('events').EventEmitter.listenerCount
   (eventEmitter,'connection');
console.log(eventListeners + " Listner(s) listening to connection event");

// Fire the connection event 
eventEmitter.emit('connection');

// Remove the binding of listner1 function
eventEmitter.removeListener('connection', listner1);
console.log("Listner1 will not listen now.");

// Fire the connection event 
eventEmitter.emit('connection');

eventListeners = require('events').EventEmitter.listenerCount(eventEmitter,'connection');
console.log(eventListeners + " Listner(s) listening to connection event");

console.log("Program Ended.");
```

```
node main.js
```
