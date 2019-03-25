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

