List comprehension[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iiii_list-comprehension/#list-comprehension "Permanent link")
====================================================================================================================================================================================================================================================

List comprehension is a way of creating lists that also allows loops to be executed with a single line of code. Everything that can be done with list comprehension can also be achieved using loops and conditionals in the way that we've already seen, but list comprehension is a useful tool that Python provides which can make your code more succinct and readable.

Suppose we want to create a list which contains the first five multiples of 3. First we can do this by writing a `for` loop and adding an element to the list in each iteration.

```python
multiples_of_3 = []

for i in range(5):
    multiples_of_3.append(3*i)
```

The same thing can be achieved by list comprehension using the syntax

`[<expression> for <item> in <iterable>]`

where `iterable` is any iterable Python object, such as a list, dictionary, string or a range object.

`[3*i for i in range(5)]`

Compare the two versions carefully to see that they contain the same logic but expressed differently. Either option is correct. For simple procedures like this many Python programmers prefer to use list comprehension because it is more compact.

The `<expression>` part can also call a function (this usage is similar to the `map()` function -- see the [Python documentation](https://docs.python.org/3/library/functions.html#map) for further details). The following shows two ways to make a list of the first 5 cube numbers using the `pow()` function.

Using a for loop:

```python
cubes = []

for i in range(5):
    cubes.append(pow(i,3))
```

Using list comprehension:

`[pow(i,3) for i in range(5)]`

### Conditionals in list comprehension[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iiii_list-comprehension/#conditionals-in-list-comprehension "Permanent link")

The syntax

`[<expression> for <item> in <iterable> if <condition>]`

adds even more power to list comprehension. Suppose we have a dictionary of student names and grades.

```python
grades =  {
    "Asterix"  : 57,
    "Galois"   : 99,
    "Cazzgr"   : 45,
    "Dilbert"  :  3,
}
```

Then we can create a list of students with high scores using a for loop.

```python
top_students = []

for key, value in grades.items():
    if value > 50: # high score
        top_students.append(key) # add student name to list
```

Or we can achieve the same thing using list comprehension with a conditional statement.

`[key for (key, value) in grades.items() if value > 50]`

The conditional expression could contain a function call provided that it evaluates to a Boolean (or a value which can be interpreted as a Boolean by Python). The next examples assume a variable `list_of_numbers`, a list containing both integers and floats, and return a list containing only the integer values. Again, compare the examples and notice the similarities.

```python
list_of_ints = []

for i in list_of_numbers:
    if isinstance(i, int):
        list_of_ints.append(i)
```

```python
[i for i in list_of_numbers if isinstance(i, int)]
```

The expression saying what should be included in the list can also contain conditional logic. The following two examples both replace non-integers in `list_of_numbers` with 0, once using a for loop and then using list comprehension.

```python
list_of_ints = []

for i in list_of_numbers:
    if isinstance(i, int):
        list_of_ints.append(i)
    else:
        list_of_ints.append(0)
```

```python
[i if isinstance(i, int) else 0 for i in list_of_numbers]
```

It's possible to achieve some quite impressive results in a single line of code using list comprehension. However, at some point the benefits of conciseness are outweighed as it becomes harder for a person reading the code to understand what is intended. It's usually best to use list comprehension only for simple tasks. Then replacing the several lines it would take to explicitly write out a loop with the one line list comprehension version improves readability. Here's an example where it's arguably not helpful to use the list comprehension version. Both pieces of code create a list of the prime numbers under 10. Both are correct, but (in my opinion) the first is clearer.

```python
primes = []

for i in range(10):
    for j in range(2,i):
        if i%j == 0:
            break # there is a divisor so this isn't a prime
    else:
        primes.append(i)
```

```python
[i for i in range(10) if 0 not in [(i%j) for  j in range(2,i)]]
```

Set and dictionary comprehension[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iiii_list-comprehension/#set-and-dictionary-comprehension "Permanent link")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The same ideas can be applied to create sets and dictionaries. To create a set the syntax is

`{<expression> for <item> in <iterable> (if <condition>)}`

and to create a dictionary write

`{<key expression>: <value expression> for <item> in <iterable> (if <condition>)}`

The key expression and value expression can contain conditionals or make calls to functions, and nesting of dictionary or set comprehensions is possible. When to use comprehensions and when to use the standard loop structures depends mainly on readability and personal preference, but the rule of thumb is that comprehensions should be *simple* to understand.

Lesson complete[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iiii_list-comprehension/#lesson-complete "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You have seen how loops and conditionals give more power and flexibility in programming. You have been introduced to Python's syntax for loops and conditionals and some useful related features.

In the next activity you will build on this knowledge.