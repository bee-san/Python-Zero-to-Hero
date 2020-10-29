# PyEnv

PyEnv is a tool that let's us switch between multiple versions of Python easily.

**Note**: PyEnv does not support Windows.

To install PyEnv, run:

```text
curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
```

Taken from here [https://github.com/pyenv/pyenv](https://github.com/pyenv/pyenv)

Now let's install 3.7

```text
pyenv install 3.7.0
```

We can use PyEnv locally or globally.

Globally means we change our entire Python version on our computer. Locally means that for a specific project or directory we use a different Python version.

In our `my-new-project` directory, run `pyenv local 3.7.0`.

And just like that we can use different Python versions for different things.

If we wanted to use 3.7.0 globally instead of 3.8:

```python
pyenv global 3.7.0
```

