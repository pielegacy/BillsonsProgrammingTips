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

```Python
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

```Python
def add(a, b): # def keyword followed by an initialiser and then a set of parameters
    print a + b # notice we refer to the two parameters using the same names in the brackets
```

The fourth part is optional, its `returning` a value. Emphasis on returning because python uses the return keyword to specify what a function
gives back. In the add function above, it didn't return a value so technically it was a procedure. If you make your functions return something,
they can be passed into variables and even other functions. For example, if we wanted the add function above to return a variable rather than
print it we need to rewrite to work as so:

```Python
def add(a, b): # def keyword followed by an initialiser and then a set of parameters
    return a + b # notice we use the return keyword rather than the print keyword: this is now a function
```

Now we can use this function in a variety of ways:

```Python
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