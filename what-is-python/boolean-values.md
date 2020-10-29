# Boolean Values

Boolean Algebra & Operators are so useful, I had to devote an entire section to them!

Binary is a bunch of 0's and 1's, but how do we display computational complexity in binary? If we convert programming languages into binary, how does the computer know that "11" means "1" and not "0"?

We have to use some operators for this. In fact, we have to use some boolean operators!

**Bee's Fun Facts: Binary was invented before Boolean algebra. But it still took us hundreds of years to figure out that we can use Binary in our electronic systems. Thanks, George Boole!**

The two values for the data type boolean are `True` and `False`.

True and False are extremely valuable. In binary, 1 represents True and 0 represents False.

Through these 2 values we can represent all data on a computer, provided we are using logic gates.

Those logic gates appear in Python as operators. We'll go through one you may already know:

```python
True or False
# True
```

The `or` operator returns true when either the left side or right side is True.

Let's quickly go through all the others:

```python
True and True
# True
```

This returns True if and only if both the left and right sides are True.

```python
not True
# False
```

`not` negates the right hand side expression. So the opposite of `True` is False.

We can negate the Or statement like so:

```python
not (True or False)
# False
```

Now it only returns True when both sides of the `or` are `False`.

What if we wanted an exclusive or \(xor\)? It only returns True when only 1 side of the equation is True, not both \(otherwise it's more like an Or with an And\).

Python can do this with:

```python
True ^ False
# True
True ^ True
# False
```

For more on the history of boolean algebra, check out [CODE](https://www.goodreads.com/book/show/44882.Code).

Now, let's see something wacky.

Remember how I said True was 1 and False was 0?

```python
x = 0
x += True
# += True is short-hand for x = x + True
x += True
x += True
print(x)
# 3
```

You've got to be real careful if you add booleans together, they don't work how you might expect them to 😅

We also have many operators that return booleans.

For example:

```python
"a" in ["a", "b", "c"]
# True
```

The in operator checks to see if the item is in an iterable \(an iterable is anything we can iterate over, such as a list\).

```python
None is None
```

The is operator checks to see if the left hand side is the right hand side.

```python
True == False
# False
```

The `==` operator checks to see if they both have the _same value_.

Remember earlier when I showed you that fun trickery with Python's pass-by-reference variables?

Let me show you something cooler!

```python
x = []
y = []

x == y
# True

x is y
# False
```

They have the same value, an empty list, but they are not referencing the same object.

Make sure to watch out for this one as it can happen a lot when you create your own data structures.

To use `not` with an equality operator we need to use `!` like so:

```python
9 != 6
# 9 not equal 6
# True
```

Now there are some other cool things, like less than or more than.

```python
6 < 6
# 6 less than 6
# True

6 > 6
# 6 more than 6
# False

6 <= 6
# 6 less than or equal to 6
# True

6 >= 6
# 6 more than or equal to 6
# True
```

You can implement these methods in your own classes using magic methods. Greater than or equal to is `__ge__`.

Okay, one last funny trick for this section! Remember how I said that True and False are 1 and 0?

```python
False < True
# True
```

What a funny quirk!

Now, onto something more important.

All empty data structures have a Falsey value, and all non-empty data structures have a Truthy value.

```python
x = []
bool(x)
# False

y = [6]
bool(y)
# True
```

This will come in very useful in the next section.

