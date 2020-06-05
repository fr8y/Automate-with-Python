# Python Basics
```python
# Collect input as str from stdin & assign to var 
myAge = input()

# Print to stdout, str only, convert with str(), + for str concat, * for str replication
print('You will be ' + str(int(myAge) + 1) + ' in a year.') 

# Returns int value of number of chars in str iwth len()
print(len('somestring'))

# Converts value passed into str(), int(), or float()
int('42')
float('3.25')
str(22)
```

# Flow Control
```python
# if keyword, a condition for T or F, a colon, new line with indent 
if name == 'Alice':
	print('Hi, Alice.')

# elif keyword, a condition for T or F, a colon, new line with indent
elif name == 'Tom':
	print('Hi, Tom.')

# else keyword, a colon, new line with indent
else:
	print('Hello, stranger.')

# while keyword, a condition for T or F, a colon, new line with indent
spam = 0
while spam < 5:
	print('Hello, world.')
	spam = spam + 1

# break keyword, exits loop immediately
while True:
	print('Please type your name.')
	name = input()
	if name == 'your name':
		break
print('Thank you!')

# continue keyword, jumps back to start of loop & reevaluates condition
while True:
	print('Who are you?')
	name = input()
	if name != 'Joe':
		continue
	print('Hello, Joe. What is the password? (It is a fish.)')
	password = input()
	if password == 'swordfish':
		break
print('Access granted.')

# for keyowrd, var name, in keyword, range(), a colon, new line with indent 
print('My name is')
for i in range(5):
	print('Jimmy Five Times (' + str(i) + ')')

# range() accepts 3 int values, 1st is for loop var start, 2nd will be stop not including, 3rd is step how loop var increments
for i in range(0, 10, 2):
	print(i) # will print 0-8
```

# Functions
```python
# Create a function with def keyword, name of func, any args in (), a colon, next line indent
def hello(name):
	print('Hello ' + name)
hello('Alice')
hello('Bob')

# return keyword, value or expression the func should return
def hello(name):
	return 'Hello ' + name
print(hello('Bob'))

# Python adds return None to the end of any func with no return statement. If you use the keyword return by itself the func returns None
# None == null == undef == nil

# global keyword, name of global var to call, in this function this var refers to global var
def spam():
	global eggs
	eggs = 'spam'
eggs = 'global'
spam()
print(eggs)
# spam will be printed

def spam(divideBy):
	# For exception handling try keyword, a colon, next line indented
	try:
		return 42 / divideBy
	# Pass error to except keyword, a colon, next line indented
	except ZeroDivisionError:
		print('Error: Invalid argument.')
```