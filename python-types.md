# Data Types and Typecasting Feat. Python

### How Types Usually Work In Programming

Originally with Programming, Data Types were **explicitly** declared with the variables
creation. What I mean by this is that in an older language like C you would
declare variables like so:

```c
int number = 10; // this is an integer
float decimal = 10.3; // this is a float
char[] name = "Alex"; // this is an array of characters (a string)
```

This is what is known as *static typed* programming. The type we assign to a variable is
set in stone and needs to explicitly told to the program. We cannot set the variable to anything
but the type it comes with. For example, the following would not work:

```c
int age = 19;
age = "nineteen"; // Setting an int to a string? The fuck are you doing
```

Whilst many languages still work like this, Python does not...

### Enter Dynamic Typed languages

Python is different because it can detect a type of a variable without you telling it as well as change the
data type of a variable on-the-fly.

Thus the name "dynamically typed language": it's not static, it changes. This is both a blessing and a curse. 

The benefits are seen in the cleanliness of python. The integer we declared in C is even simpler in Python:

```python
age = 19 # python knows its an integer without you telling it
```

Variable type conversion is also easy to the point of it being near impossible to notice

```python
age = 19
age = "nineteen" # this works fine
```

Whilst these examples are simple, take how Python creates a dynamic list as opposed to C:

```python
names = ["Alex", "Caroline", "Catherine"] # that's it, this list can be updated and such
```

```c
// This is just the code to allow it to have a list, it doesn't even include  the  list
typedef struct {
  int *array;
  size_t used;
  size_t size;
} Array;

void initArray(Array *a, size_t initialSize) {
  a->array = (int *)malloc(initialSize * sizeof(int));
  a->used = 0;
  a->size = initialSize;
}

void insertArray(Array *a, int element) {
  if (a->used == a->size) {
    a->size *= 2;
    a->array = (int *)realloc(a->array, a->size * sizeof(int));
  }
  a->array[a->used++] = element;
}

void freeArray(Array *a) {
  free(a->array);
  a->array = NULL;
  a->used = a->size = 0;
}
```

Basically, Python makes things simpler and part of this is because of this implied
variable type declaration.

There are some drawbacks however. Because Python variables have an implied type it's actually
sometimes difficult to use them in situations where we need to ensure the type.

Take the following function:

```python
def add(a, b):
    return a + b
```

Quite simple, it adds two numbers. Think about though, is there anything stopping us from not using
two numbers? What I mean is, can Python stop us from doing this:

```python
add("10", 10)
```

Or even this...

```python
add("smelly", 3.14)
```

It can't, and because of this we have to put in extra checks and validation to ensure our code is 
preventing such errors from happening.

### Typecasting 

