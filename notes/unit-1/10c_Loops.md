Loops[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#loops "Permanent link")
============================================================================================================================================================================================================

Often it is necessary to repeat the same action many times over. To avoid writing the same piece of code multiple times, and to allow for a variable number of repeats, you can use loops. Python provides two types of loop: **while** and **for**.

For loops[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#for-loops "Permanent link")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Python `for` loops are used to apply the same action to every item in an **iterable** object. What is an iterable object? It's most easily explained as something that can be used in a loop! More helpfully, an iterable object is a collection of objects that has the ability to return its elements one at a time. Lists, dictionaries, tuples, sets, and strings are all iterable. It's also possible to define new classes that are iterable. To start with we'll work with lists but the ideas are very similar for other iterable types.

### For loops over lists[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#for-loops-over-lists "Permanent link")

Applying a `for` loop to a list is a way to perform the same action (run the same block of code) for every element in a list. To create the loop, start with the keyword `for` followed by a new variable name. The variable name will hold the value of each item of the list in turn. This is followed by the keyword `in` and the list that is to be looped over, and the line ends in a colon. The next line must be indented. As with conditional statements, the indentation is essential because this is how Python knows which lines of code belong in the loop. For example, the following code loops over a list of names and prints a greeting for each one. Within the loop the variable `name` allows access to the relevant list element. The value of `name` changes with every iteration of the loop.

```python
list_of_names = ['Fred', 'George', 'Sam']

for name in list_of_names:
    print('Hello {}, nice to meet you!'.format(name))
```

There's no limit to how many lines of code can be inside the for loop, and no limit on how complicated this code is. In particular, it can include more loops or conditionals.

```python
list_of_colours = ['Red', 'Green', 'Blue', 'Yellow']

for colour in list_of_colours:
    if colour == 'Green':
        print('Green is my favourite colour!')
    else:
        print('{} is a nice colour.'.format(colour))
```

Sometimes it is useful to know the index of the current list item as well as its value. This is achieved with the `enumerate()` function, which takes a list and creates an iterable object that returns a sequence of tuples. The first item of the tuple is a the list index, the second item is the value at that index. Because two values are returned at each iteration we need two loop variables and these are separated with a comma. Otherwise the syntax is unchanged. Code within the loop uses the loop variables to access the current list index and list value.

```python
for i, list_item in enumerate(my_list):
    <code to be executed within the loop>
<code that will be executed after the loop has finished>
```

### For loops with a specified number of iterations[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#for-loops-with-a-specified-number-of-iterations "Permanent link")

Instead of applying the same code to each member of a list we might simply want to repeat the block of code some number of times. This can be achieved in a variety of ways, but the neatest way is to use a `for` loop and Python's `range` function.

The range function creates an iterable object that returns a sequence of integers. It takes up to three parameters: start, stop, and step. However, in the simplest case, only one parameter is required. `range(n)` creates an iterable object that returns, in order, the numbers from 0 to n-1. Notice that n is not included, but the total number of values returned is n. So, to create a loop that will execute a piece of code n times, you will need to write:

```python
for i in range(n):
    <code to execute within loop>
```

### Note

When only one parameter is given to the `range()` function it is assumed to be the stop parameter. The other parameters are given default values of start = 0 and step = 1. If two parameters are given then the first is the start value and the second is the stop value. In this case, `range(m, n)` creates an iterable object that returns, in order, the numbers from m to n-1. In total n-m values are returned.

The step parameter modifies the increments between the returned numbers. So `range(m, n, s)` creates an iterable object that returns, in order, the numbers m, m+s, m+2s, ... with the sequence continuing until the next item would be at least n. For example, `range(4, 11, 2)` will return the numbers 4, 6, 8, 10.

### For loops over other objects[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#for-loops-over-other-objects "Permanent link")

The syntax of a `for` loop is the same regardless of the object type being iterated over. You've already seen three iterable types: lists, enumerate objects, range objects. For dictionaries we make use of the functions `values()` and `items()`. By default if we write a `for` loop to iterate over a dictionary the iterator returns the dictionary's keys. To access the values we could simply use the key to lookup the value in the dictionary. However, it is often more convenient to have the value returned by the iterator. `dictionary.values()` creates an iterable object that returns the values from the dictionary. `dictionary.items()` creates an iterable object that returns a sequence of (key, value) tuples. Because two things are being returned we need two loop variables -- just like with `enumerate()`.

```python
people_and_places = {
    'John': {'home': 'Leeds', 'born': 'Paris', 'parents': 'Paris'},
    'Fred': {'home': 'Barcelona', 'born': 'Madrid', 'parents': 'Oviedo'},
    'George': {'home': 'London', 'born': 'Bristol', 'parents': 'Exeter'},
}

info_string = '{} lives in {}. He was born in {} and his parents live in {}.'

for name, homes in people_and_places.items():
    # name and homes refer to the key and value of this dictionary item
    print(info_string.format(name, homes['home'], homes['born'], homes['parents']))
```

While loops[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#while-loops "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The second type of loop available in Python is the `while` loop. Instead of applying a piece of code to every item in a list, or repeating it a fixed number of times, we will keep repeating the same block of code for as long as some Boolean condition evaluates to True. The loop is created with the `while` keyword followed by any expression that returns a Boolean, followed by a colon. Then the next line of code is indented. This line (and subsequent indented lines) forms the block of code that will be repeated within the loop. Python will know that the code belonging to the loop has ended when the indentation is reduced.

```python
while <condition>:
    <code to be executed as long as <condition> is True>
```

Leaving the party early[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#leaving-the-party-early "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

We've said that a `while` loop will continue until the condition evaluates to False, and a `for` loop will continue as long as the iterable still returns a next object, but there is a way to exit a loop earlier. To do this, use the `break` keyword. When Python is instructed to `break` the loop it will immediately move to the first line of code following the loop block. Any further iterations of the loop are skipped. Usually, `break` is used in a conditional statement, as in the following example. Without the break statement the loop would print every number from 5 to 11. With the condition and break statement, the loop exits early -- immediately after it has printed a number that divides by 4.

```python
a = 5
while a < 12:
    print(a)
    if a%4 == 0:
        break
    a += 1
```

Skip this iteration[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#skip-this-iteration "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

`continue` is similar but instead of breaking out of the loop completely it just causes this iteration to be skipped. In a `for` loop we move onto the next item in the iterable, in a `while` loop we go back and check the condition again. In the next example we check whether the current value of a is divisible by 4 -- if it is then we move straight on to the next iteration, skipping out the instruction to print(a). Therefore, only values between 5 and 11 that are not divisible by 4 are printed.

```python
a = 5
while a<12:
    if a%4 == 0:
        a += 1
        continue
    print(a)
    a += 1
```

Using `else` with loops[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#using-else-with-loops "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You have now seen two distinct reasons for moving on from each type of loop. In the case of a for loop, you can either exit the loop because the iterable has been exhausted -- for example, there are no more items in the list -- or because we used a `break` statement to exit early. In the case of a while loop, you either exit because the loop condition evaluates to False or because you used a `break` statement to exit early. An `else` block following a loop contains code that will be executed only if the loop has exited "naturally", that is, without using a break statement. This makes sense if you remember that the break statement is usually paired with a conditional. Then the `else` block specifies what to do if that condition was never evaluated to true.

Nested loops[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_iii_loops/#nested-loops "Permanent link")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You've already seen that the code block inside a loop can contain conditionals, it could also contain more loops. Python relies on indentation to organise code blocks and to know which lines of code belong to which of the nested loops.

The following example imagines a group of people who all want to greet each other.

```python
list_of_people = ['John', 'Fred', 'George', 'Sam']

for i, main_person in enumerate(list_of_people):
    for j, other_person in enumerate(list_of_people):
        if i == j:
            # no need to greet yourself!
            continue
        else:
            print('{} says hello to {}.'.format(main_person, other_person))
```

Nested loops can also be useful for unpacking structured data such as nested lists or dictionaries.

```python
favourite_things = {
    'John': ['raindrops on roses', 'whiskers on kittens'],
    'Fred': ['bright copper kettles', 'warm woollen mittens'],
    'George': ['brown paper packages tied up with strings'],
    'Sam': []
}

for name, favourites in favourite_things.items():
    if favourites == []:
        print('{} has no favourite things.'.format(name))
    else:
        for thing in favourites:
            print('{} likes {}.'.format(name, thing))
```