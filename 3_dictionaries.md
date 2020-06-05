# Dictionaries 
A dictionary  is a collection of key-value pairs.
```python
myCat = {'size':'fat', 'color':'grey', 'dispoition': 'loud'}

myCat['size']
# returns 'fat' 
```
## Dictionaries vs Lists
1. Unlike lists, items in dictionaries are unordered
2. The order of items matters for determining whether two lists are the same ( == operator), it does not matter in what order the key-value pairs are typed in a dictionary
3. Since dictionaries are unordered, you cannot slice like a list

Dictionaries have 3 methods that will return list-like values.
keys(), values(), & items(), *can* be used in `for` loops
```python
spam = {'color': 'red', 'age': 42}
for v in spam.values():
    print(v)
# will print 
'red' 
42
for v in spam.keys():
    print(v)
# will print 
'color' 
'age'
for i in spam.items():
    print(i)
# will print 
('color','red') 
('age', 42)

list(spam.keys())
# will return list ['color','age']

for k, v in spam.items():
    print('Key: ' + k + ' Value: ' + str(v))
# will print 
'Key: age Value: 42' 
'Key: color Value: red'
```
You can use the multiple assignment trick in a `for` loop to assign the key and value to separate variables.
```python
'color' in spam.keys()
# will return True

'color' in spam.values()
# will return False

'color' not in spam.keys()
# will return False

'color' in spam
# will return True
```
`'color' in spam` is essentially a shorter version of writing `'color' in spam.keys()`. This is always the case: If you ever want to check whether a value is (or isn’t) a key in the dictionary, you can simply use the in (or not in) keyword with the dictionary value itself.

Dictionaries have a `get()` method that takes two arguments: the key of the value to retrieve and a fallback value to return if that key does not exist.
```python
picnicItems = {'apples': 5, 'cups': 2}
print('I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.')
# will print 'I am bringing 2 cups.'
print('I am bringing ' + str(picnicItems.get('eggs', 0)) + ' eggs.')
# will print 'I am bringing 0 eggs. Using fallback value 0'
```
The `setdefault()` method offers a way to do this in one line of code. The first argument passed to the method is the key to check for, and the second argument is the value to set at that key if the key does not exist. If the key does exist, the `setdefault()` method returns the key’s value.
```python
spam.setdefault('color', 'black')
# will return 'black' & add 'color': 'black' to dictionary
```
If you `import pprint` module into your programs, you’ll have access to the `pprint()` and `pformat()` functions that will “pretty print” a dictionary’s values. This is helpful when you want a cleaner display of the items in a dictionary than what `print()` provides.
The `pprint.pprint()` function is especially helpful when the dictionary itself contains nested lists or dictionaries. If you want to obtain the prettified text as a string value instead of displaying it on the screen, call `pprint.pformat()` instead. These two lines are equivalent to each other:
```python
pprint.pprint(someDictionaryValue)
print(pprint.pformat(someDictionaryValue))
```
