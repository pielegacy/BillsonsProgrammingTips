# What is a Function? Feat. Python

### Generally Speaking...
A function is a basically a series of instructions which may or may not return a value.
I say may or may not because a function in computer science terms **always** returns something
whilst a procedure **doesn't** return something. 

I'll get into this later but basically in Python a function, can or doesn't have to return a
value.

### Structure
Functions consist of 3 to 4 major elements usually depending on if they return a value. 

The first part of a function is the *definition*, you define a function using the `def` keyword followed 
by an identifier (a name) which is how you will uniquely refer to the function in your code. For example,
if we needed to define a function called Add it would start with `def Add`.

After this, we need to specify whether the function takes any *parameters*. If a function was a recipe, the
parameters would be the ingredients. A function can have as many parameters as needed, or no parameters at all;
these parameters being defined by a tuple with comma seperated values eg: `(value1, value2, value3)`.

Here are some examples of function definitions with varying amounts of parameters:

```python
# no parameters
def functionOne(): 
...
# 1 parameter
def functionTwo(one):
...
# 2 parameters
def functionThree(one, two):
...
```

The third part is the actual operations of the function. This is where the code goes and we make use of any parameters
that have been supplied. We refer to our parameters by referencing them with the identifiers that we gave them in the 
function definition. For example, if we wanted to create a function that added and printed 2 variables referred to as a and b it would
look like this

```python
def add(a, b): # def keyword followed by an initialiser and then a set of parameters
    print a + b # notice we refer to the two parameters using the same names in the brackets
```

The fourth part is optional, its `returning` a value. Emphasis on returning because python uses the return keyword to specify what a function
gives back. In the add function above, it didn't return a value so technically it was a procedure. If you make your functions return something,
they can be passed into variables and even other functions. For example, if we wanted the add function above to return a variable rather than
print it we need to rewrite to work as so:

```python
def add(a, b): # def keyword followed by an initialiser and then a set of parameters
    return a + b # notice we use the return keyword rather than the print keyword: this is now a function
```

Now we can use this function in a variety of ways:

```python
c = add(5,6) # c = 11

d = add(c, 2) # d = 13

e = add(add(5,5), 10) # e = 20
```

By using functions, our code becomes more *modular* and cleaner. Writing good functions is a valuable step as good code is code with less repitition
and so what a better way to avoid repitition by only writing a set of instructions once. 

### So we make a function by...

1. Defining it's identifier
    
    ```python
    def createName...
    ```

2. Adding any parameters needed 

    ```python
    def createName(firstName, surName):
    ```

3. Performing any operations within the body

    ```python
    def createName(firstName, surName):
        fullName = "%s %s" % (firstName, surName)
    ```   

4. Then possibly returning a value

    ```python
    def createName(firstName, surName):
        fullName = "%s %s" % (firstName, surName)
        return fullName
    ```   

### How about using them?

Good question, in programming when we make use of what is in function we are said to be "calling" a function.

In Python calling a function is pretty easy and you've most likely been doing it already. Take the following function:

```python
def greet():
    print "Hello there"
```

If we had this function in our .py file, we could easily call it by using the following code:

```python
greet()
```

That's all there is to a function call, we just use the name of the function (its identifier) and then place brackets afterwards.
These brackets aren't always empty however, they are used to take the parameters of a function. The previous example was very limited,
what if our greet function took a name as a parameter and how would we call it? 

```python
def greet(name):
    print "Hello there, %s" % name

greet("Alex")

# Output:
# Hello there, Alex
```

Notice that the brackets of the function call now have a string in them? This is because we have called a function which requires
parameters and so they must be passed through. A function can have as many parameters as possible and so the amount of parameters we pass
through must align. For example, say we wanted to provide a name and age with our greeting?

```python
def greet(name, age):
    print "Hello there, %s. You are %d years old" % (name, age)

greet("Alex", 19)

# Output:
# Hello there, Alex. You are 19 years old
```

All you need to do is add another value to the braces and seperate them with a comma. This can be applied for as many parameters as needed.

However as mentioned, functions often return values. Say we had the add function again and we wanted to find what 1 + 2 was?

```python
def add(num1, num2):
    return num1 + num2

add(1,2)
```

This is okay, the code works fine there are no errors but the numbers we add don't get stored anywhere. How do we retrieve the contents of add? Well
the best way is obviously to assign it a variable. This is as easy as assigning a value to a variable normally, just put an identifier on the left side
of the equals and your function call on the right side:

```python
def add(num1, num2):
    return num1 + num2

answer = add(1,2) # answer = 3
```

## Quiz

1. Which of the following are functions and which are procedures?

    A. 
    ```python
    def multiply(num1, num2):
        return num1 * num2
    ```
    B.
    ```python
    def printShit():
        print "Hello all"
    ```
    C.
    ```python
    def addShit(num1, num2):
        result = num1 + num2
        print num1 + num2
    ```
    D.
    ```python
    def grabSecondNumber(numbers):
        result = -1
        try:
            result = numbers[1]
        except:
            print "No number found"
        return result
    ```