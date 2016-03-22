
# Python Functions


## Objectives:
+ Declare functions with and without parameters
+ Call functions with and without passing arguments
+ Understand local and global variable scope
+ Understand the concept of a return value

In order to write efficient code, functions are essential. Remember that functions are tiny modules of **re-usable** code. Functions allow us to avoid redundancy because they allow us to **perform similar operations on different data.** Functions also make our scripts hierarchical and more readable because they break our code apart into smaller abstractions.

As you will see as you continue to transition to Python, many of the concepts are very similar (if not identical) to other languages you may have learned. The syntax is really one of the few differences between functions in JavaScript and functions in Python. 

##Function Declaration
The syntax for writing Python functions is very specific. To define a function in Python, you want to use the `def` statement:

```python
def my_greeting():
	print "hello!"
```

The key elements here are the `def` keyword, the name of the function, the parentheses and the colon at the end of the declaration. The instructions go inside this function as demonstrated by the indentation (indentation should be 4 spaces).

Indentation matters in Python. If the code block is not properly indented, your code throw an error:

```
IndentationError: unindent does not match any outer indentation level
```

Just like variable names, function names should be written in snake_case - lowercase characters separated by underscores when necessary.

```python
def my_favorite_greeting():
	print "Hello Super Python Programmer"
```

If you put this code into a Python script, nothing will happen. Why is that? We declared our function - which is like adding the `my_greeting` function to the computer’s dictionary - but we didn’t actually tell the computer to execute the function.

To invoke a function, write the name of the function and include parentheses. The parentheses should contain any arguments if they needed. Here's how we'd invoke the `my_greeting()` function defined above. 

```
>>my_favorite_greeting()
Hello Super Python Programmer
```


## Using Parameters (Inputs)
As amazing as the `my_favorite_greeting()` function is, it's still pretty literal. It hard-codes, or directly specifies, name of the person we are greeting as `"Super Python Programmer"`. If we wanted to build a method that can greet *anyone*, even Ruby programmers, we'd have to re-implement the majority of the original logic from `greeting`:

```python
def my_favorite_greeting_ruby():
    print "Hello Super Ruby programmer!"
```

Notice the only things that changed are the function name and the language name `"Ruby"` in the body of the function. It's as though that information should be specifiable or configurable when you call the funciton, otherwise we'd have to build every permutation of the function. In other words, we'd have to re-write the funciton for every single person we want to greet. 

We always want functions to be more dynamic, more abstract, *more re-usable*. They should maintain the elements that will always be the same, no matter who we greet, and allow us to change, or swap out, the name of the person we are greeting. This is dynamic, as opposed to "hard-coded". 

Good news, that's exactly what parameters are for:


```python
def my_greeting(name):
	print 'Hello, ' + name +'!'
```
Then call the function by writing the name of the function and a name as the argument.

```python
>>>my_greeting("Newman");
Hello, Newman!

>>>my_greeting("Jerry")
Hello, Jerry!

>>>my_greeting("World")
Hello, World!

```
As you can see above, we call the function three times with a different value for the `name` parameter. The content that is printed to the console is changed based on that input.

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

So far, we've been ending our functions with `print` so that we can see the output of the function. However, we are going to move away from this from now on. When a function is invoked, the code block is executed and we want to take away a value that we can use in other parts of our code. Maybe we want to feed the value into another function, or save it to a database. If we use the `print` keyword, the return value will always be *nothing* or `'NoneType'`. If you want to make use of the value coming out of a function elsewhere in your code, you need to `return` that value. To return a variable use the `return` keyword.

```python
def weird_math(x,y):
    return (x * 10) + y

print weird_math(2,3)
=> 23		
```
Note that we're not printing the value inside of our method. Instead we're `return`ing it and then printing the return value when we call the function itself. It looks like a small change, but it makes a big difference in what you can do with your code. From now on, be sure to use `return` at the end of your functions (unless you really just want to print something). Feel free to also use `print` inside your function, just make sure it's not on the last line:

```python
def weird_math(x,y):
    print "this is a very strange equation"
    return (x * 10) + y

print weird_math(2,3)
=> this is a very strange equation
=> 23
```

## Variable Scope

Another thing that is important to reiterate about functions is variable scope. The scope refers to where a variable can be used. A global variable can be accessed anywhere in a script, whereas a local variable remains inside a function. This can be one of the trickier concepts for your students, so try and name your variables as uniquely as possible during instruction.

### More on scope

When you declare a variable **outside** of a function it will also be available **inside** of the function. For example:

 ```python
 num = 10 # variable
 
 def is_even():
 	if (num%2 ==0):
 		return True
 	else:
 		return False

print is_even()		
```

If I run `is_even();` we’ll get back false. The function `is_even()` has access to the variable num that was declared outside of the function.


*However,* if you declare a variable **inside** of a function it will **only be available inside of the function.** 

Here is an example:

 ```
 def double(num):
    doubled = num*2  # here's our variable
    return doubled

 print doubled  # Throws an error, since the variable is local to the function 'double'

 => NameError: name 'doubled' is not defined

 print double(4)  # Prints correctly since we are printing the return value when we invoke the function.
 => 8
 ```

*Variable scope*  seems complicated but it's really important to keep in mind. Easy rule of thumb: For data that you want to access in multiple functions, declare the variable outside of your fuctions, for data that should remain in one function, create your variable within that function.


## Conclusion
Functions are the building block of any developer. In most languages, functions contain a name, optional inputs, instructions inside a code block and an option return value. As you start to dive deeper into Python, be mindful about how the syntax of a function is slightly different than in other languages. 
