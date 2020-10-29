# Virtual Environments

Virtual Environments allow you to have seperate boxes of packages for each project you work on.

Let's say Project X requires Ciphey 4.2.0, but project Y requires 5.10.0. To get around the fact they both need different versions, we use a virtual environment.

Essentially we create a container for both projects. That way we can install whatever we want without conflicts in the confinement of this container!

The default tool for Virtual Environments is rather bad, and no one really uses it anymore.

So we'll install a new one.

```text
pip install virtualenvwrapper
```

**Windows** use [https://pypi.org/project/virtualenvwrapper-win/](https://pypi.org/project/virtualenvwrapper-win/) instead

Pay attention to the output in the terminal. We need to know the location of [`virtualenvwrapper.sh`](http://virtualenvwrapper.sh/).

Now in our `.bashrc` or `.zshrc` \(the file that runs everytime a terminal is opened\) add these lines:

```text
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/projects
source /usr/local/bin/virtualenvwrapper.sh
```

Replacing the `source /usr/local....` with the file location outputted in the terminal.

Now, source your .bashrc:

```text
source .bashrc
```

**Note**: this is confusing and you may get this wrong the first time. If so, please read more about .bashrc via Google 😄

Now, make a new folder and call it "my-new-project" or something.

`cd` into that folder and run:

```text
mkvirtualenv my-new-project
```

This automatically creates the virtual environment for you, and drops you into it.

Now we can `pip` install anything we want, and it will only be associated with this virtual environment.

We can leave our virtual environment with `deactivate`. We no longer have access to the package we installed in the virtual environment.

To go back, run `workon`.

```text
$ workon
my-new-project
```

This tells us the name\(s\) of our virtual environments. And then:

```text
workon my-new-project
```

Takes us back there.

And just like that, we have now fixed our packaging problem with this neat tool \(and trust me when I say, this is easier than the default tool\).

Now, remember how I said that Ciphey works on 3.7 and up, but what if we have another piece of software that only works on 3.6 and below? How would we use different versions of Python?

This is solved by....

