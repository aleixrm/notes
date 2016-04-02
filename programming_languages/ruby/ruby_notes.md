#Ruby tips

###3 kinds of vars:
1. Boolean
2. Numbers
3. Strings

###Method calls
The methods are called with '.'

###Comments:
```ruby
#This is a comment in ruby
=begin
This is
a multiline comment
in ruby
=end
```

###Naming:
####Local variables:
separated by underscore
```ruby
var_name="value"
```

###Output:
`print` Print out a text
`puts` Print out a newline char after the text
```ruby
name="John Doe"
print "Hello, my name is #{name}"
#-> "Hello, my name is John Doe"
```

###Input:
`gets` Retrieves user input from command prompt
`chomp` Removes the newline character from `gets`

###String format
upcase
downcase
capitalize

###Modify the value of a variable itself
Call a method, and end the instruction with '!'
e.g.:
```ruby
name="john"
name.capitalize!
puts name
#-> "John"
```

###Operators
* Addition: +
* Difference: -
* Multiplication: *
* Divisor: /
* Potency: **

###Flow control
####If/elsif/else
```ruby
if <condition>
    <action>
elsif <condition>
    <action>
else
    <action>
end
```
####Unless/else
```ruby
unless <condition>
    <action>
else
    <action>
end
```