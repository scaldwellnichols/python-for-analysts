Number types in Python[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#number-types-in-python "Permanent link")
====================================================================================================================================================================================================================================================

Python provides three different basic types for representing numbers.

-   `int` : an integer valued number of unspecified length e.g. -17, -1, 0, 2, 5, 10, 42, 15647989.

-   `float`: a floating point number, which is an approximate representation of a real number.

-   `complex`: Python can handle **complex** numbers, which consist of a **real** and an **imaginary** part.

In this course we will not be concerned with `complex` numbers, which are mainly used in physics, engineering and certain branches of mathematics. However, you will certainly be using `int` and `float` type numbers, so it is important to understand the difference between them, and the various operators that can be applied to them.

`int` values (**integers**) are basically whole numbers, including negative numbers and `0`. Many kinds of data come in the form of integers, for example the numbers of packets of each type of biscuit on a supermarket shelf, or USB ports on a service robot's back end. Integer values are also commonly used to control computations, which very often involve some kind of counting or numerical conditions.

For most purposes you can think of a `float` as a **decimal** number. This is how it will usually appear in a program and how it will usually be represented in a data file. But the actual way floating point numbers are stored in a running Python program is much more complicated, and not covered in this module. In fact, in most kinds of programming, it is rare to have direct references to specific floating point numbers in the code. However, many kinds of data consist of decimal numbers, so you will often be working with programs that read in such information and manipulate it in the form of `float` type values.

### Representation of `int` and `float` data[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#representation-of-int-and-float-data "Permanent link")

As you may expect, the representation of a particular `int` in Python is just a sequence of decimal digits, such as `31726`. And the representation of a `float` is the same but with a decimal point somewhere in the number, such as `317.26`.

It is important to note that while a sequence of digits, say `123` represents an `int`, the sequence `123.0` represents a `float`. Python's equality operator `==` is defined so that `123 == 123.0` does return `True`.

### Mathematical operators[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#mathematical-operators "Permanent link")

The table below summarises the most common mathematical operators used in Python. To denote such fundamental operations, Python (like most other programming langauges) uses symbols that are similar to those employed in paper-and-pencil mathematics:

| Operator | Operation |
| --- | --- |
| `x + y` | Addition of `x` and `y` |
| `x - y` | Subtraction of `y` from `x` |
| `x * y` | Multiplication of `x` and `y` |
| `x / y` | True division of `x` by `y`. The result is always a floating point number |
| `x // y` | Floor division of `x` by `y` (explained below) |
| `x % y` | Modulo. The result of this operation is the remainder when x is divided by y |
| `-x` | The negative of `x` |
| `x**y` | Has the value of `x` raised to the power of `y` --- i.e. x^y^ |

Mathematical operations are very often used to compute new values that are then assigned to a variable, which will store the value that has been computed. For example:

```python
edge = 57
cube_volume = edge**3
```

As you may expect, brackets are often required to determine the order in which operations should be carried out:

```python
(2 * 3) + 4
```

does not give the same value as

```python
2 * (3 + 4)
```

You should be very familiar with the operators of basic mathematics, but you will also see examples using some less familiar operators.

#### Modulo[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#modulo "Permanent link")

In the mathematics of integers, the value of *n* **modulo** *m* is the smallest non-negative integer *x* such that *n* - *x* is an integer multiple of *m*. In other words *m* * *k* = *n* - *x* for some integer *k*. Or, more loosely but intuitively, we can say that *n* **modulo** *m* is the *remainder* obtained when *n* is divided by *m*.

The modulo operator in mathematics is well-known but mainly studied in relation to the quite abstract theory of numbers. However, it has many computational applications, and in fact is useful in many data conversion operations.

#### Example of using `%`[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#example-of-using "Permanent link")

Suppose you have a number *t* representing the length of a time period in seconds, but want to display it in the form of *m* minutes and *s* seconds. Then the number of seconds *s*, that are not incorporated within the minutes, will be *t* **modulo** 60, since there are 60 seconds in each minute.

```python
t = 357
s = t % 60
m = (t - s) / 60

print( m, "minutes, and", s, "seconds")
> 5.0 minutes and 57 seconds
```



### `int` vs `float` types[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#int-vs-float-types "Permanent link")

If you look carefully at the output from the code just above, you will notice a difference between the way that the minutes and seconds are displayed. The number of seconds is simply expressed as `57`, an integer. But in the case of the minutes, we see `5.0`; so the number 5 is expressed as if it were a decimal, even though it is a whole number. This is because the `/` operation always returns a `float` type number. This may seem odd in the case where we divide an `int` by another `int` which divides exactly into it. However, it does mean that any expression of the form `x / y` will return a `float`, and this consistency is generally thought to be preferable to having an expression that could sometimes return an `int` and at other times a `float`, which could potentially give rise to hard-to-spot bugs.

Python provides any easy way to convert between `int` and `float` numbers. If you use the type names in the form of an operator, Python transforms its argument into the specified type:

-   `int(x)` will give the `int` corresponding to `x`. If the value of `x` is a positive `float` the `int(x)` is the largest `int` that is less than or equal to that float. Thus `int(5.7)` has the value `5`.

-   `float(x)` will give the `float` corresponding to `x`, which can be an `int`. Thus `float(5)`, will give the value `5.0`.

These kinds of operation are often called **casting**. One may say that an `int` is **cast** into a `float` (or **vice versa** ). We shall later see how `str` can be used as a casting operator to create strings from numbers.

Example of casting into an `int`

In the previous example you saw how the number of minutes was displayed as a `float` (`5.0`) instead of an `int` (because the result of the '/' operation is always a `float`). We can easily rectify this by using the `int` **casting** operator.

```python
t = 357
s = t % 60
m = int( (t - s) / 60 )

print( m, "minutes, and", s, "seconds")`
> 5 minutes and 57 seconds
```
Question

What is the value of `int( -1.7 )` ?

Answer

Try it! Open a Jupyter notebook and run the command to see what is returned.

Aside

Some languages will automatically cast data items from one type to another depending on context. In Python you have to explicitly use a function to get a value of a different type. Having said that, many functions are defined so that they can operate on different types of data (especially `int`s and `float`s), which has a similar effect to automatic casting.

Aside

We are using **Python3**, but in **Python2** the behaviour of `/` when applied to `int` numbers is very different.

In Python2, in the case where `x` and `y` are `int`s, the expression `x / y` always returns an `int`, even when `y` does not divide exactly into `x`. In such cases the result will always be rounded downwards to the highest integer value that is less than or equal to the actual floating point value of `x` divided by `y`.

This is why, in Python2, `3/4` will return the value `0` and, perhaps even more surprisingly, `-3/4` will return `-1` (since the result is always rounded downwards). To get a float result for a division in Python2, at least one of the two numbers operated on must be a `float`. Thus,`3.0/4` and `3/4.0` both return `0.75`.

The Python2 behaviour of `/` did cause a lot of confusion for beginner Python programmers and gave rise to many bugs. This is why, when **Python3** was designed, it was decided that `x / y` should always return a float.

Small but fundamental details like this can be significant in the design of a programming language and can give rise to a great deal of analysis, discussion and contention. The `/` in Python is a very good example of this. If you would like to find out more you can read the **Python Enhancement Proposal** [PEP 238](https://legacy.python.org/dev/peps/pep-0238/), which gives very detailed motivation and specification of the change made to the meaning of `/` when going from Python2 to Python3.

### Floor division[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#floor-division "Permanent link")

The so-called "floor division" operator `x // y` gives the largest whole number that is equal to or less than the real number `x / y`. This is why, for example, `7 // 3` gives `2`. Even so, the value returned is not always of type `int`. In fact, it will be an `int` only if both numbers it operates on are `int` s. If either or both is a `float` the result will be a float. Thus `7 // 3.0` and `6.0 // 3` both give `2.0`.

Using the `//` operator, the conversion from a duration in seconds to one in minutes and seconds can be given in a more succinct and clear form. Because `x // y` gives an `int` if both `x` and `y` are `int`s, there is no need to transform a `float` to an `int`:

```python
t = 357
s = t % 60
m = t // 60

print( m, "minutes, and", s, "seconds")`
> 5 minutes and 57 seconds
```
Aside

Given that `int(-1.5)` is `-1`, one might expect that `-3 // 2` would also have that value. However, the value of `-3 // 2` is actually `-2`. Why is this? If you would like to find out more you can read the blog article [Why Python's integer division floors](http://python-history.blogspot.com/2010/08/why-pythons-integer-division-floors.html) by Python's creator [Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum).

### Numerical comparisons[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#numerical-comparisons "Permanent link")

Python contains a range of comparison operators that can be applied to numbers, and have symbolic representations and meaning similar to those used in mathematics:

| Comparison Relation | Meaning |
| --- | --- |
| `x == y` | `x` is equal to `y` |
| `x != y` | `x` is not equal to `y` |
| `x > y` | `x` is greater than `y` |
| `x < y` | `x` is less than `y` |
| `x >= y` | `x` is greater than or equal to `y` |
| `x <= y` | `x` is less than or equal to `y` |

All comparison relations return a **Boolean** --- i.e. one of the values `True` or `False`, which are of type `bool`. The characteristics and uses of `bool`s will be explained below.

Note

As well as comparing `int` to `int` or `float` to `float`, we can compare `int` values to `float` values. The effect is equivalent to first casting the integer to a float and then applying the comparison.

Note

It is essential to be aware that the equality relation is symbolised by `==` rather than `=`, since `=` is the symbol used for assigning a value to a variable.

Aside

Writing `x = y` where one means `x == y` is a very common error in Python coding. Luckily, such errors can normally be detected immediately by the Python [interpreter](https://en.wikipedia.org/wiki/Interpreter_(computing)) because the `x = y` cannot occur in a place where a `bool` value is required (for example, in the condition of an `if` statement). So such a mistake will generate an error when Python reads in the code, even before it is actually executed.

The `math` module[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#the-math-module "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Python provides a large range of *built-in* functions, which could potentially enable us to code almost any application. However, for many purposes it is convenient to be able to `import` additional functions or classes that have already been implemented by other programmers. This is the case for mathematical functions, which are difficult to implement efficiently. To access these mathematical functions we simply use the following line of code:

`import math`

Having imported the `math` module we can use constants and functions defined within it. For example, the (approximate) value of `pi` is available in the math module and is accessed as follows:

`math.pi`

And to calculate the (approximate) square root of 2:

`math.sqrt(2)`

The math module contains many more important mathematical functions, such as for calculating `sin` and `cos` and `log`. Note that our code must import the math module first before using any of the properties or functions defined in the module.

Aside

In Python the term **module** technically refers to any code that is stored in a single file. The term is particularly used when talking about the standard modules that are provided with Python or distributed within some **package**. (A **package** is just a collection of modules that are grouped and distributed together).

### `int` and `float` methods[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_ii_number-types/#int-and-float-methods "Permanent link")

As mentioned above, in Python there is no specific difference between the notions of **data type** and **class**. Even the simplest types of data can be regarded as classes and provide methods that can be applied to data items of that type. For many kinds of programming the basic operators and `math` module are sufficient for working with numbers. However, there are some cases where we operate on numbers by means of methods.

For example, `int`s have a method `bit_length()`, which returns the number of bits used to store a given integer. This can be applied to a variable whose value is an `int`, using the method syntax, as follows:

```python
x = 123456
x.bit_length()
```

In the case of `float`, we might want to know whether a float value is equal to an integer value, which we can find using the Boolean valued `is_integer` method. For example, `5.0.is_integer()` will return `True`.

Note

We cannot apply methods directly to the decimal representation of an `int`. Code such as `123456.bit_length()` will give an error. This may be because `.` could also be interpreted as a decimal point, so the interpreter is expecting it to be followed by a digit. However, this issue is easily solved by use of brackets: we can write `(123456).bit_length()`, which Python is happy to evaluate.

```python
5.0.is_integer()
(123456).bit_length()
```

In the next section of this lesson you will be introduced to strings.