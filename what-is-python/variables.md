# Variables

Now in the last section, I said "String \(a string of characters\)".

What does that mean?

In programming we need to have data types. Every bit of data has a type in common with it. You already know some.

If I said:

```python
1, 2, 3, 4, 5, 6, 7, 8, 9
```

"Are these sentences?"

No! They're numbers.

See, you already know data types 😜

In Python, it's the same. We have some essential data types that hold things:

* String \(a string of characters\)
* Integer - a whole number \(-50, 50, 60, 91\)
* Float - a floating point number \(21.3, -5.1921\)
* List - a list of items \(\[1, 2, 3\], \["hi", 6, 7.91\]\)

And more.

Now, let's dis-spell a myth.

Variables are like buckets in the sense that you can store things in them. Imagine a bucket and you want to put a sentence into it:

![](../.gitbook/assets/image%20%284%29.png)

We make a bucket called hello and in the bucket we put in the string \`Hello, World!"

```python
hello = "Hello, World!"
```

We use the equals sign as an _assignment operator_. It assigns the value on the right hand side to the bucket on the left.

Now let's say we wanted to add this variable to another variable. A common misconception is that we take the bucket itself and use that.

But in Python, we don't. We _pass by reference_. As in, we merely pass a location of the variable — we do not pass the variable itself. The alternative is _pass by value_.

This is very important to understand, as it can cause a significant amount of headaches later on.

![Gif from here](../.gitbook/assets/yes.gif)

Remember lists from earlier?

```python
hellos = ["Hello", "yo", "sup?", "alright?"]
```

Lists have different methods which allow us to manipulate the list. A popular one is appending an item to a list, like this:

```python
hellos = ["Hello", "yo", "sup?", "alright?"]
hellos.append("TryHackMe")
print(hellos)
# ["Hello", "yo", "sup?", "alright?", "TryHackMe"]
```

Let's see this bug in action.

```python
list1 = [1, 2]
list2 = [3, 4]
list1.append(list2)
# List1 is now [1, 2, [3, 4]]
# We appended the list, not the contents of the list
```

When we append a list to another list, we do not merge the elements together. Instead we append the entire list \(including the list itself\) to the other list.

```python
# Continueing from last code block
list2.append(6)
print(list1)
# [1, 2, [3, 4, 6]]
```

Now, let's look at the bug in more detail:

```python
list1 = [1, 2]
list2 = [3, 4]
list1.append(list2)
list2.append(6)
print(list1)
# [1, 2, [3, 4, 6]]
```

When we appended `list2` to `list1`, we did not actually append the list. We appended the reference to the list.

When we changed `list2`, because `list1` had the reference appended it "updates" itself to match the newly updated `list2`.

In Python, this type of bug can happen all the time. We never pass the values of things, always the references. So be sure to keep an eye open for this type of thing.

In some languages like Rust you get the option of value or reference. But in Python, you only get the option of reference. This is because if we started passing values, Python would have to spend more time on their garbage collection system.

Garbage collection is where we store variables in the system and remove them when they are no longer needed. Higher level languages do this automatically. Lower level languages you might have to do it yourself.

There are a whole bunch of other data types in Python, but I'll explain most of them throuhout this room.

Here's a quick table for data structures in Python:

| String | A string of characters | `"Hello"` | `str(x)` |
| :--- | :--- | :--- | :--- |
| Boolean | True or False value | `True`, `False` | `bool(x)` |
| Integer | A whole number | `50` | `int(x)` |
| Float | A floating point number | `6.11` | `float(x)` |
| List | A list of items | `[1, 2, 3]` | `list(x)` |
| Dictionary | A key:value pairing. Talked about later. | `{1: "One"}` | `dict(x)` |

## How do lists work, really?

Lists are quite strange because they have no set length. Python is written in C, and in C arrays \(lists\) have set lengths -- so how come Python lists do not have lengths?

That's because they do, but they are abstracted in such a way that you don't need to worry about it.

Let's look at a naieve approach for arrays.

```text
[1, 2, 3, None, None, None]
```

Imagine this is an array of length 6, where None represents empty space. We fill up the array with data:

```text
[1, 2, 3, 4, 5, 6]
```

Now we want to append one more item to the array, `7`.  The array is fixed length, so we cannot append to it with this size.

Our naieve approach is to increase the array by size 1.

```text
[1, 2, 3, 4, 5, 6, None]
```

And then append the value to it:

```text
[1, 2, 3, 4, 5, 6, 7]
```

But everytime we want to append a value we have to create a whole new array, copy all the previous values in and insert our new value.

This is obviously a slow algorithm.

Python uses an algorithm called **table doubling** to battle this slowness. I bet you can guess what it does!

When we reach the limit of an array and we want to increase the size, we create a new array double the size of the previous array.

This saves us time from creating a new array with every append, while also keeping the size to a minimum. It's problematic to create an array that's only 1 element larger than our last array.

It's problematic to create an array that is the maximum possible size \(as it costs memory\).

Table doubling is the perfect balance between them both.

### Removing Elements

Let's say we have a table of size 6.

We add one element.

Our table size doubles to 12.

We remove one element.

To save space, we delete the 6 extra array elements.

We then add another element, and double the table again.

It is costly to double the table in this instance, where we rapidly remove one element and add another element. Instead what we do is only reduce the table when we go below 3 times the doubled size.

With our above example, we double to 12. We remove 1 item so we have 5 items. We do not reduce the size of the array. Only if we hit 4 elements \(12 / 3 = 4, 3 times smaller\) do we reduce the size.

This fixes our above problem.

Something to note is that I'm not sure whether Python uses 3, or 4, or 5 to decide when to shrink a table. It's unimportant so long as it's &gt;2. 



