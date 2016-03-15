
#Python Functions
In order to write efficient code, functions are essential. As you will see as you continue to transition to Python, many of the concepts of programming's building blocks are the same - including functions. The syntax is really one of the few differences between functions in JavaScript and functions in Python. 

#Objectives:
+ Declare functions with and without parameters
+ Call functions with and without passing arguments
+ Understand local and global variable scope
+ Understand the concept of a return value

##Function Declaration
The syntax for writing Python functions is very specific. To define a function in Python, you want to use the `def` statement:

```python
def get_lunch():
	print ""
```

The key elements here are the `def` statement, the name of the function, the parentheses and the colon at the end of the declaration. The instructions go inside this function as demonstrated by the indentation.

Indentation matters in Python. If the code blocks is not properly indented, your code throw an error:
```
IndentationError: unindent does not match any outer indentation level
```

Just like variable names, function names should be snake_case - lowercase characters separated by underscores when necessary.

```python
def get_lunch():
	print "Close Computer"
	print "Stand up"
	print "Walk out the door"
```
If you put this code into a Python script, nothing will happen. Why is that? We declared our function - which is like adding the `get_lunch` function to the computer’s dictionary - but we didn’t actually tell the computer to execute the function.

To invoke a function, write the name of the function and include parenthesis. The parenthesis should contain your arguments if needed. Here's how we'd invoke the `get_lunch()` defined above:

```
get_lunch()
>> "Close Computer"
>> "Stand Up"
>> "Walk out the door"
```


## Using Parameters (Inputs)

In the example above, we created functions without any inputs, or parameters. However, most of the time you'll want your functions to take in a piece of data (or more than one) and then return data based on that initial input. To add a parameter to a function in Python, just add the parameter variables inside of the parenthesis in your function declaration.

```python
def get_lunch(student):
	print 'hey, ' + student
	print 'close your computer'
	print 'stand up'
	print 'walk out the door'
```
Then call the function by writing the name of the function and a name as the argument.

```python
get_lunch("Joe");
>>'hey Joe '
>>'close your computer'
>>'stand up'
>>'walk out the door'

get_lunch("Jill");
>>'hey Jill '
>>'close your computer'
>>'stand up'
>>'walk out the door'

get_lunch("Josie");
>>'hey Josie '
>>'close your computer'
>>'stand up'
>>'walk out the door'
```
As you can see above, we call the function three times with a different name for the `student` parameter. The content that is printed to the console is changed based on that input.

Let's practice with another example. Let's say we want to create a function that prints the square of any number that we're given. First, we define the function:

```python
def square(number):

```
We created a parameter `number` to hold the value that the user passes to us when they call the function.

```python
def square(number):
    squared_number = number*number
    print squared_number
```
In the method's code block, we create a variable called `squared_number` and set it equal to the number multiplied by itself. Finally, we print this `squared_number` variable.

Now, let's try calling the method.

```
square(2)
>> 4
square(6)
>> 36
square(20)
>>400
```

### Arguments vs Parameters
It's important to distinguish between arguments and parameters.
* A parameter is a variable in the function definition: "student".
* An argument is the data you pass into the function's parameters when you call it: "Joe", "Jill", "Josie"

## Return Values
When a function is invoked, the code block is executed. If you want to make use of a modified value elsewhere in the code, you need to return that value.
```python
def weird_math(x,y):
    return (x * 10) + y

print weird_math(2,3)		
```

## Variable Scope

Another thing that is important to reiterate about functions is variable scope. The scope refers to where a variable can be used. A global variable can be access anywhere in a script, whereas a local variable remains inside a function. This can be one of the trickier concepts for your students, so try and name your variables as uniquely as possible during instruction.

### Global Variables
When you declare a variable outside of a function it will also be available inside of the function. This is called a global variable. For example:

 ```python
 num = 10 #global variable
 def is_even():
 	if (num%2 ==0):
 		return True
 	else:
 		return False

print is_even()		
```

If I run `is_even();` we’ll get back false. The function `is_even()` has access to the variable num that was declared outside of the function.

### Local Variables
If you declare a variable inside of a function it will only be available inside of the function. This is called a local variable.

Here is an example:

 ```
 def double(num):
    doubled = num*2  # local var
    return doubled

 print doubled  # Throws an error, since the variable is local to the function 'double'

 print double(4)  # Prints correctly since we are printing the returned value
 ```

*Variable scope*  seems complicated but it's really important and helpful to separate function variable and global variables.


## Conclusion
Functions are the building block of any developer. In most languages, functions contain a name, optional inputs, instructions inside a code block and an option return value. As you start to dive deeper into Python, be mindful about how the syntax of a function is slightly different than in other languages. 
