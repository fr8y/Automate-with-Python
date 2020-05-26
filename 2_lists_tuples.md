# Lists
```python
# A list contains multiple items in order, comma-seperated, in [] 
spam = ['cat', 2, True, None]  
spam[0] is cat 
spam[-1] is None
spam[-2] is True
spam[1] is 2

# A slice will return a sublist, first # is starting index, 2nd # is the end & not included
spam[0:4] is ['cat', 2, True, None]  
spam[1:3] is [2, True] 

# you can leave out first # to use 0 starting index 
spam[:2] is ['cat', 2] 

# you can get # of items in list with len()
len(spam) will return 4 

# you can change an item in a list 
spam[1] = 'felix'
spam  is now ['cat', 'felix', True, None] 

# List can be concatenated with + & replicated with *
[1,2,3] + ['a','b','c'] = [1,2,3,'a','b','c'] 
[1,2,3] * 3 = [1,2,3,1,2,3,1,2,3] 

# item in list can be removed with del 
del spam [3]
spam is now ['cat', 'felix', True]

# can iterate over items in list with for i in range(len(someList)):
for i in range(len(spam)):
	print('Index ' + str(i) + ' in spam is: ' + spam[i]) 

# can use in or not in to determine if a value is in or not in a list, will return a boolean 
'felix' in spam #will return True
5 not in spam #will return True
'cow' in spam #will return False 

# lists have index() method, will return index of value, will return valueError if value is not in list
spam.index('felix') #will return 1

# you can add items to a list with methods append() or insert()
spam.append('bat')
# spam will now return ['cat', 'felix', True, 'bat']
spam.insert(1, 8) 
# spam will now return ['cat', 8, 'felix', True, 'bat']

# you can remove items from a list with remove() method
spam.remove('bat') # spam will now return ['cat', 8, 'felix', True]

# you can sort items in a list with sort() method
# sort works in place, do not try to capture return value with assignment 
# sort works only if list is all str or all int 
# sort uses ASCII order, so all uppercase chars come before lowercase 
listA = ['Bob', 'alex', 'Arty', 'Hue']
listA.sort() 
# will assign listA ['Arty', 'Bob', 'Hue', 'alex']
listA.sort(key=str.lower)
# will assign listA ['alex', 'Arty', 'Bob', 'Hue'] sort(key=str.lower) will treat all chars as lowercase without changing the value

# A string is "list-like", a sequence of chars, similar to lists it has: indexing, slicing, use with for loops, with len(), use with in & not in operators
name = 'felix'
name[0] # will return 'f' 
name[-2] #will return 'i'
name[0:2] #will return 'fe'
'fe' in name #will return True
'Fe' in name #will return False                 

for i in name:
	print('** ' + i + ' **')

# will print
** f **
** e **
** l **
** i **
** x **
```

A list is mutable, items can be added, removed, & changed. A string is immutable, you cannot add or change a single char in str, you can slice & concatenate an old str to create a new str

# Tuples

Tuples are used to convey that you don't intend to change this sequence of values

A 2nd benefit of tuples is because their contents don't change Python can implement optimizations to make code run slightly faster

A tuple is identical to a list except it uses () instead of []
& it is immutable; cannot add, remove, or change values. 

```python
# If you have only 1 value in a tuple you need a trailing comma 
type(('hello',)) # will return <class 'tuple'>
type(('hello')) # will return <class 'str'>

# you can convert lists to tuples & tuples to lists
tuple(['some','list','to','convert'])
# returns tuple ('some','list','to','convert')
list('hello')
# returns list ['h', 'e', 'l', 'l', 'o']

# In Python variables are assigned references to a list, not the actual list value itself.
spam = [1,2,3]
cheese = spam 
del cheese[2]

for i in spam:
	print(i)
#will print
1
2
# del cheese[2] deleted value in same list referenced in spam. The variables hold a reference to the same list, not the list itself. 
```
**Python uses references whenever variables must store values of mutable data types, such as lists or dictionaries.**

**For values of immutable data types such as strings, integers, or tuples, Python variables will store the value itself.**

Python has a copy module if you'd like to copy a list without both variables referencing the same list 
```python
import copy

spam = [1,2,3]
cheese = copy.copy(spam)
del cheese[2]

for i in spam:
	print(i)
#will print
1
2
3
```
With copy.copy() cheese is now referencing a different list value, so changing cheese does not affect spam. copy.deepcopy() is available for lists that contain lists. 

