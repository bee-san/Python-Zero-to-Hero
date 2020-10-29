# Loops

Now what if we had the same name checking code from the last task, but instead of not allowing entry, we waited until the right person showed up?

How do we repeatedly ask for the persons name and check to see if their name matches?

We can do this using something called a `loop`.

`while` loops will loop until a condition is met \(much like our if statements from earlier\).

```python
name = ""
while name != "Jabba":
    name = input("What is your name? ")
```

Since while loops take conditionals, what happens if we assign a True value to it?

```python
while True:
    print("This loop runs!")
```

The loop runs forever, as the condition never changes.

This is quite useful for input / output where you expect to repeatedly receive input. Or perhaps you want to repeatedly do something \(such as check TryHackMe for new rooms\).

We can tell our loop to break using a the keyword `break`.

```python
while True:
    name = input("What is your name? ")
    if name == "Jabba":
        break
```

The `break` keyword tells Python to break out of the while loop. If we do this, our code is no longer in the `while` and will continue to run.

While loops are very good for pointers. A pointer is a variable which keeps track of where it is in a list.

![](../.gitbook/assets/image%20%289%29.png)

```python
names = ["Skidy", "DorkStar", "Ashu", "Elf"]
pointer = 0
while pointer <= len(names):
    print(names[i])
    pointer += 1
```

