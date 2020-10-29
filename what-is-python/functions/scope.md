# Scope

Scope is one of the largest problems a Python programmer will face.

Let's see a little example.

```python
name = "0xEmma"

def hello(name):
	name = "Blob Bros"
	print(f"Hello, {'DorkStar' if name == 'Dork' else name}")

hello()
print(name)
# Hello, Blob Bros
# 0xEmma
```

We changed the variable in the function, so why did it not change the variable outside the function? The answer is that the function has a scope that is smaller than the scope of the variable \(which is the global scope\).

![](../../.gitbook/assets/image%20%288%29.png)

Imagine this line going through the program. Everything not in a function is considered the global scope of that file \(the main program, in this case\).

When we build a function, it creates a new parallel line. This parallel line creates a new scope, which means it cannot change things outside of itself \(the global scope\).

If that parallel line was to create another function, another scope — it can change things in there.

Just like how the global scope can change things in functions.

When we build more functions and code, we want to stay as low down in the nest of scope as possible. If we have so many functions each calling eachother, it will be confusing for us to work out where the problem is. The code becomes messy.

Each function should do one thing, and one thing only. And we should minimise how many other functions call that function. If we do not, we might end up in a spiderweb of function calls which would be impossible to debug.

Now, back to scope.

![https://www.geeksforgeeks.org/namespaces-and-scope-in-python/](../../.gitbook/assets/image%20%286%29.png)

Scope is closely linked to something called a "namespace" in Python. There's 3 types of scope.

The built-in namespace \(what default functions / data structures use\), the global namespace and the local namespace.

There's a lot more to scope, but honestly the only thing you need to remember is the line idea. Everytime we make a new scope, we diverge from the original scope we were in.

If we repeatedly make new scopes, our line gets more and more branches resulting in more confusion.

[Here's a nice article on the concept.](https://realpython.com/python-scope-legb-rule/#nested-functions-the-enclosing-scope)

