Python Notes
===
Documentation
---
+ Windows:
```
python -m pydoc <function or module>
```
+ Linux:
```
pydoc <function or module>
```

Interesting modules or functions: 
---
+ open
+ file
+ os
+ sys

---
Strings
---
####Format printed strings
```python 
my_eyes = 'Blue'
my_hair = 'Brown'
print "He's got %s eyes and %s hair." % (my_eyes, my_hair)
```

+ Raw format: %r -> Prints the variable definition, for debugging
+ Use '*' operator to repeat strings
+ Use ',' operator to avoid end line

####Heredocs
```python
print """
Alright, so you said %s about liking me.
You live in %s.  Not sure where that is.
And you have a %s computer.  Nice.
""" % ('Yes', 'Barcelona', 'Desktop')
```

####Split a string into a list
```python
ten_things = "Apples Oranges Crows Telephone Light Sugar"
stuff = ten_things.split(' ')
print stuff
>>['Apples', 'Oranges', 'Crows', 'Telephone', 'Light', 'Sugar']
```

---
Lists
---
####Create a list
```python
list = []
```

####Accessing list elements
```python
list = [1,2,3,4,5]
print list[2]
print list[-2]
print list[1:3]
>>3
>>4
>>[2, 3]
```
####Check if an element exists in a list
```python
list = [1,2,3,4,5]
exists = 1 in list
print exists
>> True
```

####Append element to a list
```python
list = [1,2,3,4,5]
list.append(6)
print 6 in list
>> True
```

####Retrieve last element from a list
```python
list = [1,2,3,4,5]
element = list.pop()
print element
print list
>> 5
>> [1,2,3,4]
```

####Join list elements as string
```python
list = ['a','b','c','d']
print '#'.join(list)
>> a#b#c#d
```

---
Dictionaries
---
####Create dictionary and access its elements
```python
dict = {'name': 'John', 'surname': 'Doe', 'age': 15, 'height': 5 * 2 + 170}
print dict['height']
>> 180

dict['weight']=75
print dict
>> {'age': 15, 'surname': 'Doe', 'name': 'John', 'weight': 75, 'height': 180}
```

####Enumerate dictionary items (key,value pairs)
```python
dict = {'name':'John', 'surname':'Doe'}
for key, value in dict.items():
    print 'key: %s, value: %s' % (key, value)
>>key: surname, value: Doe
>>key: name, value: John
```

####Removing elements from a dictionary
```python
del dict['name']
#or
dict.pop('name')
```

---
Input
---
####Obtain raw input from user
```python
print "How old are you?",
age = raw_input()
age = raw_input("How old are you? ")
```
> __WARNING__: Avoid input() use for security!!

####Arguments
#####Unpacking arguments
```python
from sys import argv
script_name, first, second, third = argv
```

---
File Handling
---
#####Open file : 
```python
file = open(filename, open_mode)
```

>Open mode: 
>
>+ __r__: read
>+ __a__: append
>+ __w__: write __WARNING__ This mode truncates file!

#####Read file
```python
file.read()
```
#####Close file
```python
file.close()
```
#####Read only one file line
```python
file.readLine()
```
#####Empty the file
```python
file.truncate()
```
#####Write stuff to the file
```python
file.write('stuff')
```
#####check if file exists
```python
exists(filename)
```
#####check file length
```python
len(file)
```

---
Functions
---
####Declare a function
```python
def sum_function(parameter1, parameter2)
    print "Here goes the function content"
    return_stuff = parameter1 + parameter2
    return return_stuff
```

####Call a function and store its returning value
```python
sum_result = sum_function(5,8)
```

---
Flow Control
---

####Conditionals
```python
if cars > people:
    print "We should take the cars."
elif cars < people:
    print "We should not take the cars."
else:
    print "We can't decide."
```

####Loops
#####"While" loop
```python
count = 0
while count < 5:
    print count
    count += 1  # This is the same as count = count + 1
```

#####"For" loop
```python
fruits = ['apples', 'oranges', 'pears', 'apricots']
for fruit in fruits:
    print "A fruit of type: %s" % fruit
```

#####Loop over a range
```python
for x in xrange(3, 8, 2): # or range(3, 8, 2)
    print x
```

#####Break and continue
```python
count = 0
while True:
    print count
    count += 1
    if count >= 5:
        break

for x in xrange(10):
    # Check if x is even
    if x % 2 == 0:
        continue
    print x
```

#####Else clauses in loops
```python
count=0
while(count<5):
    print count
    count +=1
else:
    print "count value reached %d" %(count)
```

---
Modules
---
* Called ````<module_name>.py```
* Contains functions
* Can be imported using the ```import <module_name>``` instruction.

```python
import maths_module
print maths_module.add(3,5)
>> 8
```

---
Classes
---
####Declaring a class
```python
class MyStuff(object):

    def __init__(self):
        self.tangerine = "And now a thousand years between"

    def apple(self, colour):
        print "I AM %s CLASSY APPLES!" % (colour)

```

####Using a class
```python
thing = MyStuff()
thing.apple()
print thing.tangerine
>>I AM CLASSY APPLES!
>>And now a thousand years between
```
