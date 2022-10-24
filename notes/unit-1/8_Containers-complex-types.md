Containers and complex types in Python[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#containers-and-complex-types-in-python "Permanent link")
=================================================================================================================================================================================================================================================================================================

In this lesson, you will explore the basic **structured** data types that can be used in Python.

### Learning outcomes

Successful completion of this lesson will help you to:

-   understand how to use lists and dictionaries in Python
-   see how simple data types can be combined to build more complex types using classes
-   understand potential problems caused by Python's lack of variable typing.

Python provides a variety of means to create complex data objects out of collections of other objects. These include:

-   **Container types** -- These are general purpose (and extremely useful) ways to collect multiple items within some containing structure. The four major kinds are lists, tuples, dictionaries and sets.

-   **Classes** -- By defining new classes, we can create complex data objects that incorporate other objects in almost any way we want.

#### Note

The words "class" and "type" (or data type) mean almost the same thing.

Typically "type" is more general, whereas "class" was traditionally used to describe only complex data types defined within an object-oriented programming language. But in Python3 there is no real distinction, and even primitive data types can also be referred to as classes. However, as we shall see below, within the actual syntax of Python, the words `class` and `type` do have different meanings. The keyword `class` used to define a new class/type of data object, whereas the built-in function `type( ... )` is used to find the class/type of its argument.

Lists[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#lists "Permanent link")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

A list is an ordered collection of objects. The objects in the list can be numbers, strings, other lists, or more complex types... Lists are specified using square brackets `[ ]`. A complex list definition may need to be split over several lines to improve readability.

```python
list_of_numbers = [1, 3, 7, 9, 12, 10, 2]

list_of_strings = ["this", "is", "a", "list"]

nested_list = [ [1,2,3], [4,5,6], [7,8,9] ]

character = [ "Bob", 27,
              ["items", ["gun", "cake", "onion"]]
            ]
```

The items in a list are kept in a fixed order, and you can access items according to their position, or **index**. This is done by writing the name of the list, followed by the numerical position of the item you want to access inside square brackets. Be careful though! The index numbers start from zero, so the third item in the list is at position 2 according to Python.

```python
list_of_numbers = [1, 3, 7, 9, 2, 10, 2]

list_of_numbers[2]

> 7
```
Negative numbers are used to access items counting backwards from the right-hand end of the list.

```python
alist_of_numbers[-2]
> 10
```

To access a part of a list you can specify a start and end position. To extract the part of my_list including everything which has a position at least m and less than n, write `my_list[m:n]`.

```python
list_of_numbers[2:5]
> [7, 9, 2]
```

Python provides a very versatile range of operations that can be performed on lists.

### Modifying a list[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#modifying-a-list "Permanent link")

-   `my_list.append(new_item)` adds `new_item` as the final element in `my_list`.
-   `my_list.extend(list_of_new_items)` adds everything from `list_of_new_items` to `my_list`, in order.
-   `my_list.insert(index, new_item)` adds `new_item` at position `index` in `my_list`.
-   `my_list.pop(index)` returns the item at position `index` in `my_list`, and also deletes it from the list.
-   `my_list[index] = new_item` assigns the list element at position `index` to be `new_item`. This is not only inserting a new element, but overwriting whatever was in this position previously.

### Basic information about a list[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#basic-information-about-a-list "Permanent link")

-   `len(my_list)` returns the number of items in `my_list`.
-   `max(my_list)` and `min(my_list)` return the maximum and minimum valued item from `my_list`.
-   `sum(my_list)` returns the sum of all the items in `my_list` -- of course this assumes that the list elements are numerical!

### Nested lists[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#nested-lists "Permanent link")

Remember that lists can contain any type of object, including other lists. In order to access elements of a list inside another list we make repeated use of the square bracket notation.

```python
list_of_lists = [[1,2,3], ['a', 'b', 'c'], ['fish', 'dog', 'cat']]

# first access list_of_lists[1], which is ['a', 'b', 'c'], then access element [2] of this
list_of_lists[1][2]

> 'c'
```

Tuples[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#tuples "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Tuples are exactly the same as lists except that tuples are *immutable*, which means they cannot be changed. Tuples are specified using parentheses instead of square brackets (but accessing elements is still done using square brackets).

```python
my_tuple = ('fish', 'dog', 'cat')

my_tuple[1]

> 'dog'
```

Dictionaries[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#dictionaries "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Dictionaries are an extremely useful data object, both because of their power and flexibility as a vehicle for storing structure, and because of the clear and intuitive form of the structure they provide. Also, for many kinds of data manipulation, especially when rapid access is required, dictionaries are much more efficient than lists, and hence give much faster execution performance. Dictionaries are specified using curly braces `{}`.

```python
grades =  { "Asterix"  : 57,
            "Galois"   : 99,
            "Cazzgr"   : 45,
            "Dilbert"  :  3,
          }
```

In this dictionary, "Asterix", "Galois", "Cazzgr" and "Dilbert" are the **keys** and 57, 99, 45, 3 are the **values**. Dictionaries are collections of **key:value** pairs. A key can be any **immutable** object -- this is one reason why tuples can be useful. A tuple can be a dictionary key, a list cannot. The values can be any Python object, including lists or other dictionaries.

The syntax for accessing a dictionary element is similar to that for accessing a list element, the difference is that instead of using the position of the element we want, we use its key:

```python
grades["Dilbert"]

> 3
```

If the specified key does not exist in the dictionary this will cause an error. Instead, you could use `my_dict.get(key)`, which returns the value associate with `key` if it exists, and otherwise returns `None`.

### Modifying a dictionary[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#modifying-a-dictionary "Permanent link")

-   `my_dict[key] = value` adds the pair `key:value` to `my_dict`. Any old value stored with the same key is overwritten.
-   `my_dict.pop(key)` returns the value associated with `key` and removes this pair from the dictionary.

### Combining dictionaries and lists[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#combining-dictionaries-and-lists "Permanent link")

If a dictionary contains a list then we can access the elements of that list by first using the right key to access our list, and then using the index to access a specific element in the list.

Classes and objects[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#classes-and-objects "Permanent link")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Later in the module you will learn about the *object oriented* features of Python. But, with regard to the learning objectives of the current lesson, you should be aware that the concepts of *class* and *object* are closely related to data types.

-   A **class** defines a complex data type that may incorporate multiple data components. (It may also define **methods** that specify operations on that data.)
-   In this way, classes can be used to define arbitrarily complex data types.
-   An **object** is a particular instance of a class.

The following is a simple example of how a class is defined and instantiated to create an object. We will look at this syntax in more detail in Unit 2.

```python
class Tile:
    def __init__(self, w, h, c):
        self.width = w
        self.height = h
        self.colour = c
        self.material = "ceramic"

my_tile = Tile(10, 10, "red")  # an object of class Tile
```

The `type` function[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#the-type-function "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Python provides a special built-in function `type` that enables us to find the type of a given value.

If we apply `type` to a variable, we will get the type of its current value. (In Python, variables themselves do not have types and can potentially hold values of different types at different times.) Thus for example:

```python
type(1)`

> int

type(3.5)

> float
```
If we apply `type` to a variable, we will get the type of its current value. Variables themselves do not have types and can potentially hold values of different types at different times.

```python
x = 57
type(x)

> int
```

Aside

Just to make things a bit more confusing, Python treats types themselves as also being a special class of entity. And the type of these entities is the class type.

### The `is` relation.[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#the-is-relation "Permanent link")

When considering the relation between `int` and `float` numbers in an earlier lesson, we noted that the equality relation `==` can hold between an `int` and a `float` provided that the `float` is equivalent to an integer value (i.e. its decimal part is `0`). The `is` relation is more specific and tells us whether two variables are pointing to the same memory address, i.e. whether these two variables reference *exactly* the same object.

```python
x = 5
y = 5.0
x == y

> True

x is y

> False
```
### Potential problems arising from lack of variable typing[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#potential-problems-arising-from-lack-of-variable-typing "Permanent link")

Python's tolerance in allowing a variable to be assigned any kind of value can potentially cause problems. Also, a function name in Python is essentially just a variable that has a function, so you can set a function to have a new value, even one of the standard built-in functions. This can cause confusion. The following code illustrates the kind of problem that could occur.

```python
cw1_mark = 23
cw2_mark = 39
sum = cw1_mark + cw2_mark

## More code in between would make the problem harder to spot.

cw3_mark = sum([5,3,7,9])
```
This code would cause an error because `sum`, which normally specifies a function, has instead been assigned an integer value!

From binary digits to complex data types[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#from-binary-digits-to-complex-data-types "Permanent link")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

It is common for people to say that computers process information in terms of binary digits (`0`s and `1`s). This is true in the sense that at a fine level of granularity, both information and programs are stored and transmitted in the form of binary digits. It is also true that, in view of the analysis of computing in terms of theoretical models such as the [Turing machine](https://en.wikipedia.org/wiki/Turing_machine), all algorithms can be reduced to manipulations of just a couple of basic symbols.

However, it would be wrong to say that computer systems and programs are just very complicated mechanisms for shuffling around `0`s and `1`s. In fact, though of course they understand binary representations, for most tasks modern computer programmers quite rarely think about `0`s and `1`s. They will normally think and program in terms of much higher level data times.

Early programming languages only provided a limited range of built-in data types for representing different types of number, characters and strings. To represent sets of data they provided arrays, which could store a sequence of items and enable them to be accessed by means of an index number. During the subsequent development of programming languages, more and more complex data structures and apparatus for creating and operating upon these structures have been added.

Question

Python provides very rich and varied facilities for handling data. What is the benefit of this? After you have considered this question, return to the discussion thread in Minerva and share your thoughts. Access the thread for this topic by selecting the **'Discussion'** tab in the side navigation in Minerva and selecting the **'Python provides very rich and varied facilities for handling data. What is the benefit of this?'**' thread for this lesson.

The complexity of all the syntax involved in handling such a wide variety of data types could make a language difficult to learn. There may also be concerns that all this extra machinery in the language makes it inefficient to execute. But it seems that the benefits do outweigh the costs. Today we are seeing rapid progress in development of complex software systems providing novel functionalities. This certainly makes heavy use of recent developments in the functionality provided by programming languages, especially with regard to the organisation and manipulation of data. So there is very strong evidence that the development of rich data-structuring capabilities has greatly increased programmers' capacity to build reliable, powerful and highly sophisticated software systems.

Lesson complete[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_08_containers-and-complex-types/#lesson-complete "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You have looked at how to use structured data types such as lists, dictionaries and classes and objects in Python. You also now understand the potential problems caused by Python's lack of variable typing, and how binary digits become complex data types.

In the next activity you will use list and dictionary data in Python.