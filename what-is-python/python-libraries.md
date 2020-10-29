# Python Libraries

Now let's talk about the Python packaging ecosystem!

Imagine you wanted to write code to download something from a website. Without knowing about packaging, you would have to manually write all the code yourself.

But what if I told you that someone else has written the code for you? And what if I told you it's easy to download their code and use it in your projects?

Python ships with a neat bit of software called `pip`. `pip` allows you to install other peoples code \(called packages\).

These packages are stored in a repository called PyPi.

We can search for packages on PyPi \(although most of the time, we don't need to. We'll know the name of a package from Stack Overflow telling us to install it.

Here's a good example.

[https://pypi.org/project/requests/](https://pypi.org/project/requests/)

The Requests package is managed by the Python Software Foundation. It's a package that allows you to do cool HTTP/s stuff and download webpages.

In a Terminal \(not in Python\) run:

```text
pip install requests
```

**Note**: If you have to run `python3`, run `pip3` here instead.

And just like that we have someone elses code!

We can now import Requests and use it.

```python
import requests
r = requests.get("https://tryhackme.com")
print(r.status_code)
# Since you are reading this, TryHackMe should
# be up so it should return 200
```

To import code, we run the command `import {name}` where `{name}` is the name of the module / library / package we want. As we just installed requests, we can import it.

We can also import some others built into Python, such as `math`.

```python
import math
```

Here's a common misconception. Some people say "if you write code in Python, you can be sure it'll run everywhere that Python runs". This is not true.

A great example of this is a package I wrote, Ciphey.

Ciphey only runs on Python 3.7 higher \(at the time, Ubuntu server uses 3.6.9\).

This is because Ciphey uses a feature in 3.7 \(type hints\) that breaks lower versions.

Ciphey can only run on Windows / Linux too. No Mac support!

This is because Python is a "glue" language, you can use other languages in Python. Ciphey uses C++ and the combination of C++ and Python on Mac breaks.

This is definitely my fault, not Pythons — but it's a good example of why "write once, run everywhere" doesn't always apply to Python.

These kind of issues can happen everywhere. Even using default Python, if you was to use a `ulimit` library you would no longer be able to distribute on Windows unless you did conditional imports.

Also, the version you use in your code may not be the latest version.

Let's say you use Ciphey 4.2.0, but the latest version is 5.10.0.

Your code works fine, as you use 4.2.0, but everyone else who downloads gets Ciphey 5.10.0 which breaks your code.

You have to do something called _version pinning._ And by doing this, you are essentially installing multiple versions of the same piece of software. This gets confusing, **fast**. And breaks everything. That's why in Python we need.....

