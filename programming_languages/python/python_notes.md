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


