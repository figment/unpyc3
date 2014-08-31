unpyc3
======

Decompiler for Python 3.3  (forked from https://code.google.com/p/unpyc3)

## Original README

The aim is to be able to recreate Python3 source code from code objects. Current version is able to decompile itself successfully :). It has been tested with Python 3.3 only.

It currently reconstructs most of Python 3 constructs but probably needs to be tested more thoroughly. All feedback welcome.

Example:

```python
>>> from unpyc3 import decompile
>>> def foo(x, y, z=3, *args):
...    global g
...    for i, j in zip(x, y):
...        if z == i + j or args[i] == j:
...            g = i, j
...            return
...    
>>> print(decompile(foo))
def foo(x, y, z=3, *args):
    global g
    for i, j in zip(x, y):
        if z == i + j or args[i] == j:
            g = i, j
            return
>>>
```

Unpyc3 is made of a single python module. Download unpyc3.py and try it now!

the unpyc3 module is able de decompile itself! (try import unpyc3; unpyc3.decompile(unpyc3)) so theorically I could just distribute the .pyc file.

TODO:

* Support for keyword-only arguments
* Handle assert statements
* Show docstrings for functions and modules
* Nice spacing between function/class declarations 

## Addendum

* I am not the original author and just hacked this enough to work with Python 3.3
* I will not be maintaining this repository to any degree
* Also thanks to MadeCoder at StackOverflow.com for their work
  * http://stackoverflow.com/questions/22096717/decompile-python-3-3-pyc-using-unpyc3

